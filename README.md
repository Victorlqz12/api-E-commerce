# 🛍️ API de E-commerce com Flask

Esta API simula funcionalidades básicas de um sistema de e-commerce, como cadastro de produtos, carrinho de compras e autenticação de usuários.

> 🔒 Login obrigatório para rotas de manipulação (add/update/delete).

---

## 🚀 Tecnologias

- 🐍 Python + Flask
- 🗄️ SQLite + SQLAlchemy
- 🔐 Flask-Login (autenticação)
- 🔄 Flask-CORS (requisições externas)

---

## ⚙️ Instalação

```bash
git clone https://github.com/seu-usuario/ecommerce-flask-api.git
cd ecommerce-flask-api

python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # Linux/macOS

pip install -r requirements.txt

Criar o banco:
# No terminal Python interativo:
from app import db
db.create_all()

Rodar a aplicação:
python app.py


🔐 Autenticação
Método	Rota	Descrição
POST	/login	Login com usuário
POST	/logout	Logout do usuário


📦 Produtos
Método	Rota	Descrição
GET	/api/products	Lista todos os produtos
GET	/api/products/<id>	Detalhes de um produto
POST	/api/products/add	Adiciona produto (login)
PUT	/api/products/update/<id>	Atualiza produto (login)
DELETE	/api/products/delete/<id>	Remove produto (login)


🛒 Carrinho
Método	Rota	Descrição
POST	/api/cart/add/<product_id>	Adiciona item ao carrinho (login)
DELETE	/api/cart/remove/<product_id>	Remove item do carrinho (login)
GET	/api/cart	Visualiza itens no carrinho (login)
POST	/api/cart/checkout	Finaliza compra e limpa carrinho


👤 Usuário de Teste
Crie um usuário manualmente:
from app import db, User
user = User(username="admin", password="123")
db.session.add(user)
db.session.commit()


📂 Estrutura
ecommerce-flask-api/
├── app.py
├── requirements.txt
└── README.md


📄 Licença
Este projeto está sob a licença MIT.
