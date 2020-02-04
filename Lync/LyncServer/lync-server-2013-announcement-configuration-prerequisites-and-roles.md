---
title: 'Lync Server 2013: Requisitos previos y roles para configurar anuncios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42cbc1429d4e27ee172dc1dacf6b86fa6ac243d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="00187-102">Requisitos previos y roles para configurar anuncios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00187-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00187-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="00187-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="00187-104">El anuncio es una característica de administración de llamadas de voz de empresa.</span><span class="sxs-lookup"><span data-stu-id="00187-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="00187-105">En este tema se describe lo que debe tener en cuenta antes de poder configurar el anuncio y las asignaciones de roles que necesita para realizar tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="00187-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="00187-106">En esta sección se supone que ha leído la documentación de planeación relacionada con el anuncio (vea [planear las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="00187-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="00187-107">Requisitos previos de configuración del anuncio</span><span class="sxs-lookup"><span data-stu-id="00187-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="00187-108">La aplicación de anuncios requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="00187-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="00187-109">Servicio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="00187-109">Application service</span></span>

  - <span data-ttu-id="00187-110">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="00187-110">Response Group application</span></span>

  - <span data-ttu-id="00187-111">Almacén de archivos, para mantener los archivos de audio</span><span class="sxs-lookup"><span data-stu-id="00187-111">File Store, to hold audio files</span></span>

<span data-ttu-id="00187-112">Todos estos componentes se instalan de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="00187-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="00187-113">Roles de configuración de anuncio</span><span class="sxs-lookup"><span data-stu-id="00187-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="00187-114">Puede usar las siguientes herramientas administrativas para configurar anuncios:</span><span class="sxs-lookup"><span data-stu-id="00187-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="00187-115">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="00187-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="00187-116">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="00187-116">Lync Server Management Shell</span></span>

<span data-ttu-id="00187-117">La configuración de la aplicación de anuncio requiere uno de los siguientes roles administrativos:</span><span class="sxs-lookup"><span data-stu-id="00187-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="00187-118">**CsVoiceAdministrator**   esta función de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz, incluyendo la configuración de la presentación.</span><span class="sxs-lookup"><span data-stu-id="00187-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="00187-119">**CsServerAdministrator**   esta función de administrador puede administrar, supervisar y solucionar problemas con servidores y servicios, y configurar todas las opciones de presentación.</span><span class="sxs-lookup"><span data-stu-id="00187-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="00187-120">**CsAdministrator**   esta función de administrador puede realizar todas las tareas administrativas y modificar toda la configuración.</span><span class="sxs-lookup"><span data-stu-id="00187-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="00187-121">**CsViewOnlyAdministrator**   este rol de administrador puede ver la implementación para supervisar el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="00187-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00187-122">Para obtener más información sobre los derechos de usuario administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="00187-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00187-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="00187-123">See Also</span></span>


[<span data-ttu-id="00187-124">Implementación de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00187-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="00187-125">Planeamiento de las características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00187-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

