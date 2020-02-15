---
title: 'Lync Server 2013: Planeación de conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1197dd61ea6ed871b851061d86c8653de32ddc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Planeación de conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-29_

Lync Server 2013 ofrece un amplio conjunto de capacidades de Conferencia:

  - Conferencia web, que incluye colaboración en documentos, uso compartido de aplicaciones y uso compartido de escritorio. Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y la representación de presentaciones de PowerPoint. Para más información sobre la instalación y la configuración del servidor de Office Web Apps, vea [Configuring Integration with Office Web Apps Server and Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Conferencia de audio/vídeo (A/V), que permite a los usuarios participar en conferencias de audio o vídeo en tiempo real sin necesidad de servicios externos, como el servicio Microsoft Live Meeting o un puente de audio de terceros.

  - Conferencia de acceso telefónico local, que permite a los usuarios unirse a la parte de audio de una conferencia de Lync Server 2013 mediante un teléfono de red telefónica conmutada (RTC) sin necesidad de un proveedor de servicios de audioconferencia de terceros.

  - Conferencia de mensajería instantánea, donde más de dos participantes se comunican en una única sesión de mensajería instantánea. Para obtener más información sobre las conferencias de mensajería instantánea, vea [planeación de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 admite conferencias programadas y conferencias improvisadas.

Al implementar Lync Server 2013, el servidor front-end, puede elegir si también desea implementar la conferencia Web, la conferencia A/V y las capacidades de conferencia de acceso telefónico local. Las capacidades de conferencia de mensajería instantánea se implementan siempre de forma automática junto con las funciones de conversación de mensajería instantánea en los servidores front-end de Lync Server 2013.

<div>


> [!NOTE]  
> Si su implementación incluye reuniones organizadas mediante clientes de Office Communicator 2007 R2 (incluido el complemento de conferencia o consola de Live Meeting para Microsoft Office Outlook), las reuniones tendrán las siguientes limitaciones después de que se migren a Lync. Servidor 2013: 
> <UL>
> <LI>
> <P>Los usuarios de la reunión no podrán usar las características de colaboración de datos, como la colaboración en documentos, el uso compartido de aplicaciones y el uso compartido de escritorio.</P>
> <LI>
> <P>Los problemas de estabilidad pueden surgir debido a que los clientes de Office Communicator 2007 R2 no son compatibles con Lync Server 2013.</P></LI></UL>Para evitar estos problemas, reprograme cualquier reunión organizada mediante los clientes de Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 mediante el complemento de reunión en línea para Lync 2010 o el complemento de reunión en línea para Lync 2013.



</div>

En las secciones siguientes se describe lo que es necesario para implementar los distintos tipos de capacidades de conferencia, incluido el proceso de planeación, los componentes, los requisitos de hardware y software y el proceso de implementación.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre las conferencias en Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Definición de los requisitos para las conferencias en Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Componentes y topologías para conferencias en Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Requisitos técnicos para conferencias en Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lista de comprobación para la implementación de conferencias en Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Compatibilidad con reuniones grandes en Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

