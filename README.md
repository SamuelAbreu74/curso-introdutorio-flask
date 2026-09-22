# API de E-commerce - Flask (Projeto Rocketseat)

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![Swagger](https://img.shields.io/badge/-Swagger-%23Clojure?style=for-the-badge&logo=swagger&logoColor=white)

Este projeto é uma **API RESTful** simulando o backend de um sistema de E-commerce. Ele foi desenvolvido como projeto prático para a formação de **Introdução ao Python da Rocketseat**. 

A aplicação permite o gerenciamento de produtos, autenticação de usuários e operações completas de um carrinho de compras (adicionar, remover, visualizar e finalizar compra).

## Funcionalidades

De acordo com os conceitos abordados no curso, esta API implementa:

- **Autenticação de Usuários:** Login e Logout seguros utilizando `Flask-Login` e controle de sessões.
- **Gerenciamento de Produtos (CRUD):** 
  - Criação de novos produtos (protegido).
  - Listagem de todos os produtos ou detalhes de um produto específico.
  - Atualização de dados do produto (protegido).
  - Exclusão de produtos (protegido).
- **Carrinho de Compras:**
  - Adição e remoção de itens vinculados ao usuário logado.
  - Visualização dos itens atuais no carrinho.
  - Checkout (limpa o carrinho após a "compra").
- **Banco de Dados Relacional:** Modelagem de dados (`User`, `Product`, `CartItem`) utilizando `Flask-SQLAlchemy` integrado ao banco de dados `SQLite`.
- **Documentação Interativa:** Interface visual do Swagger UI acessível diretamente pelo navegador.
- **CORS:** Configurado via `Flask-CORS` para permitir a comunicação com o frontend.

## Tecnologias Utilizadas

- **Linguagem:** Python 3
- **Micro-framework:** Flask
- **ORM & Banco de Dados:** SQLAlchemy e SQLite
- **Autenticação:** Flask-Login
- **Documentação:** Swagger UI (`flask-swagger-ui`)
- **Outras Bibliotecas:** Werkzeug, Flask-CORS

## Como executar o projeto localmente

Siga os passos abaixo para rodar a API na sua máquina.

### Pré-requisitos
- Python 3.x instalado
- Git (opcional, para clonar o repositório)

### Passos

1. **Clone o repositório (ou baixe os arquivos):**
   ```bash
   git clone https://seu-link-do-github.com/seu-repositorio.git
   cd seu-repositorio
   ```

2. **Crie e ative um ambiente virtual (recomendado):**
   ```bash
   # Windows
   python -m venv venv
   venv\Scripts\activate

   # Linux/Mac
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Instale as dependências:**
   Crie um arquivo `requirements.txt` com as dependências do projeto e rode:
   ```bash
   pip install -r requirements.txt
   ```

4. **Execute a aplicação:**
   ```bash
   python app.py
   ```
   *Nota: O banco de dados `ecommerce.db` será criado automaticamente na primeira execução, assim como um usuário administrador padrão (`username: admin`, `password: 123`).*

5. **Acesse a API:**
   A aplicação estará rodando em: `http://127.0.0.1:5000`

## Documentação da API (Swagger)

A API possui uma documentação interativa completa gerada com Swagger.
Com o servidor rodando, acesse no seu navegador:

--> **[http://127.0.0.1:5000/swagger](http://127.0.0.1:5000/swagger)**

Através dessa interface, você pode testar todas as rotas diretamente, verificar os parâmetros necessários, os schemas de requisição (JSON) e os retornos esperados.

### Principais Endpoints

* **Auth:**
  * `POST /login` - Realiza o login (use as credenciais `admin` / `123`).
  * `POST /logout` - Realiza o logout do usuário atual.
* **Produtos:**
  * `GET /api/products` - Lista todos os produtos.
  * `POST /api/products/add` - Adiciona um novo produto *(Requer Login)*.
  * `PUT /api/products/update/<id>` - Edita um produto *(Requer Login)*.
  * `DELETE /api/products/delete/<id>` - Remove um produto *(Requer Login)*.
* **Carrinho:**
  * `GET /api/cart/` - Visualiza os itens do carrinho *(Requer Login)*.
  * `POST /api/cart/add/<produto_id>` - Adiciona item ao carrinho *(Requer Login)*.
  * `DELETE /api/cart/remove/<produto_id>` - Remove item do carrinho *(Requer Login)*.
  * `POST /api/cart/checkout` - Finaliza a compra e limpa o carrinho *(Requer Login)*.

## Certificado

Este projeto é fruto dos conhecimentos adquiridos na formação "Introdução ao Python" pela Rocketseat.

![Certificado de Conclusão Rocketseat](/assets/imagem-certificado.jpeg ) 

---
Feito com 💜 por Samuel Abreu