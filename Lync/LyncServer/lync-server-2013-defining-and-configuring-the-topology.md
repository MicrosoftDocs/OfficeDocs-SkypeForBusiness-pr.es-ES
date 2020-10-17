---
title: 'Lync Server 2013: definir y configurar la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86f98c5961385bd2f99c0698af1b5f422abe4c60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504547"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definición y configuración de la topología en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-14_

Puede definir y configurar la topología con el generador de topologías. El generador de topologías no requiere que usted sea miembro del grupo de administradores locales o de un grupo de dominios privilegiado (como administradores del dominio). Puede definir su topología como usuario estándar. Cuando inicie el Generador de topologías, en el primer uso y en los usos posteriores se le solicitará la ubicación en la que desea que el Generador de topologías cargue el documento de configuración actual. Las opciones son las siguientes:

  - Descargar una topología desde una implementación existente

  - Abrir una topología desde un archivo local

  - Nueva topología

Si ya ha definido una topología y ha establecido el almacén de administración central, debe elegir descargar una topología de una implementación existente. El Generador de topologías leerá la base de datos y recuperará la definición actual. Si ya tiene un almacén de administración central, elija esta opción siempre.

Si no ha establecido un almacén de administración central y desea editar una configuración previamente guardada, debe optar por abrir la topología desde un archivo local. El archivo que abrirá será el archivo de configuración que se guardó en una sesión anterior. Puede usar esta opción para editar la topología guardada anteriormente.

<div>


> [!WARNING]  
> Si ya tiene una topología publicada, no deberá cargar un archivo de configuración local. Deberá descargar la topología desde una implementación existente.



</div>

Elija crear una nueva topología si desea crear una nueva configuración del generador de topologías. Un diseño guardado anteriormente no se sobrescribe a no ser que elija guardarlo como el mismo archivo creado en una sesión de diseño anterior.

En cada una de estas opciones, se le pedirá que indique una ubicación para almacenar el archivo de configuración del generador de topologías. La ubicación del archivo podría ser una ubicación local, una ubicación compartida en un recurso compartido de archivos establecido o un medio extraíble.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Definir y configurar una topología en el generador de topologías para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Implementación de grupos de servidores front-end emparejados para la recuperación ante desastres en Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Implementación de la creación de reflejos de SQL para la alta disponibilidad del servidor back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Seleccione el servidor de administración central en Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

