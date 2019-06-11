---
title: 'Lync Server 2013: Planificar conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Planificar conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-29_

Lync Server 2013 ofrece un amplio conjunto de capacidades de Conferencia:

  - Conferencias web, que incluye colaboración de documentos, uso compartido de aplicaciones y uso compartido de escritorio. Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y el procesamiento de presentaciones de PowerPoint. Para obtener más información sobre cómo instalar y configurar el servidor de Office Web Apps, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Conferencias de audio y vídeo (A/V), que permite a los usuarios tener conferencias de audio o vídeo en tiempo real sin necesidad de servicios externos, como el servicio Microsoft Live Meeting o un puente de audio de terceros.

  - Conferencias de acceso telefónico local, que permite a los usuarios unirse a la parte de audio de una conferencia de 2013 de Lync Server mediante un teléfono con red telefónica conmutada (RTC) sin requerir un proveedor de servicios de audioconferencia de terceros.

  - Conferencias de mensajería instantánea (mi), en las que más de dos partes se comunican en una sola sesión de mensajería instantánea. Para obtener más información sobre las conferencias de mensajería instantánea, consulte [planificación de servidores de aplicaciones para el usuario, mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 admite tanto conferencias programadas como conferencias espontáneas.

Al implementar Lync Server 2013, el servidor front-end, puede elegir si implementar también las conferencias web, las conferencias A/V y las capacidades de conferencia de acceso telefónico local. Las capacidades de conferencia de mi siempre se implementan automáticamente junto con las funciones de conversación de mensajería instantánea en servidores front-end de Lync Server 2013.

<div>


> [!NOTE]  
> Si su implementación incluye reuniones organizadas con clientes de Office Communicator 2007 R2 (incluida la consola de Live Meeting o el complemento de conferencias para Microsoft Office Outlook), las reuniones tendrán las siguientes limitaciones después de migrar a Lync. Server 2013: 
> <UL>
> <LI>
> <P>Los usuarios de la reunión no podrán usar características de colaboración de datos, como la colaboración de documentos, uso compartido de aplicaciones y uso compartido de escritorio.</P>
> <LI>
> <P>Pueden surgir problemas de estabilidad, ya que los clientes de Office Communicator 2007 R2 no son compatibles con Lync Server 2013.</P></LI></UL>Para evitar estos problemas, reprograme cualquier reunión organizada con clientes de Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 con el complemento de reunión en línea para Lync 2010 o el complemento de reunión en línea para Lync 2013.



</div>

En las siguientes secciones, se describen los pasos necesarios para implementar los distintos tipos de capacidades de conferencia, incluidos el proceso de planeamiento, los componentes, los requisitos de hardware y software, y el proceso de implementación.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre conferencias en Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Definición de requisitos para conferencias en Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

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

