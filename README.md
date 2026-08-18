# 🍽️ Painel de Métricas — Restaurante

Painel de métricas em tempo real para restaurantes, construído com **Python + Streamlit + PostgreSQL**.

---

## 📁 Estrutura do projeto

```
restaurante-dashboard/
├── app.py            # Interface Streamlit (telas e gráficos)
├── database.py       # Queries e conexão com PostgreSQL
├── schema.sql        # Tabelas + dados de exemplo
├── requirements.txt  # Dependências Python
└── .env.example      # Modelo de variáveis de ambiente
```

---

## 🚀 Como rodar

### 1. Pré-requisitos
- Python 3.10+
- PostgreSQL rodando localmente ou na nuvem

### 2. Clone e instale dependências
```bash
git clone <seu-repositorio>
cd restaurante-dashboard

python -m venv venv
source venv/bin/activate        # Linux/Mac
# venv\Scripts\activate         # Windows

pip install -r requirements.txt
```

### 3. Configure o banco de dados
```bash
# Crie o banco
psql -U postgres -c "CREATE DATABASE restaurante;"

# Rode o schema (cria tabelas + dados de exemplo)
psql -U postgres -d restaurante -f schema.sql
```

### 4. Configure as variáveis de ambiente
```bash
cp .env.example .env
# Edite o .env com suas credenciais do PostgreSQL
```

### 5. Rode o painel
```bash
streamlit run app.py
```

Acesse: **http://localhost:8501**

---

## 📊 Métricas disponíveis

| Métrica | Descrição |
|---|---|
| Receita Total | Soma dos pedidos fechados no período |
| Total de Pedidos | Quantidade de pedidos fechados |
| Ticket Médio | Valor médio por pedido |
| Lucro Bruto | Receita menos custo dos ingredientes |
| Receita Diária | Gráfico de linha dia a dia |
| Formas de Pagamento | PIX, cartão, dinheiro (gráfico pizza) |
| Movimento por Hora | Horários de pico do dia |
| Receita por Categoria | Entradas, pratos, bebidas, etc. |
| Top Produtos | Ranking por receita com margem de lucro |

---

## 🗄️ Modelo de dados

```
categorias → cardapio
mesas      → pedidos → pedido_itens → cardapio
```

Tabelas principais:
- **pedidos** — cada comanda/mesa
- **pedido_itens** — itens de cada pedido
- **cardapio** — produtos com preço e custo
- **categorias** — grupos do cardápio

---

## 🔧 Customizações sugeridas

- Adicionar autenticação com `streamlit-authenticator`
- Exportar relatório em PDF com `reportlab`
- Adicionar filtro por garçom ou turno
- Alertas de produto com estoque baixo
- Integrar com sistema de caixa via API
