---
title: 'Lync Server 2013: componentes de conectividad RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecda38b4164a70cd4dbb21271ff6efedb08cd498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Componentes de conectividad RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde el punto de vista del usuario, una llamada entre la infraestructura de telefonía IP empresarial y la RTC debe parecer simplemente otra sesión de SIP.

En las conexiones de RTC, puedes implementar un tronco SIP o una puerta de enlace RTC (también denominada vínculo SIP directo, con una PBX o sin ella).

<div>

## <a name="sip-trunking"></a>Enlace troncal SIP

Como alternativa al uso de puertas de enlace RTC, puede conectar su solución de telefonía empresarial a la RTC mediante el uso de troncales SIP. El enlace troncal SIP habilita los siguientes escenarios:

  - Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.

  - Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.

El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP.

</div>

<div>

## <a name="pstn-gateways"></a>Puertas de enlace RTC

Las puertas de enlace RTC son dispositivos de terceros que traducen la señalización y los medios entre la infraestructura de voz empresarial y una RTC o un sistema PBX. Las puertas de enlace RTC funcionan con el servidor de mediación para presentar una llamada RTC o PBX a un cliente de telefonía empresarial. El servidor de mediación también presenta llamadas de clientes de telefonía de empresa a la puerta de enlace RTC para el enrutamiento a la RTC o a la PBX. Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionen con Lync Server, consulte el sitio web de [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)socios de comunicaciones unificadas de Microsoft en.

</div>

<div>

## <a name="private-branch-exchanges"></a>Centrales de conmutación

Si tiene una infraestructura de voz existente que usa una central de conmutación (PBX), puede usar su PBX con Lync Server Enterprise Voice.

Los escenarios de integración de la telefonía IP empresarial compatibles son los siguientes:

  - IP-PBX que admite omisión de medios, con un servidor de mediación.

  - IP-PBX que requiere una puerta de enlace RTC independiente.

  - PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace RTC independiente.

<div>


> [!NOTE]  
> La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco. La omisión de elementos multimedia solo se admite con productos y versiones que se incluyen en el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

Para obtener más información sobre los partners que ofrecen soluciones de telefonía IP empresarial, consulte el sitio [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Web de socios de comunicaciones unificadas de Microsoft en.

Para obtener más información sobre los partners que ofrecen soluciones de hardware de voz empresarial, incluidas las puertas de enlace RTC, [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)consulte el sitio web de socios de comunicaciones unificadas de Microsoft.

</div>

</div>

<span> </span>

</div>

</div>

</div>

