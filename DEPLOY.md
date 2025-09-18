# 🚀 Deploy no Vercel - Apple Company 24hs

## 📋 Pré-requisitos

- ✅ Conta no [Vercel](https://vercel.com)
- ✅ Repositório no GitHub
- ✅ Node.js 18+ (especificado no `.nvmrc`)

## 🛠️ Configuração do Projeto

### 1. Estrutura de Arquivos
```
appleeeeetailwind/
├── src/
│   └── input.css          # CSS principal
├── dist/
│   └── output.css         # CSS compilado
├── index.html             # Página principal
├── package.json           # Dependências e scripts
├── tailwind.config.js     # Configuração Tailwind
├── postcss.config.js      # Configuração PostCSS
├── vercel.json           # Configuração Vercel
└── .nvmrc                # Versão Node.js
```

### 2. Scripts Disponíveis
```json
{
  "build": "tailwindcss -i ./src/input.css -o ./dist/output.css --minify",
  "vercel-build": "npm run build"
}
```

## 🚀 Deploy Automático

### Opção 1: Deploy via GitHub (Recomendado)
1. **Conecte o repositório:**
   - Acesse [vercel.com](https://vercel.com)
   - Clique em "New Project"
   - Conecte sua conta GitHub
   - Selecione o repositório

2. **Configurações automáticas:**
   - Framework: `Other`
   - Build Command: `npm run build`
   - Output Directory: `.`
   - Install Command: `npm install`

3. **Deploy:**
   - Clique em "Deploy"
   - Aguarde o build automático
   - Site estará disponível em `https://seu-projeto.vercel.app`

### Opção 2: Deploy via CLI
```bash
# Instale o Vercel CLI
npm i -g vercel

# Faça login
vercel login

# Deploy
vercel

# Deploy para produção
vercel --prod
```

## ⚙️ Configurações do Vercel

### vercel.json
```json
{
  "version": 2,
  "builds": [
    {
      "src": "package.json",
      "use": "@vercel/static-build",
      "config": {
        "distDir": "."
      }
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "/$1"
    }
  ],
  "buildCommand": "npm run build",
  "outputDirectory": ".",
  "installCommand": "npm install"
}
```

## 🔧 Solução de Problemas

### Erro: "Permission denied"
```bash
# Solução: Use scripts sem npx
"build": "tailwindcss -i ./src/input.css -o ./dist/output.css --minify"
```

### Erro: "Command not found"
```bash
# Verifique se as dependências estão instaladas
npm install

# Verifique se o Tailwind está instalado
npm list tailwindcss
```

### CSS não está sendo aplicado
1. Verifique se o arquivo `dist/output.css` existe
2. Execute `npm run build` localmente
3. Verifique se o link no HTML está correto

### Build falha no Vercel
1. Verifique os logs de build
2. Teste localmente: `npm run build`
3. Verifique se todas as dependências estão no `package.json`

## 📊 Monitoramento

### Logs de Build
- Acesse o dashboard do Vercel
- Vá em "Functions" > "Build Logs"
- Verifique erros e warnings

### Performance
- Use o Vercel Analytics
- Monitore Core Web Vitals
- Otimize imagens e CSS

## 🔄 Deploy Contínuo

### GitHub Actions (Opcional)
```yaml
name: Deploy to Vercel
on:
  push:
    branches: [main]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with:
          node-version: '18'
      - run: npm install
      - run: npm run build
      - uses: amondnet/vercel-action@v20
        with:
          vercel-token: ${{ secrets.VERCEL_TOKEN }}
          vercel-org-id: ${{ secrets.ORG_ID }}
          vercel-project-id: ${{ secrets.PROJECT_ID }}
```

## 📱 Domínio Personalizado

1. **Adicione domínio:**
   - Vercel Dashboard > Project > Settings > Domains
   - Adicione seu domínio

2. **Configure DNS:**
   - Aponte para o Vercel
   - Aguarde propagação

## 🎯 Otimizações

### Performance
- ✅ CSS minificado
- ✅ Imagens otimizadas
- ✅ Cache configurado
- ✅ CDN global

### SEO
- ✅ Meta tags otimizadas
- ✅ Sitemap configurado
- ✅ Robots.txt
- ✅ Schema markup

## 📞 Suporte

- 📧 Email: contato@applecompany24hs.com
- 📞 Telefone: (11) 9999-9999
- 🐛 Issues: [GitHub Issues](https://github.com/applecompany24hs/site/issues)

---

**Deploy realizado com sucesso! 🎉**
