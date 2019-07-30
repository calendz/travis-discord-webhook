<p align="center"><a href="https://calendz.app/" target="_blank" rel="noopener noreferrer"><img width="100" src="https://avatars3.githubusercontent.com/u/51510476?s=400&u=e110cf083bbc29eab84d4dceb85c94d7a87882db&v=4" alt="calendz's logo"></a></p>
  
<p align="center">
  <a href="https://discord.gg/ZXnG2HC"><img src="https://img.shields.io/badge/join-our%20discord-7289da.svg" alt="Support"></a>
</p>

<h2 align="center">TRAVIS-DISCORD-WEBHOOK</h2>

---

## Introduction

Simple script shell postant les résultats des builds des différents éléments de [calendz]() dans le salon #build-status du [discord officiel de calendz](https://discord.gg/ZXnG2HC).

## Mise en place

La mise en place est simple et rapide :
* Créer un webhook sur le serveur discord.
* Créer une variable `DISCORD_WEBHOOK_URL` sur Travis aillant pour valeur l'adresse du webhook créé sur discord.

  ![img](https://i.imgur.com/SXcLND7.png)

* Rajouter la configuration suivante dans le fichier `.travis.yml` :

  ```yml
  after_success:
    - wget https://raw.githubusercontent.com/DiscordHooks/travis-ci-discord-webhook/master/send.sh
    - chmod +x send.sh
    - ./send.sh success $WEBHOOK_URL
  after_failure:
    - wget https://raw.githubusercontent.com/DiscordHooks/travis-ci-discord-webhook/master/send.sh
    - chmod +x send.sh
    - ./send.sh failure $WEBHOOK_URL
  ```

## Résultat

<p align="center">
  <img src="https://i.imgur.com/JwKLd4k.png">
  <br>
</p>

---

*Forked from [DiscordHooks/travis-ci-discord-webhook](https://github.com/DiscordHooks/travis-ci-discord-webhook)*