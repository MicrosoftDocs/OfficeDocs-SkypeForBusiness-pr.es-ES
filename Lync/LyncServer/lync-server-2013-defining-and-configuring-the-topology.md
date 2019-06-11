---
title: 'Lync Server 2013: Definición y configuración de la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660ac75e325e5737ceb5df59e9463c88ef1c077
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definición y configuración de la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-14_

Defina y configure su topología con el generador de topologías. El generador de topología no requiere que usted sea miembro del grupo de administradores locales o de un grupo de dominios privilegiado (como administradores de dominio). Puede definir su topología como usuario estándar. Al iniciar el generador de topología en el primer uso y en sesiones de edición posteriores, se le pedirá la ubicación en la que desea que el generador de topología cargue el documento de configuración actual. Las opciones son las siguientes:

  - Descargar una topología desde una implementación existente

  - Abrir topología desde un archivo local

  - Nueva topología

Si ya ha definido una topología y ha establecido el almacén de administración central, debe elegir descargar una topología de una implementación existente. El generador de topología leerá la base de datos y recuperará la definición actual. Si ya tiene un almacén de administración central, siempre debe elegir esta opción.

Si no ha establecido un almacén de administración central y desea editar una configuración guardada anteriormente, debe optar por abrir la topología desde un archivo local. El archivo que se abrirá sería el archivo de configuración que se guardó en una sesión anterior. Puede usar esta opción para editar la topología guardada anteriormente.

<div>


> [!WARNING]  
> Si ya tiene una topología publicada, no debe cargar un archivo de configuración local. Debe elegir descargar la topología de una implementación existente.



</div>

Elija esta opción para crear una nueva topología, si desea crear una configuración de topología nueva. Un diseño guardado anteriormente no se sobrescribe a menos que decida guardarlo como el mismo archivo que ha creado en una sesión de diseño anterior.

En cada una de estas opciones, se le pedirá una ubicación para almacenar el archivo de configuración de Topology Builder. La ubicación del archivo puede ser una ubicación local, una ubicación compartida en un recurso compartido de archivos o un medio extraíble.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Definir y configurar una topología en Topology Builder para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Implementación de grupos front-end emparejados para recuperación ante desastres en Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Seleccionar el servidor de administración central en Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

