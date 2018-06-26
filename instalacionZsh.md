# Instalación ZSH y Oh-my-zsh

## CentOS

`$ sudo yum update && sudo yum -y install zsh`

## Ubuntu/Debian

`$ sudo apt install zsh`

## Configuramos zsh como shell por defecto

Ejecutamos chsh para cambiar shell, [usuario] es el nombre de usuario al que se le va a cambiar la shell.

`# chsh -s $(which zsh) [usuario]`

Después de este paso, es necesario cerrar sesión o reiniciar para que el cambio tenga efecto.

## Instalación de oh-my-zsh

Se puede utilizas curl o wget

### curl

`$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

### wget

`$ sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`

## Powerline Fonts

Las fuentes powerline son necesarias para algunos temas de oh-myzsh

### Ubuntu/Debian

`$ sudo apt-get install fonts-powerline`


### Otras distribuciones

```
$ git clone https://github.com/powerline/fonts.git --depth=1

$ cd fonts
$ ./install.sh

$ cd ..
$ rm -rf fonts
```

## Configuración zsh y oh-my-zsh

zsh se configura mediante el archivo `.zshrc` que se encuentra en el directorio home del usuario, es decir, en `~/.zshrc` este archivo también incluye las configuraciones de oh-my-zsh.


oh-my-zsh incuye un template de configuración que copiaremos para empezar a configurarlo.

```
$ cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
$ source ~/.zshrc
```

Ahora para personalizar el tema de la shell, editamos la linea 10 del archivo `.zshrc` y cambiamos la variable `ZSH_THEME='nombre-del-tema'` ejecutando `$ ls -a ~/.oh-my-zsh/themes/`encontrarás todos los temas disponibles, también hay temas extras que requieren otros pasos para su instalación.

- [Temas de oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)
- [Temas externos de oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/External-themes)

Oh-my-zsh también nos permite utilizar plugins que harán que el uso de la shell sea mas eficiente, ya sea con `aliases` o herramientas especiales.

Para agregar plugins, también se realiza editando el archivo de configuración `.zshrc`

```
plugins=(
  git
  bundler
  dotenv
  osx
  rake
  rbenv
  ruby
)
```

Antes de agregar un plugin, les recomiendo leer la documentación para saber la utilidad del mismo.

- [Plugins oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins)

Plugins recomendados
- common-aliasses
- colored-man-pages
- colorize

Plugins externos recomendados
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)
- [zsh-completions](https://github.com/zsh-users/zsh-completions)


## Terminator otro emulador de terminal

### Ubuntu/Debian
`$ sudo apt-get install terminator`

### CentOS
`$ yum install -y epel-release && yum install -y terminator`