---
title: Mover al resto de los usuarios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Puede mover usuarios a la nueva Skype para la implementación empresarial Server 2019 mediante cualquiera Skype para Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial. Deben cumplir algunos requisitos para garantizar una transición sin problemas a Skype para Business Server 2019. Para obtener información detallada sobre los requisitos previos para completar los procedimientos descritos en este tema, vea a configurar clientes para la migración. Para los pasos detallados sobre cómo mover usuarios, vea fase 4: mover usuarios de prueba al grupo piloto.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878328"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="54079-106">Mover el resto de usuarios a Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="54079-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="54079-107">Puede mover usuarios a la nueva Skype para la implementación empresarial Server 2019 mediante cualquiera Skype para Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="54079-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="54079-108">Deben cumplir algunos requisitos para garantizar una transición sin problemas a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54079-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="54079-109">Para obtener información detallada sobre los requisitos previos para completar los procedimientos descritos en este tema, vea [Configurar clientes para la migración](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="54079-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="54079-110">Para obtener instrucciones detalladas sobre cómo mover usuarios, vea [fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="54079-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="54079-111">No puede usar el complemento Usuarios y equipos de usuarios de Active Directory o las herramientas administrativas de heredado para mover los usuarios del entorno heredado a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54079-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="54079-112">Cuando un usuario se mueve a un Skype para Business Server 2019 grupo, los datos para el usuario se mueven a la base de datos back-end que está asociada con el nuevo grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="54079-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="54079-113">Esto incluye las reuniones activas creadas por el usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="54079-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="54079-114">Por ejemplo, si un usuario heredado ha configurado una conferencia de **Mi reunión** , esa conferencia aún estará disponible en el nuevo Skype para Business Server 2019 grupo después de que el usuario se ha movido.</span><span class="sxs-lookup"><span data-stu-id="54079-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="54079-115">Los detalles para tener acceso a dicha reunión seguirá siendo la misma **dirección URL de conferencia y el identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="54079-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="54079-116">La única diferencia es que la conferencia ahora está hospedada en el Skype para Business Server 2019 grupo y no en el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="54079-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="54079-117">Hospedar los usuarios de Skype para Business Server 2019 no requiere que implementar los clientes actualizados al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="54079-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="54079-118">Nueva funcionalidad estará disponible para los usuarios sólo cuando se ha actualizado para el nuevo software de cliente.</span><span class="sxs-lookup"><span data-stu-id="54079-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="54079-119">Tarea posterior a la migración</span><span class="sxs-lookup"><span data-stu-id="54079-119">Post migration task</span></span>

1. <span data-ttu-id="54079-120">Después de mover usuarios, compruebe la directiva de conferencia que se les haya asignado.</span><span class="sxs-lookup"><span data-stu-id="54079-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="54079-121">Para garantizar que las reuniones organizadas por los usuarios hospedados en Skype para el trabajo de Business Server 2019 sin problemas con los usuarios federados que están hospedados en install heredado, la directiva de conferencia asignada a los usuarios migrados debe permitir a participantes anónimos.</span><span class="sxs-lookup"><span data-stu-id="54079-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="54079-122">Las directivas de conferencia que permiten participantes anónimos tienen seleccionada en Skype para el Panel de Control de Business Server 2019 de **Permitir que los participantes invitar a usuarios anónimos** y tienen la **opción AllowAnonymousParticipantsInMeetings** establecen en **True** en el resultado desde el cmdlet **Get-CsConferencingPolicy** en la Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="54079-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

