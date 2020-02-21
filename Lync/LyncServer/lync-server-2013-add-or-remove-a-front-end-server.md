---
title: 'Lync Server 2013: agregar o quitar un servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e358415b086594b67fabdc5ed74706a510e2f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Agregar o quitar un servidor front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-01-21_

Cuando agrega un servidor front-end a un grupo o cuando quita un servidor front-end de un grupo, debe reiniciar el grupo. Para evitar interrupciones del servicio para los usuarios, use el siguiente procedimiento al agregar o quitar un servidor front-end.

<div>


> [!NOTE]  
> Si va a agregar nuevos servidores al grupo, actualice los nuevos servidores de grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes en el grupo.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Para agregar o quitar servidores front-end

1.  Si desea quitar servidores front-end, primero detenga las nuevas conexiones a esos servidores. Para ello, puede usar el siguiente cmdlet:
    
        Stop-CsWindowsServices -Graceful

2.  Cuando los servidores que se quitará no tienen sesiones actuales, detenga los servicios de Lync Server en esos servidores.

3.  Abra el Generador de topologías, y agregue o quite los servidores necesarios.

4.  Publique la topología.

5.  Si el grupo de servidores front-end ha pasado de tener dos servidores front-end a más de dos o ha ido de más de dos servidores a dos exactamente, debe escribir el siguiente cmdlet:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Si el grupo tiene tres o más servidores, debe haber al menos tres de esos servidores en ejecución cuando escriba este cmdlet.

6.  Reinicie todos los servidores front-end del grupo, uno por vez.

</div>

</div>

<span> </span>

</div>

</div>

</div>

