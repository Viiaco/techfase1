# Embrapa

Este é um projeto de API desenvolvido com Flask, que inclui operações CRUD, web scraping em páginas do dominio http://vitibrasil.cnpuv.embrapa.br/ e autenticação básica.

## 🚀 Funcionalidades

- **Autenticação Básica**: Protege rotas sensíveis usando autenticação HTTP básica.
- **Operações CRUD**: Permite criar, ler, atualizar e deletar itens.
- **Web Scraping**: Extrai dados de páginas web http://vitibrasil.cnpuv.embrapa.br/ (label, table, tbody, tr, td) usando BeautifulSoup.
- **Cache e Documentação**: Implementa cache para otimização e documentação automática com Swagger.

## 📁 Estrutura do Projeto

```bash
intro_api/
├── app/
│   ├── __init__.py
│   ├── data/
│   │   ├── __init__.py
│   │   ├── comercializacao.py
│   │   ├── exportacao.py
│   │   └── importacao.py
│   │   └── processamento.py
│   │   └── producao.py
│   ├── routes/
│   │   ├── __init__.py
│   │   ├── auth.py
│   │   ├── crud.py
│   │   └── scrape.py
│   ├── utils/
│   │   ├── __init__.py
│   │   └── auth.py
│   └── config.py
├── requirements.txt
├── README.md
└── run.py
```

- **`app/`**: Diretório principal do aplicativo.
  - **`data/`**: Classes para lógica de negócios para scrapping das informações (comercializacao, exportacao, importacao, processamento, produção) do site da embrapa.
  - **`routes/`**: Contém as rotas organizadas por acesso aos dados no site da embrapa. 
                   As rotas não recebem argumentos uma vez que o método captura todas as datas disponíveis no site para consulta.
  - **`utils/`**: Utilitários, como autenticação.
  - **`config.py`**: Configurações da aplicação Flask.
- **`run.py`**: Ponto de entrada para iniciar o aplicativo.
- **`requirements.txt`**: Lista de dependências do projeto.
- **`Dockerfile`**: Configurações para Docker.
- **`README.md`**: Documentação do projeto.

## 🛠️ Como Executar o Projeto

### 1. Clone o Repositório

```bash
git clone https://github.com/nat-lima/techfase1
cd techfase1
```

### 2. Crie um Ambiente Virtual

```bash
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
```

### 3. Instale as Dependências

```bash
pip install -r requirements.txt
```

### 4. Execute o Aplicativo

```bash
python run.py
```

O aplicativo estará disponível em `http://localhost:5000` ou `http://127.0.0.1:5000`

Acesse a aplicação em `http://localhost:5000`.

### 5. Deploy na Vercel

Instale o Node.js
Crie uma conta na Vercel em https://vercel.com/
Instale no VSCode a extensão da Vercel oficial.
Criar arquivo vercel.json:
{
    "version": 2,
    "builds": [
      {
        "src": "run.py",
        "use": "@vercel/python"
      }
    ],
    "routes": [
      { "src": "/(.*)", "dest": "run.py" }
    ]
  }

```bash
npm i -g vercel
vercel
vercel --prod
```
### 6. Arquitetura

![Arquitetura](D:\0Viviana\1 FIAP\1 fase\challenge\techfase1\image\Arquitetura.jpg)


## 📖 Documentação da API

A documentação da API é gerada automaticamente com Swagger e está disponível em `http://localhost:5000/apidocs/`.

## 🤝 Contribuindo

1. Fork este repositório.
2. Crie sua branch (`git checkout -b feature/nova-funcionalidade`).
3. Faça commit das suas alterações (`git commit -m 'Adiciona nova funcionalidade'`).
4. Faça push para sua branch (`git push origin feature/nova-funcionalidade`).
5. Abra um Pull Request.
instalar, configurar e usar o projeto. Ele também cobre contribuições, contato, licença e agradecimentos, tornando-o completo e fácil de entender para novos desenvolvedores.
