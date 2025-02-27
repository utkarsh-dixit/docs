---
title: Actualizar el sistema operativo
slug: upgrade-os
excerpt: 'Cómo actualizar un sistema operativo al final de su vida útil'
section: Tutoriales
---

> [!primary]
> Esta traducción ha sido generada de forma automática por nuestro partner SYSTRAN. En algunos casos puede contener términos imprecisos, como en las etiquetas de los botones o los detalles técnicos. En caso de duda, le recomendamos que consulte la versión inglesa o francesa de la guía. Si quiere ayudarnos a mejorar esta traducción, por favor, utilice el botón «Contribuir» de esta página.
>

**Última actualización: 09/07/2021**

## Objetivo

Este tutorial explica los pasos a seguir para actualizar un sistema operativo al final de su vida útil a una nueva versión.

> [!alert]
> Aviso: como en el caso de cualquier actualización importante de un sistema operativo, existe el riesgo de avería, pérdida de datos o fallo de la configuración de software.
> Por lo tanto, antes de seguir este tutorial, OVHcloud le recomienda encarecidamente que [guarde su instancia](../guardar_copia_de_seguridad_de_una_instancia) y realice pruebas en profundidad de sus aplicaciones para asegurarse de que funcionan en la nueva versión del sistema operativo.
>

> [!primary]
> Para evitar los problemas anteriores, le recomendamos que instale una nueva instancia con el nuevo sistema operativo al que vaya a realizar la actualización y que luego mire los datos.
> Todavía puede ser necesario analizar las diferencias en su aplicación, pero el sistema operativo probablemente sea más estable.
>

## Requisitos

- Tener un [acceso root al servidor.](../conectarse_como_usuario_root_y_establecer_una_contrasena/)
- Haber realizado [una copia de seguridad de la instancia.](../guardar_copia_de_seguridad_de_una_instancia)

## Procedimiento

### Ubuntu

Antes de actualizar la versión principal del SO, asegúrese de actualizar las versiones más recientes de todos los paquetes instalados en su versión actual:

```sh
$ sudo apt-get update
```

Actualice los paquetes instalados a sus últimas versiones:

```sh
$ sudo apt-get upgrade -y
```

Una vez completada esta operación, realice una *actualización* que permita realizar otras actualizaciones necesarias:

```sh
$ sudo apt-get dist-upgrade -y
```

En ese caso, puede actualizarse la versión principal. Ubuntu proporciona ahora una herramienta llamada *do-release-upgrade* que hace la actualización más segura y fácil. Comience la actualización con el siguiente comando:

```sh
$ sudo do-release-upgrade
```

Siga las instrucciones que se le presenten. En primer lugar, es necesario confirmar que quiere continuar la actualización.

Observaciones:

- La herramienta le puede pedir que reinicie el servidor antes de realizar la actualización. Para ello, escriba "reiniciar" y pulse Entrar.
- Le informaremos de que no es recomendable realizar esta operación por SSH. Como no hay acceso físico al servidor, la conexión por SSH es la principal forma de acceder al servidor.
Ubuntu iniciará un nuevo servicio SSH en otro puerto para que pueda conservar otro acceso en caso de fallo. Además, siempre podrá acceder al servidor a través de la consola si ya no tiene acceso por SSH.
- Es posible que, durante la actualización, deba confirmar la eliminación de los paquetes que ya no estén soportados. Compruebe que esto no tenga ningún impacto en sus aplicaciones antes de continuar.

Una vez completada la actualización, el servidor reiniciará y perderá la conexión hasta que se reinicie.
Unos minutos más tarde, podrá conectarse y ver un mensaje similar al de abajo (la versión será la próxima versión disponible en relación con su versión anterior):

```sh
$ Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 4.15.0-147-generic x86_64)
```

> [!primary]
> Al actualizar el sistema operativo en lugar de reinstalarlo, la nueva versión del SO no se indica en el área de cliente ni en la API de OVHcloud, ni en la API Horizon/OpenStack.
>

Compruebe que sus aplicaciones funcionen según lo previsto. Si necesita ayuda, le recomendamos que [restaure la copia de seguridad](../crear_o_restaurar_un_servidor_virtual_a_partir_de_un_snapshot/) realizada antes de la actualización.

### Fedora

Antes de actualizar la versión principal del SO, asegúrese de actualizar las versiones más recientes de todos los paquetes instalados en su versión actual. Introduzca el siguiente comando:

```sh
$ sudo dnf upgrade --refresh
```

A continuación, reinicie el servidor:

```sh
$ reboot
```

Una vez reiniciado el servidor, instale el paquete de actualización:

```sh
$ sudo dnf install dnf-plugin-system-upgrade
```

Una vez que disponga del paquete necesario, podrá realizar la actualización. Las actualizaciones del sistema solo se admiten oficialmente y se prueban en un máximo de 2 versiones (por ejemplo, de 32 a 34).
En este ejemplo, vamos a pasar de Fedora 32 a 33:

```sh
$ sudo dnf system-upgrade download --releasever=33
$ sudo dnf system-upgrade reboot
```

Una vez que se ha descargado la versión y se ha iniciado el proceso de actualización, el servidor se reinicia para finalizar la actualización.
<br>Puede tardar un tiempo en volver a conectarse al servidor, ya que la actualización lleva tiempo.

Compruebe que sus aplicaciones funcionan según lo previsto. Si necesita ayuda, le recomendamos que [restaure la copia de seguridad](../crear_o_restaurar_un_servidor_virtual_a_partir_de_un_snapshot/) realizada antes de la actualización.

> [!primary]
> Si necesita ayuda, encontrará respuestas en el sitio web [Fedora Docs](https://docs.fedoraproject.org/en-US/quick-docs/dnf-system-upgrade/) {.external}.
>

## Más información

Interactúe con nuestra comunidad de usuarios en <https://community.ovh.com/en/>.
