---
title: Requisitos previos y derechos de usuario para la configuración de la llamada grupal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2eb0af5b78d5d391ba055e557ad71da79484b5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="09227-102">Requisitos previos y derechos de usuario para la configuración de la llamada grupal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09227-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09227-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="09227-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="09227-104">La recogida de llamada grupal es una característica de administración de llamadas que se instala de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="09227-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="09227-105">En este tema se describe lo que debe tener en cuenta antes de poder configurar la recogida de llamadas grupales y los derechos de usuario que necesita para realizar las tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="09227-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="09227-106">En esta sección se presupone que ha leído la documentación de planificación relacionada con la recogida de llamadas grupales (consulte [planificación de la recogida de llamadas grupales en Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="09227-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="09227-107">Requisitos previos de configuración de la llamada grupal</span><span class="sxs-lookup"><span data-stu-id="09227-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="09227-108">La recogida de llamadas grupales requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="09227-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="09227-109">Servicio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="09227-109">Application service</span></span>

  - <span data-ttu-id="09227-110">Aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="09227-110">Call Park application</span></span>

<span data-ttu-id="09227-111">Estos componentes se instalan automáticamente al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="09227-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="09227-112">Configuración de la recogida de llamada grupal derechos de usuario</span><span class="sxs-lookup"><span data-stu-id="09227-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="09227-113">Use las siguientes herramientas administrativas para configurar la recogida de llamadas grupales:</span><span class="sxs-lookup"><span data-stu-id="09227-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="09227-114">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="09227-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="09227-115">Herramienta del kit de recursos de SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="09227-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="09227-116">Use el shell de administración de Lync Server para crear y administrar grupos de recogida de llamadas en la tabla de llamadas en órbita de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="09227-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="09227-117">Use la herramienta del kit de recursos de SEFAUtil para asignar un grupo de recogida de llamadas y habilitar la recogida de llamadas grupales para los usuarios o para deshabilitar la recogida de llamadas grupales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="09227-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="09227-118">La configuración de la recogida de llamadas de grupo requiere cualquiera de los siguientes roles administrativos, en función de la tarea:</span><span class="sxs-lookup"><span data-stu-id="09227-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="09227-119">**CsVoiceAdministrator:** Esta función de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con las voz.</span><span class="sxs-lookup"><span data-stu-id="09227-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="09227-120">**CsUserAdministrator:** Este rol de administrador puede habilitar la recogida de llamadas grupales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="09227-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="09227-121">Esta función de administrador también tiene acceso de vista de solo lectura a todas las configuraciones de voz.</span><span class="sxs-lookup"><span data-stu-id="09227-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="09227-122">**CsServerAdministrator:** Esta función de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios.</span><span class="sxs-lookup"><span data-stu-id="09227-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="09227-123">**CsAdministrator:** Esta función de administrador puede realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="09227-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="09227-124">Para obtener más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="09227-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09227-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="09227-125">See Also</span></span>


[<span data-ttu-id="09227-126">Implementación de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09227-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="09227-127">Planeamiento de las características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09227-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

