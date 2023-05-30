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

* Hace falta reiniciar el PC para que salte zsh en lugar de bash al abrir la terminal (Este paso se puede dejar para el final si queremos instalar los plugins)

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

* Configuramos powerlevel10k al gusto (También se puede usar el archivo _.p10k.zsh_ del repositorio)

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

Una vez instalados, escribimos en el fichero _.zshrc_ estos comandos para que aplique los cambios:

```
# Plugins
source ~/.zsh/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
source ~/.zsh/zsh-sudo/sudo.plugin.zsh
source ~/.zsh/zsh-colored-man-pages/colored-man-pages.plugin.zsh
```

### Instalación de lsd y bat

lsd y bat son dos herramientas para que los comandos ls y cat se vean mejor en terminal.

Para instalarlas, vamos a las releases de sus repositorios en github:

* Repositorio de [lsd](https://github.com/lsd-rs/lsd/releases)
* Repositorio de [bat](https://github.com/sharkdp/bat/releases)

De allí descargar el archivo que queramos de sus assets (zip, deb, tar)

O también se pueden descargar así el archivo _.deb_ y ejecutar luego:

```
wget https://github.com/sharkdp/bat/releases/download/v0.23.0/bat_0.23.0_amd64.deb
```

```
wget https://github.com/lsd-rs/lsd/releases/download/0.23.1/lsd_0.23.1_amd64.deb
```

Luego escribimos los _alias_ en _.zshrc_ para que los comandos funcionen:
```
# Manual aliases
alias ll='lsd -lh --group-dirs=first'
alias la='lsd -a --group-dirs=first'
alias l='lsd --group-dirs=first'
alias lla='lsd -lha --group-dirs=first'
alias ls='lsd --group-dirs=first'
alias cat='bat'
```

Ejemplos de ejecución de los comandos:

#### Bat

![ejemplo-ejecucion-bat](/imgs/ejemplo-bat.png)

#### Lsd

![ejemplo-ejecucion-lsd](/imgs/ejemplo-lsd.png)