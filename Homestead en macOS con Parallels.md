# Homestead en macOS con Parallels

## Instalación de Vagrant

Ingresar a https://www.vagrantup.com/ y descargar la ultima version para macOS

### Para verificar la instalacion de vagrant

```shell
$ vagrant -v
Vagrant 2.2.5
$
```

## Instalación de Homestead con Parallels

Clonar el homestead desde su repositorio a la maquina anfitriona.

```shell
$ git clone https://github.com/laravel/homestead.git ~/Homestead
$ cd ~/Homestead
```

### Cambiar rama `release`

```shell
$ git checkout release
```

### Inicializar Homestead

```shell
$ chmod +x init.sh
$ ./init.sh
```

### Configurar el `Homestead.yaml` para trabajan con Parallels

Modificar el `provider` dentro del archivo `Homestead.yaml`.

```yaml
provider: parallels
```

### Instalar plugin para Parallels

```shell
$ sudo vagrant plugin install vagrant-parallels
```

### Instalar Homestead

```shell
$ bash init.sh
```

### Generar una `SSH KEY` (solo en caso de que no exista)

```shell
$ ssh-keygen -t rsa
```

### Levantar máquina virtual de homestead

```shell
$ vagrant up
```

### Ingresar a la máquina por SSH

```shell
$ vagrant ssh
```

### Recargar configuración de máquina virtual de homestead

```shell
$ vagrant reload --provision
```