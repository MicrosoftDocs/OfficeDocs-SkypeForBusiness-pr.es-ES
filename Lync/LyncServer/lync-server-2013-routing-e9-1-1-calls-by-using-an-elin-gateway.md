---
title: 'Lync Server 2013: Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdb4b5879f92da79e8a6ec96f61e24fbe182c028
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-05_

Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado. Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC). Para obtener más información sobre los partners que proporcionan puertas de enlace de ELIN y vínculos [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)a la documentación, consulte.

Al igual que las conexiones troncales SIP con los proveedores de servicios E9-1-1, las puertas de enlace ELIN también ofrecen los medios necesarios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública (PSAP) más adecuado para el autor de la llamada, pero estas puertas de enlace usan un número ELIN para identificar la ubicación. Defina ELINs para cada ubicación de respuesta de emergencia (ERL) de su organización (para obtener más información, vea [administrar ubicaciones de puertas de enlace de Elin en Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Cuando use una puerta de enlace de ELIN para llamadas de emergencia, use la misma infraestructura de Lync Server E9-1-1 que usaría para una conexión de protocolo troncal de SIP. Es decir, la base de datos del servicio de información de ubicación proporciona la ubicación al cliente de Lync Server y la Directiva de ubicación la habilita y define el enrutamiento. Sin embargo, con una puerta de enlace de ELIN necesita agregar la ELINs a la base de datos de servicios de información de ubicación y hacer que el operador PSTN la cargue en la base de datos de identificación de ubicación automática (ALI).

Cuando un cliente de Lync obtiene su ubicación desde el servicio de información de ubicación, la ubicación incluye la ELIN. Durante una llamada de emergencia, ELIN se incluye con la ubicación que se envía a la puerta de enlace de ELIN. La puerta de enlace de ELIN identifica la llamada como llamada de emergencia e intercambia el número de la persona que llama con el ELIN. A continuación, la puerta de enlace de ELIN enruta la llamada a la RTC con el ELIN como el número de llamada. El proveedor E9-1-1 de RTC busca la ELIN en la base de datos de ALI, que es una base de datos complementaria para la base de datos de la guía de dirección maestra (MSAG). La RTC envía entonces la llamada a la PSAP más adecuada en función de la búsqueda de ALI, y el PSAP envía los primeros respondedores a la ubicación de la persona que llama basándose en la búsqueda de ALI. El número de llamada se almacena en caché en la puerta de enlace de ELIN durante un período de tiempo predefinido para las devoluciones de llamada. Durante una devolución de llamada, el PSAP llega a la puerta de enlace de ELIN, que intercambia el ELIN para el número de marcado interno directo de la persona que llama.

Las puertas de enlace de ELIN solo admiten llamadas de emergencia desde la red de su organización. No admiten llamadas de emergencia hechas desde fuera de la red.

<div>


> [!NOTE]  
> Para obtener detalles sobre el uso de una conexión de troncal de SIP para llamadas de emergencia, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls Using an SIP trunk in Lync Server 2013</A>.



</div>

En el siguiente diagrama se muestra cómo se enruta una llamada de emergencia de Lync Server a la PSAP al usar una puerta de enlace de ELIN.

**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1] (images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Una invitación SIP que contiene la ubicación, el número de devolución de llamada de la persona que llama y la dirección URL de notificación (opcional) y el número de devolución de llamada de la Conferencia se enrutan a Lync Server.

2.  Lync Server coincide con el número de emergencia y, después, enruta la llamada (según el valor de **uso de RTC** definido en la política de ubicación correspondiente) a un servidor de mediación y desde allí a una puerta de enlace de Elin.

3.  La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.

4.  La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI. 

5.  Si ha configurado la Directiva de ubicación para las notificaciones, uno o varios de los responsables de seguridad de la organización reciben un mensaje instantáneo especial de notificación de emergencia de Lync. Este mensaje siempre se muestra en la pantalla de los equipos de los responsables de seguridad y proporciona información sobre el nombre, el número de teléfono, la hora y la ubicación de la persona que realiza la llamada, lo que permite al personal de seguridad responder con rapidez a la persona que realiza la llamada de emergencia por medio de un mensaje instantáneo o de voz.

6.  En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.

</div>

<span> </span>

</div>

</div>

</div>

