---
title: 'Lync Server 2013: enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: befa9ad077780eb57d4690790673fc0a5452af60
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-05_

Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado. Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC). Para más información sobre los socios que proporcionan ELIN puertas de enlace y vínculos a la [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)documentación, consulte.

Al igual que las conexiones de enlace troncal SIP a los proveedores de servicios E9-1-1, las puertas de enlace de ELIN también proporcionan los medios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública más apropiado del autor de la llamada (PSAP), pero estas puertas de enlace utilizan un ELIN como identificador de ubicación. Defina Elin para cada ubicación de respuesta de emergencia (ERL) de la organización (para obtener más información, consulte [administrar ubicaciones para puertas de enlace de Elin en Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Cuando se usa una puerta de enlace de ELIN para las llamadas de emergencia, se usa la misma infraestructura de Lync Server E9-1-1 que se usaría para una conexión de enlace troncal SIP. Es decir, la base de datos del servicio de información de ubicación proporciona la ubicación al cliente de Lync Server y la Directiva de ubicación habilita la característica y define el enrutamiento. Sin embargo, con una puerta de enlace ELIN, debe agregar el Elin a la base de datos del servicio de información de ubicación y hacer que el operador de RTC los cargue a la base de datos de identificación de ubicación automática (ALI).

Cuando un cliente de Lync obtiene su ubicación del servicio de información de ubicación, la ubicación incluye ELIN. Durante las llamadas de emergencia, el ELIN se incluye con la información de ubicación que se envía a la puerta de enlace ELIN. Esta puerta de enlace identifica la llamada como llamada de emergencia y cambia el número de la persona que llama por el ELIN. A continuación, la puerta de enlace ELIN enruta la llamada al RTC con el ELIN como número llamante. El proveedor de servicios E9-1-1 de RTC busca el ELIN en la base de datos ALI, que actúa como una base de datos adicional a la base de datos de guía de direcciones principal (MSAG). Acto seguido el operador de RTC envía la llamada al PSAP más adecuado en función de la búsqueda realizada en la base de datos ALI y el PSAP envía el personal de emergencia disponible a la ubicación de la persona que realiza según los resultados de la búsqueda ALI. El número de llamada se almacena en la memoria caché de la puerta de enlace ELIN durante un tiempo predeterminado para las devoluciones de llamadas. Durante la devolución de llamada, el PSAP contacta con la puerta de enlace ELIN que, a su vez, cambia el ELIN por el número de llamada directa a la extensión (DID) de la persona que realiza la llamada.

Las puertas de enlace ELIN solo admiten las llamadas de emergencia desde la red de su organización. No admiten las llamadas de emergencia realizadas fuera de su red.

<div>


> [!NOTE]  
> Para obtener más información sobre el uso de una conexión de enlace troncal SIP para llamadas de emergencia, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by Using a SIP trunk in Lync Server 2013</A>.



</div>

El siguiente diagrama muestra cómo se enruta una llamada de emergencia desde Lync Server a la PSAP cuando se usa una puerta de enlace ELIN.

**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Un SIP INVITE que contiene la ubicación, el número de devolución de llamada del autor de la llamada y la dirección URL de notificación (opcional) y el número de devolución de llamada de conferencia se enruta a Lync Server.

2.  Lync Server coincide con el número de emergencia y, a continuación, enruta la llamada (en función del valor **uso de RTC** definido en la Directiva de ubicación correspondiente) a un servidor de mediación y desde ahí a una puerta de enlace Elin.

3.  La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.

4.  La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI.

5.  Si ha configurado la Directiva de ubicación para las notificaciones, se enviará a uno o más de los responsables de seguridad de la organización un mensaje instantáneo especial de notificación de emergencia de Lync. Este mensaje siempre aparece en la pantalla de los responsables de seguridad y contiene el nombre, número de teléfono, hora y ubicación del autor de la llamada para que el personal de seguridad pueda ponerse en contacto con él rápidamente mediante un mensaje instantáneo o de voz.

6.  En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.

</div>

<span> </span>

</div>

</div>

</div>

