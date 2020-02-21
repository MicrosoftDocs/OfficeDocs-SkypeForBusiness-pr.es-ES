---
title: 'Lync Server 2013: configurar plataformas del sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59aafcda7cbe94401cdbd77479eecf38e3e9e351
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="eed80-102">Configurar plataformas del sistema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed80-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eed80-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="eed80-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="eed80-104">Antes de iniciar la implementación del servidor de chat persistente, debe instalar el sistema operativo necesario en hardware que cumpla los requisitos del sistema en los servidores:</span><span class="sxs-lookup"><span data-stu-id="eed80-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="eed80-105">Para obtener más información sobre el hardware compatible con servidores que ejecutan Lync Server 2013, servidores de bases de datos y servidores de archivos, consulte [Supported hardware for Lync server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="eed80-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="eed80-106">Para obtener más información sobre los sistemas operativos y el software de bases de datos compatibles, consulte [Server Software and Infrastructure support en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="eed80-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="eed80-107">Para obtener más información sobre los requisitos de Windows Update, consulte [soporte y requisitos de servidor adicionales en Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="eed80-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="eed80-108">El servidor front-end del servidor de chat persistente, **PersistentChatService**, se puede implementar en uno o varios equipos independientes de un grupo de servidores de Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="eed80-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="eed80-109">No se pueden combinar en los servidores front-end de Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="eed80-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="eed80-110">El arranque puede implementar el servidor de chat persistente, al igual que ocurre con otras funciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eed80-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="eed80-111">Los **servicios Web de chat persistente para la carga y descarga de archivos**y los **servicios Web de chat persistente para la administración de salones de chat** son componentes Web implementados en los servidores Front-End de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eed80-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="eed80-112">Un solo servidor front-end de servidor de chat persistente puede admitir usuarios activos de 20.000.</span><span class="sxs-lookup"><span data-stu-id="eed80-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="eed80-113">Puede tener un grupo de servidores de chat persistente con hasta 4 servidores front-end activos que admitan un total de 80.000 usuarios simultáneos.</span><span class="sxs-lookup"><span data-stu-id="eed80-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="eed80-114">El servidor back-end de chat persistente, **PersistentChatStore**, almacena las categorías y los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="eed80-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="eed80-115">Le recomendamos que instale el **PersistentChatStore** en un servidor back-end de SQL Server dedicado en el grupo de servidores Enterprise Edition; aunque admitimos combinar servidor back-end de Lync Server 2013 y **PersistentChatStore** en la misma instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eed80-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="eed80-116">Si su organización requiere compatibilidad con el cumplimiento, puede instalarla mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="eed80-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="eed80-117">El servicio de cumplimiento del servidor de chat persistente está instalado en el mismo equipo que el servidor front-end del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="eed80-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="eed80-118">Se necesita una base de datos diferente para el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="eed80-118">A separate database is required for compliance.</span></span> <span data-ttu-id="eed80-119">Para obtener más información sobre los requisitos de cumplimiento para el servidor de chat persistente, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="eed80-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="eed80-120">Como mínimo, cada topología requiere un servidor que tenga instalado Lync Server 2013 y un servidor con software de base de datos de SQL Server instalado.</span><span class="sxs-lookup"><span data-stu-id="eed80-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="eed80-121">El generador de topologías admite varios grupos de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="eed80-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="eed80-122">Siga las mismas instrucciones de implementación para implementar varios grupos de servidores de chat persistente como lo haría para cualquier grupo de servidores desde la implementación de [Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="eed80-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="eed80-123">También puede implementar un servidor de chat persistente con Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="eed80-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="eed80-124">En este caso, el servidor front-end de **PersistentChatService** se combina en el servidor Standard Edition y puede implementar el servidor back-end de **PersistentChatStore** en la instancia local de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="eed80-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eed80-125">No se admite el servidor&nbsp;de chat persistente Standard Edition para alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="eed80-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="eed80-126">El rendimiento y la escala se limitarán.</span><span class="sxs-lookup"><span data-stu-id="eed80-126">Performance and scale will be limited.</span></span> <span data-ttu-id="eed80-127">Además, solo se admiten las implementaciones&nbsp;de servidor de servidor de chat persistente de Standard Edition nuevas.</span><span class="sxs-lookup"><span data-stu-id="eed80-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="eed80-128">No se admite una actualización de Lync Server 2010, servidor de chat en grupo a un servidor&nbsp;&nbsp;de chat persistente de Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="eed80-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eed80-129">Consulta también</span><span class="sxs-lookup"><span data-stu-id="eed80-129">See Also</span></span>


[<span data-ttu-id="eed80-130">Compatibilidad de servidor adicional y requisitos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed80-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="eed80-131">Hardware compatible con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed80-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="eed80-132">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed80-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="eed80-133">Planeación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed80-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="eed80-134">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed80-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

