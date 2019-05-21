---
title: Administrar las cuentas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.
ms.openlocfilehash: 5276bd1f2b74000e681efadd8961b9c048351c3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293336"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="ff675-103">Administrar las cuentas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="ff675-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="ff675-104">Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="ff675-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff675-105">Salas de Microsoft Teams es un producto diferente con diferentes dependencias y procedimientos de implementación.</span><span class="sxs-lookup"><span data-stu-id="ff675-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="ff675-106">Para obtener información sobre las salas de Microsoft Teams, consulte la [información general de administración](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff675-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="ff675-107">Mover la cuenta del sistema de salas de Skype entre los grupos</span><span class="sxs-lookup"><span data-stu-id="ff675-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="ff675-108">Si necesita mover la cuenta del sistema de salas de Skype de un grupo de servidores de Skype empresarial a otro (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de cuentas del sistema de salas de Skype:</span><span class="sxs-lookup"><span data-stu-id="ff675-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="ff675-109">Deshabilitar la cuenta del sistema de Skype Room para servicios de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="ff675-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="ff675-110">Si necesita deshabilitar una cuenta del sistema de Skype Room existente en los servicios de Skype empresarial en un grupo de servidores de Skype empresarial, use el siguiente comando para deshabilitar la cuenta:</span><span class="sxs-lookup"><span data-stu-id="ff675-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="ff675-111">Opcional: crear un grupo de administradores de sistemas de salas de Skype en Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff675-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="ff675-112">Cada cliente del sistema de salas de Skype que se une al dominio puede ser administrado por un usuario de dominio con derechos de administrador local en el equipo del sistema de la sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="ff675-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="ff675-113">Por lo tanto, puede crear un grupo de administradores dedicado en Active Directory y otorgar a este grupo derechos administrativos durante la configuración del nuevo equipo del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="ff675-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

