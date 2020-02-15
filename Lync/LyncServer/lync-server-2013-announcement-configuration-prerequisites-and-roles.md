---
title: 'Lync Server 2013: requisitos previos y roles de configuración del anuncio'
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
ms.openlocfilehash: 09a7a8a17e3431c382ce4f49534336d266bbaa13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="49916-102">Requisitos previos y roles de configuración del anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49916-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49916-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="49916-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="49916-104">El anuncio es una característica de administración de llamadas de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="49916-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="49916-105">En este tema se describe lo que necesita tener en su ubicación antes de poder configurar el anuncio y las asignaciones de roles que necesita para realizar tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="49916-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="49916-106">En esta sección se da por sentado que ha leído la documentación de planeación relacionada con el anuncio (consulte [planeación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="49916-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="49916-107">Requisitos previos de configuración del anuncio</span><span class="sxs-lookup"><span data-stu-id="49916-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="49916-108">La aplicación de anuncio requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="49916-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="49916-109">Servicio de aplicación</span><span class="sxs-lookup"><span data-stu-id="49916-109">Application service</span></span>

  - <span data-ttu-id="49916-110">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="49916-110">Response Group application</span></span>

  - <span data-ttu-id="49916-111">Almacenamiento de archivos, para los archivos de audio</span><span class="sxs-lookup"><span data-stu-id="49916-111">File Store, to hold audio files</span></span>

<span data-ttu-id="49916-112">Todos estos componentes se instalan de forma predeterminada al implementar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="49916-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="49916-113">Roles de configuración de anuncios</span><span class="sxs-lookup"><span data-stu-id="49916-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="49916-114">Puede usar las siguientes herramientas administrativas para configurar anuncios:</span><span class="sxs-lookup"><span data-stu-id="49916-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="49916-115">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="49916-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="49916-116">Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="49916-116">Lync Server Management Shell</span></span>

<span data-ttu-id="49916-117">La configuración de la aplicación de anuncio requiere uno de los siguientes roles administrativos:</span><span class="sxs-lookup"><span data-stu-id="49916-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="49916-118">**CsVoiceAdministrator**   este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz, incluida la configuración del anuncio.</span><span class="sxs-lookup"><span data-stu-id="49916-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="49916-119">**CsServerAdministrator**   este rol de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios, además de configurar todas las opciones de anuncio.</span><span class="sxs-lookup"><span data-stu-id="49916-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="49916-120">**CsAdministrator**   este rol de administrador puede realizar todas las tareas administrativas y modificar toda la configuración.</span><span class="sxs-lookup"><span data-stu-id="49916-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="49916-121">**CsViewOnlyAdministrator**   este rol de administrador puede ver la implementación para supervisar el estado de la implementación.</span><span class="sxs-lookup"><span data-stu-id="49916-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49916-122">Para obtener más información sobre los derechos de usuario administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="49916-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49916-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="49916-123">See Also</span></span>


[<span data-ttu-id="49916-124">Implementar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49916-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="49916-125">Planeación de características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49916-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

