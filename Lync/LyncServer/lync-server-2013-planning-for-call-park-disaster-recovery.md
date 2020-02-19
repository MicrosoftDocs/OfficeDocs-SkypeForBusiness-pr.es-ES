---
title: 'Lync Server 2013: Planeación de la recuperación ante desastres del estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9eb8b87d4485fe1cb02aa8663b362d921a4fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="8b912-102">Planeación de la recuperación ante desastres del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b912-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b912-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="8b912-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="8b912-104">En esta sección se describen algunas formas de preparar la aplicación de estacionamiento de llamadas para la recuperación ante desastres y algunas consideraciones sobre el proceso de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="8b912-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="8b912-105">Preparación para la recuperación ante desastres del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8b912-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="8b912-106">Recuerde las siguientes prácticas recomendadas a la hora de preparar y llevar a cabo procedimientos de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="8b912-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="8b912-107">Planee la recuperación ante desastres cuando realice la planificación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="8b912-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="8b912-108">Para la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder administrar las cargas de trabajo de los servicios de estacionamiento de llamadas en ambos grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="8b912-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="8b912-109">Para obtener más información sobre la planeación de la capacidad de estacionamiento de llamadas, consulte [Capacity Planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="8b912-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="8b912-110">Durante la recuperación ante desastres, los usuarios que hayan sido redirigidos al grupo de servidores de copia de seguridad como parte del proceso de conmutación por error usan el servicio Estacionamiento de llamadas implementado en el grupo de servidores de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8b912-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="8b912-111">Por lo tanto, la compatibilidad con el estacionamiento de llamadas durante la recuperación ante desastres requiere que la aplicación de estacionamiento de llamadas se implemente y esté habilitada tanto en el grupo principal como en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8b912-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="8b912-112">Cada grupo de servidores debe tener un intervalo válido de números de órbita para que lo usen los usuarios hospedados en dicho grupo para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="8b912-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="8b912-113">Mantenga siempre una copia de seguridad independiente de cualquier música personalizada en espera que se haya cargado para el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8b912-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="8b912-114">Estos archivos no se incluyen en la copia de seguridad como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados.</span><span class="sxs-lookup"><span data-stu-id="8b912-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="8b912-115">Consideraciones de recuperación ante desastres del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8b912-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="8b912-116">Solo puede definir un conjunto de opciones de configuración de aplicación de estacionamiento de llamadas y un archivo de audio de música en espera personalizado por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8b912-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="8b912-117">Estas configuraciones incluyen el umbral de tiempo en espera, música en espera, número máximo de intentos de respuesta de llamadas y el URI del tiempo en espera.</span><span class="sxs-lookup"><span data-stu-id="8b912-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="8b912-118">Para ver estas opciones de configuración, ejecute el cmdlet **Get-CsCpsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8b912-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="8b912-119">Para obtener más información sobre el cmdlet **Get-CsCpsConfiguration** , consulte [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8b912-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="8b912-120">Durante la recuperación ante desastres, el estacionamiento de llamadas usa la aplicación estacionamiento de llamadas en el grupo de servidores de copia de seguridad, por lo que no se realiza una copia de seguridad de la configuración del grupo principal.</span><span class="sxs-lookup"><span data-stu-id="8b912-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="8b912-121">Si no se puede recuperar el grupo principal e implementa un nuevo grupo de servidores para reemplazar el grupo principal, se pierde la configuración del grupo principal y es necesario volver a configurar las opciones de estacionamiento de llamadas y los archivos de audio de música en espera personalizados en el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="8b912-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="8b912-122">Si implementa un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente para reemplazar el grupo principal, tendrá que reasignar todos los intervalos de órbita de estacionamiento de llamadas asociados con el grupo principal al FQDN del nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="8b912-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="8b912-123">Para reasignar intervalos de órbitas al nuevo grupo, puede usar el panel de control de Lync Server o el cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="8b912-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="8b912-124">Para obtener más información sobre el cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="8b912-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

