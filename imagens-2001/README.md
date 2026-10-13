# Imagens Lojas 2001 · Processador HD

Sistema web estático (HTML + JavaScript, sem backend) para padronizar as fotos de produto do e-commerce.

O que ele faz:

1. **Recorte inteligente** – localiza o produto na foto ignorando fundo branco ou transparente.
2. **Padronização** – redimensiona o produto proporcionalmente para 750x750 e centraliza numa tela branca de 1080x1080, em PNG.
3. **Agrupamento por código** – o código vem do nome do arquivo (trecho antes do primeiro hífen). Produtos com várias fotos ficam agrupados e numerados em sequência.
4. **Salvamento** – direto numa pasta local escolhida pelo usuário (subpasta por código, sem sobrescrever) ou em um ZIP estruturado.

Todo o processamento acontece no navegador. Nenhuma imagem é enviada a servidor.

> O salvamento direto em pasta usa a File System Access API, disponível no Chrome e no Edge. Em outros navegadores o sistema gera o ZIP.

## Estrutura

```
.
├── public/
│   ├── index.html     # o sistema completo (HTML, CSS e JS)
│   └── favicon.svg    # símbolo da marca
├── vercel.json        # configuração de deploy (URLs limpas e cabeçalhos)
├── package.json       # script local de pré-visualização
├── .gitignore
└── README.md
```

## Rodar localmente

Basta abrir `public/index.html` no navegador. Para servir em `http://localhost:3000`:

```bash
npm run dev
```

## Publicar no GitHub

Dentro desta pasta:

```bash
git init
git add .
git commit -m "Sistema de imagens Lojas 2001"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/imagens-2001.git
git push -u origin main
```

## Publicar na Vercel

1. Acesse [vercel.com/new](https://vercel.com/new) e importe o repositório do GitHub.
2. Em **Framework Preset** deixe **Other**.
3. Em **Output Directory** informe `public`.
4. Deixe **Build Command** vazio e clique em **Deploy**.

Cada `git push` na branch `main` gera um novo deploy automaticamente.

## Dependências externas (CDN)

- JSZip `3.10.1` (geração do ZIP)
- Lucide `0.460.0` (ícones)
- Google Fonts: Oswald, Mulish e Roboto (tipografia da marca)

Identidade visual conforme o guia da marca Lojas 2001.
