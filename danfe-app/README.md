# DANFE Reader — Deploy no Vercel

## Estrutura do projeto

```
danfe-app/
├── vercel.json          ← configuração do Vercel
├── api/
│   └── nfe.js           ← backend (consulta NF-e sem CORS)
└── public/
    └── index.html       ← frontend (app completo)
```

---

## Como publicar no Vercel (passo a passo)

### 1. Crie uma conta gratuita
Acesse https://vercel.com e crie uma conta (pode usar sua conta Google ou GitHub).

### 2. Instale o Vercel CLI (opcional, mas mais fácil)
Abra o terminal do seu computador e execute:
```bash
npm install -g vercel
```

### 3. Faça o deploy
Dentro da pasta `danfe-app`, execute:
```bash
vercel
```
- Responda as perguntas: projeto novo → sim, diretório → `./` → confirme
- Aguarde o deploy (1-2 minutos)
- Você receberá um link como: `https://danfe-app-xxxx.vercel.app`

### 4. Alternativa sem terminal — Vercel via GitHub
1. Crie repositório no GitHub (github.com)
2. Faça upload de todos os arquivos desta pasta
3. Acesse vercel.com → "Add New Project" → importe o repositório
4. Clique em Deploy

---

## Como usar no celular

1. Abra o link gerado pelo Vercel no navegador do celular
2. Toque em **"Iniciar Câmera"**
3. Aponte para o código de barras do DANFE impresso
4. A NF-e será consultada automaticamente!

---

## Fontes de dados (em ordem de prioridade)

1. **meuDANFE** — tenta buscar dados completos da NF-e
2. **SEFAZ** — portal público da Fazenda
3. **Chave** — extrai dados básicos da própria chave de acesso

---

## Observações

- O leitor de câmera **só funciona em HTTPS** — o Vercel já fornece HTTPS automaticamente.
- O download do DANFE em PDF redireciona para meudanfe.com.br.
- A consulta é feita pelo backend (api/nfe.js), eliminando o problema de CORS.
