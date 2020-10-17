---
title: 'Lync Server 2013: habilitación de Office Web Apps Server y Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89ec4337bd4bc728f9737ecb75bb29075831bc09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528547"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Configuración de la integración con Office Web Apps Server y Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-08-19_

Lync Server 2013 usa Office Web Apps Server para controlar las presentaciones de PowerPoint. Para obtener información sobre las ventajas de este enfoque, consulte [información general sobre las conferencias web en Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Para poder usar estas nuevas funciones, los administradores deben instalar Office Web Apps Server y deben configurar Lync Server 2013 para comunicarse con Office Web Apps Server. En esta documentación se proporciona información sobre cómo configurar Lync Server 2013 para que funcione con Office Web Apps Server. Lo que no proporciona esta documentación es información sobre cómo instalar Office Web Apps Server en sí mismo; para obtener esa información, vea el sitio web de implementación de Microsoft Office Web Apps en <https://go.microsoft.com/fwlink/p/?linkid=257525> . Esta guía incluye la información de requisitos previos completos para Office Web Apps Server; Tenga en cuenta que Office Web Apps Server debe instalarse en un equipo independiente que no ejecute Lync Server, Microsoft SQL Server o cualquier otra aplicación de servidor. (No debe tener ninguna versión de Microsoft Office instalada en ese equipo). Cualquier equipo que se use para ejecutar Office Web Apps Server también debe tener instalado un conjunto específico de software (incluido .NET Framework 4,5 y Windows PowerShell 3,0); Estos requisitos, junto con información sobre la configuración de certificados y servicios de Internet Information Server (IIS), se describen en detalle en el sitio web de implementación de Microsoft Office Web Apps en <https://go.microsoft.com/fwlink/p/?linkid=257525> .

<div>


> [!NOTE]  
> La última iteración de Office Web Apps Server se denomina Office Online Server, que es compatible con Lync Server 2013. Para obtener más información, consulte la <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">documentación de Office Online Server</A>.



</div>

En este documento se tratan las siguientes áreas de temas:

  - [Configuración de Lync Server 2013 para que funcione con Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Publicación de Office Web Apps Server en Lync Server 2013 con un servidor proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Validación de la configuración de Office Web Apps Server en Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Configuración de clientes de Lync Server 2013 para su uso con Office Web Apps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

