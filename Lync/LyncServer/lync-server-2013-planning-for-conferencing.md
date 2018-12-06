---
title: 'Lync Server 2013: Planificar conferencias'
TOCTitle: Planificar conferencias
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48276116
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planificar conferencias en Lync Server 2013

 

_**Última modificación del tema:** 2013-01-29_

Lync Server 2013 nm-ocs-14-1st-legal-desc ofrece un completo conjunto de capacidades de conferencia:

  - Conferencia web, que incluye colaboración en documentos, uso compartido de aplicaciones y uso compartido de escritorio. Lync Server 2013 usa Office Web Apps y el Servidor Office Web Apps para administrar el uso compartido y la representación de presentaciones de PowerPoint. Para más información acerca de cómo instalar y configurar el Servidor Office Web Apps, consulte [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Conferencia de audio/vídeo (A/V), que permite a los usuarios participar en conferencias de audio o vídeo en tiempo real sin necesidad de servicios externos, como el servicio Microsoft Live Meeting o un puente de audio de terceros.

  - Conferencia de acceso telefónico local, que permite a los usuarios participar en la parte de audio de una conferencia de Lync Server 2013 mediante un teléfono de red telefónica conmutada (RTC) sin necesidad de usar los servicios de un proveedor de servicios de audioconferencia de terceros.

  - Conferencia de mensajería instantánea, donde más de dos participantes se comunican en una única sesión de mensajería instantánea. Para más información sobre las conferencias de mensajería instantánea, consulte [Planificar los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 admite tanto conferencias programadas como improvisadas.

Al implementar Lync Server 2013,  Servidor front-end, puede elegir si también desea implementar las capacidades de conferencia web, conferencia A/V y conferencia de acceso telefónico local. Las capacidades de conferencia de mensajería instantánea se implementan de forma automática junto con las capacidades de conversación de mensajería instantánea en los Servidores front-end de Lync Server 2013.


> [!NOTE]
> Si su implementación incluye reuniones organizadas con clientes de Office Communicator 2007 R2 (incluida la consola de Live Meeting o Complemento para conferencias para Microsoft Office Outlook), las reuniones tendrán las siguientes limitaciones después de su migración a Lync Server 2013: 
> <UL>
> <LI>
> <P>Los usuarios de la reunión no podrán usar características de colaboración de datos, incluida la colaboración en documentos, el uso compartido de aplicaciones y el uso compartido de escritorio.</P>
> <LI>
> <P>Pueden producirse problemas de estabilidad ya que los clientes de Office Communicator 2007 R2 no son compatibles con Lync Server 2013.</P></LI></UL>Para evitar estos problemas, vuelva a programar las reuniones que se hayan organizado usando clientes de Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013, pero use el Complemento para conferencia en línea para Lync 2010 o el Complemento para conferencia en línea para Lync 2013.



En las secciones siguientes se describe lo que es necesario para implementar los distintos tipos de capacidades de conferencia, incluido el proceso de planeación, los componentes, los requisitos de hardware y software y el proceso de implementación.

## En esta sección

  - [Información general sobre conferencias en Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Definición de requisitos para conferencias en Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Componentes y topologías para conferencias en Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Requisitos técnicos para conferencias en Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lista de comprobación para la implementación de conferencias en Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Compatibilidad con reuniones grandes en Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

