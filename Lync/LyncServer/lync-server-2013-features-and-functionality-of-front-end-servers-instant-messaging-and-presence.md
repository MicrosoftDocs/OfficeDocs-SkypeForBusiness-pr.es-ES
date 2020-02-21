---
title: 'Lync Server 2013: características y funciones de los servidores front-end, la mensajería instantánea y la presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab1b2285b80098ec6acf1faad64f21a78472c0b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Características y funciones de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-17_

Los servidores front-end proporcionan la funcionalidad de Lync Server. Hay dos ediciones disponibles: Lync Server Enterprise Edition, que está diseñado principalmente para organizaciones más grandes y Lync Server Standard Edition, diseñado principalmente para organizaciones más pequeñas que quieren una Investement de hardware más pequeña y no requieren alta disponibilidad. Ambas ediciones admiten todas las cargas de trabajo de Lync Server, incluidas la mensajería instantánea, la presencia, la Conferencia y la telefonía IP empresarial.

La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.

<div>


> [!IMPORTANT]
> Los clientes de Lync y Communicator cuando participan en una comunicación de una a una, a menudo se denominan de punto a punto. Técnicamente, los dos clientes se comunican en una conversación de una a una, con la unidad de control multipunto (IMMCU) de mensajería instantánea en la parte central. IMMCU es un componente del servidor front-end. La colocación de IMMCU en el flujo de trabajo de comunicación necesario permite el registro detallado de llamadas y otras características que permite el servidor front-end. La comunicación es desde un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada). Por diseño, la comunicación punto a punto (así como la mensajería instantánea de varios participantes) solo es posible cuando Lync Server y el IMMCU está activo y disponible.



</div>

*Presencia* proporciona información a los usuarios acerca del estado de los otros usuarios en la red. El estado de presencia de un usuario proporciona información que ayuda a los demás usuarios a decidir si deben intentar ponerse en contacto con él y si deben usar la mensajería instantánea, el teléfono o el correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se muestra como un icono de presencia en Lync y otras aplicaciones para la presencia, como el cliente de mensajería y colaboración de Microsoft Outlook, las tecnologías de Microsoft SharePoint, Microsoft Word y la hoja de cálculo de Microsoft Excel. aplicaciones. El icono del estado de presencia representa la disponibilidad y la disposición de comunicación del usuario.

</div>

<span> </span>

</div>

</div>

</div>

