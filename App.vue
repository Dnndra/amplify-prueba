<template>
  <div class="page">
    <div class="noise"></div>

    <header class="header">
      <div class="badge">🚀 Desplegado con AWS Amplify</div>
    </header>

    <main class="main">
      <div class="hero">
        <p class="label">Hola, mundo</p>
        <h1 class="title">Mi primera app<br><span class="accent">en Amplify</span></h1>
        <p class="subtitle">
          Esta aplicación fue creada con <strong>Vue 3</strong> + Vite y desplegada
          automáticamente desde GitHub usando AWS Amplify.
        </p>
        <div class="tags">
          <span class="tag">Vue 3</span>
          <span class="tag">Vite</span>
          <span class="tag">AWS Amplify</span>
          <span class="tag">GitHub CI/CD</span>
        </div>
      </div>

      <div class="cards">
        <div class="card">
          <div class="card-icon">⚡</div>
          <h3>Build automático</h3>
          <p>Cada push a la rama main dispara un nuevo build y despliegue automáticamente.</p>
        </div>
        <div class="card">
          <div class="card-icon">🌐</div>
          <h3>HTTPS incluido</h3>
          <p>Amplify provee un dominio con SSL/TLS sin configuración adicional.</p>
        </div>
        <div class="card">
          <div class="card-icon">🔁</div>
          <h3>CI/CD listo</h3>
          <p>Conectado a GitHub, cada rama puede tener su propio entorno de preview.</p>
        </div>
      </div>
    </main>

    <footer class="footer">
      <p>Construido con Vue 3 · Desplegado en AWS Amplify</p>
    </footer>
  </div>
</template>

<script setup>
// App simple de demostración — sin lógica adicional necesaria
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=DM+Sans:wght@300;400;500&display=swap');

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg: #0a0a0f;
  --surface: #13131a;
  --border: #1e1e2e;
  --accent: #e8ff47;
  --accent2: #6c63ff;
  --text: #f0f0f5;
  --muted: #7070a0;
}

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'DM Sans', sans-serif;
  min-height: 100vh;
}

.page {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  position: relative;
  overflow: hidden;
}

/* Grain texture overlay */
.noise {
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 0;
  opacity: 0.5;
}

/* Gradient glow */
.page::before {
  content: '';
  position: fixed;
  top: -200px;
  left: 50%;
  transform: translateX(-50%);
  width: 800px;
  height: 600px;
  background: radial-gradient(ellipse, rgba(108,99,255,0.15) 0%, transparent 70%);
  pointer-events: none;
}

.header {
  padding: 2rem;
  display: flex;
  justify-content: center;
  position: relative;
  z-index: 1;
}

.badge {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 100px;
  padding: 0.4rem 1.2rem;
  font-size: 0.82rem;
  color: var(--muted);
  letter-spacing: 0.02em;
}

.main {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 4rem 2rem;
  gap: 5rem;
  position: relative;
  z-index: 1;
}

.hero {
  max-width: 680px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
  animation: fadeUp 0.8s ease both;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}

.label {
  font-size: 0.78rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--accent);
  font-weight: 500;
}

.title {
  font-family: 'Syne', sans-serif;
  font-size: clamp(2.8rem, 7vw, 5rem);
  font-weight: 800;
  line-height: 1.05;
  letter-spacing: -0.02em;
}

.accent {
  color: var(--accent);
  position: relative;
  display: inline-block;
}

.subtitle {
  font-size: 1.1rem;
  color: var(--muted);
  line-height: 1.7;
  max-width: 520px;
}

.subtitle strong {
  color: var(--text);
  font-weight: 500;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
}

.tag {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 6px;
  padding: 0.3rem 0.8rem;
  font-size: 0.8rem;
  color: var(--muted);
  font-family: 'DM Sans', monospace;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
  width: 100%;
  max-width: 780px;
  animation: fadeUp 0.8s 0.2s ease both;
}

.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
  transition: border-color 0.2s, transform 0.2s;
}

.card:hover {
  border-color: var(--accent2);
  transform: translateY(-4px);
}

.card-icon {
  font-size: 1.8rem;
}

.card h3 {
  font-family: 'Syne', sans-serif;
  font-size: 1rem;
  font-weight: 700;
}

.card p {
  font-size: 0.88rem;
  color: var(--muted);
  line-height: 1.6;
}

.footer {
  padding: 2rem;
  text-align: center;
  font-size: 0.8rem;
  color: var(--muted);
  position: relative;
  z-index: 1;
}
</style>
