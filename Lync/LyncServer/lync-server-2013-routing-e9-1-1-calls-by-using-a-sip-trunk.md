---
title: 'Lync Server 2013: Enrutamiento de llamadas E9-1-1 mediante un SIP troncal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Enrutamiento de llamadas E9-1-1 mediante un SIP troncal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

El uso de un tronco SIP para conectarse a un proveedor de servicios E9-1-1 certificado es una manera de implementar E9-1-1. Para obtener detalles sobre el uso de una puerta de enlace de ELIN para conectarse a un proveedor de servicios de red de telefonía pública conmutada (RTC) E9-1-1, consulte [enrutamiento E9-1-1 llamadas mediante una puerta de enlace Elin en Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

En el siguiente diagrama se muestra cómo se dirige una llamada de emergencia desde Lync Server al punto de respuesta de seguridad pública (PSAP) cuando usa un tronco de SIP y un proveedor de servicios de E9-1-1 calificado.

**Enrutamiento de llamadas E9-1-1 a través de un tronco SIP**

![Enrutar llamada de emergencia de Lync Server a un punto de respuesta de seguridad pública (PSAP)](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Enrutar llamada de emergencia de Lync Server a un punto de respuesta de seguridad pública (PSAP)")

Cuando se realiza una llamada de emergencia desde un cliente de Lync Server compatible:

1.  Una invitación SIP que contiene la ubicación, el número de devolución de llamada de la persona que llama y la dirección URL de notificación (opcional) y el número de devolución de llamada de la Conferencia se enrutan a Lync Server.

2.  Lync Server coincide con el número de emergencia y enruta la llamada (según el valor de **uso de RTC** que se define en la política de ubicación correspondiente) a un servidor de mediación, y desde allí, a través de un enlace SIP al proveedor de servicios E9-1-1.

3.  El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.

4.  Si ha configurado la Directiva de ubicación para las notificaciones, uno o varios de los responsables de seguridad de la organización reciben un mensaje instantáneo especial de notificación de emergencia de Lync. Este mensaje siempre se muestra en la pantalla de los equipos de los responsables de seguridad y proporciona información sobre el nombre, el número de teléfono, la hora y la ubicación de la persona que realiza la llamada, lo que permite al personal de seguridad responder con rapidez a la persona que realiza la llamada de emergencia por medio de un mensaje instantáneo o de voz.

5.  Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.

6.  Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.

</div>

<span> </span>

</div>

</div>

</div>

