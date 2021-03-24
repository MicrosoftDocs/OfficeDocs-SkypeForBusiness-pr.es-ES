---
title: Administrar cuentas del Sistema de salas de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lea este tema para obtener información sobre cómo administrar cuentas del sistema de salón de Skype.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093298"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="fb6c8-103">Administrar cuentas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="fb6c8-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="fb6c8-104">Lea este tema para obtener información sobre cómo administrar cuentas del sistema de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="fb6c8-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb6c8-105">Microsoft Teams Rooms es un producto diferente con diferentes dependencias y procedimientos de implementación.</span><span class="sxs-lookup"><span data-stu-id="fb6c8-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="fb6c8-106">Para obtener información sobre salas de Microsoft Teams, vea la introducción a la administración de salas [de](/microsoftteams/rooms/rooms-manage)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6c8-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="fb6c8-107">Mover la cuenta del sistema de sala de Skype entre grupos</span><span class="sxs-lookup"><span data-stu-id="fb6c8-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="fb6c8-108">Si necesita mover la cuenta del sistema de salón de Skype de un grupo de Skype Empresarial Server a otro (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de cuentas del sistema de salón de Skype:</span><span class="sxs-lookup"><span data-stu-id="fb6c8-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="fb6c8-109">Deshabilitar la cuenta del sistema de sala de Skype para los servicios de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fb6c8-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="fb6c8-110">Si necesita deshabilitar una cuenta existente del sistema de sala de Skype desde los servicios de Skype Empresarial en un grupo de skype empresarial, use el siguiente comando para deshabilitar la cuenta:</span><span class="sxs-lookup"><span data-stu-id="fb6c8-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="fb6c8-111">Opcional: crear un grupo de administradores del sistema de salón de Skype en Active Directory</span><span class="sxs-lookup"><span data-stu-id="fb6c8-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="fb6c8-112">Cada cliente del sistema de salón de Skype que se une al dominio puede ser administrado completamente por un usuario de dominio con derechos de administrador local en el equipo del dispositivo sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="fb6c8-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="fb6c8-113">Por lo tanto, puede crear un grupo de administradores dedicado en Active Directory y dar a este grupo derechos administrativos durante la configuración del nuevo equipo del sistema de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="fb6c8-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
