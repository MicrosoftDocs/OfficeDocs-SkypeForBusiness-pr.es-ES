---
title: Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end, que sirve como registrador de copias de seguridad de la SBA. Cuando se actualiza el grupo de servidores front-end a Lync Server 2013, SBA debe estar desvinculada del grupo de servidores front-end mientras se actualiza el grupo de servidores front-end. Una vez actualizado el grupo de servidores front-end, SBA puede reasociarse con el grupo de servidores front-end. Esto implica eliminar la SBA de la topología en el generador de topología y, a continuación, agregar la SBA de nuevo al generador de topología. Los usuarios alojados en SBA deben moverse a otro grupo de servidores front end antes de quitar SBA de la topología. Después de agregar SBA a la topología, esos usuarios pueden devolverse a la SBA.

Estos pasos se resumen a continuación:

1.  Mueva los usuarios alojados en SBA a otro grupo de servidores front-end.

2.  Quite SBA de su topología para desvincular el grupo de servidores front-end existente como registrador de la copia de seguridad.

3.  Actualice el grupo de servidores front-end a Microsoft Lync Server 2013.

4.  Agregue SBA a su topología.

5.  Asocie el nuevo grupo de servidores front-end a SBA como registrador de copias de seguridad.

6.  Mueva los usuarios de la sucursal de nuevo a SBA.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia Lync Server 2010 a la topología](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

