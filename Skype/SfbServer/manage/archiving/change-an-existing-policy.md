---
title: Cambiar una directiva de archivado existente en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumen: obtenga información sobre cómo cambiar las directivas de archivado de usuarios para Skype Empresarial Server.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817710"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="d4c85-103">Cambiar una directiva de archivado existente en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d4c85-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="d4c85-104">**Resumen:** Obtenga información sobre cómo cambiar las directivas de archivado de usuarios para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4c85-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="d4c85-105">Cuando implementa Skype Empresarial Server por primera vez, configura directivas de archivado iniciales que determinan cómo se implementa el archivado para los usuarios de su implementación.</span><span class="sxs-lookup"><span data-stu-id="d4c85-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="d4c85-106">En este tema se describe cómo administrar y modificar directivas.</span><span class="sxs-lookup"><span data-stu-id="d4c85-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="d4c85-107">Cambiar las directivas de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="d4c85-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="d4c85-108">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d4c85-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d4c85-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4c85-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d4c85-110">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="d4c85-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d4c85-111">En la lista de directivas, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d4c85-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="d4c85-112">Para cambiar la directiva de toda la implementación, haga clic en **Global** en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d4c85-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="d4c85-113">Para cambiar la directiva de un solo sitio, haga clic en el nombre del sitio en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d4c85-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="d4c85-114">Para cambiar la directiva de solo usuario o grupo de usuarios, haga clic en el nombre del usuario o del grupo de usuarios en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d4c85-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d4c85-115">En la página **Editar directiva de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4c85-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="d4c85-116">Para habilitar o deshabilitar el archivado interno para la directiva, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="d4c85-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d4c85-117">Para habilitar o deshabilitar el archivado externo para la directiva, active o desactiva la casilla **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="d4c85-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="d4c85-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d4c85-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d4c85-119">La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="d4c85-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="d4c85-120">Para obtener más información, [consulte Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="d4c85-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="d4c85-121">Cambiar las directivas de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c85-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="d4c85-122">También puede cambiar las directivas de archivado con Windows PowerShell **Cmdlet Set-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="d4c85-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="d4c85-123">Habilitar directivas de archivado</span><span class="sxs-lookup"><span data-stu-id="d4c85-123">Enable archiving policies</span></span>

<span data-ttu-id="d4c85-124">Para habilitar el archivado de sesiones de comunicación internas, establezca el valor del parámetro ArchiveInternal en True ($True):</span><span class="sxs-lookup"><span data-stu-id="d4c85-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="d4c85-125">Para habilitar el archivado de sesiones de comunicación externas, establezca el valor del parámetro ArchiveExternal en True ($True):</span><span class="sxs-lookup"><span data-stu-id="d4c85-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="d4c85-126">Para habilitar el archivado de sesiones de comunicación internas y externas, establezca el valor de los parámetros ArchiveInternal y ArchiveExternal en True:</span><span class="sxs-lookup"><span data-stu-id="d4c85-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="d4c85-127">Deshabilitar directivas de archivado</span><span class="sxs-lookup"><span data-stu-id="d4c85-127">Disable archiving policies</span></span>

<span data-ttu-id="d4c85-128">Para deshabilitar el archivado por completo, establezca el valor de los parámetros ArchiveInternal y ArchiveExternal en False ($False):</span><span class="sxs-lookup"><span data-stu-id="d4c85-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
