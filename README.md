# 🚀 Amplify Vue App

App de demostración construida con **Vue 3 + Vite**, lista para desplegar en AWS Amplify.

## Estructura del proyecto

```
amplify-vue-app/
├── src/
│   ├── main.js
│   └── App.vue
├── index.html
├── vite.config.js
├── amplify.yml       ← configuración de build para Amplify
└── package.json
```

## Correr localmente

```bash
npm install
npm run dev
```

## Desplegar en AWS Amplify

1. Sube este proyecto a un repositorio de GitHub
2. Ve a la consola de AWS Amplify
3. Click en **"Deploy an app"** → **"GitHub"**
4. Selecciona este repositorio y la rama `main`
5. Amplify detectará el `amplify.yml` automáticamente
6. Click en **"Save and deploy"** ✅

El build usará:
- **Build command:** `npm run build`
- **Output directory:** `dist`
