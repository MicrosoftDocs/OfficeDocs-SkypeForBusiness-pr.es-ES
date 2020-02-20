---
title: 'Lync Server 2013: configuración de clientes para su uso con Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10ec5ddaca5a8409a18504cb73912d107c9a6455
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Configuración de clientes de Lync Server 2013 para su uso con Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

Si quiere que los usuarios experimenten todas las capacidades de Office Web App Server, debe actualizar esos usuarios a Microsoft Lync 2013; solo los usuarios de Lync 2013 podrán realizar tareas como desplazarse por las diapositivas de PowerPoint independientemente de la presentación real de PowerPoint. (Es decir, estos usuarios pueden mirar en cualquier diapositiva de la presentación en cualquier momento, sin interferir en ninguna forma con la presentación real). Los usuarios que no usan Lync 2013 aún podrán unirse a conferencias en línea y ver la presentación de PowerPoint; sin embargo, no podrán desplazarse por las diapositivas de forma independiente, ni podrán ver las transiciones de diapositivas ni ver vídeos incrustados.

Tenga en cuenta que estas capacidades siempre estarán disponibles para los usuarios de Lync 2013; Esto es así incluso si el moderador de PowerPoint ejecuta Microsoft Lync 2010. Si un usuario que ejecuta Lync 2010 hospeda una presentación de PowerPoint, Lync Server 2013 se coordinará con Office Web Apps Server para asegurarse de que los usuarios de Lync 2013 verán la versión de Office Web Apps Server de la presentación. Office Web Apps Server no proporciona servicios de PowerPoint a los usuarios que ejecutan clientes que no sean Lync 2013. En su lugar, estos usuarios se conectan al servicio del servidor de conferencia y ven las presentaciones de PowerPoint de la misma manera que en Microsoft Lync Server 2010. Esto también significa que estos usuarios solo tendrán acceso a las funciones más limitadas que ofrece Lync Server 2010.

Aunque no se requiere ninguna configuración de cliente para Office Web Apps Server (aparte de la actualización de usuarios a Lync 2013), se recomienda que los asistentes a la Conferencia se actualicen a Internet Explorer 9. Aunque se puede tener acceso a las conferencias con Internet Explorer 8, hay algunas limitaciones en el uso de ese explorador Web. Por ejemplo, los usuarios de Internet Explorer 8 no podrán cambiar el tamaño de la fase de PowerPoint a un tamaño personalizado; en su lugar, se limitarán a usar uno de los tres tamaños de fase predefinidos. De forma similar, los usuarios de Internet Explorer 8 no podrán reproducir archivos multimedia.

</div>

<span> </span>

</div>

</div>

</div>

