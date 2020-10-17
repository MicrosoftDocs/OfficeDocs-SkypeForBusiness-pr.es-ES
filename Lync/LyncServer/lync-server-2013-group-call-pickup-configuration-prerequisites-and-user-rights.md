---
title: Requisitos previos y derechos de usuario para la configuración de llamada de grupo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b15be02b48c5e3f95a9b05475bea42284ec275
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498797"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="8d3a9-102">Requisitos previos de configuración de llamada de grupo y derechos de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d3a9-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d3a9-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="8d3a9-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="8d3a9-104">La recogida de llamadas grupales es una característica de administración de llamadas que se instala de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="8d3a9-105">En este tema se describe lo que necesita tener en su ubicación antes de poder configurar la atención de llamadas grupales y los derechos de usuario necesarios para realizar tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="8d3a9-106">En esta sección se da por sentado que ha leído la documentación de planeación relacionada con la recogida de llamadas de grupo (consulte [Planning for Group Call pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="8d3a9-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="8d3a9-107">Requisitos previos de configuración de llamada de grupo</span><span class="sxs-lookup"><span data-stu-id="8d3a9-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="8d3a9-108">La recogida de llamadas de grupo requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="8d3a9-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="8d3a9-109">Servicio de aplicación</span><span class="sxs-lookup"><span data-stu-id="8d3a9-109">Application service</span></span>

  - <span data-ttu-id="8d3a9-110">Aplicación Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8d3a9-110">Call Park application</span></span>

<span data-ttu-id="8d3a9-111">Estos componentes se instalan automáticamente al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="8d3a9-112">Derechos de usuario de configuración de llamada de grupo</span><span class="sxs-lookup"><span data-stu-id="8d3a9-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="8d3a9-113">Puede usar las siguientes herramientas administrativas para configurar la recogida de llamadas de Grupo:</span><span class="sxs-lookup"><span data-stu-id="8d3a9-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="8d3a9-114">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="8d3a9-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="8d3a9-115">Herramienta del kit de recursos de SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="8d3a9-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="8d3a9-116">Use el shell de administración de Lync Server para crear y administrar grupos de recogida de llamadas en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="8d3a9-117">Use la herramienta del kit de recursos de SEFAUtil para asignar un grupo de atención de llamadas y habilitar la atención de llamadas grupales para los usuarios o para deshabilitar la atención de llamadas grupales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="8d3a9-118">La configuración de la recogida de llamadas de grupo requiere cualquiera de los siguientes roles administrativos, en función de la tarea:</span><span class="sxs-lookup"><span data-stu-id="8d3a9-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="8d3a9-119">**CsVoiceAdministrator:** Este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="8d3a9-120">**CsUserAdministrator:** Este rol de administrador puede habilitar la recepción de llamadas grupales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="8d3a9-121">De igual modo, permite el acceso de vista de solo lectura a todas las configuraciones de voz.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="8d3a9-122">**CsServerAdministrator:** Este rol de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="8d3a9-123">**CsAdministrator:** Este rol de administrador puede realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8d3a9-124">Para obtener más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="8d3a9-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d3a9-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d3a9-125">See Also</span></span>


[<span data-ttu-id="8d3a9-126">Implementar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d3a9-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="8d3a9-127">Planeación de características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d3a9-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

