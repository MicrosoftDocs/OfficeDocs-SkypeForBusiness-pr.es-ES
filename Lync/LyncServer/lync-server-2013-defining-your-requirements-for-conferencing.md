---
title: 'Lync Server 2013: Definición de requisitos para conferencias'
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
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definición de requisitos para conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Al determinar qué funciones de conferencia se van a implementar, es necesario tener en cuenta las características que quiere poner a disposición de los usuarios, así como la capacidad de ancho de banda de la red. La siguiente lista de preguntas le guiará a través del proceso de planeación de conferencias para determinar qué características de las conferencias debe implementar, en función de los requisitos de la organización.

  - **¿Desea habilitar la conferencia web, que incluye la colaboración con documentos y el uso compartido de aplicaciones?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end en Microsoft Lync Server 2013, la herramienta de planeación o el generador de topología. Cuando se habilita la Conferencia, se habilitan las conferencias web y A/V.
    
    El uso compartido de aplicaciones requiere y utiliza más ancho de banda de red que la colaboración en documentos. Lync Server 2013 proporciona un mecanismo de limitación para controlar cada sesión de uso compartido de aplicaciones. De forma predeterminada, esto se establece en 1,5 KB por segundo para cada sesión.
    
    Si no desea habilitar el uso compartido de aplicaciones pero desea la colaboración de documentos, puede habilitar la Conferencia y usar las directivas de reunión para deshabilitar el uso compartido de aplicaciones. Para obtener más información sobre cómo configurar directivas de reunión, consulte [directivas de conferencia en Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Para que los usuarios puedan compartir presentaciones de PowerPoint, necesita configurar Office Web Apps Server. Para obtener más información sobre cómo configurar Office Web Apps Server, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **¿Desea habilitar las conferencias A/V?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end en Lync Server 2013, la herramienta de planeación o en el generador de topología. Cuando se habilita la Conferencia, se habilitan las conferencias web y A/V.
    
    Las conferencias A/V requieren y usan más ancho de banda de la red que las conferencias web (que incluyen colaboración de documentos y uso compartido de aplicaciones). Si no desea habilitar una conferencia a/V pero desea habilitar las conferencias web, puede habilitar la Conferencia y usar las directivas de reunión para deshabilitar las conferencias de A/V.
    
    Si desea habilitar conferencias de audio pero no videoconferencias, puede habilitar conferencias A/V y usar directivas de reunión para evitar las videoconferencias. Como alternativa, puede habilitar la conferencia A/V y habilitar únicamente determinados usuarios para que inicien o participen en conferencias A/V.
    
    <div>
    

    > [!NOTE]  
    > No se necesita la telefonía IP empresarial para usar las conferencias A/V. Si habilita las conferencias A/V, los usuarios que dispongan de dispositivos de audio podrán agregar audio a las conferencias, aun cuando se use una PBX como solución de telefonía.

    
    </div>

  - **¿Desea permitir que los usuarios se unan a la parte de audio de las conferencias al usar un teléfono PSTN?**
    
    Si es así, implemente y habilite la conferencia de acceso telefónico. Los usuarios invitados, tanto dentro como fuera de su organización, puede unirse entonces a la parte de audio de las conferencias por medio de un teléfono RTC.

  - **¿Desea permitir que los usuarios externos con clientes de Lync Server 2013 se unan a los tipos de conferencias que haya habilitado?**
    
    Si es así, debe implementar servidores perimetrales. Al permitir la participación externa en las reuniones, podrá maximizar su inversión en Lync Server 2013. Por ejemplo, los usuarios con equipos portátiles con Lync Server 2013 pueden unirse a las conferencias desde cualquier lugar: en casa, en el aeropuerto o en los sitios de los clientes.
    
    Además, con los servidores perimetrales implementados, puede crear relaciones federadas con otras organizaciones, como los clientes o los proveedores, y los usuarios de esas organizaciones pueden colaborar más fácilmente con los usuarios.
    
    Para obtener más información sobre la implementación de servidores perimetrales, vea [planear el acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Para obtener detalles sobre cómo habilitar el acceso externo para Office Web Apps Server, consulte [publicación de Office Web Apps Server en Lync Server 2013 con un servidor proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **¿Desea controlar los clientes que pueden unirse a reuniones de Lync Server 2013?**
    
    En caso afirmativo, necesitará configurar una página de participación en la reunión para que solo estén disponibles las opciones de cliente que quiera permitir. Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Lync Server 2013 detecta si un cliente ya está instalado en el equipo. Luego inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos. La página de la combinación de reuniones siempre contiene la opción de usar Microsoft Lync Web App. Además de esta opción, puede decidir si desea incluir vínculos para asistentes y para versiones anteriores de Communicator. Para obtener más información, vea [configurar la página de combinación de reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Requisitos de conferencia web en Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [Requisitos de conferencia A/V en Lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Requisitos de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificar conferencias en Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Lista de comprobación para la implementación de conferencias en Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

