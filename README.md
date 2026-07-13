# 🍔 Cascatinha Burguer — Cardápio Digital

Cardápio digital com carrinho de compras e finalização de pedido via WhatsApp, feito para uma hamburgueria fictícia (projeto de estudo/portfólio).

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)

## ✨ Funcionalidades

- 📋 Listagem de hambúrgueres e bebidas com preços
- 🛒 Carrinho de compras (adicionar, remover, atualizar quantidade)
- 💾 Carrinho persistente (salvo no `localStorage` do navegador)
- 🕐 Indicador de aberto/fechado baseado no horário de funcionamento
- 📱 Finalização de pedido via WhatsApp, com endereço de entrega
- 🎨 Layout responsivo (mobile e desktop)

## 🛠️ Tecnologias

- HTML5
- [Tailwind CSS](https://tailwindcss.com/)
- JavaScript (vanilla, sem frameworks)
- [Toastify-js](https://github.com/apvarun/toastify-js) — notificações
- [Font Awesome](https://fontawesome.com/) — ícones
- Google Fonts (Poppins)

## 🚀 Como rodar localmente

### Pré-requisitos
- [Node.js](https://nodejs.org/) instalado (para compilar o Tailwind CSS)

### Passo a passo

```bash
# 1. Clone o repositório
git clone <url-do-repositorio>
cd Cardapio-main

# 2. Instale as dependências
npm install

# 3. Compile o CSS (modo watch, recompila automaticamente ao salvar)
npm run dev
```

Em outra aba/terminal, sirva os arquivos estáticos. Algumas opções:

```bash
# Usando a extensão "Live Server" do VS Code, ou:
npx serve .
```

Depois é só abrir `index.html` no navegador (ou o endereço indicado pelo `serve`).

### Build de produção

```bash
npm run build
```

Isso gera o `styles/output.css` já minificado, pronto para deploy.

## ⚙️ Configuração obrigatória

Antes de colocar em produção, edite o arquivo `script.js` e configure o número de WhatsApp do restaurante:

```js
const WHATSAPP_PHONE = "5532999999999" // código do país + DDD + número, sem espaços/símbolos
```

Enquanto isso não for feito, o botão "Finalizar pedido" mostra um aviso e não abre o WhatsApp.

## 📁 Estrutura do projeto

```
Cardapio-main/
├── assets/              # Imagens dos produtos (formato .webp, otimizadas)
├── styles/
│   ├── styles.css       # Fonte do Tailwind (diretivas @tailwind)
│   └── output.css       # CSS compilado (gerado, não editar direto)
├── index.html           # Estrutura da página
├── script.js            # Lógica do carrinho e pedido
├── tailwind.config.js   # Configuração do Tailwind
├── favicon.ico
├── robots.txt
├── sitemap.xml
└── package.json
```

## 📝 Editando o cardápio

Os produtos ficam direto no `index.html`, dentro da `<div id="menu">`. Para adicionar um item novo, copie um bloco `<!-- PRODUTO ITEM -->` existente e ajuste:

- `src` da imagem (coloque o arquivo em `assets/`, de preferência em `.webp`)
- `alt` da imagem
- Nome e descrição do produto
- `data-name` e `data-price` do botão (usados pelo carrinho)

## 🗺️ Roadmap / próximos passos

- [ ] Separar os itens do cardápio em um arquivo de dados (`menu.json`) em vez de hardcoded no HTML
- [ ] Categorias/abas de navegação (Lanches, Bebidas, Sobremesas)
- [ ] Campo de observações por item (ex: "sem cebola")
- [ ] Taxa de entrega e valor mínimo de pedido
- [ ] Modo escuro

## 📄 Licença

ISC
