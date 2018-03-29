---
title: Administrar las cuentas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="4ec65-103">Administrar las cuentas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="4ec65-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="4ec65-104">Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="4ec65-104">Read this topic to learn how to manage Skype Room System accounts.</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="4ec65-105">Mueva la cuenta de sistema del sitio de Skype entre grupos</span><span class="sxs-lookup"><span data-stu-id="4ec65-105">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="4ec65-106">Si necesita mover la cuenta de sistema del sitio de Skype de uno Skype para el grupo de servidores empresariales a otro (por ejemplo, durante las actualizaciones), utilice el siguiente comando para mover el grupo de la cuenta de sistema del sitio de Skype:</span><span class="sxs-lookup"><span data-stu-id="4ec65-106">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="4ec65-107">Deshabilitar la cuenta de sistema del sitio de Skype de Skype para servicios de negocios</span><span class="sxs-lookup"><span data-stu-id="4ec65-107">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="4ec65-108">Si necesita deshabilitar una cuenta ya existente sistema de sala de Skype de Skype servicios comerciales en un Skype para el grupo de servidores empresariales, utilice el siguiente comando para deshabilitar la cuenta:</span><span class="sxs-lookup"><span data-stu-id="4ec65-108">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="4ec65-109">Opcional: Crear un grupo de administrador de sistema de sala de Skype en Active Directory</span><span class="sxs-lookup"><span data-stu-id="4ec65-109">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="4ec65-110">Cada cliente de sistema de sala de Skype que se une al dominio puede ser totalmente administrado por un usuario de dominio con derechos de administrador local en el dispositivo de sistema de sala de Skype PC.</span><span class="sxs-lookup"><span data-stu-id="4ec65-110">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="4ec65-111">Por lo tanto, puede crear un dedicado grupo en Active Directory y renunciar a este derechos administrativos de grupo durante la configuración del nuevo equipo de sistema del sitio de Skype.</span><span class="sxs-lookup"><span data-stu-id="4ec65-111">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

