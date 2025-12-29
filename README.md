# SoluçãoWebMangueLimpo
Projeto de criação de protótipo de aplicativo para Limpeza e preservação do Mangue através da conscientização
# 🦀 Manguecity: A Jornada Gamificada por Recife

![Status do Projeto](https://img.shields.io/badge/status-em_desenvolvimento-yellow)
![Plataforma](https://img.shields.io/badge/plataforma-Mobile-blue)

O **Manguecity** é uma solução web que transforma aprender a importãncia do Mangue em uma experiência épica e gamificada. Inspirado pelo movimento Manguebeat, a solução Web ensina crianças, oferecendo desafios, recompensas e uma imersão profunda na identidade pernambucana e a importância do Mangue.

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



### Arquivo: `App.js` (Estrutura Principal)

```javascript
import React, { useState } from 'react';
import { StyleSheet, Text, View, ScrollView, TouchableOpacity, SafeAreaView } from 'react-native';
import { Trophy, MapPin, User, Star } from 'lucide-react-native';

export default function App() {
  const [xp, setXp] = useState(450);

  return (
    <SafeAreaView style={styles.container}>
      <ScrollView contentContainerStyle={styles.scrollContent}>
        
        {/* Header - Perfil do Usuário */}
        <View style={styles.header}>
          <View style={styles.profileBadge}>
            <User color="#FFF" size={32} />
          </View>
          <View>
            <Text style={styles.greeting}>Olá, Explorador!</Text>
            <Text style={styles.level}>Nível 12 - Mestre do Cais</Text>
          </View>
        </View>

        {/* Barra de Progresso XP */}
        <View style={styles.xpCard}>
          <View style={styles.xpInfo}>
            <Text style={styles.xpText}>XP Atual: {xp}/1000</Text>
            <Star color="#FFD700" size={20} fill="#FFD700" />
          </View>
          <View style={styles.progressBarBg}>
            <View style={[styles.progressBarFill, { width: '45%' }]} />
          </View>
        </View>

        {/* Missões Ativas */}
        <Text style={styles.sectionTitle}>Missões no Mangue</Text>
        
        <TouchableOpacity style={styles.missionCard}>
          <MapPin color="#e67e22" size={24} />
          <View style={styles.missionDetails}>
            <Text style={styles.missionTitle}>Marco Zero</Text>
            <Text style={styles.missionSub}>Faça check-in para ganhar 50 XP</Text>
          </View>
          <Trophy color="#bdc3c7" size={20} />
        </TouchableOpacity>

        <TouchableOpacity style={styles.missionCard}>
          <MapPin color="#2ecc71" size={24} />
          <View style={styles.missionDetails}>
            <Text style={styles.missionTitle}>Paço do Frevo</Text>
            <Text style={styles.missionSub}>Complete o Quiz Cultural</Text>
          </View>
          <Trophy color="#bdc3c7" size={20} />
        </TouchableOpacity>

      </ScrollView>

      {/* Menu Inferior */}
      <View style={styles.tabBar}>
        <TouchableOpacity style={styles.tabItem}><MapPin color="#FFF" /></TouchableOpacity>
        <TouchableOpacity style={styles.tabItem}><Trophy color="#FFF" /></TouchableOpacity>
        <TouchableOpacity style={styles.tabItem}><User color="#FFF" /></TouchableOpacity>
      </View>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: '#f4f7f6' },
  scrollContent: { padding: 20 },
  header: { flexDirection: 'row', alignItems: 'center', marginBottom: 30, marginTop: 20 },
  profileBadge: { width: 60, height: 60, borderRadius: 30, backgroundColor: '#2c3e50', justifyContent: 'center', alignItems: 'center', marginRight: 15 },
  greeting: { fontSize: 18, fontWeight: 'bold', color: '#34495e' },
  level: { fontSize: 14, color: '#7f8c8d' },
  xpCard: { backgroundColor: '#FFF', padding: 20, borderRadius: 15, elevation: 4, marginBottom: 30 },
  xpInfo: { flexDirection: 'row', justifyContent: 'space-between', marginBottom: 10 },
  xpText: { fontWeight: 'bold', color: '#2c3e50' },
  progressBarBg: { height: 10, backgroundColor: '#ecf0f1', borderRadius: 5 },
  progressBarFill: { height: 10, backgroundColor: '#e67e22', borderRadius: 5 },
  sectionTitle: { fontSize: 20, fontWeight: 'bold', color: '#2c3e50', marginBottom: 15 },
  missionCard: { backgroundColor: '#FFF', padding: 15, borderRadius: 12, flexDirection: 'row', alignItems: 'center', marginBottom: 12, borderLeftWidth: 5, borderLeftColor: '#e67e22' },
  missionDetails: { flex: 1, marginLeft: 15 },
  missionTitle: { fontSize: 16, fontWeight: 'bold' },
  missionSub: { fontSize: 12, color: '#95a5a6' },
  tabBar: { height: 60, backgroundColor: '#2c3e50', flexDirection: 'row', justifyContent: 'space-around', alignItems: 'center', borderTopLeftRadius: 20, borderTopRightRadius: 20 }
});
