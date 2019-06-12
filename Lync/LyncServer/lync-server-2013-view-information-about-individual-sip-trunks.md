---
title: 'Lync Server 2013: ver información sobre los troncos SIP individuales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c7d29c7318c8fb6d1cd08775853eb46b1c898d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Ver información sobre los troncos SIP individuales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Los troncos SIP se usan para conectar Lync Server 2013 voz a través de una red telefónica IP con la red de telefonía pública conmutada. En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal. Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos. Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.

En Lync Server 2013, sin embargo, ahora se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos ya no están en el mismo. A su vez, esto significa que los administradores deben usar el nuevo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.

El cmdlet Get-CsTrunk se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>Para ver información sobre todos los enlaces troncales SIP

  - El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>Para ver información sobre un enlace troncal SIP específico

  - Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Ver información de todos los troncos SIP asignados a un grupo

  - En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

