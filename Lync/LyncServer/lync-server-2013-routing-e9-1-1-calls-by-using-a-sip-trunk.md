---
title: 'Lync Server 2013: enrutamiento de llamadas E9-1-1 mediante un enlace troncal SIP'
description: 'Lync Server 2013: enrutamiento de llamadas E9-1-1 mediante un tronco SIP.'
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
ms.openlocfilehash: 9e45b2b3d33556a5ff97235345c7b538023a7449
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571826"
---
# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Routing E9-1-1 calls by Using a SIP trunk in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

El uso de troncos SIP para establecer una conexión con un proveedor de servicios E9-1-1 es una de las formas de implementar servicios E9-1-1. Para obtener información detallada sobre el uso de una puerta de enlace de ELIN para conectarse a un proveedor de servicios E9-1-1 basado en una red telefónica conmutada (RTC), consulte [Routing E9-1-1 calls by Using a Elin Gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

El siguiente diagrama muestra cómo se enruta una llamada de emergencia desde Lync Server al punto de respuesta de seguridad pública (PSAP) cuando se usa un tronco SIP y un proveedor de servicios E9-1-1 cualificado.

**Enrutamiento de llamadas E9-1-1 mediante troncos SIP**

![Enrutamiento de llamadas de emergencia de Lync Server a PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Enrutamiento de llamadas de emergencia de Lync Server a PSAP")

Cuando se realiza una llamada de emergencia desde un cliente compatible de Lync Server:

1.  Un SIP INVITE que contiene la ubicación, el número de devolución de llamada del autor de la llamada y la dirección URL de notificación (opcional) y el número de devolución de llamada de conferencia se redirige a Lync Server.

2.  Lync Server coincide con el número de emergencia y enruta la llamada (en función del valor de **uso de RTC** que se define en la Directiva de ubicación correspondiente) a un servidor de mediación y, desde allí, a través de un tronco SIP al proveedor de servicios E9-1-1.

3.  El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.

4.  Si ha configurado la Directiva de ubicación para las notificaciones, se enviará a uno o más de los responsables de seguridad de la organización un mensaje instantáneo especial de notificación de emergencia de Lync. Este mensaje siempre aparece en la pantalla de los responsables de seguridad y contiene el nombre, número de teléfono, hora y ubicación del autor de la llamada para que el personal de seguridad pueda ponerse en contacto con él rápidamente mediante un mensaje instantáneo o de voz.

5.  Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.

6.  Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.

</div>

<span> </span>

</div>

</div>

</div>

