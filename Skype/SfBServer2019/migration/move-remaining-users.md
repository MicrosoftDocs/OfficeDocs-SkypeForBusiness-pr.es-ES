---
title: Mover el resto de usuarios
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Puede mover usuarios a la nueva implementación de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype Empresarial Server 2019. Para obtener más información acerca de los requisitos previos para completar los procedimientos de este tema, vea Configurar clientes para la migración. Para obtener instrucciones detalladas sobre cómo mover usuarios, consulte Fase 4: Mover usuarios de prueba al grupo piloto.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753718"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="b5f2b-106">Mover los usuarios restantes a Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="b5f2b-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="b5f2b-107">Puede mover usuarios a la nueva implementación de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b5f2b-108">Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="b5f2b-109">Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [Configurar clientes para la migración.](configure-clients-for-migration.md)</span><span class="sxs-lookup"><span data-stu-id="b5f2b-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="b5f2b-110">Para obtener instrucciones detalladas sobre cómo mover usuarios, vea [fase 4:](phase-4-move-test-users-to-the-pilot-pool.md)Mover usuarios de prueba al grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b5f2b-111">No puede usar el complemento Usuarios y equipos de Active Directory ni las herramientas administrativas heredadas para mover usuarios de su entorno heredado a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="b5f2b-112">Cuando mueve un usuario a un grupo de Skype Empresarial Server 2019, los datos del usuario se mueven a la base de datos back-end asociada con el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b5f2b-113">Estos datos incluyen las reuniones activas creadas por el usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="b5f2b-114">Por ejemplo, si un usuario  heredado ha configurado una conferencia de mi reunión, esa conferencia seguirá estando disponible en el nuevo grupo de Skype Empresarial Server 2019 después de que se haya movido el usuario.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="b5f2b-115">Los datos de acceso de esa reunión continuarán siendo los mismos **URL de conferencia e ID de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="b5f2b-116">La única diferencia es que la conferencia ahora se hospeda en el grupo de Skype Empresarial Server 2019 y no en el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b5f2b-117">No es necesario que implemente clientes actualizados al mismo tiempo en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="b5f2b-118">La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="b5f2b-119">Tarea posterior a la migración</span><span class="sxs-lookup"><span data-stu-id="b5f2b-119">Post migration task</span></span>

1. <span data-ttu-id="b5f2b-120">Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="b5f2b-121">Para asegurarse de que las reuniones organizadas por usuarios que se encuentran en Skype Empresarial Server 2019 funcionan sin problemas con los usuarios federados que se encuentran en una instalación heredada, la directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="b5f2b-122">Las directivas de conferencia que permiten a los **participantes anónimos** permiten a los participantes invitar a usuarios anónimos seleccionados en el Panel de control de Skype Empresarial Server 2019 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **True** en el resultado del cmdlet **Get-CsConferencingPolicy** en el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b5f2b-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

