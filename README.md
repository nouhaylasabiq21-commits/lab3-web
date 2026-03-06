"# lab3-web" 
# Lab 3 – Android Formulaire avec Intent

## 📱 Description

Cette application Android simple permet à l'utilisateur de remplir un **formulaire** avec ses informations personnelles, puis d'afficher un **écran récapitulatif** contenant les données saisies.

L'application utilise **deux Activities** et communique entre elles grâce aux **Intents**.

---

## 🎯 Objectifs du Lab

* Créer une interface utilisateur avec **XML**
* Utiliser des **EditText** pour la saisie des données
* Implémenter un **Button** pour déclencher une action
* Naviguer entre deux écrans avec **Intent**
* Passer des données entre Activities avec **putExtra()**
* Récupérer les données avec **getStringExtra()**

---

## 🧱 Structure du Projet

```
lab3_web
│
├── MainActivity.java
├── Screen2Activity.java
│
├── res
│   └── layout
│        ├── activity_main.xml
│        └── activity_screen2.xml
│
└── AndroidManifest.xml
```

---

## 🖥️ Écran 1 : Formulaire

Fichier :

```
activity_main.xml
```

Contient les champs :

* Nom & Prénom
* Email
* Téléphone
* Adresse
* Ville

Et un bouton :

```
Envoyer
```
* <img width="236" height="434" alt="image" src="https://github.com/user-attachments/assets/5e77c631-54f8-46bc-aaad-f811f3242e13" />
### Fonctionnement

L'utilisateur saisit les informations puis clique sur **Envoyer**.

Le bouton déclenche un **Intent** qui ouvre `Screen2Activity` et envoie les données.

---

## 📤 Envoi des données (MainActivity)


```java
Intent intent = new Intent(MainActivity.this, Screen2Activity.class);

intent.putExtra("nom", sNom);
intent.putExtra("email", sEmail);
intent.putExtra("phone", sPhone);
intent.putExtra("adresse", sAdresse);
intent.putExtra("ville", sVille);

startActivity(intent);
```

---

## 🖥️ Écran 2 : Récapitulatif

Fichier :

```
activity_screen2.xml
```

Cet écran contient :

* Un titre **Screen2**
* Un **TextView** pour afficher les informations
* Un bouton **Retour**
* 

<img width="193" height="391" alt="image" src="https://github.com/user-attachments/assets/b02f7f34-f886-4045-a382-ccda32196eb8" />

---

## 📥 Réception des données (Screen2Activity)

```java
Intent intent = getIntent();

String nom = intent.getStringExtra("nom");
String email = intent.getStringExtra("email");
String phone = intent.getStringExtra("phone");
String adresse = intent.getStringExtra("adresse");
String ville = intent.getStringExtra("ville");
```

Les données sont ensuite affichées dans un **TextView**.

