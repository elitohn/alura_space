# 🌌 Alura Space

O **Alura Space** é uma aplicação web desenvolvida com **Python e Django**, criada com o objetivo de colocar em prática conceitos fundamentais do desenvolvimento web utilizando o framework Django.

A aplicação funciona como uma plataforma de compartilhamento e visualização de fotografias relacionadas ao espaço, permitindo que usuários tenham acesso a uma galeria de imagens organizadas por diferentes categorias.

O projeto também conta com um sistema de autenticação, permitindo que usuários realizem cadastro, login e logout, além de funcionalidades relacionadas ao gerenciamento das fotografias.

---

## Tecnologias utilizadas

O projeto foi desenvolvido utilizando as seguintes tecnologias:

- **Python** — Linguagem principal utilizada no desenvolvimento da aplicação.
- **Django** — Framework utilizado para construção da aplicação web.
- **SQLite** — Banco de dados utilizado durante o desenvolvimento.
- **HTML** — Estrutura das páginas da aplicação.
- **CSS** — Estilização e organização visual das páginas.
- **Pillow** — Biblioteca utilizada para trabalhar com imagens.
- **python-dotenv** — Utilizado para gerenciamento de variáveis de ambiente.

---

## Funcionalidades

A aplicação possui diferentes funcionalidades voltadas para a exibição e gerenciamento das fotografias.

### Sistema de usuários

O projeto possui um sistema de autenticação utilizando o sistema de usuários do Django.

É possível:

- Criar uma nova conta;
- Realizar login;
- Realizar logout;
- Acessar funcionalidades da aplicação de acordo com o estado de autenticação.

---

### Galeria de fotografias

A principal funcionalidade da aplicação é a exibição de uma galeria de fotografias relacionadas ao espaço.

As fotografias possuem informações utilizadas para organizar e apresentar o conteúdo dentro da aplicação.

Entre essas informações estão:

- Nome da fotografia;
- Legenda;
- Categoria;
- Descrição;
- Imagem;
- Data da fotografia;
- Usuário responsável;
- Status de publicação.

As fotografias publicadas são apresentadas na galeria de acordo com os dados cadastrados.

---

### Categorias

As fotografias podem ser classificadas de acordo com diferentes categorias relacionadas ao espaço.

Entre elas estão:

-  **Nebulosa**
-  **Estrela**
-  **Galáxia**
-  **Planeta**

Essa organização facilita a navegação e permite separar as fotografias de acordo com seu tipo.

---

### 🔎 Pesquisa

A aplicação possui uma funcionalidade de busca que permite encontrar fotografias através do nome.

O usuário pode informar um termo de pesquisa e a aplicação realiza a busca entre as fotografias cadastradas.

Exemplo:

```text
/buscar?buscar=Saturno
```

---

### Upload de imagens

O projeto permite trabalhar com arquivos de imagem através do modelo responsável pelas fotografias.

As imagens são armazenadas utilizando o sistema de arquivos de mídia do Django.

A estrutura de armazenamento utiliza informações de data para organizar os arquivos.

---

## Estrutura do projeto

A aplicação está organizada utilizando a estrutura padrão de um projeto Django, separando responsabilidades entre diferentes aplicações.

```text
alura_space/
│
├── galeria/
│   ├── migrations/
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── usuarios/
│   ├── migrations/
│   ├── forms.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
│
├── setup/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── static/
├── templates/
├── media/
│
├── db.sqlite3
├── manage.py
├── requirements.txt
└── README.md
```

### `galeria`

É a aplicação responsável pelas funcionalidades relacionadas às fotografias.

Nela estão concentrados os arquivos responsáveis por:

- Modelos das fotografias;
- Views da galeria;
- URLs;
- Configurações do Django Admin;
- Migrations;
- Testes.

---

### `usuarios`

É a aplicação responsável pelas funcionalidades relacionadas aos usuários.

Ela possui recursos relacionados a:

- Cadastro;
- Autenticação;
- Formulários;
- Views;
- URLs;
- Models;
- Migrations.

---

### `setup`

Contém as principais configurações do projeto Django.

Entre os arquivos estão:

- `settings.py` — configurações gerais do projeto;
- `urls.py` — configuração das URLs principais;
- `asgi.py` — configuração para servidores ASGI;
- `wsgi.py` — configuração para servidores WSGI.

---

### `static`

Diretório destinado aos arquivos estáticos utilizados pela aplicação, como arquivos CSS e outros recursos necessários para o funcionamento e apresentação das páginas.

---

### `templates`

Contém os templates HTML utilizados pelo Django para renderizar as páginas da aplicação.

---

### `media`

Diretório utilizado para armazenar os arquivos de mídia enviados para a aplicação, principalmente as fotografias cadastradas.

---

## Como executar o projeto

Para executar o projeto localmente, é necessário ter o **Python** instalado na máquina.

### 1. Clone o repositório

```bash
git clone https://github.com/elitohn/alura_space.git
```

### 2. Acesse o diretório

```bash
cd alura_space
```

### 3. Crie um ambiente virtual

No Windows:

```bash
python -m venv venv
```

No Linux/macOS:

```bash
python3 -m venv venv
```

### 4. Ative o ambiente virtual

#### Windows

```bash
venv\Scripts\activate
```

#### Linux/macOS

```bash
source venv/bin/activate
```

### 5. Instale as dependências

Com o ambiente virtual ativado, execute:

```bash
pip install -r requirements.txt
```

### 6. Execute as migrations

```bash
python manage.py migrate
```

### 7. Inicie o servidor

```bash
python manage.py runserver
```

Depois disso, acesse a aplicação através do endereço:

```text
http://127.0.0.1:8000/
```

---

## Banco de dados

Durante o desenvolvimento, o projeto utiliza o **SQLite** como banco de dados.

O arquivo do banco está localizado na raiz do projeto:

```text
db.sqlite3
```

A estrutura do banco de dados é controlada através do sistema de **migrations do Django**.

Para aplicar novas migrations:

```bash
python manage.py migrate
```

Caso seja necessário criar novas migrations após alterações nos models:

```bash
python manage.py makemigrations
```

---

## Variáveis de ambiente

O projeto utiliza o pacote `python-dotenv` para trabalhar com variáveis de ambiente.

A `SECRET_KEY` do Django deve ser configurada através de uma variável de ambiente.

Crie um arquivo `.env` na raiz do projeto:

```env
SECRET_KEY=sua-chave-secreta
```

>  O arquivo `.env` não deve ser compartilhado publicamente quando contiver informações sensíveis.

---

## Django Admin

O projeto também utiliza o sistema administrativo disponibilizado pelo Django.

Para criar um usuário administrador, execute:

```bash
python manage.py createsuperuser
```

Depois de informar os dados solicitados, inicie o servidor:

```bash
python manage.py runserver
```

O painel administrativo poderá ser acessado através de:

```text
http://127.0.0.1:8000/admin/
```

---

## Conceitos praticados

O desenvolvimento do Alura Space permite colocar em prática diversos conceitos importantes do desenvolvimento web com Django, como:

- Arquitetura MVT;
- Criação de aplicações Django;
- Models;
- Views;
- URLs;
- Templates;
- Formulários;
- Autenticação de usuários;
- Django Admin;
- Migrations;
- Banco de dados;
- Upload e armazenamento de imagens;
- Arquivos estáticos;
- Arquivos de mídia;
- Variáveis de ambiente;
- Organização de um projeto web.

---

## Objetivo

O projeto foi desenvolvido com finalidade **educacional**, pela Alura, servindo como prática para aprender e consolidar conhecimentos sobre desenvolvimento web utilizando **Python e Django**.

Através dele, são aplicados conceitos desde a criação das estruturas do projeto até a implementação de funcionalidades como autenticação, gerenciamento de dados, exibição de imagens e interação com o banco de dados.

---

## Autor

Desenvolvido por **Wellyton Huan**.

🔗 [GitHub](https://github.com/elitohn)

🔗 [Repositório do projeto](https://github.com/elitohn/alura_space)

---

## Licença

Este projeto foi desenvolvido para fins educacionais e de aprendizado.
