---
title: 'Lync Server 2013: agregar o quitar un servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Add or remove a Front End Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-01-21_

Al agregar un servidor front-end a un grupo o quitar un servidor front-end de un grupo, debe reiniciar el grupo. Para evitar que se interrumpa el servicio para los usuarios, use el siguiente procedimiento al agregar o quitar un servidor front-end.

<div>


> [!NOTE]  
> Si agrega nuevos servidores al grupo, actualice los nuevos servidores del grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes del grupo.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Para agregar o quitar servidores front-end

1.  Si va a quitar los servidores front-end, primero detenga las conexiones nuevas a esos servidores. Para ello, puede usar el siguiente cmdlet:
    
        Stop-CsWindowsServices -Graceful

2.  Cuando los servidores que se van a quitar no tengan sesiones actuales, detenga los servicios de Lync Server en ellos.

3.  Abra el generador de topologías y agregue o quite los servidores necesarios.

4.  Publique la topología.

5.  Si el grupo ha desaparecido de dos servidores front-end a más de dos o ha ido de más de dos servidores a dos exactamente, debe escribir el siguiente cmdlet:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Si el grupo tiene tres o más servidores, al menos tres de esos servidores deben estar ejecutándose al escribir este cmdlet.

6.  Reinicie todos los servidores front-end del grupo, uno por uno.

</div>

</div>

<span> </span>

</div>

</div>

</div>

