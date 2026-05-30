# Top 10 Spotify — Deploy no Firebase

## Pré-requisitos
- [Node.js](https://nodejs.org) instalado
- Conta Google (para o Firebase)
- App criado no [Spotify Dashboard](https://developer.spotify.com/dashboard)

---

## Passo a passo

### 1. Instalar Firebase CLI
```bash
npm install -g firebase-tools
```

### 2. Login no Firebase
```bash
firebase login
```

### 3. Criar projeto no Firebase Console
- Acesse https://console.firebase.google.com
- Clique em "Adicionar projeto"
- Dê um nome (ex: `spotify-top10`)
- Pode desativar Google Analytics
- Anote o **Project ID** (ex: `spotify-top10-abc12`)

### 4. Atualizar o .firebaserc
Abra o arquivo `.firebaserc` e substitua `SEU-PROJECT-ID-AQUI` pelo seu Project ID:
```json
{
  "projects": {
    "default": "spotify-top10-abc12"
  }
}
```

### 5. Deploy
Na pasta do projeto, rode:
```bash
firebase deploy
```

Você verá algo assim no final:
```
✔  Deploy complete!
Hosting URL: https://spotify-top10-abc12.web.app
```

---

## Configurar o Spotify

### 6. Copiar a URL do deploy
Ex: `https://spotify-top10-abc12.web.app`

### 7. Adicionar no Spotify Dashboard
- Acesse https://developer.spotify.com/dashboard
- Clique no seu app → **Edit Settings**
- Em **Redirect URIs**, adicione a URL exata:
  ```
  https://spotify-top10-abc12.web.app
  ```
- Clique em **Save**

### 8. Usar o app
- Abra `https://spotify-top10-abc12.web.app`
- Cole seu **Client ID** na tela inicial
- Clique em **Conectar ao Spotify** e pronto!

---

## Estrutura do projeto
```
spotify-top10/
├── public/
│   └── index.html   ← app completo (single file)
├── firebase.json    ← config do hosting
├── .firebaserc      ← project ID
└── README.md
```

## Atualizar o site depois
Edite o `public/index.html` e rode `firebase deploy` novamente.
