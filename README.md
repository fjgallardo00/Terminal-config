# Configuracion de mi terminal en zsh

### Instalación de zsh

* Comando para instalar la terminal de zsh

```
sudo apt-get install zsh
```

* Con estos comandos se establece la terminal de zsh como predeterminada

```
chsh -s /bin/zsh
chsh -s $(which zsh)
```

* Hace falta reiniciar el PC para que salte zsh en lugar de bash al abrir la terminal

* Si se quiere volver a poner bash como terminal por defecto ejecutar este comando:

```
chsh -s $(which bash)
```

### Instalación de powerlevel10k y plugins

* Instalamos primero powerlevel10k para que la terminal se vea bonita

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```

* Configuramos powerlevel10k al gusto

* A continuación instalamos los plugins:

    - zsh-autosuggestions
    - zsh-syntax
    - zsh-sudo
    - zsh-colored-man

```
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
```

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.zsh/zsh-syntax-highlighting
```

```
git clone https://github.com/hcgraf/zsh-sudo.git ~/.zsh/zsh-sudo
```

```
git clone https://github.com/ael-code/zsh-colored-man-pages.git ~/.zsh/zsh-colored-man-pages
```

### Instalación de lsd y bat

lsd y bat son dos herramientas para que los comandos ls y cat se vean mejor en terminal.

Para instalarlas, vamos a las releases de sus repositorios en github:

* Repositorio de [lsd](https://github.com/lsd-rs/lsd/releases)
* Repositorio de [bat](https://github.com/sharkdp/bat/releases)

De allí descargar el archivo que queramos de sus assets (zip, deb, tar)

O también se pueden descargar así y ejecutar luego:

```
wget https://github.com/sharkdp/bat/releases/download/v0.23.0/bat_0.23.0_amd64.deb
```

```
wget https://github.com/lsd-rs/lsd/releases/download/0.23.1/lsd_0.23.1_amd64.deb
```

Ejemplos de ejecución de los comandos:

#### Bat

![ejemplo-ejecucion-bat](/imgs/ejemplo-bat.png)

#### Lsd

![ejemplo-ejecucion-lsd](/imgs/ejemplo-lsd.png)