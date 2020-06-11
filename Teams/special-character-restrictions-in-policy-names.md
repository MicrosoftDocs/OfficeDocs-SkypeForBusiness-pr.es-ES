---
title: Restricciones de caracteres especiales en directivas de Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Vea qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para corregirlo.
ms.openlocfilehash: 7358bd989b793e988f0a3dacdded275b5232c8cc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691516"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="f2e9f-103">¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?</span><span class="sxs-lookup"><span data-stu-id="f2e9f-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="f2e9f-104">**No puede crear o editar directivas (de mensajería, reuniones, etc.) que tengan un carácter especial en el nombre en el centro de administración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="f2e9f-105">Si un nombre de Directiva contiene caracteres especiales, tendrá limitaciones para administrar estas directivas en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f2e9f-106">**Como tal, recomendamos encarecidamente que los nombres de las directivas no incluyan caracteres especiales**.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="f2e9f-107">Los nombres de directiva que se han creado con PowerShell para reuniones y mensajería en Teams pueden tener caracteres especiales como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="f2e9f-108">Sin embargo, si desea realizar cambios en la Directiva en el centro de administración de Microsoft Teams, no podrá.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="f2e9f-109">Si tiene una directiva con caracteres especiales, tendrá que editar la Directiva con Windows PowerShell (para siempre) o crear una nueva Directiva en el centro de administración de Microsoft Teams con la misma configuración que la directiva anterior y asignarla al mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="f2e9f-110">Para quitar caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="f2e9f-110">To remove special characters</span></span>

<span data-ttu-id="f2e9f-111">**Paso 1: establecer una conexión remota con PowerShell.** 
 [Configure su equipo para Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) si todavía no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="f2e9f-112">**Paso 2: obtenga la configuración de la directiva anterior y Capture la salida.**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="f2e9f-113">Este ejemplo es para una directiva de [Mensajería](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f2e9f-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="f2e9f-114">Los pasos serían iguales para otros tipos de directivas, pero debe usar el cmdlet correcto.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="f2e9f-115">**Paso 3: crear una nueva Directiva.**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="f2e9f-116">Puede crear la nueva directiva con la misma configuración con el centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="f2e9f-117">Si se ejecuta, se creará una nueva Directiva, pero tendrá que agregar la configuración correcta si ve [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) y, a continuación, lo ejecuta:</span><span class="sxs-lookup"><span data-stu-id="f2e9f-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="f2e9f-118">**Paso 4: asignar la Directiva.**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-118">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="f2e9f-119">Para obtener más información sobre este cmdlet, consulte [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f2e9f-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="f2e9f-120">**Paso 5: eliminar la directiva anterior.**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="f2e9f-121">Esto eliminará la directiva anterior con los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-121">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="f2e9f-122">Para obtener más información sobre este cmdlet, consulte [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f2e9f-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="f2e9f-123">Si este comando se ejecuta correctamente, ya habrá terminado.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="f2e9f-124">Si el comando anterior devuelve un error, esto se debe a que la Directiva antigua se asigna a los usuarios, por lo que necesita ejecutar para quitar todos los usuarios asignados de la Directiva:</span><span class="sxs-lookup"><span data-stu-id="f2e9f-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f2e9f-125">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f2e9f-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="f2e9f-126">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f2e9f-127">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f2e9f-128">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="f2e9f-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f2e9f-129">¿Por qué necesita usar Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f2e9f-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f2e9f-130">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2e9f-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f2e9f-131">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="f2e9f-132">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f2e9f-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f2e9f-133">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f2e9f-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="f2e9f-134">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f2e9f-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f2e9f-135">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f2e9f-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f2e9f-136">El módulo Windows PowerShell para Skype empresarial online le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2e9f-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="f2e9f-137">Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="f2e9f-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

