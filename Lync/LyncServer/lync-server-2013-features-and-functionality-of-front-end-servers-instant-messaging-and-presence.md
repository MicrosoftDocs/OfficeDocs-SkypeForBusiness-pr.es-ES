---
title: 'Lync Server 2013: Características y funcionalidades de los servidores front-end, la mensajería instantánea y la presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Características y funcionalidades de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-17_

Los servidores front-end proporcionan la mayor parte de la funcionalidad de Lync Server. Hay dos ediciones disponibles: Lync Server Enterprise Edition, que está diseñado principalmente para organizaciones grandes y Lync Server Standard Edition, que está diseñado principalmente para organizaciones pequeñas que quieren un hardware más Investement y no requieren una alta disponibilidad. Ambas ediciones admiten todas las cargas de trabajo de Lync Server, incluidas la mensajería instantánea, presencia, Conferencia y telefonía IP empresarial.

La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y por medio de mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.

<div>


> [!IMPORTANT]
> Los clientes de Lync y Communicator, cuando participan en una sola comunicación, se suelen denominar de punto a punto. Técnicamente, los dos clientes se comunican en una conversación de una en una, con la unidad de control multipunto de mensajería instantánea (IMMCU) en el medio. El IMMCU es un componente de servidor front-end. La colocación de IMMCU en el flujo de trabajo de comunicaciones requerido permite la grabación de detalles de llamadas y otras características que permite el servidor front-end. La comunicación es de un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada). Por diseño, la comunicación de punto a punto (así como la de mensajería instantánea de varios participantes) solo es posible cuando Lync Server y IMMCU está activo y disponible.



</div>

*Presencia* proporciona información a los usuarios sobre el estado de otros en la red. El estado de presencia de un usuario brinda información que ayuda a los demás usuarios a decidir si pueden intentar ponerse en contacto con él y si hacerlo con la mensajería instantánea, el teléfono o el correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se muestra como un icono de presencia en Lync y en otras aplicaciones para la presencia, como el cliente de mensajería y colaboración Microsoft Outlook, las tecnologías de Microsoft SharePoint, Microsoft Word y la hoja de cálculo de Microsoft Excel. antivirus. El icono del estado de presencia representa la disponibilidad y la disposición de comunicación actual del usuario.

</div>

<span> </span>

</div>

</div>

</div>

