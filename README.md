# desafio-globo
#Passo a passo do desafio recebido pela globo.com

#Script "Push to Start":

#!/bin/bash

echo "Criando um container LXD para servidor local..."
lxc launch ubuntu:16.04 localserver
apt-get update

echo "Configurando servidor local..."
echo "Instalando unzip..."
lxc exec localserver -- apt-get install unzip
echo "Instalando openjdk..."
lxc exec localserver -- apt-get install openjdk-8-jre -y
echo "Instalando glassfish..."
lxc exec localserver -- wget http://download.oracle.com/glassfish/5.0/release/glassfish-5.0.zip
lxc exec localserver -- unzip glassfish-5.0.zip
lxc exec localserver -- glassfish5/bin/asadmin start-domain
