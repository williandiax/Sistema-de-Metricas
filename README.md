# Sistema de Metricas

Projeto interno para evoluir um sistema de gestão de restaurantes, com foco inicial em comandas digitais, controle de mesas, cardápio, pedidos e metricas operacionais.

O objetivo e substituir comandas físicas por uma experiência visual e centralizada: garcons abrem pedidos por mesa, lancam itens, acompanham o consumo e fecham a conta ao final do atendimento.

# Status do Projeto
Este repositório contem a primeira versão/prototipo, construído em Python com Streamlit e PostgreSQL.

# O projeto atual ja possui:

Dashboard administrativo com metricas de vendas.
Cadastro de produtos e categorias do cardápio.
Cadastro e visualização de mesas.
Abertura de pedidos por mesa.
Lançamento e remoção de itens em pedidos abertos.
Fechamento e cancelamento de pedidos.
Modelo inicial de banco de dados em PostgreSQL.
Ainda nao e uma versão final de produto. Esta base sera usada para organizar as primeiras regras de negocio e evoluir gradualmente para um ecossistema mais completo.

# Visão do Produto
A ideia e construir uma plataforma para operação de restaurantes, bares, lanchonetes e casas similares.

O primeiro modulo sera o de comandas:

Mesas livres em verde.
Mesas ocupadas em vermelho.
Mesas reservadas em amarelo.
Pedido vinculado a uma mesa.
Itens lançados pelo garçom.
Total da mesa atualizado automaticamente.
Fechamento da conta pelo caixa ou responsável.
Com o tempo, o ecossistema poderá incluir:

Controle de reservas.
Perfis de usuário: admin, garçom, caixa e cozinha.
Painel de cozinha/bar.
Controle de estoque.
Fechamento de caixa.
Relatórios financeiros.
Histórico de atendimentos.
Integrações com pagamento, impressoras e delivery.

# Stack Atual
Python
Streamlit
PostgreSQL
Pandas
Plotly
psycopg2
python-dotenv

# Modelo de Dados Atual
O banco inicial trabalha com as seguintes entidades:

categorias: grupos do cardapio.
cardapio: produtos vendidos pelo restaurante.
mesas: mesas fisicas do estabelecimento.
pedidos: comandas abertas, fechadas ou canceladas.
pedido_itens: itens vinculados a cada pedido.

# Roadmap Inicial

### Fase 1 - Organizar a Base
Padronizar nomes de arquivos.
Corrigir textos com encoding quebrado.
Proteger todas as telas administrativas.
Criar constraints importantes no banco.
Melhorar README e documentacao interna.
Versionar o projeto no GitHub.

### Fase 2 - Comandas Visuais
Criar tela principal de mesas mais visual.
Adicionar status: livre, ocupada, reservada, aguardando pagamento.
Permitir abrir comanda clicando diretamente na mesa.
Mostrar total, tempo aberto e quantidade de itens na mesa.
Melhorar fluxo de adicionar itens.

### Fase 3 - Operação de Restaurante
Criar usuarios e permissoes.
Registrar qual garcom abriu/lancou cada pedido.
Criar painel de cozinha/bar.
Adicionar status por item: enviado, preparando, pronto, entregue.
Permitir transferir mesa.
Permitir dividir ou juntar contas.

### Fase 4 - Gestão e Escala
Fechamento de caixa.
Relatorios por periodo.
Controle de estoque.
Reservas.
Integracoes externas.
Avaliar migracao da interface operacional para React/Next.js com backend em FastAPI.
