---
title: Mover los usuarios restantes a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afb495a3500491bb85e9107770ec12f9544832b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="67ad3-102">Mover los usuarios restantes a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ad3-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67ad3-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="67ad3-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="67ad3-104">Puede mover usuarios a la nueva implementación de Lync Server 2013 mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67ad3-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="67ad3-105">Debe cumplir algunos requisitos para garantizar una transición sin problemas a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67ad3-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="67ad3-106">Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [Configure clients for Migration](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="67ad3-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="67ad3-107">Para obtener instrucciones detalladas sobre cómo mover usuarios, consulte [Phase 6: Move users to the Pilot Pool](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="67ad3-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="67ad3-108">No puede usar el complemento usuarios y equipos de Active Directory o las herramientas administrativas de Microsoft Office Communications Server 2007 R2 para mover usuarios de su entorno heredado a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67ad3-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="67ad3-p102">El cmdlet <STRONG>Move-CsLegacyUser</STRONG> requiere que los nombres de usuario se formen debidamente y que no tengan espacios en blanco al principio o al final. No puede transferir cuentas de usuario con el cmdlet <STRONG>Move-CsLegacyUser</STRONG> si tiene espacios en blanco al principio o al final.</span><span class="sxs-lookup"><span data-stu-id="67ad3-p102">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces. You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="67ad3-111">Al mover un usuario a un grupo de servidores de Lync Server 2013, los datos del usuario se mueven a la base de datos back-end asociada al nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="67ad3-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="67ad3-112">Estos datos incluyen las reuniones activas creadas por el usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="67ad3-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="67ad3-113">Por ejemplo, si un usuario heredado ha configurado una conferencia de <STRONG>mi reunión</STRONG> , esa Conferencia seguirá disponible en el nuevo grupo de servidores de Lync Server 2013, una vez que se haya movido al usuario.</span><span class="sxs-lookup"><span data-stu-id="67ad3-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="67ad3-114">Los datos de acceso de esa reunión continuarán siendo los mismos <STRONG>URL de conferencia e ID de conferencia</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="67ad3-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="67ad3-115">La única diferencia es que la Conferencia ahora está hospedada en el grupo de servidores de Lync Server 2013 y no en el grupo de servidores de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="67ad3-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="67ad3-116">El alojamiento de usuarios en Lync Server 2013 no requiere que se implementen clientes actualizados al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="67ad3-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="67ad3-117">La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente.</span><span class="sxs-lookup"><span data-stu-id="67ad3-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="67ad3-118">Tarea posterior a la migración</span><span class="sxs-lookup"><span data-stu-id="67ad3-118">Post Migration Task</span></span>

1.  <span data-ttu-id="67ad3-119">Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada.</span><span class="sxs-lookup"><span data-stu-id="67ad3-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="67ad3-120">Para asegurarse de que las reuniones organizadas por usuarios hospedados en Lync Server 2013 funcionan sin problemas con usuarios federados alojados en Office Communications Server 2007 R2, la Directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.</span><span class="sxs-lookup"><span data-stu-id="67ad3-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="67ad3-121">Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Lync Server 2013 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **true** en el resultado del cmdlet **Get-CsConferencingPolicy** en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67ad3-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="67ad3-122">Para obtener más información sobre cómo configurar la Directiva de conferencias mediante el shell de administración de Lync Server, vea [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67ad3-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

