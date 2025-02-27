---
title: 'Restaurar e importar una base de datos en su servidor de bases de datos'
slug: restaurar-importar-base-de-datos
excerpt: 'Cómo restaurar e importar la base de datos'
section: 'SQL Privado'
order: 5
---

> [!primary]
> Esta traducción ha sido generada de forma automática por nuestro partner SYSTRAN. En algunos casos puede contener términos imprecisos, como en las etiquetas de los botones o los detalles técnicos. En caso de duda, le recomendamos que consulte la versión inglesa o francesa de la guía. Si quiere ayudarnos a mejorar esta traducción, por favor, utilice el botón «Contribuir» de esta página.
>

**Última actualización: 11/06/2020**

## Objetivo

Si se produce un error en la base de datos, es necesario que pueda restaurar una copia de seguridad o importar una base de datos local. 

**Esta guía explica cómo restaurar e importar la base de datos en un servidor de bases de datos.**

## Requisitos

- Tener contratado un plan de [hosting SQL Privado](https://www.ovhcloud.com/es/web-hosting/options/start-sql/) o [Cloud Databases](https://www.ovh.es/cloud-databases/).
- Haber iniciado sesión en el [área de cliente de OVHcloud](https://ca.ovh.com/auth/?action=gotomanager&from=https://www.ovh.com/world/&ovhSubsidiary=ws).

## Procedimiento

> [!primary]
>
> Tenga en cuenta que los productos [SQL Privado](https://www.ovhcloud.com/es/web-hosting/options/start-sql/) y [Cloud Databases](https://www.ovh.es/cloud-databases/) no dan acceso al host, sino a las bases de datos alojadas en este, por lo que no hay accesos super usuario "root". Los comandos SQL genéricos funcionan con normalidad y los programas de tipo HeidiSQL, SQuirreL SQL o Adminer son totalmente compatibles.
> 

### Restaurar e importar una base de datos desde el área de clientes

Acceda al [área de cliente de OVHcloud](https://ca.ovh.com/auth/?action=gotomanager&from=https://www.ovh.com/world/&ovhSubsidiary=ws). Haga clic en la pestaña `Web` y seleccione `Base de datos`{.action} en el panel izquierdo. Seleccione el nombre del servidor de bases de datos. Acceda a la pestaña `Bases de datos`.

En la columna **"Copias de seguridad"**, la cifra corresponde al número de copias de seguridad disponibles para la base de datos.

#### 1\. Restaurar una copia de seguridad existente

Haga clic en el botón `...`{.action} a la derecha de la base de datos y, seguidamente, en `Mostrar las copias de seguridad`{.action}.

Se mostrará una lista de las copias de seguridad disponibles. Haga clic en el botón `...`{.action} a la derecha de la copia de seguridad seleccionada y, seguidamente, en `Restaurar la copia de seguridad`{.action}.

![private-sql](images/private-sql-restore01.png){.thumbnail}

> [!warning]
>
> La restauración implica la sustitución del contenido de la base de datos tras la restauración.
> Si no está seguro de lo que está haciendo, le recomendamos que realice una copia de seguridad antes.
> 

#### 2\. Importar una copia de seguridad local

Haga clic en el botón `...`{.action} a la derecha de la base de datos y seleccione `Importar archivo`{.action}.

![private-sql](images/private-sql-import01.png){.thumbnail}

Tiene dos posibilidades:

##### Importar un nuevo archivo

Haga clic en **"Importar un nuevo archivo"** y, seguidamente, en `Siguiente`{.action}.

Escriba un nombre para el archivo importado, haga clic en `Navegar`{.action} para seleccionarlo, luego `Enviar`{.action} y luego en `Siguiente`{.action}.

> [!warning]
>
> El archivo debe tener el formato ".gz".
> 

![private-sql](images/private-sql-import02.png){.thumbnail}

Marque **"Vaciar la base de datos actual"** antes de la importación y **"Enviar un email al final de la importación"** para estar informado del fin de la operación en la dirección de correo electrónico de referencia de su cuenta de OVHcloud y haga clic en `Aceptar`{.action}.

##### Utilizar un archivo existente

Si ya había importado un archivo antes, puede seleccionar la opción **"Importar un archivo existente"**.

Seleccione el archivo en el menú desplegable y haga clic en `Siguiente`{.action}.

![private-sql](images/private-sql-import03.png){.thumbnail}

Marque **"Vaciar la base de datos actual"** antes de la importación y **"Enviar un email al final de la importación"** para estar informado del fin de la operación en la dirección de correo electrónico de referencia de su cuenta de OVHcloud y haga clic en `Aceptar`{.action}.

### Importación de bases de datos MySQL o MariaDB fuera del área de cliente

En algunos casos, la RAM disponible en el servidor de bases de datos puede no permitir la importación deseada. En ese caso, le recomendamos que utilice la herramienta OVHcloud en el área de cliente. Consulte la sección ["Restaurar e importar una base de datos desde el área de cliente"](./#restaurar-e-importar-una-base-de-datos-desde-el-area-de-cliente) de esta guía.


#### Importar una base MySQL o MariaDB desde phpMyAdmin

Para importar su base de datos directamente desde phpMyAdmin, es necesario conectarse a ella previamente. Para ello, puede utilizar el apartado ["Conectarse a una base de datos MySQL o MariaDB"](../coneccion-base-de-datos-servidor-bdd).

Una vez conectado a phpMyAdmin, seleccione la base de datos haciendo clic en su nombre.

A continuación, abra la pestaña `Importar`{.action}.

Seleccione el archivo de backup haciendo clic en `Navegar`{.action} (atención: el archivo no puede superar los 100 MB).

> [!primary]
>
> Le recomendamos que fraccione su base de datos en varios archivos cuando supere los 100 MB y realice varias importaciones desde phpMyAdmin.<br>
> La importación de archivos que superen los 100 MB puede realizarse desde el área de cliente siguiendo el paso ["Guardar, restaurar e importar una base de datos desde el área de cliente".](./#restaurar-e-importar-una-base-de-datos-desde-el-area-de-clientes) 


Deje las opciones predeterminadas y haga clic en `Ejecutar`{.action} para iniciar la importación.

![private-sql](images/private-sql-import04.png){.thumbnail}

#### Importar una base de datos MySQL o MariaDB en línea de comandos

Esta operación solo es posible por [SSH](../web_hosting_ssh_en_alojamiento_compartido/) desde un alojamiento compartido de OVHcloud.

```bash
cat nombre_de_la_base.sql | mysql —host=servidor —user=usuario —port=puerto —contraseña=contraseña nombre_de_la_BD
```
#### Importar una base de datos MySQL o MariaDB desde un archivo PHP

```php
1. <?php
2. echo "La base de datos se está restaurando.......<br>";
3. system("cat nombre_de_la_base.sql | mysql —host=servidor —user=usuario —port=puerto —password=contraseña nombre_de_la_BD");
4. echo "Ya se acabó. Su base de datos está instalada en este alojamiento".
5. ?>
```

> [!warning]
>
> - Para evitar que alguien acceda a este archivo, que contiene datos sensibles, consulte la guía Proteger el acceso a él: [Uso de .htaccess para proteger con contraseña un directorio de su sitio web](https://docs.ovh.com/us/es/hosting/compartido-htaccess-como-proteger-el-acceso-a-un-directorio-por-autenticacion/)
> - Esta acción solo es posible desde un alojamiento de OVHcloud compartido.
>

### importación de bases de datos PostgreSQL fuera del área de cliente

En algunos casos, la RAM disponible en el servidor de bases de datos puede no permitir la importación deseada. En ese caso, le recomendamos que utilice la herramienta OVHcloud en el área de cliente. Consulte la sección ["Restaurar e importar una base de datos desde el área de cliente"](./#restaurar-e-importar-una-base-de-datos-desde-el-area-de-clientes) de esta guía.

#### Importar una base de datos PostgreSQL en línea de comandos

Esta operación solo es posible por [SSH](../web_hosting_ssh_en_alojamiento_compartido/) desde un alojamiento compartido de OVHcloud en versión estable o superior.

```bash
psql —host=servidor —port=puerto —user=usuario —password=contraseña nombre_de_la_BD < nombre_de_la_BD.sql
```

#### Importar una base de datos PostgreSQL desde un archivo PHP

```php
1. <?php
2. echo "La base de datos se está restaurando.......<br>";
3. system("PGPASSWORD=contraseña psql —host=servidor —port=puerto —user=usuario —password=contraseña nombre_de_la_BD < nombre_de_la_BD.sql");
4. echo "Ya se acabó. Su base de datos está instalada en este alojamiento".
5. ?>
```

> [!warning]
>
> - Para evitar que alguien acceda a este archivo con datos sensibles, le recomendamos que proteja el acceso a él en la guía [Uso de .htaccess para proteger con contraseña un directorio de su sitio web](https://docs.ovh.com/us/es/hosting/compartido-htaccess-como-proteger-el-acceso-a-un-directorio-por-autenticacion/).
> - Esta acción solo es posible desde un alojamiento de OVHcloud compartido.
>

## Más información

Interactúe con nuestra comunidad de usuarios en <https://community.ovh.com/en/>.