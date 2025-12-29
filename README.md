# 🦀 SoluçãoWebMangueLimpo: Manguecity

![Status do Projeto](https://img.shields.io/badge/status-em_desenvolvimento-yellow)
![Plataforma](https://img.shields.io/badge/plataforma-Web-green)
![Público](https://img.shields.io/badge/público-Infantil-orange)

O **Manguecity** é uma solução web educativa e gamificada criada para ensinar crianças sobre a importância vital dos manguezais. Através de uma interface lúdica inspirada no movimento Manguebeat, transformamos o aprendizado sobre preservação e limpeza ambiental em uma aventura interativa.

[[Acesse o Design no Figma]](https://www.figma.com/make/T1T2dKOrnz9WOFKcreg6B9/Manguecity-Gamified-App-Design?fullscreen=1&t=xCSdFKIpTtqp6vcE-1)

---

## 🚀 Funcionalidades Principais

* **Mapa Interativo:** Explore Recife através de um mapa estilizado com pontos históricos e culturais.
* **Missões e Desafios:** Complete quizzes e tarefas presenciais (check-ins) para ganhar XP.
* **Sistema de Conquistas:** Desbloqueie medalhas baseadas em ícones da cultura local (Chico Science, Frevo, Galo da Madrugada).
* **Ranking de Exploradores:** Dispute o topo do ranking com outros usuários da comunidade.
* **Guia Gastronômico e Cultural:** Informações detalhadas sobre os melhores pontos da cidade.

---

## 🎨 Design (UI/UX)

O design foi focado na estética vibrante do Recife, utilizando cores que remetem ao ecossistema do mangue e à energia do carnaval. 

> [!TIP]
> Visualize o protótipo interativo no Figma para entender o fluxo de navegação e as animações de gamificação.

---

## 🛠️ Tecnologias Utilizadas

Este projeto utiliza as seguintes tecnologias:

* **React Native / Expo:** Framework para desenvolvimento mobile cross-platform.
* **React Navigation:** Para a fluidez entre as telas de mapa e perfil.
* **Lucide React Native:** Para ícones modernos e leves.
* **Styled Components:** Para uma estilização organizada e escalável.

---

Desenvolvido com ❤️ e muito Manguebeat.


---

## 💻 Código Base do Aplicativo (Exemplo Funcional)

Como o link do Figma foca na interface, preparei um código inicial em **React Native** que reflete a estrutura de uma das telas principais de gamificação do Manguecity.

Desenvolvido com ❤️ para proteger nossos mangues e educar as próximas gerações.


---

## 💻 Código Base da Solução Web (React)

Este código foi adaptado para rodar no **Navegador (Web)**, usando elementos mais visuais e divertidos para crianças.

### Arquivo: `App.js` (Interface Educativa)

```jsx
import React, { useState } from 'react';
import { Trophy, Trees, Trash2, Star, Award, Map } from 'lucide-react';

export default function ManguecityWeb() {
  const [ecoPontos, setEcoPontos] = useState(120);

  return (
    <div style={styles.container}>
      {/* Cabeçalho Lúdico */}
      <header style={styles.header}>
        <div style={styles.logoArea}>
          <Trees color="#2ecc71" size={40} />
          <h1 style={styles.title}>Manguecity Kids</h1>
        </div>
        <div style={styles.scoreBoard}>
          <Star color="#f1c40f" fill="#f1c40f" />
          <span style={styles.scoreText}>{ecoPontos} Eco-Pontos</span>
        </div>
      </header>

      <main style={styles.main}>
        <section style={styles.welcomeSection}>
          <h2>Olá, Pequeno Protetor! 👋</h2>
          <p>O mangue precisa da sua ajuda. Vamos aprender e brincar?</p>
        </section>

        {/* Card de Missão em Destaque */}
        <div style={styles.cardDestaque}>
          <div style={styles.cardIcon}>
            <Trash2 color="#FFF" size={48} />
          </div>
          <div style={styles.cardContent}>
            <h3>Operação Mangue Limpo</h3>
            <p>Ajude o caranguejo a limpar a lama e ganhe 50 pontos!</p>
            <button style={styles.buttonAction} onClick={() => setEcoPontos(ecoPontos + 50)}>
              Começar Aventura!
            </button>
          </div>
        </div>

        {/* Grade de Atividades */}
        <div style={styles.grid}>
          <div style={styles.miniCard}>
            <Map color="#e67e22" />
            <span>Explorar Mapa</span>
          </div>
          <div style={styles.miniCard}>
            <Award color="#9b59b6" />
            <span>Minhas Medalhas</span>
          </div>
          <div style={styles.miniCard}>
            <Trophy color="#f1c40f" />
            <span>Ranking</span>
          </div>
        </div>
      </main>

      <footer style={styles.footer}>
        <p>Aprender sobre o mangue é massa! 🦀✨</p>
      </footer>
    </div>
  );
}

const styles = {
  container: { fontFamily: 'Arial, sans-serif', backgroundColor: '#e8f5e9', minHeight: '100vh', padding: '20px' },
  header: { display: 'flex', justifyContent: 'space-between', alignItems: 'center', backgroundColor: '#FFF', padding: '15px 30px', borderRadius: '50px', boxShadow: '0 4px 15px rgba(0,0,0,0.1)' },
  logoArea: { display: 'flex', alignItems: 'center', gap: '10px' },
  title: { color: '#2d3436', fontSize: '24px', margin: 0 },
  scoreBoard: { display: 'flex', alignItems: 'center', gap: '8px', background: '#34495e', padding: '10px 20px', borderRadius: '30px', color: '#FFF' },
  scoreText: { fontWeight: 'bold' },
  main: { maxWidth: '800px', margin: '40px auto' },
  welcomeSection: { textAlign: 'center', marginBottom: '40px' },
  cardDestaque: { display: 'flex', backgroundColor: '#27ae60', borderRadius: '24px', padding: '30px', color: '#FFF', alignItems: 'center', gap: '20px', boxShadow: '0 10px 20px rgba(39, 174, 96, 0.3)' },
  cardIcon: { backgroundColor: 'rgba(255,255,255,0.2)', padding: '20px', borderRadius: '20px' },
  cardContent: { flex: 1 },
  buttonAction: { backgroundColor: '#f1c40f', border: 'none', padding: '12px 25px', borderRadius: '12px', fontWeight: 'bold', cursor: 'pointer', marginTop: '10px', fontSize: '16px' },
  grid: { display: 'grid', gridTemplateColumns: '1fr 1fr 1fr', gap: '20px', marginTop: '30px' },
  miniCard: { backgroundColor: '#FFF', padding: '20px', borderRadius: '20px', display: 'flex', flexDirection: 'column', alignItems: 'center', gap: '10px', fontWeight: 'bold', color: '#34495e', cursor: 'pointer' },
  footer: { textAlign: 'center', marginTop: '50px', color: '#7f8c8d' }
};
