# desafio-globo
Passo a passo do desafio recebido pela globo.com

Script "Push to Start":
#!/bin/bash

echo "Criando um container LXD para servidor local..."
lxc launch ubuntu:16.04 localserver
