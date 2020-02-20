---
title: 'Lync Server 2013: implementación del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a23190033bca9047a3d1a6d70b914d02017db8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f654d-102">Implementación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f654d-103">_**Última modificación del tema:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="f654d-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="f654d-104">Lync Server 2013, el servidor de chat persistente forma parte de la infraestructura de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f654d-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="f654d-105">La implementación del servidor de chat persistente requiere que:</span><span class="sxs-lookup"><span data-stu-id="f654d-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="f654d-106">Use el generador de topologías para definir o importar y, posteriormente, publicar la topología y los componentes que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="f654d-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="f654d-107">Preparar el entorno para la implementación de componentes del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f654d-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="f654d-108">Instale y configure los componentes del servidor de chat persistente para su implementación.</span><span class="sxs-lookup"><span data-stu-id="f654d-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="f654d-109">El servidor de chat persistente está disponible con Lync Server 2013 Enterprise Edition como un grupo independiente (no combinado con los servidores front-end de Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="f654d-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="f654d-110">El servidor de chat persistente requiere un servidor back-end de SQL Server en el grupo de servidores Enterprise Edition para almacenar el contenido del salón de chat y otros metadatos relevantes.</span><span class="sxs-lookup"><span data-stu-id="f654d-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="f654d-111">Le recomendamos que instale el **PersistentChatStore** en un servidor back-end de SQL Server dedicado, aunque combinar el servidor back-end de Lync Server 2013 y **PersistentChatStore** en la misma instancia de SQL Server es compatible.</span><span class="sxs-lookup"><span data-stu-id="f654d-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="f654d-112">El servidor de chat persistente también se puede implementar con Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f654d-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="f654d-113">En este caso, el servidor front-end de **PersistentChatService** se combina en el equipo Standard Edition y el servidor back-end **PersistentChatStore** se puede implementar en la instancia local de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="f654d-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="f654d-114">Para obtener más información sobre las configuraciones de colocaciones admitidas, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="f654d-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f654d-115">No se admite la alta disponibilidad para el servidor&nbsp;de chat persistente Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f654d-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="f654d-116">El rendimiento y la escala se limitarán.</span><span class="sxs-lookup"><span data-stu-id="f654d-116">Performance and scale will be limited.</span></span> <span data-ttu-id="f654d-117">Además, solo admitimos un nuevo servidor de&nbsp;servidor de chat persistente Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f654d-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="f654d-118">No se admite la actualización de Lync Server 2010, el servidor de chat en grupo a un&nbsp;servidor&nbsp;de chat persistente de Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f654d-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="f654d-119">Si su organización requiere compatibilidad con el cumplimiento, puede instalar el servicio de cumplimiento del servidor de chat persistente en el servidor front-end del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f654d-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="f654d-120">Se necesita una base de datos diferente para el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f654d-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="f654d-121">Como mínimo, cada topología requiere un servidor que tenga instalado Lync Server 2013 y un servidor con software de base de datos de SQL Server instalado.</span><span class="sxs-lookup"><span data-stu-id="f654d-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="f654d-122">Use el generador de topologías para agregar un servidor de chat persistente a las implementaciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f654d-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="f654d-123">Puede elegir agregar uno o varios grupos de servidores de chat persistente con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="f654d-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="f654d-124">Siga las mismas instrucciones de implementación para implementar varios grupos de servidores de chat persistente de la misma manera que lo haría para cualquier grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f654d-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="f654d-125">Para más información, vea [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f654d-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f654d-126">Para obtener más información sobre las topologías disponibles y los requisitos técnicos y de software para instalar el servidor de chat persistente, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación, [Cómo funciona el servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) en la documentación de planeación, la documentación de implementación o las operaciones y el [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md)</span><span class="sxs-lookup"><span data-stu-id="f654d-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f654d-127">Para obtener información detallada acerca de la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="f654d-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f654d-128">Un solo servidor front-end de servidor de chat persistente puede admitir usuarios activos de 20.000.</span><span class="sxs-lookup"><span data-stu-id="f654d-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="f654d-129">Puede tener un grupo de servidores de chat persistente con un máximo de 4 servidores front-end activos que admitan un total de 80.000 usuarios simultáneos.</span><span class="sxs-lookup"><span data-stu-id="f654d-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="f654d-130">El servidor de chat persistente también se admite en un servidor virtual.</span><span class="sxs-lookup"><span data-stu-id="f654d-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="f654d-131">El servidor virtual puede admitir hasta 20 000 usuarios si coincide con las especificaciones del servidor físico.</span><span class="sxs-lookup"><span data-stu-id="f654d-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f654d-132">El servidor de chat persistente debe estar instalado en un sistema de archivos NTFS para ayudar a forzar la seguridad del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="f654d-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="f654d-133">FAT32 no es un sistema de archivos compatible con el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f654d-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f654d-134">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f654d-134">In This Section</span></span>

  - [<span data-ttu-id="f654d-135">Cómo funciona el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="f654d-136">Lista de comprobación para la implementación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="f654d-137">Requisitos técnicos para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="f654d-138">Configurar los sistemas y la infraestructura para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="f654d-139">Adición de un servidor de chat persistente a la implementación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="f654d-140">Instalar el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="f654d-141">Adición de un administrador de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="f654d-142">Configurar el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="f654d-143">Configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f654d-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="f654d-144">Solución de problemas de configuración de servidores de chat persistentes mediante los cmdlets de Windows PowerShell en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="f654d-145">Configurar el servidor de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="f654d-146">Conmutación por recuperación y conmutación por recuperación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f654d-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

