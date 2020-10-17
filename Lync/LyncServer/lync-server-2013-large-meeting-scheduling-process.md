---
title: 'Lync Server 2013: proceso de programación de reuniones grandes'
description: 'Lync Server 2013: proceso de programación de reuniones grandes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d383b6da96fb7d36e031485feac2ff927df347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557596"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Proceso de programación de reuniones grandes en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Como solo se admite una única reunión grande en el grupo de servidores exclusivo de la reunión grande, recomendamos que implemente un proceso de programación de reunión grande para que le sea más fácil evitar conflictos en dicha reunión. El objetivo de la programación es facilitar la configuración de las reuniones grandes. Esta capacidad no la proporcionan directamente los clientes de Lync Server o Lync Server. Para implementar este proceso tiene la posibilidad de usar el sistema de vales del equipo de soporte técnico de la organización, si está disponible.

Los organizadores de reuniones grandes que deseen programar una de estas reuniones deben ejecutar los pasos siguientes:

1.  El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.

2.  El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.

3.  Si se aprueba la solicitud, el personal de programación (con credenciales en el grupo dedicado) usa el complemento de reunión en línea para Lync 2013 con Outlook para configurar una reunión en el grupo de reuniones de gran tamaño dedicado. Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.

4.  El organizador de la reunión o el delegado usa Outlook para programar la próxima reunión, agregando la dirección URL para unirse a la reunión a la invitación a la reunión. Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.
    
    En la figura siguiente se muestra una solicitud y un flujo de trabajo de aprobación típicos para programar grandes reuniones.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

