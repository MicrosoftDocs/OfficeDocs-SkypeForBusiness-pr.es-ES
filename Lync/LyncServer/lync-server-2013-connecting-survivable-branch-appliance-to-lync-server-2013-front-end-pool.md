---
title: Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051f4c0837b654f389841dc94275577a51f5b904
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end, que sirve como registrador de copias de seguridad para SBA. Cuando se actualiza el grupo de servidores front-end a Lync Server 2013, SBA debe desasociarse del grupo de servidores front-end mientras se actualiza el grupo de servidores front-end. Una vez actualizado el grupo de servidores front-end, SBA puede volver a asociarse con el grupo de servidores front-end. Esto implica eliminar la SBA de la topología en Topology Builder y luego agregar nuevamente la SBA a Topology Builder. Los usuarios hospedados en SBA deben moverse a otro grupo de servidores front-end antes de quitar SBA de la topología. Luego de que la SBA se agrega nuevamente a la topología, esos usuarios pueden trasladarse de vuelta a la SBA.

Estos pasos se sintetizan a continuación:

1.  Mueva los usuarios de sucursal alojados en SBA a otro grupo de servidores front-end.

2.  Quite SBA de la topología para desasociar el grupo de servidores front-end existente como registrador de reserva.

3.  Actualice el grupo de servidores front-end a Microsoft Lync Server 2013.

4.  Agregar SBA de vuelta en su topología.

5.  Asocie el nuevo grupo de servidores front-end a SBA como registrador de reserva.

6.  Mover los usuarios de la sucursal de vuelta a la SBA.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Agregar un sitio de sucursal de aplicación de sucursal con funciones de supervivencia de Lync Server 2013 a la topología](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Agregar un sitio de sucursal de aplicación de sucursal con funciones de supervivencia de Lync Server 2010 a la topología](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

