# Nexus-Lang-Transductor-Pro-v2.0.0
✅ Détection sur 24 langues avec stopwords  ✅ Détection sur 30 scripts Unicode  ✅ 10 paires de dictionnaires bidirectionnels  ✅ Cache LRU de 10 000 entrées détection  ✅ Cache persistant traduction  ✅ Extraction HTML par 12 balises structurantes  ✅ 7 endpoints REST  ✅ UI web complète intégrée  ✅ CLI avec --test, --port, --local



# 🧬 Nexus Lang-Transductor Pro

> *Détection et traduction locale. Zéro API externe. Zéro compromis.*

**Version** : 2.0.0 · **Build** : 2026.10.15
**Licence** : MPL 2.0 · **Auteur** : Aissa Mohammedi (DGK)
**Protocole** : Nametron 3 Lara / ZTMESH v1.5.15 · **Port** : 9994

---

## Ce que c'est

Un **détecteur de langue** et **traducteur local** écrit intégralement en Python, fonctionnant **entièrement hors ligne**. Aucune clé API. Aucun appel à Google, DeepL ou OpenAI. Tout se passe sur ta machine.

Interface web intégrée. CLI. API REST. Serveur HTTP autonome.

---

## 💎 Les gems du projet

### 1. Détection multi-couche

**3 méthodes combinées** pour identifier la langue d'un texte :

| Méthode | Ce qu'elle fait |
|---------|-----------------|
| **Unicode Script** | Analyse les plages Unicode (Cyrillique, Arabe, CJK, Devanagari…) — 30 scripts détectables |
| **Stopwords** | Compare aux mots-outils de chaque langue (le, la, the, and, und, y, e…) |
| **N-grams** | Signatures de séquences de caractères propres à chaque langue |

**Scoring pondéré** : stopwords (70%) + n-grams (30%) → score de confiance final.

### 2. Détection par blocs

Un texte mixte (FR + EN + ES) ? Le mode `detect_multi` **découpe automatiquement** et détecte la langue **de chaque bloc**. Résultat :

```json
{
  "primary_language": "fr",
  "is_mixed": true,
  "languages_detected": {"fr": 5, "en": 3, "es": 1}
}
