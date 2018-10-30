---
title: 'Lync Server 2013: Definición y configuración de la topología'
TOCTitle: Definición y configuración de la topología
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48275265
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definición y configuración de la topología en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-14_

La definición y configuración de la topología mediante Generador de topologías. Generador de topologías no precisa que sea miembro del grupo de administradores local ni de un grupo de dominio con privilegios (como, por ejemplo, Admins. del dominio). Puede definir la topología como un usuario estándar. Cuando inicie Generador de topologías por primera vez y en sesiones de edición posteriores, se le preguntará la ubicación en la que desea que Generador de topologías cargue el documento de configuración actual. Las opciones son:

  - Descargar una topología desde una implementación existente

  - Abrir una topología desde un archivo local

  - Nueva topología

Si ya ha definido una topología y ha establecido el Almacén de administración central, debería elegir la descarga de una topología desde una implementación existente. Generador de topologías leerá la base de datos y recuperará la definición actual. Si tiene un Almacén de administración central existente, siempre deberá seleccionar esta opción.

Si no ha establecido un Almacén de administración central y desea editar una configuración guardada anteriormente, deberá seleccionar la apertura de la topología desde un archivo local. El archivo que abrirá será el archivo de configuración que se guardó en una sesión anterior. Puede usar esta opción para editar la topología guardada anteriormente.

> [!WARNING]  
> Si ya tiene una topología publicada, no deberá cargar un archivo de configuración local. Deberá descargar la topología desde una implementación existente.



Si desea crear una nueva configuración de Generador de topologías, seleccione crear una nueva topología. Un diseño guardado anteriormente no se sobrescribe a no ser que elija guardarlo como el mismo archivo creado en una sesión de diseño anterior.

En cada una de esta opciones se le pedirá una ubicación para guardar el archivo de configuración de Generador de topologías. La ubicación del archivo podría ser una ubicación local, una ubicación compartida en un recurso compartido de archivos establecido o un medio extraíble.

## En esta sección

  - [Definir y configurar una topología en Topology Builder para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Implementación de grupos front-end emparejados para recuperación ante desastres en Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Seleccionar el servidor de administración central en Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

