# Workflow Make.com — Mise à jour registre HSE via Telegram

Automatisation no-code : un message Telegram met à jour un registre Google Sheets et déclenche un email de notification automatique.

**Créé le 17 mars 2026**

## Ce que ça fait

```
Message Telegram
      │
      ▼
Mise à jour Google Sheets
(Registre Infirmerie — feuille 3.1)
      │
      ▼
Email Gmail automatique
"Nouvelle entrée enregistrée — lien vers le registre"
```

## Cas d'usage concret

Dans un contexte HSE, le responsable infirmerie envoie un message Telegram après chaque soin ou incident bénin. Le registre Google Sheets se met à jour automatiquement et le responsable HSE reçoit une notification Gmail avec le lien direct vers le document.

**Résultat : zéro saisie manuelle, traçabilité en temps réel.**

## Stack

- **Make.com** — orchestration no-code
- **Telegram Bot API** — déclencheur (webhook)
- **Google Sheets** — stockage et mise à jour des données
- **Gmail** — notification automatique

## Modules Make.com

| # | Module | Rôle |
|---|--------|------|
| 1 | `telegram:WatchUpdates` | Écoute les messages entrants via webhook |
| 2 | `util:GetVariable2` | Extrait le texte du message |
| 3 | `google-sheets:updateRow` | Met à jour la ligne dans le registre infirmerie |
| 4 | `google-email:sendAnEmail` | Envoie la notification Gmail |

## Utiliser ce blueprint

1. Importer le fichier `blueprint.json` dans Make.com
2. Reconnecter vos propres credentials :
   - Telegram Bot Token
   - Compte Google Sheets
   - Compte Gmail
3. Pointer vers votre propre fichier Google Sheets
4. Activer le scénario

## Structure Google Sheets attendue

Le workflow cible une feuille nommée `3.1_Registre_Infirmerie` avec des colonnes A à J correspondant aux champs du registre infirmerie HSE standard.

## Auteur

Mahmoudou Diallo · [LinkedIn](https://www.linkedin.com/in/mahmoudou-diallo-qhse) · [matzodiallo02@gmail.com](mailto:matzodiallo02@gmail.com)
