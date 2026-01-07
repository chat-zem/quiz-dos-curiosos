# 🚀 Como Publicar no GitHub Pages

## Método Rápido (arquivo HTML único)

### 1️⃣ Criar Repositório no GitHub

1. Vá em [github.com](https://github.com)
2. Clique em **"New repository"** (botão verde)
3. Nome do repositório: `quiz-curiosidades` (ou qualquer nome)
4. Marque **"Public"**
5. Marque **"Add a README file"**
6. Clique em **"Create repository"**

### 2️⃣ Fazer Upload do Arquivo HTML

**Opção A: Via Interface Web (Mais Fácil)**

1. No seu repositório, clique em **"Add file"** → **"Upload files"**
2. Arraste o arquivo `quiz-curiosidades.html`
3. Renomeie para **`index.html`** (importante!)
4. Clique em **"Commit changes"**

**Opção B: Via Git (Se você já usa)**

```bash
git clone https://github.com/SEU-USUARIO/quiz-curiosidades.git
cd quiz-curiosidades
cp quiz-curiosidades.html index.html
git add index.html
git commit -m "Adiciona jogo de quiz"
git push
```

### 3️⃣ Ativar GitHub Pages

1. No repositório, vá em **"Settings"** (engrenagem)
2. No menu esquerdo, clique em **"Pages"**
3. Em **"Source"**, selecione:
   - Branch: **main** (ou master)
   - Folder: **/ (root)**
4. Clique em **"Save"**

### 4️⃣ Acessar seu Jogo! 🎉

Aguarde 1-2 minutos e acesse:

```
https://SEU-USUARIO.github.io/quiz-curiosidades
```

---

## Método Completo (com React)

Se quiser a versão React completa:

### 1️⃣ Criar Projeto React

```bash
npm create vite@latest quiz-curiosidades -- --template react
cd quiz-curiosidades
npm install lucide-react
```

### 2️⃣ Copiar Código

Cole o conteúdo do artifact em `src/App.jsx`

### 3️⃣ Configurar para GitHub Pages

Edite `vite.config.js`:

```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  base: '/quiz-curiosidades/' // Nome do seu repositório
})
```

Adicione no `package.json`:

```json
{
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  }
}
```

### 4️⃣ Instalar gh-pages

```bash
npm install --save-dev gh-pages
```

### 5️⃣ Deploy

```bash
# Criar repositório no GitHub primeiro
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/quiz-curiosidades.git
git push -u origin main

# Deploy
npm run deploy
```

### 6️⃣ Configurar GitHub Pages

1. Settings → Pages
2. Source: **gh-pages** branch
3. Save

Acesse: `https://SEU-USUARIO.github.io/quiz-curiosidades`

---

## 🎯 Recomendação

Use o **Método Rápido** (HTML único)! É:
- ✅ Mais simples
- ✅ Sem dependências
- ✅ Funciona imediatamente
- ✅ Mesmo resultado visual

---

## 🆘 Problemas Comuns

**"404 Not Found"**
- Verifique se o arquivo se chama `index.html`
- Aguarde 2-3 minutos após ativar Pages

**"Página em branco"**
- Abra o Console do navegador (F12)
- Verifique se há erros

**"Changes não aparecem"**
- Limpe o cache do navegador (Ctrl+Shift+R)
- Aguarde alguns minutos (GitHub demora a atualizar)

---

## 📝 Customização

Para mudar cores, perguntas, etc., edite o arquivo HTML:

```html
<!-- Procure por "const CATEGORIAS" -->
const CATEGORIAS = {
    'Sua Categoria': { cor: '#FF0000', corClara: '#FFE0E0' },
    // ...
}

<!-- Procure por "const PERGUNTAS" -->
const PERGUNTAS = {
    'Sua Categoria': [
        {
            pergunta: 'Sua pergunta?',
            opcoes: ['A', 'B', 'C', 'D'],
            correta: 0,
            explicacao: 'Sua explicação'
        }
    ]
}
```

Salve, faça commit, e aguarde atualizar!

---

**Link direto para criar repo:** https://github.com/new

**Documentação GitHub Pages:** https://pages.github.com
