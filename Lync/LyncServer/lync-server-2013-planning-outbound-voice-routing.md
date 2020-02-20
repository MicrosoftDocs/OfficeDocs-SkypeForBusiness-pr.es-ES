---
title: 'Lync Server 2013: Planeación del enrutamiento de voz saliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e912a3934ae7262c85cfb7b47c62abf6bc70b5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Planeación del enrutamiento de voz saliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El enrutamiento de llamadas realizadas se aplica a las llamadas destinadas a una puerta de enlace de red telefónica conmutada (RTC), un enlace troncal o una central de conmutación PBX. Cuando un usuario realiza una llamada, el servidor normaliza el número de teléfono al formato E.164, si es necesario, e intenta establecer una coincidencia con un URI de SIP. Si el servidor no puede establecer la coincidencia, aplicará la lógica de enrutamiento de llamadas realizadas basándose en la cadena de marcado proporcionada. Dicha lógica se define con la configuración de las opciones de servidor que se describe en la siguiente tabla.

### <a name="lync-server-outbound-call-routing-settings"></a>Configuración del servidor de enrutamiento de llamadas realizadas de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objeto</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Plan de marcado</p></td>
<td><p>Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Regla de normalización</p></td>
<td><p>Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado. Una misma cadena de marcado se puede interpretar y convertir de manera distinta en función de la ubicación desde la que se marque y la persona o el objeto de contacto que realice la llamada. Un conjunto de reglas de normalización asociado a una ubicación determinada constituye un plan de marcado.</p></td>
</tr>
<tr class="odd">
<td><p>Directiva de voz</p></td>
<td><p>Una directiva de voz asocia uno o varios registros de uso de RTC a un usuario o un grupo de usuarios. Además proporciona una lista de características de llamada que se puede habilitar o deshabilitar.</p></td>
</tr>
<tr class="even">
<td><p>Registro de uso de RTC</p></td>
<td><p>Un registro de uso de RTC especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización.</p></td>
</tr>
<tr class="odd">
<td><p>Ruta de llamada</p></td>
<td><p>Una ruta de llamada asocia los números de teléfono de destino a determinados circuitos de enlace y a determinados registros de uso de PSTN. Un circuito de enlace de PSTN se considera una puerta de enlace.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>En esta sección

En esta sección se proporcionan instrucciones para configurar las siguientes opciones del servidor de enrutamiento de llamadas realizadas:

  - <span></span>  
    [Planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Directivas de voz en Lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Registros de uso de RTC en Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Enlace troncal SIP en Lync Server 2013](lync-server-2013-sip-trunking.md)  
[Conexiones SIP directas en Lync Server 2013](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

