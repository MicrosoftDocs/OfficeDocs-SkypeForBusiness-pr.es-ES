---
title: Requisitos previos y permisos para la configuración de conferencias de acceso telefónico local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40bceea093ff5ffc99f941b27cfc13f2b4eff589
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="bee55-102">Requisitos previos y permisos de configuración para conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bee55-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bee55-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="bee55-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="bee55-104">La Conferencia de acceso telefónico local es un componente opcional de la carga de trabajo de conferencia de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bee55-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="bee55-105">Los componentes que debe instalar para poder configurar la Conferencia de acceso telefónico local se implementan al usar el generador de topologías para diseñar la topología y, a continuación, configurar el grupo de servidores front-end o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bee55-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="bee55-106">En este tema se describe lo que debe hacer antes de poder configurar la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bee55-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="bee55-107">En esta sección se presupone que ha leído las secciones de planeación relacionadas con la carga de trabajo de conferencia y las conferencias de acceso telefónico local en particular.</span><span class="sxs-lookup"><span data-stu-id="bee55-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="bee55-108">Requisitos previos para la configuración de conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bee55-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="bee55-109">La Conferencia de acceso telefónico local requiere los siguientes componentes de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="bee55-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="bee55-110">Servicio de aplicación de comunicaciones unificadas (UCAS) (denominado *servicio de aplicación*)</span><span class="sxs-lookup"><span data-stu-id="bee55-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="bee55-111">Aplicación Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="bee55-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="bee55-112">Aplicación de anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="bee55-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="bee55-113">Página Web de configuración de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bee55-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="bee55-114">Al menos un servidor de mediación de Lync Server 2013 y al menos una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="bee55-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="bee55-115">Estos componentes se implementan cuando se usa el generador de topologías para definir y publicar la topología y, a continuación, implementar un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bee55-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="bee55-116">Si va a implementar la telefonía IP empresarial, debe implementarla antes de configurar la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bee55-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="bee55-117">Si no está implementando la telefonía IP empresarial, puede implementar un servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC) al implementar el grupo de servidores front-end o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bee55-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bee55-118">Si va a actualizar desde Office Communications Server 2007 R2 a Lync Server 2013, implemente conferencias de acceso telefónico local en cada grupo de servidores que planea usar para hospedar conferencias de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bee55-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="bee55-119">Para obtener más información sobre cómo migrar las conferencias de acceso telefónico local, vea <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migración desde Office Communications server 2007 R2 a Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bee55-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="bee55-120">En esta sección se presupone que ha hecho lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bee55-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="bee55-121">Se aplicaron las actualizaciones más recientes en el entorno de Office Communications Server 2007 R2, si va a migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bee55-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="bee55-122">Se usó el generador de topologías para diseñar y configurar la topología.</span><span class="sxs-lookup"><span data-stu-id="bee55-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="bee55-123">Mientras especifica la carga de trabajo de conferencia, seleccionó la opción de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bee55-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="bee55-124">Para obtener información detallada sobre cómo definir la topología, consulte [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="bee55-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="bee55-125">Publicó la topología y configure el grupo de servidores front-end o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bee55-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="bee55-126">Para obtener información detallada sobre la publicación de la topología y la instalación de Lync Server 2013, consulte [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="bee55-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bee55-127">Al instalar su topología publicada, la Página Web de configuración de conferencia de acceso telefónico local se instala en el servidor front-end o el servidor Standard Edition como parte de los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="bee55-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="bee55-128">Si cambia la ruta de acceso al almacén de archivos en el generador de topologías después de implementar Lync Server 2013, deberá reiniciar las aplicaciones del operador de conferencia y del anuncio de conferencia para usar la nueva ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bee55-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="bee55-129">Se implementó la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="bee55-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="bee55-130">Si no está implementando la telefonía IP empresarial, combina un servidor de mediación en el servidor front-end Enterprise Edition o en el servidor Standard Edition, o bien ha implementado un servidor de mediación independiente y ha implementado una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="bee55-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="bee55-131">Para obtener más información sobre la implementación de Enterprise Voice, consulte [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="bee55-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="bee55-132">Para obtener información detallada sobre la instalación de un servidor de mediación independiente y una puerta de enlace RTC, consulte [Deploying Mediation Servers and Defining Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="bee55-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="bee55-133">El siguiente diagrama de flujo muestra los pasos que debe realizar antes de poder configurar la Conferencia de acceso telefónico local y los pasos que debe realizar para configurar la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bee55-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="bee55-134">**Implementación de la Conferencia de acceso telefónico local**</span><span class="sxs-lookup"><span data-stu-id="bee55-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="bee55-135">![Diagrama de flujo de implementación de conferencias de acceso telefónico local](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagrama de flujo de implementación de conferencias de acceso telefónico local")</span><span class="sxs-lookup"><span data-stu-id="bee55-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="bee55-136">Permisos de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bee55-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="bee55-137">Para configurar la Conferencia de acceso telefónico local, debe usar las siguientes herramientas administrativas:</span><span class="sxs-lookup"><span data-stu-id="bee55-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="bee55-138">Panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bee55-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="bee55-139">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="bee55-139">Lync Server Management Shell</span></span>

<span data-ttu-id="bee55-140">Use estas herramientas administrativas para configurar la configuración de conferencias de acceso telefónico local y los planes de marcado, las directivas y otras opciones que requiere la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bee55-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="bee55-141">La configuración de la Conferencia de acceso telefónico local requiere cualquiera de los siguientes roles administrativos, en función de la tarea:</span><span class="sxs-lookup"><span data-stu-id="bee55-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="bee55-142">**CsVoiceAdministrator**   este rol de administrador puede crear, configurar y administrar configuraciones y directivas relacionadas con la voz.</span><span class="sxs-lookup"><span data-stu-id="bee55-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="bee55-143">**CsUserAdministrator**   este rol de administrador puede habilitar y deshabilitar usuarios para Lync Server y asignar directivas existentes, como directivas de conferencia y directivas de PIN, a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bee55-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="bee55-144">**CsAdministrator**   este rol de administrador puede realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bee55-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bee55-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="bee55-145">See Also</span></span>


[<span data-ttu-id="bee55-146">Implementar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bee55-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

