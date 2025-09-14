{
  "name": "bossmed-simple",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "next dev -p 3000",
    "build": "next build",
    "start": "next start -p 3000"
  },
  "dependencies": {
    "next": "14.0.0",
    "react": "18.2.0",
    "react-dom": "18.2.0"
  }
}
const nextConfig = { reactStrictMode: true };
module.exports = nextConfig;
import '../styles/globals.css';

export default function App({ Component, pageProps }) {
  return <Component {...pageProps} />;
}
import Head from 'next/head';

const quizzes = [
  {
    id: 1,
    title: "Anatomie — Membre supérieur",
    description: "Testez vos connaissances de base sur l’anatomie du membre supérieur.",
    questions: 10
  },
  {
    id: 2,
    title: "Physiologie — Bases",
    description: "Les notions essentielles de la physiologie en QCM.",
    questions: 8
  },
  {
    id: 3,
    title: "Pharmacologie cardiovasculaire",
    description: "Révisez les médicaments principaux en cardio.",
    questions: 12
  }
];

export default function Home() {
  return (
    <>
      <Head>
        <title>Boss Med</title>
      </Head>
      <main style={{ fontFamily: 'Inter, sans-serif', padding: 24, maxWidth: 900, margin: '0 auto' }}>
        <header style={{ display: 'flex', alignItems: 'center', gap: 12, marginBottom: 32 }}>
          <img src="/logo.svg" alt="Boss Med" style={{ height: 50 }} />
          <h1 style={{ margin: 0 }}>Boss Med</h1>
        </header>

        <h2>📚 Quizzes disponibles</h2>
        <section style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(250px, 1fr))', gap: 16, marginTop: 20 }}>
          {quizzes.map(q => (
            <article key={q.id} style={{ background: '#fff', padding: 16, borderRadius: 12, boxShadow: '0 4px 12px rgba(0,0,0,0.05)' }}>
              <h3 style={{ marginTop: 0 }}>{q.title}</h3>
              <p style={{ color: '#555' }}>{q.description}</p>
              <p><strong>{q.questions}</strong> questions</p>
              <button style={{ background: '#0B6EFF', color: '#fff', padding: '8px 12px', borderRadius: 8, border: 'none' }}>
                Commencer
              </button>
            </article>
          ))}
        </section>

        <footer style={{ marginTop: 40, textAlign: 'center', color: '#777' }}>
          © {new Date().getFullYear()} Boss Med — Plateforme d’apprentissage médical
        </footer>
      </main>
    </>
  );
}
<svg xmlns="http://www.w3.org/2000/svg" width="220" height="60" viewBox="0 0 220 60">
  <rect width="220" height="60" rx="10" fill="#0B6EFF"/>
  <text x="110" y="38" text-anchor="middle" font-family="Inter, Arial, sans-serif" font-size="26" fill="white">Boss Med</text>
</svg>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap');

body {
  margin: 0;
  background: #f3f6fb;
  color: #222;
  font-family: 'Inter', sans-serif;
}
