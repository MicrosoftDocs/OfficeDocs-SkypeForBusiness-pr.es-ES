---
title: Mover los usuarios restantes a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a728afae37c2e8d317cd6c75872c75d358226475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="e6dae-102">Mover los usuarios restantes a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6dae-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6dae-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="e6dae-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="e6dae-104">Puede mover usuarios a la nueva implementación de Lync Server 2013 con el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6dae-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="e6dae-105">Debe cumplir algunos requisitos para garantizar una transición sin problemas a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6dae-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="e6dae-106">Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [configurar clientes para la migración](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="e6dae-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="e6dae-107">Para conocer los pasos detallados sobre cómo mover usuarios, consulte [fase 6: mover usuarios a la agrupación piloto](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e6dae-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6dae-108">No puede usar el complemento usuarios y equipos de Active Directory o las herramientas administrativas de Microsoft Office Communications Server 2007 R2 para mover usuarios de su entorno heredado a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6dae-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6dae-109">El cmdlet <STRONG>Move-CsLegacyUser</STRONG> requiere que los nombres de usuario estén formados correctamente y no tengan espacios iniciales ni finales.</span><span class="sxs-lookup"><span data-stu-id="e6dae-109">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces.</span></span> <span data-ttu-id="e6dae-110">No puede mover una cuenta de usuario mediante el cmdlet <STRONG>Move-CsLegacyUser</STRONG> si contiene espacios iniciales o finales.</span><span class="sxs-lookup"><span data-stu-id="e6dae-110">You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="e6dae-111">Al mover un usuario a un grupo de servidores de Lync Server 2013, los datos del usuario se mueven a la base de datos back-end asociada con el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="e6dae-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6dae-112">Esto incluye las reuniones activas creadas por el usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="e6dae-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="e6dae-113">Por ejemplo, si un usuario heredado ha configurado una conferencia de <STRONG>reunión</STRONG> , dicha conferencia seguirá estando disponible en el nuevo grupo de Lync Server 2013, después de que se haya movido al usuario.</span><span class="sxs-lookup"><span data-stu-id="e6dae-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="e6dae-114">Los detalles para acceder a la reunión seguirán siendo la misma <STRONG>dirección URL de conferencia y</STRONG>el mismo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e6dae-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="e6dae-115">La única diferencia es que la Conferencia ahora está hospedada en el grupo de servidores de Lync Server 2013, y no en el grupo de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e6dae-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e6dae-116">El alojamiento de usuarios en Lync Server 2013 no requiere que implemente clientes actualizados al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="e6dae-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="e6dae-117">Las nuevas funcionalidades estarán disponibles solo para los usuarios cuando se actualicen al nuevo software de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6dae-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="e6dae-118">Tarea posterior a la migración</span><span class="sxs-lookup"><span data-stu-id="e6dae-118">Post Migration Task</span></span>

1.  <span data-ttu-id="e6dae-119">Después de mover usuarios, Compruebe la Directiva de conferencia que tiene asignada.</span><span class="sxs-lookup"><span data-stu-id="e6dae-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="e6dae-120">Para asegurarse de que las reuniones organizadas por usuarios alojados en Lync Server 2013 funcionan sin problemas con usuarios federados alojados en Office Communications Server 2007 R2, la Directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.</span><span class="sxs-lookup"><span data-stu-id="e6dae-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="e6dae-121">Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Lync Server 2013 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **verdadero** en el resultado de el cmdlet **Get-CsConferencingPolicy** en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6dae-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="e6dae-122">Para obtener detalles sobre la configuración de la Directiva de Conferencia mediante el shell de administración de Lync Server, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6dae-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

