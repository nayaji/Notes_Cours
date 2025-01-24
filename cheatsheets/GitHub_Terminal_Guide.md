
# Guide: Publier un projet sur GitHub uniquement depuis le terminal

## Étape 1 : Initialiser un dépôt Git localement
```bash
git init
```
- **Explication :** Initialise un dépôt Git dans le dossier actuel. Cela crée un sous-dossier `.git` pour suivre les versions des fichiers.

---

## Étape 2 : Configurer vos informations utilisateur (si ce n'est pas déjà fait)
```bash
git config --global user.name "VotreNom"
git config --global user.email "VotreEmail@example.com"
```
- **Explication :** Définit votre nom et votre e-mail pour que Git puisse les associer aux commits que vous allez créer.

---

## Étape 3 : Ajouter les fichiers au suivi
```bash
git add .
```
- **Explication :** Ajoute tous les fichiers du dossier actuel au suivi de Git. Le `.` signifie "tout le contenu".

---

## Étape 4 : Créer un commit
```bash
git commit -m "Initial commit"
```
- **Explication :** Crée un commit (enregistrement) avec un message décrivant les changements, ici "Initial commit".

---

## Étape 5 : Créer un dépôt sur GitHub
- Allez sur [GitHub](https://github.com).
- Cliquez sur le bouton **New Repository**.
- Donnez un nom au projet, laissez-le vide (sans README, .gitignore, etc.).
- Copiez l'URL du dépôt (par exemple : `https://github.com/votre-utilisateur/votre-projet.git`).

---

## Étape 6 : Lier le dépôt local à GitHub
```bash
git remote add origin https://github.com/votre-utilisateur/votre-projet.git
```
- **Explication :** Lien votre dépôt local au dépôt distant sur GitHub. Remplacez l’URL par celle que vous avez copiée.

---

## Étape 7 : Envoyer vos modifications à GitHub
```bash
git branch -M main
```
- **Explication :** Renomme la branche par défaut en `main`, qui est souvent utilisée par GitHub.

```bash
git push -u origin main
```
- **Explication :** Envoie le contenu de la branche `main` au dépôt GitHub distant et établit une connexion par défaut pour les prochains push.

---

## Commandes supplémentaires (si nécessaire) :
### Vérifier l’état du dépôt :
```bash
git status
```
- Montre les fichiers suivis/non suivis ou les modifications à valider.

### Voir les journaux des commits :
```bash
git log
```
- Affiche un historique des commits.

---

## Exemple complet dans l'ordre :
```bash
cd chemin/vers/votre-projet
git init
git config --global user.name "VotreNom"
git config --global user.email "VotreEmail@example.com"
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/votre-utilisateur/votre-projet.git
git branch -M main
git push -u origin main
```
Après cela, votre projet sera disponible sur GitHub 🎉 !
