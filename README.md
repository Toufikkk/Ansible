
# Mise en place de l'infrastructure pour Ansible 

## Générer une paire de clefs SSH dans le meme dossier avec

    ssh-keygen -f ansible_rsa

## Re-provisionner si besoin

Avec

    vagrant rsync && vagrant provision

Pour démarrer SSH-AGENT si besoin  ⁼^.^=

    eval $(ssh-agent -s)

Pour charger la clef en mémoire

    ssh-add ~/.ssh/ansible_rsa

## Pour se connecter sur les différentes machines (depuis control)

ssh root@server0
ssh root@server1
ssh root@server2

## Pour valider automatiquement les clefs 

Ajouter la liste des machines dans le fichier liste-pour-ssh

    cat liste-pour-ssh \
      |xargs -iSERVER ssh-keyscan SERVER  >> ~/.ssh/known_hosts 

