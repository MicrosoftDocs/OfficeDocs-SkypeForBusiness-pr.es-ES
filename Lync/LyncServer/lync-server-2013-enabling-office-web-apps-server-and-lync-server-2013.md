---
title: 'Lync Server 2013: habilitación de Office Web Apps Server y Lync Server 2013'
description: 'Lync Server 2013: habilitación de Office Web Apps Server y Lync Server 2013.'
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
ms.openlocfilehash: a1bf4e09dc29bf344b78df50595258f0663cd731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546526"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="8aca9-103">Configuración de la integración con Office Web Apps Server y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aca9-103">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aca9-104">_**Última modificación del tema:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="8aca9-104">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="8aca9-105">Lync Server 2013 usa Office Web Apps Server para controlar las presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="8aca9-105">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="8aca9-106">Para obtener información sobre las ventajas de este enfoque, consulte [información general sobre las conferencias web en Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8aca9-106">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="8aca9-107">Para poder usar estas nuevas funciones, los administradores deben instalar Office Web Apps Server y deben configurar Lync Server 2013 para comunicarse con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="8aca9-107">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="8aca9-108">En esta documentación se proporciona información sobre cómo configurar Lync Server 2013 para que funcione con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="8aca9-108">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="8aca9-109">Lo que no proporciona esta documentación es información sobre cómo instalar Office Web Apps Server en sí mismo; para obtener esa información, vea el sitio web de implementación de Microsoft Office Web Apps en <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="8aca9-109">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="8aca9-110">Esta guía incluye la información de requisitos previos completos para Office Web Apps Server; Tenga en cuenta que Office Web Apps Server debe instalarse en un equipo independiente que no ejecute Lync Server, Microsoft SQL Server o cualquier otra aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="8aca9-110">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="8aca9-111">(No debe tener ninguna versión de Microsoft Office instalada en ese equipo). Cualquier equipo que se use para ejecutar Office Web Apps Server también debe tener instalado un conjunto específico de software (incluido .NET Framework 4,5 y Windows PowerShell 3,0); Estos requisitos, junto con información sobre la configuración de certificados y servicios de Internet Information Server (IIS), se describen en detalle en el sitio web de implementación de Microsoft Office Web Apps en <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="8aca9-111">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8aca9-112">La última iteración de Office Web Apps Server se denomina Office Online Server, que es compatible con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8aca9-112">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="8aca9-113">Para obtener más información, consulte la <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">documentación de Office Online Server</A>.</span><span class="sxs-lookup"><span data-stu-id="8aca9-113">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="8aca9-114">En este documento se tratan las siguientes áreas de temas:</span><span class="sxs-lookup"><span data-stu-id="8aca9-114">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="8aca9-115">Configuración de Lync Server 2013 para que funcione con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="8aca9-115">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="8aca9-116">Publicación de Office Web Apps Server en Lync Server 2013 con un servidor proxy inverso</span><span class="sxs-lookup"><span data-stu-id="8aca9-116">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="8aca9-117">Validación de la configuración de Office Web Apps Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aca9-117">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="8aca9-118">Configuración de clientes de Lync Server 2013 para su uso con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="8aca9-118">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

