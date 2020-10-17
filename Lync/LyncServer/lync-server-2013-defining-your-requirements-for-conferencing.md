---
title: 'Lync Server 2013: definición de los requisitos para las conferencias'
description: 'Lync Server 2013: definición de los requisitos para las conferencias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 009a80d2fd48341723743bb6a06ad2ee05289a6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545416"
---
# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definición de los requisitos para las conferencias en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Al determinar qué capacidades de conferencia se van a implementar, debe tener en cuenta las características que desea que estén disponibles para los usuarios y las capacidades de ancho de banda de la red. La lista de preguntas que aparece a continuación le orienta a través del proceso de planeación de conferencia para determinar qué características de conferencia deberá implementar en función de los requisitos de su organización.

  - **¿Desea habilitar la conferencia web, lo que incluye colaboración en documentos y uso compartido de aplicaciones?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end en la herramienta de planeación de Microsoft Lync Server 2013, o en el generador de topologías. Al habilitar las conferencias, se habilitan las conferencias web y A/V.
    
    El uso compartido de aplicaciones requiere y usa un mayor ancho de banda que la colaboración en documentos. Lync Server 2013 proporciona un mecanismo de limitación para controlar cada sesión de uso compartido de aplicaciones. De forma predeterminada, este está establecido en 1,5 KB/segundo para cada sesión.
    
    Si no desea habilitar el uso compartido de aplicaciones pero desea permitir la colaboración en documentos, puede habilitar la conferencia y usar directivas de reunión para deshabilitar el uso compartido de aplicaciones. Para más información sobre cómo configurar las directivas de reuniones, consulte [directivas de conferencia en Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Para permitir que los usuarios compartan presentaciones de PowerPoint, debe configurar Office Web Apps Server. Para más información sobre la configuración de Office Web Apps Server, vea [Configuring Integration with Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **¿Desea habilitar la conferencia A/V?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end en la herramienta de planeación de Lync Server 2013 o en el generador de topologías. Al habilitar las conferencias, se habilitan las conferencias web y A/V.
    
    La conferencia A/V requiere y usa un mayor ancho de banda que la conferencia web (lo que incluye la colaboración en documentos y los recursos compartidos de aplicaciones). Si no desea habilitar la conferencia A/V pero desea habilitar la conferencia Web, puede habilitar la Conferencia y usar las directivas de reunión para deshabilitar las conferencias de A/V.
    
    Si desea habilitar las conferencias de audio, pero no las conferencias de vídeo, puede habilitar la conferencia A/V y usar directivas de reunión para evitar las conferencias de vídeo. Como alternativa, puede habilitar la conferencia A/V y habilitar solo a determinados usuarios para que inicien conferencias A/V o participen en ellas.
    
    <div>
    

    > [!NOTE]  
    > La telefonía IP empresarial no es necesaria para usar la conferencia A/V. Si habilita las conferencias A/V, los usuarios pueden agregar audio a sus conferencias si tienen dispositivos de audio, incluso si usa una PBX para la solución telefónica.

    
    </div>

  - **¿Desea permitir que los usuarios se unan a secciones de audio de conferencias al usar un teléfono RTC?**
    
    Si es así, implemente y habilite las conferencias de acceso telefónico local. De este modo, los usuarios invitados, tanto de dentro como de fuera de la organización, podrán unirse a la sección de audio de las conferencias a través de un teléfono RTC.

  - **¿Desea habilitar a los usuarios externos con clientes de Lync Server 2013 para que se unan a los tipos de conferencias que ha habilitado?**
    
    De ser así, deberá implementar servidores perimetrales. Al permitir la participación externa en las reuniones, se maximiza la inversión en Lync Server 2013. Por ejemplo, los usuarios con equipos portátiles con Lync Server 2013 pueden unirse a conferencias desde cualquier lugar: en el domicilio, en el aeropuerto o en los sitios de los clientes.
    
    Asimismo, la implementación de servidores perimetrales permite crear relaciones federadas con otras organizaciones, por ejemplo, sus clientes o proveedores. Así los usuarios de dichas organizaciones pueden colaborar con mayor facilidad con sus usuarios.
    
    Para obtener más información sobre la implementación de servidores perimetrales, consulte [Planning for external User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Para obtener más información sobre cómo habilitar el acceso externo para Office Web Apps Server, consulte [Publishing Office Web Apps Server in Lync Server 2013 Using a inverso Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **¿Desea controlar los clientes que pueden unirse a reuniones de Lync Server 2013?**
    
    Si es así, debe configurar la página de participación en la reunión para que solo estén disponibles las opciones de cliente que desea admitir. Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Lync Server 2013 detecta si un cliente ya está instalado en el equipo. A continuación, inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos. La página para participar en reuniones contiene siempre la opción de usar Microsoft Lync Web App. Además de esta opción, puede decidir si desea incluir vínculos para asistentes y versiones anteriores de Communicator. Para obtener más información, consulte [configurar la página de participación en la reunión en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Requisitos de conferencia web en Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [Requisitos de conferencia A/V en Lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Requisitos de conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Planeación de conferencias en Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Lista de comprobación para la implementación de conferencias en Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

