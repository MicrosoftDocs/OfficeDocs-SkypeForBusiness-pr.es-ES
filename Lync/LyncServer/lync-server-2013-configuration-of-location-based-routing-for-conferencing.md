---
title: 'Lync Server 2013: configuración del enrutamiento basado en ubicación para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f982f6e484412234c75eadaea925b65ee11bcbb
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuración del enrutamiento basado en ubicación para conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-11_

La aplicación de conferencia de enrutamiento basada en ubicación se basa en la configuración del enrutamiento basado en ubicación 2013 de Lync Server. Las configuraciones principales son las siguientes:

  - La ubicación de los participantes que se unen a una reunión se determina en función de su sitio de red. Un sitio de red y sus subredes de red asociadas deben definirse en Lync Server para aplicar el enrutamiento basado en la ubicación.

  - Para aplicar el enrutamiento basado en la ubicación de las reuniones, los participantes de Lync deben estar habilitados para el enrutamiento basado en ubicación.

  - Para aplicar el enrutamiento basado en la ubicación de los extremos de RTC que se unen a las reuniones, el tronco SIP que se usa para conectar los extremos de RTC debe configurarse para el enrutamiento basado en ubicación.

Para obtener más información sobre la implementación y la configuración del enrutamiento basado en ubicación de Lync Server 2013, consulte Configuring [location-based Routing](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Habilitación de la aplicación de conferencia de enrutamiento basada en ubicación

La aplicación de conferencia de enrutamiento basada en ubicación está deshabilitada de forma predeterminada. Antes de habilitar esta aplicación, debe determinar la prioridad correcta que se asignará a la aplicación. Para determinar esta prioridad, ejecute el siguiente cmdlet en el shell de administración de Lync Server:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

En este cmdlet, \<Pool FQDN\> es el grupo en el que se habilitará la aplicación de conferencia de enrutamiento basada en ubicación.

Este cmdlet devolverá la lista de las aplicaciones hospedadas en Lync Server y el valor de prioridad de cada una de ellas. La aplicación de conferencia de enrutamiento basada en ubicación debe tener asignado un valor de prioridad mayor que el de la aplicación "UdcAgent" y menor que el de las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting". Le recomendamos que asigne la aplicación de conferencia de enrutamiento basada en ubicación un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".

Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10", debe asignar a la aplicación de conferencia de enrutamiento basada Si lo hace, se colocará la prioridad de las aplicaciones en el siguiente orden: otras aplicaciones (prioridades: 0 a 1), "UdcAgent" (prioridad: 2), aplicación de conferencia de enrutamiento basada en ubicación (prioridad: 3), otras aplicaciones (prioridades: 4 a 8), "DefaultRouting" (prioridad: 9), "ExumRouting" (prioridad: 10) y "OutboundRouting" (prioridad: 11).

Una vez que haya encontrado el valor de prioridad correcto para la aplicación de conferencia de enrutamiento basada en ubicación, escriba el siguiente cmdlet para cada grupo de servidores front-end o servidor Standard Edition que aloje a los usuarios habilitados para el enrutamiento basado en ubicación:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Por ejemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Después de usar este cmdlet, reinicie todos los servidores front-end en el grupo o los servidores Standard Edition donde se haya habilitado la aplicación de conferencia de enrutamiento basada en ubicación.

<div>


> [!IMPORTANT]  
> Las fuerzas de enrutamiento basadas en ubicación para las conferencias o las transferencias de consulta no se aplicarán hasta que se reinicien todos los servidores front-end de los grupos de servidores correspondientes o los servidores Standard Edition.



</div>

Una vez que la aplicación de conferencia de enrutamiento basada en ubicación se haya habilitado correctamente y se hayan reiniciado todos los servidores de Lync aplicables, se supervisarán todas las conferencias organizadas por usuarios de Lync habilitados para el enrutamiento basado en ubicación para evitar el desvío de llamadas RTC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

