---
layout: single
toc: true
title: "Instalar Gitea en Zimaboard"
---


## ¿Qué es Gitea?
Gitea es un software de código abierto que permite alojar código con control de versión de versiones, de manera similar a como se lleva a cabo en GitHub. Debido a que Gitea es más ligero, este se puede alojar en ordenadores monoplaca como Raspberry Pi o Zimaboard. En este caso, alojaremos Gitea en una Zimaboard, que es un ordenador monoplaca que utiliza una CPU de arquitectura amd64 en vez de arm64.

## Instalar Gitea
La instalación de Gitea es muy sencilla. Se lleva a cabo a través de la tienda de aplicaciones de la ZimaBoard. Los valores de los diferentes campos no es necesario tocarlos. Si decidieras cambiar el puerto SSH, tienes que quedarte con el nuevo valor que le asignes, ya que se tendrá que utilizar de cara a la conexión por SSH a la placa. Tras instalar la aplicación, puedes entrar en ella clicando el icono de la misma. Si todo ha ido bien, accederéis a la página de inicio de Gitea (véase la Figura 1), donde podréis crear vuestra cuenta o iniciar sesión.

<figure>
    <img src="/assets/images/gitea/gitea-home-page.png"
         alt="Pagina de inicio de Gitea">
    <figcaption>Figura 1. Página de inicio de Gitea.</figcaption>
</figure>


## Configuración de la clave SSH
Al igual que en GitHub, en Gitea se puede (y se debe) configurar una clave SSH de tal manera que no haga falta escribir la contraseña cada vez que hacemos un `git push`. No obstante, cuando se configura dicha clave, es posible que nos siga pidiendo la contraseña. Esto se debe a que al instalar Gitea como un contenedor, el puerto 22 correspondiente a SSH lo asignamos a un porto diferente del host (por defecto es el puerto 222). Por lo tanto, hay que indicar dicho cambio a nuestra máquina local para que se conecte a través del puerto correcto. Existen tres métodos diferentes.

### Modificar el fichero de configuración de git del repositorio
La primera solución es añadir la opción `sshcommand = ssh -p <puerto-ssh-host> -i <ruta-clave-privada>` dentro de la sección `[core]` del fichero `.git/config` que se encuentra en la raíz del repositorio que quieres subir a Gitea. Un ejemplo de dicho fichero sería el siguiente:

```
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
    sshcommand = sshcommand = ssh -p <puerto-ssh-host> -i <ruta-clave-privada>
[remote "origin"]
	url = <url-repositorio-remoto>
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "main"]
	remote = origin
	merge = refs/heads/main
```

El problema de esta solución es que sólo vale para el repositorio cuyo fichero de configuración de git modifiquemos.

### Modificar el puerto por defecto a nivel global
Si se quiere modificar dicha opción a nivel global, habría que ejecutar el siguiente commando: `git config --global core.sshCommand "ssh -p <puerto-ssh-host> -i <ruta-clave-privada>"`. De esta manera, se modifica el fichero de configuración global de git para el usuario. No obstante, puede que queramos tener algunos repositorios en GitHub o GitLab, que utilizan el puerto 22 para SSH. En este caso, lo que imagino que pasaría (no lo he probado, no obstante) es que al sincronizar los cambios con GitHub, nos pida la contraseña. Por eso, lo mejor sería llevar a cabo la tercera solución.

### Modificar el fichero de configuración de SSH
Dentro del fichero de configuración de SSH (`~/.ssh/config`) se pueden definir diferentes hosts con diferentes características. Esto es muy útil si solemos acceder con frecuencia a un ordenador por SSH y no queremos estar tecleando el usuario y la dirección IP constantemente. Además, en este fichero podemos cambiar opciones de configuración para los diferentes ordenadores remotos que tengamos definidos en él. Por ejemplo, en mi caso, el fichero `~/.ssh/config` contiene lo siguiente:

```
# Host-specific settings
Host casaos.local
  # Ajustes personalizados para el host casaos.local
  HostName casaos.local
  Port 222
  User casaos 
  IdentityFile ~/.ssh/id_rsa
```

De este modo, cada vez que sincronice el repositorio con el repositorio remoto localizado en casaos.local, se usará el puerto 222 en vez del 22. Un detalle importante a mencionar en este punto es que esta sección definida en el fichero, no nos serviría para acceder a la ZimaBoard por SSH, ya que para eso se utilizaría el puerto 22 y la clave SSH que se haya usado para tal efecto.

## Conclusiones
Esta entrada del blog no detalla la instalación de Gitea a través de contenedores. Está destinada a ofrecer diferentes soluciones al problema de la generación de claves SSH que me ocurrió a mi en el momento de instalarlo. Asimismo, no soy experto en el tema, así que si he metido la pata en algún detalle técnico, perdón.