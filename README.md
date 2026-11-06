# FlixView — Conversor de Dados TMDB

**Módulo de Extração e Exportação de Dados | Projeto — Grupo 3 | São Paulo Tech School (SPTech)**

O Conversor Python é um módulo auxiliar do projeto FlixView, desenvolvido para automatizar a obtenção e organização de informações sobre filmes e séries disponíveis no catálogo da Netflix no Brasil.

A ferramenta utiliza a API do The Movie Database (TMDB) para consultar informações dos títulos, processar os dados retornados e exportá-los para planilhas Excel. Essas planilhas podem ser utilizadas posteriormente como fonte de dados para análises e integração com o banco de dados do projeto.

## 🛠️ Tecnologias e bibliotecas

| Tecnologia | Utilização |
| --- | --- |
| Python | Linguagem utilizada no desenvolvimento do conversor. |
| Requests | Realização de requisições HTTP à TMDB API. |
| Pandas | Tratamento, organização e manipulação dos dados. |
| OpenPyXL | Geração e manipulação de arquivos Excel. |
| TMDB API | Fonte externa de informações sobre filmes e séries. |

## ✨ Funcionalidades

- **Consulta à TMDB API:** obtenção de informações sobre filmes e séries disponíveis na Netflix no Brasil.
- **Filtragem por disponibilidade:** consulta aos títulos associados ao provedor Netflix na região brasileira.
- **Extração de informações:** coleta de dados como identificadores, títulos, sinopses, datas de lançamento, avaliações, popularidade, gêneros e demais informações disponibilizadas pela API.
- **Tratamento de dados:** organização das informações retornadas para estruturar os dados em formato tabular.
- **Exportação para Excel:** geração de planilhas `.xlsx` com os dados obtidos, facilitando sua consulta e utilização em outras etapas do projeto.

## 🚀 Como executar o conversor

### Pré-requisitos

- Python 3 instalado.
- Pip instalado e configurado.
- Conexão com a internet.
- Token de leitura da TMDB API.

### 1. Instale as dependências

No terminal, execute:

```bash
python -m pip install requests pandas openpyxl
```

### 2. Configure o token da TMDB

O conversor utiliza um token de leitura para realizar as requisições à API.

Configure a variável de ambiente `TMDB_TOKEN` com seu token de acesso.

**Windows (PowerShell):**

```powershell
$env:TMDB_TOKEN="seu_token_de_leitura"
```

**Linux:**

```bash
export TMDB_TOKEN="seu_token_de_leitura"
```

Substitua o valor pelo seu próprio token.

**Importante:** não compartilhe seu token nem o publique no repositório.

### 3. Execute o script

Na raiz do repositório, execute:

```bash
python python/conversor/tmdb_excel.py
```

O script iniciará as consultas à TMDB API, processará as informações retornadas e gerará a planilha Excel no diretório do conversor.

## 📊 Fonte de dados e critérios de consulta

O conversor utiliza a TMDB API como fonte de informações e considera a disponibilidade de conteúdos na Netflix para a região brasileira.

A consulta utiliza os recursos da API relacionados a provedores de streaming e descoberta de títulos (*Watch Providers* e *Discover*).

Entre os critérios utilizados estão:

- **Região:** Brasil (`BR`).
- **Provedor:** Netflix.
- **Disponibilidade:** conteúdos associados à modalidade de assinatura (*flatrate*).
- **Categorias:** filmes e séries.
- **Paginação:** obtenção dos resultados disponibilizados pela API em diferentes páginas de consulta.

A disponibilidade dos títulos é baseada nas informações fornecidas pela TMDB, que utiliza dados relacionados ao JustWatch. Portanto, os resultados podem apresentar diferenças em relação ao catálogo efetivamente disponível na Netflix em determinado momento.

## 📁 Estrutura do módulo

```text
python/
└── conversor/
    ├── tmdb_excel.py       # Script de extração e conversão
    └── ...                 # Arquivos auxiliares e planilhas geradas
```

Os arquivos Excel gerados são armazenados no diretório do conversor, conforme definido no script.

## ⚠️ Observações importantes

- A execução depende da disponibilidade da TMDB API e de um token de acesso válido.
- A quantidade de informações retornadas está sujeita aos limites e critérios de consulta da API.
- A disponibilidade dos títulos pode sofrer alterações conforme a região e a atualização das informações fornecidas pela TMDB.
- Os dados exportados representam um retrato das informações disponíveis no momento da consulta, não uma atualização em tempo real.
- O projeto utiliza a TMDB API, mas não é endossado nem certificado pela TMDB.

## 👥 Equipe

**Projeto — Grupo 3 | São Paulo Tech School (SPTech)**

| Integrante | RA |
| --- | --- |
| Beatriz Reis | 01261094 |
| Gustavo de Souza | 01261071 |
| Jefferson Watabe | 01261036 |
| Miguel Carvalho | 01261101 |
| Nicolas Augusto | 01261014 |
| Sabrina Toledo | 01261004 |

## 📄 Licença

Consulte o arquivo `LICENSE` presente no repositório principal para conhecer os termos de utilização e distribuição do projeto.
