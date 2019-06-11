---
title: 'Lync Server 2013: proceso de programación de reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af97cdbd07603c420780a92fbbe0a03c8a4d0520
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Proceso de programación de reuniones grandes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Puesto que solo se admite una reunión de gran tamaño a la vez en el grupo dedicado de reuniones grandes, recomendamos implementar un proceso de programación de reuniones de gran tamaño para ayudar a evitar conflictos de reuniones grandes. El propósito de este proceso de programación es facilitar la configuración de las reuniones de gran tamaño. Esta capacidad no la proporcionan directamente los clientes de Lync Server o Lync Server. Para implementar este proceso tiene la posibilidad de usar el sistema de vales del equipo de soporte técnico de la organización, si está disponible.

En el caso de los organizadores de reuniones de gran tamaño, la programación de una reunión grande conlleva la realización de los siguientes pasos:

1.  El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.

2.  El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.

3.  Si se aprueba la solicitud, el personal de programación (con credenciales en el grupo dedicado) usa el complemento de reunión en línea para Lync 2013 con Outlook para configurar una reunión en el grupo de reuniones de gran tamaño dedicado. Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.

4.  El organizador de la reunión o el delegado usará Outlook para programar la próxima reunión y agregará a la invitación la dirección URL para unirse a la reunión. Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.
    
    En la siguiente ilustración se muestra un flujo de trabajo de solicitud y aprobación típico para programar reuniones grandes.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d] (images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

