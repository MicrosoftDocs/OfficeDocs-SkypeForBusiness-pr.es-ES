---
title: 'Lync Server 2013: configuración del enrutamiento basado en ubicación para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657978ee622713ffd830d4aeb92a05d949287568
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuración del enrutamiento basado en ubicación para conferencias de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-11_

La aplicación de conferencia de enrutamiento basada en la ubicación se basa en la configuración del enrutamiento basado en la ubicación 2013 de Lync Server. Las siguientes son las opciones de configuración principales:

  - La ubicación de los participantes que se unen a una reunión se determina a partir de su sitio de red. Para aplicar el enrutamiento basado en la ubicación, se debe definir un sitio de red y sus subredes de red asociadas.

  - Para aplicar el enrutamiento basado en la ubicación de las reuniones, los participantes de Lync deben estar habilitados para el enrutamiento basado en la ubicación.

  - Para aplicar el enrutamiento basado en la ubicación de los puntos de conexión RTC que se unen a las reuniones, el troncal SIP usado para conectar los puntos de conexión RTC debe estar configurado para el enrutamiento basado en la ubicación.

Para obtener más información sobre cómo implementar y configurar el enrutamiento basado en la ubicación 2013 de Lync Server, consulte Configuración del [enrutamiento basado en la ubicación](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Habilitar la aplicación de conferencia de enrutamiento basada en la ubicación

La aplicación de conferencia de enrutamiento basada en la ubicación está deshabilitada de forma predeterminada. Antes de habilitar esta aplicación, tienes que determinar la prioridad adecuada para asignar a la aplicación. Para determinar esta prioridad, ejecute el siguiente cmdlet en el shell de administración de Lync Server:

Get-CsServerApplication-Identity Service: registrar:\<FQDN del grupo de servidores\>

En este cmdlet, \<FQDN\> del grupo es el grupo en el que se va a habilitar la aplicación de conferencia de enrutamiento basado en la ubicación.

Este cmdlet devolverá la lista de las aplicaciones hospedadas por Lync Server y el valor de prioridad de cada una de ellas. La aplicación de conferencia de enrutamiento basada en la ubicación debe tener asignado un valor de prioridad mayor que el de la aplicación "UdcAgent" y menor que las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting". Le recomendamos que asigne la aplicación de conferencia de enrutamiento basada en la ubicación un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".

Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10" y, a continuación, debe asignar a la aplicación de conferencia de enrutamiento basada en la ubicación un valor de prioridad de "3". Al hacerlo, la prioridad de las aplicaciones quedará ordenada así: otras aplicaciones (prioridades: de 0 a 1), “UdcAgent” (prioridad: 2), aplicación de conferencias con enrutamiento basado en ubicación (prioridad: 3), otras aplicaciones (prioridades: de 4 a 8), “DefaultRouting” (prioridad: 9), “ExumRouting” (prioridad: 10) y “OutboundRouting” (prioridad: 11).

Después de encontrar el valor de prioridad correcto para la aplicación de conferencia de enrutamiento basado en la ubicación, escriba el siguiente cmdlet para cada grupo de servidores front-end o un servidor Standard Edition que aloje usuarios habilitado para el enrutamiento basado en la ubicación:

New-CsServerApplication-Identity Service: registrar:\<FQDN\>del grupo de/LBRouting \<-priority Application priority\> Enabled $true-URI $true-URIhttp://www.microsoft.com/LCS/LBRouting

Por ejemplo:

New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-habilitado $true-$true-URIhttp://www.microsoft.com/LCS/LBRouting

Después de usar este cmdlet, reinicie todos los servidores front-end del grupo o los servidores Standard Edition donde se haya habilitado la aplicación de conferencia de enrutamiento basado en ubicación.

<div>


> [!IMPORTANT]  
> Los cumplimientos de enrutamiento basado en la ubicación de las conferencias o las transferencias de asesoría no se aplicarán hasta que se reinicien todos los servidores front-end de los servidores Standard Edition o Standard Edition.



</div>

Una vez que la aplicación de conferencia de enrutamiento basada en ubicación se haya habilitado correctamente y se hayan reiniciado todos los servidores de Lync aplicables, se supervisarán todas las conferencias organizadas por usuarios de Lync habilitados para el enrutamiento basado en la ubicación para evitar el bypass de llamadas RTC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

