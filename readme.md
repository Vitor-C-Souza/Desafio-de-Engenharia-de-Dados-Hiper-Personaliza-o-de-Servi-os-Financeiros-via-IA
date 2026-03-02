# 🚀 Desafio de Engenharia de Dados: Hiper-Personalização de Serviços Financeiros via IA

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Vitor-C-Souza/Desafio-de-Engenharia-de-Dados-Hiper-Personaliza-o-de-Servi-os-Financeiros-via-IA/blob/main/ETLDadosBancarios.ipynb)

> Projeto de ETL (Extract, Transform, Load) desenvolvido para o **Bootcamp Bradesco - GenAI & Dados** da DIO, focado em criar comunicações de marketing financeiro personalizadas usando IA Generativa.

## 📋 Sobre o Projeto

Este projeto simula o trabalho de um Cientista de Dados em uma Fintech, desenvolvendo um **pipeline de ETL** que transforma dados transacionais estáticos em **recomendações de investimento hiper-personalizadas** usando IA Generativa.

O diferencial está na utilização da **Google Gemini API** para analisar o perfil financeiro de cada cliente (saldo, limite, comportamento de uso) e gerar mensagens de marketing contextualizadas e persuasivas.

## 🎯 Objetivo

Elevar o engajamento dos usuários através de comunicações de marketing altamente contextuais, substituindo mensagens genéricas por conselhos de investimento personalizados gerados por IA.

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **Pandas** - Manipulação e análise de dados
- **Google Generative AI (Gemini 2.5 Flash)** - Geração de conteúdo personalizado
- **Jupyter Notebook** - Desenvolvimento e documentação interativa
- **Google Colab** - Ambiente de execução em nuvem

## 📊 Estrutura do Projeto

```
📁 Desafio-de-Engenharia-de-Dados-Hiper-Personaliza-o-de-Servi-os-Financeiros-via-IA/
├── 📓 ETLDadosBancarios.ipynb          # Pipeline ETL completo
├── 📄 clientes_fintech.csv             # Dataset com 20 clientes simulados
└── 📝 readme.md                        # Documentação do projeto
```

## 🔄 Fluxo do Pipeline ETL

### 1️⃣ **Extract (Extração)**
- **Fonte**: Arquivo CSV (`clientes_fintech.csv`) com 20 registros de clientes
- **Dados capturados**:
  - Nome do usuário
  - Número da conta e agência
  - Saldo e limite da conta
  - Número e limite do cartão
  - Funcionalidades mais utilizadas (PIX, Extrato, Investimentos, etc.)

### 2️⃣ **Transform (Transformação com IA)**

#### Limpeza e Estruturação
- Parsing de valores monetários (conversão de strings como "R$ 1.500" e "R$ 5k" para float)
- Separação de campos compostos (Número/Agência, Saldo/Limite)
- Normalização da estrutura de dados em JSON

#### Geração com IA Generativa
- **API utilizada**: Google Gemini 2.5 Flash
- **Lógica de negócio**: A IA analiza o perfil financeiro para gerar conselhos contextualizados:
  - **Alto saldo**: Sugestão de diversificação em renda variável ou CDBs
  - **Saldo baixo + uso frequente**: Programas de arredondamento ou poupança programada
  - **Alto limite de cartão**: Dicas sobre uso consciente do crédito para investimentos

#### Prompt Estruturado
```python
"Crie uma frase de marketing bancário genérica e impactante sobre a importância 
de investir. Deixe o termo '{nome}' no início da frase para que eu possa 
substituir depois. Máximo de 90 caracteres."
```

### 3️⃣ **Load (Carregamento)**
- **Destino**: Novo campo `News` no dataset
- **Output**: CSV atualizado (`clientes_fintech_updated.csv`) com mensagens personalizadas
- **Formato**: Dados estruturados prontos para integração via API REST

## 💡 Exemplo de Resultado

**Entrada (Cliente):**
```json
{
  "Nome do Usuário": "Ana Silva",
  "contaSaldo": 1500.0,
  "contaLimite": 500.0,
  "cartaoLimite": 2000.0
}
```

**Saída (Mensagem Personalizada):**
```
"Ana Silva, invista hoje e construa o futuro financeiro que você sonha."
```

## 🚀 Como Executar

### Opção 1: Google Colab (Recomendado)
1. Clique no badge "Open in Colab" no topo deste README
2. Execute as células sequencialmente
3. Insira sua API Key do Google Gemini quando solicitado

### Opção 2: Ambiente Local
```bash
# Clone o repositório
git clone https://github.com/Vitor-C-Souza/Desafio-de-Engenharia-de-Dados-Hiper-Personaliza-o-de-Servi-os-Financeiros-via-IA.git

# Navegue até o diretório
cd Desafio-de-Engenharia-de-Dados-Hiper-Personaliza-o-de-Servi-os-Financeiros-via-IA

# Instale as dependências
pip install pandas google-genai jupyter

# Execute o notebook
jupyter notebook ETLDadosBancarios.ipynb
```

### 📌 Requisitos
- Python 3.8+
- Google Gemini API Key ([obtenha aqui](https://ai.google.dev/))

## 📈 Resultados

O pipeline processa **20 clientes** e gera:
- ✅ Mensagens 100% personalizadas com o nome de cada cliente
- ✅ Conteúdo contextualizado baseado em perfil financeiro
- ✅ Dados estruturados prontos para integração (CSV/JSON)
- ✅ Pipeline escalável para milhares de clientes

## 🎓 Contexto Acadêmico

Este projeto foi desenvolvido como desafio prático do **Bootcamp Bradesco - GenAI & Dados** oferecido pela [DIO](https://www.dio.me/), cobrindo:
- ✔️ Fundamentos de ETL e Engenharia de Dados
- ✔️ Integração com APIs de IA Generativa
- ✔️ Manipulação de dados financeiros
- ✔️ Boas práticas de documentação e versionamento

## 👤 Autor

**Vítor Cavalcante Souza**
- GitHub: [@Vitor-C-Souza](https://github.com/Vitor-C-Souza)
- LinkedIn: [Vítor Cavalcante Souza](https://www.linkedin.com/in/vitor-cavalcante-souza/)

## 📝 Licença

Este projeto é de código aberto e está disponível para fins educacionais.

---

⭐ Se este projeto foi útil para você, considere dar uma estrela no repositório!
