# ⚛️ Dashboard Enrichissement Uranium — République Française

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/fr/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-0055A4?style=for-the-badge)](LICENSE)
[![Made in France](https://img.shields.io/badge/Made%20in-France-EF4135?style=for-the-badge)](#)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-3fb950?style=for-the-badge)](#)

> **Liberté · Égalité · Fraternité**
>
> Dashboard interactif de simulation et d'optimisation de l'enrichissement de l'uranium, basé sur la relation fondamentale `α = exp(ΔM·v²/2RT) · η` et l'équation d'Einstein `E = Δm · c²`.

---

## 📖 Sommaire

- [Aperçu](#-aperçu)
- [Fonctionnalités](#-fonctionnalités)
- [Formules physiques](#-formules-physiques)
- [Algorithmes comparés](#-algorithmes-comparés)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Exports](#-exports)
- [Structure du projet](#-structure-du-projet)
- [Roadmap](#-roadmap)
- [Licence](#-licence)

---

## 🎯 Aperçu

Ce dashboard permet de **comparer trois méthodes d'enrichissement isotopique** de l'uranium — diffusion gazeuse, centrifugation et laser — sous l'angle du **gain de temps** et de **l'efficacité énergétique**, selon trois leviers d'optimisation :

| Levier | Impact |
|--------|--------|
| **Physique** | `α = exp(ΔM·v²/2RT) · η` — séparation élémentaire |
| **Cascade** | Conique vs carrée : **−22 % à −39 %** de centrifugeuses |
| **Algorithme** | PSO / IGWO / FHS — vitesse de convergence |

---

## ✨ Fonctionnalités

- 🎛️ **Curseurs physiques interactifs** — vitesse rotor, température, efficacité η, enrichissement cible
- 📊 **Comparaison temps réel** des trois méthodes (α, n, SWU, énergie, ratio fission/enrichissement)
- 📈 **Courbe de convergence** avec pan (clic-glisser) et zoom
- 🔬 **Mode comparaison côte à côte** des trois algorithmes d'optimisation
- 🎬 **Mode présentation plein écran** pour démos et soutenances
- 🌙 **Mode nuit / jour** commutable
- 🇫🇷 **Identité République Française** — bandeau tricolore, Marianne SVG, devise, signature `RF.`
- 📥 **Exports** CSV, JSON et PNG avec métadonnées et signature RF
- 🔔 **Toasts de confirmation** à chaque action

---

## 🧮 Formules physiques

### Séparation élémentaire (centrifugation)

\[
\alpha = \exp\left(\frac{\Delta M \cdot v^2}{2RT}\right) \cdot \eta
\]

| Symbole | Description | Valeur |
|---------|-------------|--------|
| `ΔM` | Différence de masse molaire U-238 / U-235 | `0.003 kg/mol` |
| `v` | Vitesse rotor | `300–1500 m/s` |
| `R` | Constante des gaz parfaits | `8.314 J/(mol·K)` |
| `T` | Température | `280–450 K` |
| `η` | Efficacité de séparation | `0.5–0.95` |

### Nombre d'étages

\[
n = \frac{\ln(R_P / R_F)}{\ln \alpha}
\]

### Valeur de séparation (SWU)

\[
V(x) = (2x - 1) \ln\left(\frac{x}{1-x}\right)
\]

\[
\text{SWU} = V(x_P) + W \cdot V(x_W) - F \cdot V(x_F)
\]

### Énergie de fission

\[
E = \Delta m \cdot c^2 \approx 8.2 \times 10^{13} \ \text{J/kg}
\]

---

## 🤖 Algorithmes comparés

| Algorithme | Type | Convergence | Précision | Usage |
|------------|------|-------------|-----------|-------|
| **PSO** | Essaim particulaire | ⚡ Rapide | Moyenne | Prototypage rapide |
| **IGWO** | Loup gris amélioré | 🐢 Lente | 🎯 Élevée | Optimisation fine |
| **FHS** | Recherche harmonique + flou | ⚖️ Équilibrée | Bonne | Compromis |

**Gain de temps** avec cascade conique :

| Algorithme | Temps relatif | Coût final |
|------------|---------------|------------|
| PSO | `× 0.60` | `0.05` |
| IGWO | `× 0.84` | `0.01` |
| FHS | `× 0.53` | `0.02` |

---

## 🚀 Installation

**Aucune dépendance, aucun build.** Un simple navigateur suffit.

### Option 1 — Téléchargement direct

Cloner le dépôt :

```
git clone https://github.com/votre-user/dashboard-enrichissement.git
cd dashboard-enrichissement
```

Puis ouvrir `index.html` dans un navigateur moderne (Chrome, Firefox, Edge, Safari).

### Option 2 — Serveur local (recommandé pour le plein écran)

Avec Python 3 :

```
python -m http.server 8000
```

Avec Node.js :

```
npx serve .
```

Puis ouvrir l'adresse suivante dans le navigateur :

```
http://localhost:8000
```

---

## 🎮 Utilisation

### Paramètres d'entrée

| Curseur | Plage | Effet |
|---------|-------|-------|
| Vitesse rotor | 300–1500 m/s | Pilote `α` (centrifugation) |
| Température | 280–450 K | Affecte `δ = ΔM·v²/2RT` |
| Efficacité η | 0.5–0.95 | Corrige `α` réel vs idéal |
| Enrichissement cible | 1–90 % | Modifie `Rp/Rf` et SWU |

### Raccourcis et interactions

| Action | Effet |
|--------|-------|
| Clic-glisser sur la courbe | Déplace la vue (pan) |
| Zoom + / − | Change l'échelle |
| Onglets PSO / IGWO / FHS | Change l'algorithme actif |
| `Échap` | Quitte le mode présentation |
| Bouton 🌙 / ☀️ | Bascule nuit/jour |
| Bouton 🎬 | Active le mode présentation |

---

## 📥 Exports

Tous les exports contiennent la **signature `RF.`** et la devise républicaine.

### CSV — `enrichissement_france.csv`

```
# Dashboard Enrichissement — République Française
# Liberté · Égalité · Fraternité
# Signature: RF.
Paramètre;Valeur
Vitesse rotor (m/s);700
...
```

### JSON — `enrichissement_france.json`

```json
{
  "signature": "RF.",
  "pays": "République Française",
  "devise": "Liberté · Égalité · Fraternité",
  "timestamp": "2026-10-04T14:32:15.000Z",
  "params": { "v": 700, "T": 343, "eta": 0.8, "xp": 5 },
  "centrifugation": { "alpha": 1.23, "n": 10, "swu": 8.85 },
  "optimisation": { "algo": "PSO", "machines": 619, "gain": "-30 %" }
}
```

### PNG — `convergence_france.png`

Capture du canvas avec les trois courbes et la signature RF en bas à droite.

---

## 📁 Structure du projet

```
dashboard-enrichissement/
├── index.html          # Dashboard complet (HTML + CSS + JS inline)
├── README.md           # Ce fichier
└── LICENSE             # MIT
```

**Aucun asset externe** — tout est embarqué dans un seul fichier HTML pour une portabilité maximale.

---

## 🗺️ Roadmap

- [x] Dashboard v1 — comparaison 3 méthodes
- [x] Optimisation cascade + algorithme
- [x] Courbe de convergence interactive
- [x] Mode présentation plein écran
- [x] Signature RF dans les exports
- [ ] Simulation Monte-Carlo des incertitudes
- [ ] Comparaison avec données industrielles réelles (IR-6, AC100, Urenco)
- [ ] Export PDF avec mise en page rapport
- [ ] Mode multilingue (FR / EN)
- [ ] Tests unitaires des formules physiques

---

## 🤝 Contribution

Les contributions sont bienvenues !

1. Fork le projet
2. Créer une branche (`git checkout -b feature/amelioration`)
3. Commit (`git commit -m 'Ajout fonctionnalité X'`)
4. Push (`git push origin feature/amelioration`)
5. Ouvrir une Pull Request

---

## 📜 Licence

Distribué sous licence **MIT**. Voir [`LICENSE`](LICENSE) pour plus d'informations.

---

## 🇫🇷 République Française

<div align="center">

**Liberté · Égalité · Fraternité**

[![RF](https://img.shields.io/badge/RF-République%20Française-0055A4?style=for-the-badge)](https://www.gouvernement.fr)

*Dashboard scientifique — Usage éducatif et de recherche*

</div>
