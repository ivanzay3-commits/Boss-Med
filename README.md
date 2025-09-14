{
  "name": "bossmed",
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
import quizzesData from '../seed/bossmed-seed.json';

export default function Home() {
  return (
    <>
      <Head>
        <title>Boss Med</title>
      </Head>
      <main className="max-w-4xl mx-auto p-6 font-inter">
        <header className="flex items-center gap-4 mb-10">
          <img src="/logo.svg" alt="Boss Med" className="h-12" />
          <h1 className="text-3xl font-bold">Boss Med</h1>
        </header>

        <h2 className="text-2xl font-semibold mb-6">📚 Quizzes disponibles</h2>
        <div className="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
          {quizzesData.items.map(q => (
            <div key={q.id} className="bg-white p-4 rounded-xl shadow-md">
              <h3 className="font-semibold text-lg">{q.title}</h3>
              <p className="text-gray-600 mt-1 mb-2">{q.questions?.length || 0} questions</p>
              <button className="bg-blue-600 text-white px-4 py-2 rounded-lg mt-2">Commencer</button>
            </div>
          ))}
        </div>

        <footer className="mt-12 text-center text-gray-500">
          © {new Date().getFullYear()} Boss Med — Plateforme d’apprentissage médical
        </footer>
      </main>
    </>
  );
}
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap');

body {
  margin: 0;
  font-family: 'Inter', sans-serif;
  background-color: #f3f6fb;
  color: #111;
}
**<svg xmlns="http://www.w3.org/2000/svg" width="200" height="60" viewBox="0 0 200 60">
  <rect width="200" height="60" rx="10" fill="#0B6EFF"/>
  <text x="100" y="38" text-anchor="middle" font-family="Inter, Arial, sans-serif" font-size="24" fill="white">Boss Med</text>
</svg>
{
  "items": [
    {
      "id": "quiz-anat-upperlimb",
      "type": "quiz",
      "title": "Anatomie — Membre supérieur : bases",
      "published": true,
      "questions": [
        {"q":"Quel est le principal nerf moteur du biceps brachial ?","a":"Nerf musculocutané."},
        {"q":"Quelle artère continue à la face dorsale de la main après l'arche palmaire profonde ?","a":"L'artère radiale forme l'arche dorsale et contribue à l'arcade palmaire profonde via l'artère radiale profonde."}
      ]
    },
    {
      "id": "quiz-cv-pharma",
      "type": "quiz",
      "title": "Pharmacologie cardiovasculaire — Principes",
      "published": true,
      "questions": [
        {"q":"Quel est le mécanisme d'action des inhibiteurs ACE (IECA) ?","a":"Inhibition de l'enzyme de conversion de l'angiotensine I en II."},
        {"q":"Quel diurétique est épargneur de potassium ?","a":"Spironolactone et amiloride."}
      ]
    }
  ]
}
**
