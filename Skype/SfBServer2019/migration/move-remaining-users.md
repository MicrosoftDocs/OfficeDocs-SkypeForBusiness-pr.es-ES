---
title: Mover al resto de los usuarios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Puede mover usuarios a la nueva implementación de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype empresarial Server 2019. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea Configurar clientes para la migración. Para conocer los pasos detallados sobre cómo mover usuarios, consulte la fase 4: mover usuarios de prueba a la agrupación piloto.'
ms.openlocfilehash: 67bc2d3b239e65b5b1c83e2dcda81a1610d5a31c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273962"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="8cfb9-106">Mover los usuarios restantes a Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="8cfb9-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="8cfb9-107">Puede mover usuarios a la nueva implementación de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8cfb9-108">Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="8cfb9-109">Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [configurar clientes para la migración](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="8cfb9-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="8cfb9-110">Para conocer los pasos detallados sobre cómo mover usuarios, consulte [la fase 4: mover usuarios de prueba a la agrupación piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8cfb9-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8cfb9-111">No puede usar el complemento usuarios y equipos de Active Directory ni las herramientas administrativas heredadas para mover usuarios de su entorno heredado a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="8cfb9-112">Al mover un usuario a un grupo de servidores de Skype empresarial 2019, los datos del usuario se mueven a la base de datos back-end asociada con el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8cfb9-113">Esto incluye las reuniones activas creadas por el usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="8cfb9-114">Por ejemplo, si un usuario heredado ha configurado una conferencia de **reunión** , dicha conferencia seguirá estando disponible en el nuevo grupo de servidores de Skype empresarial 2019 después de que se haya movido al usuario.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="8cfb9-115">Los detalles para acceder a la reunión seguirán siendo la misma **dirección URL de conferencia y**el mismo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="8cfb9-116">La única diferencia es que la Conferencia ahora está hospedada en el grupo de servidores de Skype empresarial 2019, y no en el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8cfb9-117">El alojamiento de usuarios en Skype empresarial Server 2019 no requiere que implemente clientes actualizados al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="8cfb9-118">Las nuevas funcionalidades estarán disponibles solo para los usuarios cuando se actualicen al nuevo software de cliente.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="8cfb9-119">Tarea posterior a la migración</span><span class="sxs-lookup"><span data-stu-id="8cfb9-119">Post migration task</span></span>

1. <span data-ttu-id="8cfb9-120">Después de mover usuarios, Compruebe la Directiva de conferencia que tiene asignada.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="8cfb9-121">Para asegurarse de que las reuniones organizadas por usuarios alojados en Skype empresarial Server 2019 funcionen sin problemas con usuarios federados que estén alojados en una instalación heredada, la Directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="8cfb9-122">Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Skype empresarial Server 2019 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **verdadero** en el salida del cmdlet **Get-CsConferencingPolicy** en el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8cfb9-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

