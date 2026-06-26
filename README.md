# 🏥 MedFlow OS v2.5 - Triagem Hospitalar

O **MedFlow OS** é um sistema web responsivo projetado para otimizar o fluxo de atendimento em prontos-socorros e hospitais. Ele permite que a equipe de enfermagem realize o cadastro, registre os sinais vitais, classifique o risco do paciente e gerencie a fila de espera do plantão em tempo real de forma simplificada.

---

## 🚀 Funcionalidades Principais

* **Autenticação**: Tela de login integrada para controle de acesso seguro do profissional responsável.
* **Formatadores Inteligentes**: Máscara automática para CPF e capitalização automática de nomes no formulário.
* **Alertas Clínicos Automáticos**: O sistema monitora as entradas de sinais vitais e gera avisos visuais imediatos na tela se detectar parâmetros críticos:
  * 🫁 **Saturação de O₂**: Alerta para valores $\le$ 92% (risco de hipóxia).
  * 🌡️ **Temperatura**: Alerta para hipertermia ($\ge$ 39°C) ou hipotermia ($\le$ 35°C).
  * 🫀 **Pressão Arterial**: Alerta para picos hipertensivos (sistólica $\ge$ 180 mmHg) ou hipotensão crítica ($\le$ 90 mmHg).
* **Protocolo de Classificação**: Escala visual colorida baseada nas diretrizes de gravidade: *Emergência*, *Muito Urgente*, *Urgente*, *Pouco Urgente* e *Não Urgente*.
* **Histórico e Ficha Detalhada**: Visualização modal individual da ficha do paciente triado, contendo destaque visual adaptativo caso possua alguma alergia registrada.
* **Painel do Plantão**: Exibe o tempo médio de espera e o contador de pacientes aguardando atendimento.

---

## 🎨 Interface e Estilo (UI/UX)

* **Design Limpo**: Layout construído com uma paleta de cores voltada para o ambiente da saúde (tons de azul e branco).
* **Totalmente Responsivo**: O layout se adapta perfeitamente a computadores, tablets e smartphones (através de regras CSS `@media`).
* **Microinterações**: Animações fluidas de pulsação nos alertas críticos e efeitos ao passar o mouse (*hover*) nos botões.

---

## 🛠️ Tecnologias Utilizadas

O sistema foi desenvolvido utilizando tecnologias web nativas para garantir o máximo de desempenho e portabilidade, dispensando a necessidade de instaladores:

* **HTML5**: Estrutura semântica dos formulários, modais e painéis.
* **CSS3**: Estilização moderna utilizando variáveis nativas (`:root`), Grid Layout e Flexbox.
* **JavaScript (Vanilla)**: Lógica de negócio, validações clínicas, manipulação do DOM e simulação do banco de dados local.

---

## 📦 Como Executar o Projeto

Como o projeto utiliza apenas tecnologias front-end nativas, nenhuma instalação de dependências é necessária.

1. Baixe ou clone os arquivos deste repositório.
2. Certifique-se de que os arquivos `login.html` e o arquivo de triagem principal estejam no mesmo diretório.
3. Abra o arquivo `login.html` em qualquer navegador de sua preferência (Chrome, Edge, Firefox, Safari).

---

## 📝 Detalhes Técnicos de Implementação

* **Persistência de Sessão**: O sistema valida a autenticação utilizando a API `localStorage` do navegador para simular o login do enfermeiro responsável.
* **Estrutura de Dados**: Os dados dos pacientes ficam armazenados temporariamente na memória da sessão (`bancoDadosAtendimentos`), inserindo os novos registros sempre no topo da fila (`unshift`).
* **Manipulação de Datas**: A data de registro é capturada dinamicamente e convertida por extenso no formato local (Ex: *"26 de junho"*).
