---
title: Mover los usuarios restantes a Lync Server 2013
description: Mueva los usuarios restantes a Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 291b58d6644f9ac8f10c63f6585ba865602580df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571316"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="8293d-103">Mover los usuarios restantes a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8293d-103">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8293d-104">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8293d-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8293d-105">Puede mover usuarios a la nueva implementación de Lync Server 2013 mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8293d-105">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="8293d-106">Debe cumplir algunos requisitos para garantizar una transición sin problemas a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8293d-106">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="8293d-107">Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [Configure clients for Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="8293d-107">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="8293d-108">Para obtener instrucciones detalladas sobre cómo mover usuarios, consulte [Phase 4: Move test users to the Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8293d-108">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8293d-109">No puede usar el complemento usuarios y equipos de Active Directory o las herramientas administrativas de Lync Server 2010 para mover usuarios de su entorno heredado a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8293d-109">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="8293d-110">Al mover un usuario a un grupo de servidores de Lync Server 2013, los datos del usuario se mueven a la base de datos back-end asociada al nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="8293d-110">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8293d-111">Estos datos incluyen las reuniones activas creadas por el usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="8293d-111">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="8293d-112">Por ejemplo, si un usuario heredado ha configurado una conferencia de <STRONG>mi reunión</STRONG> , esa Conferencia seguirá disponible en el nuevo grupo de servidores de Lync Server 2013 después de que se haya movido al usuario.</span><span class="sxs-lookup"><span data-stu-id="8293d-112">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="8293d-113">Los datos de acceso de esa reunión continuarán siendo los mismos <STRONG>URL de conferencia e ID de conferencia</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8293d-113">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="8293d-114">La única diferencia es que la Conferencia ahora está hospedada en el grupo de servidores de Lync Server 2013 y no en el grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8293d-114">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8293d-115">El alojamiento de usuarios en Lync Server 2013 no requiere que se implementen clientes actualizados al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8293d-115">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="8293d-116">La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente.</span><span class="sxs-lookup"><span data-stu-id="8293d-116">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="8293d-117">Tarea posterior a la migración</span><span class="sxs-lookup"><span data-stu-id="8293d-117">Post Migration Task</span></span>

1.  <span data-ttu-id="8293d-118">Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada.</span><span class="sxs-lookup"><span data-stu-id="8293d-118">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="8293d-119">Para asegurarse de que las reuniones organizadas por usuarios hospedados en Lync Server 2013 funcionan sin problemas con los usuarios federados hospedados en Lync Server 2010, la Directiva de conferencia asignada a los usuarios migrados debe permitir los participantes anónimos.</span><span class="sxs-lookup"><span data-stu-id="8293d-119">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="8293d-120">Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Lync Server 2013 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **true** en el resultado del cmdlet **Get-CsConferencingPolicy** en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8293d-120">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="8293d-121">Para obtener más información sobre cómo configurar la Directiva de conferencias mediante el shell de administración de Lync Server, vea [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8293d-121">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

