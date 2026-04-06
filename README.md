# 🛍️ LuxStore — Loja Virtual de Perfumes, Roupas e Tênis

## 📌 Visão Geral
LuxStore é uma loja virtual completa, moderna e responsiva, desenvolvida para vender **perfumes**, **roupas** e **tênis** de alto padrão. O projeto inclui vitrine para clientes e painel administrativo completo para gerenciamento de produtos.

---

## ✅ Funcionalidades Implementadas

### 🛒 Vitrine (index.html)
- Hero slider automático com 3 slides (Perfumes, Roupas, Tênis)
- Seção de categorias com destaque visual
- Grid de produtos em destaque
- Catálogo completo com filtros por categoria (Todos / Perfumes / Roupas / Tênis)
- Ordenação por: Relevância, Menor Preço, Maior Preço, Avaliação, Nome A-Z
- Busca em tempo real por nome, marca, descrição
- Modal de detalhe do produto (imagem, descrição, tamanhos, avaliação, quantidade)
- Carrinho lateral (drawer) com localStorage
  - Adicionar, remover, limpar itens
  - Cálculo automático de frete grátis acima de R$299
  - Badge com contagem de itens
- Favoritos (visual toggle)
- Banner promocional (frete grátis, parcelas, segurança)
- Newsletter com feedback visual
- Toast notifications
- Design responsivo (desktop, tablet, mobile)

### 🛠️ Painel Admin (admin.html)
- Dashboard com contadores (total, perfumes, roupas, tênis)
- Tabela de produtos com busca e filtros por categoria
- Formulário completo de cadastro de produto:
  - Nome, categoria, marca, preço, preço original, estoque, avaliação, cor
  - Tamanhos (separados por vírgula)
  - URL da imagem com preview ao vivo
  - Descrição
  - Toggle de destaque na home
- Edição inline de produtos existentes
- Exclusão com confirmação (modal de segurança)
- Layout responsivo com sidebar colapsável no mobile

---

## 📁 Estrutura de Arquivos

```
index.html          → Vitrine da loja
admin.html          → Painel administrativo
css/
  style.css         → Estilos globais da loja
  admin.css         → Estilos do painel admin
js/
  app.js            → Lógica da vitrine (slider, carrinho, modal, filtros...)
  admin.js          → Lógica do painel admin (CRUD de produtos)
```

---

## 🗃️ Modelo de Dados — Tabela `produtos`

| Campo          | Tipo       | Descrição                                  |
|----------------|------------|--------------------------------------------|
| id             | text       | ID único (gerado automaticamente)          |
| nome           | text       | Nome do produto                            |
| descricao      | rich_text  | Descrição detalhada                        |
| preco          | number     | Preço atual (R$)                           |
| preco_original | number     | Preço original (para exibir desconto)      |
| categoria      | text       | perfumes / roupas / tenis                  |
| imagem_url     | text       | URL da imagem do produto                   |
| destaque       | bool       | Exibir na seção de destaques               |
| estoque        | number     | Quantidade em estoque                      |
| marca          | text       | Marca do produto                           |
| tamanhos       | array      | Ex: ["P","M","G"] ou ["38","39","40"]      |
| cor            | text       | Cor(es) do produto                         |
| avaliacao      | number     | Nota média de 0 a 5                        |

---

## 🔗 URIs Funcionais

| Rota           | Descrição                         |
|----------------|-----------------------------------|
| `/`            | Vitrine da loja (index.html)      |
| `/admin.html`  | Painel administrativo             |

### API RESTful usada internamente:

| Método | Endpoint                  | Ação                   |
|--------|---------------------------|------------------------|
| GET    | `tables/produtos`         | Listar produtos        |
| GET    | `tables/produtos/{id}`    | Buscar por ID          |
| POST   | `tables/produtos`         | Criar produto          |
| PUT    | `tables/produtos/{id}`    | Atualizar produto      |
| DELETE | `tables/produtos/{id}`    | Excluir produto        |

---

## 🚀 Próximas Etapas Recomendadas

- [ ] Sistema de login para o painel admin
- [ ] Página de checkout com formulário completo
- [ ] Integração com gateway de pagamento (Mercado Pago, PagSeguro)
- [ ] Página de detalhe individual do produto (`produto.html?id=xxx`)
- [ ] Upload de imagem direta (em vez de URL)
- [ ] Sistema de avaliações pelos clientes
- [ ] Lista de favoritos persistente (conta do usuário)
- [ ] Filtro por preço (slider range)
- [ ] Cupom de desconto
- [ ] Cálculo de frete por CEP

---

## 🎨 Tecnologias Utilizadas

- HTML5 + CSS3 (custom properties, grid, flexbox)
- JavaScript ES6+ (fetch API, localStorage)
- Font Awesome 6.4 (ícones)
- Google Fonts — Poppins
- RESTful Table API (backend de dados)

---

## 📦 Produtos de Exemplo Pré-cadastrados

| Nome              | Categoria | Preço     |
|-------------------|-----------|-----------|
| Chanel Nº5        | Perfumes  | R$899,90  |
| Dior Sauvage      | Perfumes  | R$749,90  |
| Jaqueta Couro Premium | Roupas | R$599,90 |
| Nike Air Max 270  | Tênis     | R$799,90  |
