---
title: 'Lync Server 2013: requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39fd811a39a1221ec522c7ca3874d0de4f340b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="5f0d3-102">Requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f0d3-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f0d3-103">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="5f0d3-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="5f0d3-104">El estacionamiento de llamadas es una característica de administración de llamadas que se instala de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="5f0d3-105">En este tema se describe lo que necesita tener en su ubicación antes de poder configurar el estacionamiento de llamadas y los derechos de usuario que necesita para realizar las tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f0d3-106">No se realiza una copia de seguridad de los archivos de música en espera personalizados de la aplicación de estacionamiento de llamadas como parte del proceso de recuperación ante desastres de Lync Server 2013, y los archivos se perderán si los archivos cargados en el grupo están dañados, dañados o borrados.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="5f0d3-107">Guarde siempre una copia de seguridad independiente de los archivos de música en espera que haya cargado para Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="5f0d3-108">En esta sección se da por sentado que ha leído la documentación de planeación relacionada con el parque de llamadas (consulte [planeación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="5f0d3-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="5f0d3-109">Requisitos previos de configuración del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="5f0d3-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="5f0d3-110">El estacionamiento de llamadas requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="5f0d3-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="5f0d3-111">Servicio de aplicación</span><span class="sxs-lookup"><span data-stu-id="5f0d3-111">Application service</span></span>

  - <span data-ttu-id="5f0d3-112">Aplicación Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="5f0d3-112">Call Park application</span></span>

<span data-ttu-id="5f0d3-113">Estos componentes se instalan automáticamente al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="5f0d3-114">Si desea que los autores de las llamadas oigan música mientras la llamada está estacionada, también se requiere un archivo de música en espera.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="5f0d3-115">El archivo de música en espera predeterminado se instala automáticamente al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="5f0d3-116">Puede sustituir el archivo predeterminado por su propio archivo de música en espera.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="5f0d3-117">El estacionamiento de llamadas usa el almacén de archivos para guardar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="5f0d3-118">Derechos de usuario de configuración del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="5f0d3-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="5f0d3-119">Puede usar las siguientes herramientas administrativas para configurar el estacionamiento de llamadas:</span><span class="sxs-lookup"><span data-stu-id="5f0d3-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="5f0d3-120">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5f0d3-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="5f0d3-121">Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5f0d3-121">Lync Server Management Shell</span></span>

<span data-ttu-id="5f0d3-122">Use estas herramientas para configurar la tabla de órbitas de estacionamiento de llamadas y configurar otras opciones que usa el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="5f0d3-123">La configuración del estacionamiento de llamadas requiere cualquiera de los siguientes roles administrativos, en función de la tarea:</span><span class="sxs-lookup"><span data-stu-id="5f0d3-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="5f0d3-124">**CsVoiceAdministrator:** Este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="5f0d3-125">**CsUserAdministrator:** Este rol de administrador puede habilitar el estacionamiento de llamadas en la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="5f0d3-126">De igual modo, permite el acceso de vista de solo lectura a todas las configuraciones de voz.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="5f0d3-127">**CsServerAdministrator:** Este rol de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="5f0d3-128">**CsAdministrator:** Este rol de administrador puede realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f0d3-129">Para obtener más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="5f0d3-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f0d3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f0d3-130">See Also</span></span>


[<span data-ttu-id="5f0d3-131">Implementar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f0d3-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="5f0d3-132">Planeación de características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f0d3-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

