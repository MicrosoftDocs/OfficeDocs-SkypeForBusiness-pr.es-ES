---
title: Administrar las cuentas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.
ms.openlocfilehash: 715eda137395d2133b6b19dee4a9d2336923c13b
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699247"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="5dfc7-103">Administrar las cuentas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="5dfc7-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="5dfc7-104">Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="5dfc7-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="5dfc7-105">Sistemas de salón de Skype v2 es un producto diferente con dependencias diferentes y procedimientos de implementación.</span><span class="sxs-lookup"><span data-stu-id="5dfc7-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="5dfc7-106">Para obtener información sobre los sistemas de la sala de Skype v2, vea el de v2 [Introducción a la administración](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="5dfc7-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="5dfc7-107">Mover la cuenta del sistema de salas de Skype entre grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="5dfc7-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="5dfc7-108">Si necesita mover la cuenta del sistema de salas de Skype de uno Skype para el grupo de servidores de negocio a otra (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de servidores de la cuenta del sistema de salas de Skype:</span><span class="sxs-lookup"><span data-stu-id="5dfc7-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="5dfc7-109">Deshabilitar la cuenta del sistema de salas de Skype para Skype para servicios de negocios</span><span class="sxs-lookup"><span data-stu-id="5dfc7-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="5dfc7-110">Si necesita deshabilitar una sistema de salas de Skype cuenta existente de Skype para servicios de negocios en un Skype para grupo de servidores de negocio, use el siguiente comando para deshabilitar la cuenta:</span><span class="sxs-lookup"><span data-stu-id="5dfc7-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="5dfc7-111">Opcional: Crear un grupo de administrador del sistema de salas de Skype en Active Directory</span><span class="sxs-lookup"><span data-stu-id="5dfc7-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="5dfc7-112">Cada cliente del sistema de salas de Skype que se une al dominio puede ser totalmente administrado por un usuario de dominio con derechos de administrador local en el dispositivo del sistema de salas de Skype PC.</span><span class="sxs-lookup"><span data-stu-id="5dfc7-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="5dfc7-113">Por lo tanto, puede crear grupo dedicado de un administradores en Active Directory y da como resultado este derechos administrativos de grupo durante conjunto de copia de seguridad de la nueva máquina de sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="5dfc7-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

