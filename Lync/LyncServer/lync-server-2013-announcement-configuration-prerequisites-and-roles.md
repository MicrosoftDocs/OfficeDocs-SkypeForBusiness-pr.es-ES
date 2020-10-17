---
title: 'Lync Server 2013: requisitos previos y roles de configuración del anuncio'
description: 'Lync Server 2013: requisitos previos y roles de configuración de anuncio.'
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
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561896"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="33c67-103">Requisitos previos y roles de configuración del anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33c67-103">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33c67-104">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="33c67-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="33c67-105">El anuncio es una característica de administración de llamadas de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="33c67-105">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="33c67-106">En este tema se describe lo que necesita tener en su ubicación antes de poder configurar el anuncio y las asignaciones de roles que necesita para realizar tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="33c67-106">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="33c67-107">En esta sección se da por sentado que ha leído la documentación de planeación relacionada con el anuncio (consulte [planeación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="33c67-107">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="33c67-108">Requisitos previos de configuración del anuncio</span><span class="sxs-lookup"><span data-stu-id="33c67-108">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="33c67-109">La aplicación de anuncio requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="33c67-109">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="33c67-110">Servicio de aplicación</span><span class="sxs-lookup"><span data-stu-id="33c67-110">Application service</span></span>

  - <span data-ttu-id="33c67-111">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="33c67-111">Response Group application</span></span>

  - <span data-ttu-id="33c67-112">Almacenamiento de archivos, para los archivos de audio</span><span class="sxs-lookup"><span data-stu-id="33c67-112">File Store, to hold audio files</span></span>

<span data-ttu-id="33c67-113">Todos estos componentes se instalan de forma predeterminada al implementar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="33c67-113">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="33c67-114">Roles de configuración de anuncios</span><span class="sxs-lookup"><span data-stu-id="33c67-114">Announcement Configuration Roles</span></span>

<span data-ttu-id="33c67-115">Puede usar las siguientes herramientas administrativas para configurar anuncios:</span><span class="sxs-lookup"><span data-stu-id="33c67-115">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="33c67-116">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="33c67-116">Lync Server Control Panel</span></span>

  - <span data-ttu-id="33c67-117">Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="33c67-117">Lync Server Management Shell</span></span>

<span data-ttu-id="33c67-118">La configuración de la aplicación de anuncio requiere uno de los siguientes roles administrativos:</span><span class="sxs-lookup"><span data-stu-id="33c67-118">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="33c67-119">**CsVoiceAdministrator**     Este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz, incluida la configuración del anuncio.</span><span class="sxs-lookup"><span data-stu-id="33c67-119">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="33c67-120">**CsServerAdministrator**     Esta función de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios, además de configurar todas las opciones de anuncio.</span><span class="sxs-lookup"><span data-stu-id="33c67-120">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="33c67-121">**CsAdministrator**     Este rol de administrador puede realizar todas las tareas administrativas y modificar toda la configuración.</span><span class="sxs-lookup"><span data-stu-id="33c67-121">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="33c67-122">**CsViewOnlyAdministrator**     Este rol de administrador puede ver la implementación para supervisar el estado de la implementación.</span><span class="sxs-lookup"><span data-stu-id="33c67-122">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33c67-123">Para obtener más información sobre los derechos de usuario administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="33c67-123">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33c67-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33c67-124">See Also</span></span>


[<span data-ttu-id="33c67-125">Implementar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33c67-125">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="33c67-126">Planeación de características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33c67-126">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

