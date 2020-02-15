---
title: 'Lync Server 2013: componentes de conectividad con RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b307e88bbf85b43a6997d46c5a822684e0421752
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Componentes de conectividad con RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Una solución de telefonía VoIP profesional debe proporcionar llamadas entrantes y realizadas a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra sesión de SIP.

Para las conexiones RTC, puede implementar un tronco SIP o una puerta de enlace RTC (con una PBX, también conocida como vínculo SIP directo o sin PBX).

<div>

## <a name="sip-trunking"></a>Enlace troncal SIP

Como alternativa al uso de puertas de enlace RTC, puede conectar la solución de Enterprise Voice a la RTC usando el enlace troncal SIP. El enlace troncal SIP habilita los siguientes escenarios:

  - Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.

  - Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.

El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP.

</div>

<div>

## <a name="pstn-gateways"></a>Puertas de enlace RTC

Las puertas de enlace RTC son dispositivos de otro fabricante que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y una red telefónica conmutada (RTC) o una central de conmutación (PBX). Las puertas de enlace RTC trabajan con el servidor de mediación para presentar una llamada de RTC o de PBX a un cliente de Enterprise Voice. El servidor de mediación también presenta llamadas de los clientes de Enterprise Voice a la puerta de enlace RTC para redirigir las llamadas a la RTC o a la PBX. Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionan con Lync Server, vea el sitio web de asociados [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)de comunicaciones unificadas de Microsoft en.

</div>

<div>

## <a name="private-branch-exchanges"></a>Centrales de conmutación

Si tiene una infraestructura de voz existente que usa una central de conmutación (PBX), puede usar la PBX con Lync Server Enterprise Voice.

Los escenarios de integración de Enterprise Voice y PBX admitidos son los siguientes:

  - IP-PBX que admite desvío de medios, con un servidor de mediación.

  - IP-PBX que requiere una puerta de enlace de RTC independiente.

  - PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace de RTC independiente.

<div>


> [!NOTE]  
> El desvío de medios no interactuará con todas las puertas de RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

Para obtener más información sobre los socios que ofrecen soluciones de telefonía IP empresarial, consulte el sitio [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Web de asociados de comunicaciones unificadas de Microsoft en.

Para obtener más información sobre los socios que ofrecen soluciones de hardware de telefonía IP empresarial, incluidas las puertas de enlace RTC [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836), consulte el sitio web de asociados de comunicaciones unificadas de Microsoft.

</div>

</div>

<span> </span>

</div>

</div>

</div>

