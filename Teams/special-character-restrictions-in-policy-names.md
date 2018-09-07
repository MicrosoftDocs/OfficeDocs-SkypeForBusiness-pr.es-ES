---
title: ¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Vea ¿qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para solucionarlo.
ms.openlocfilehash: 61902c3cdeafbacbf316b99834e7ac32286443b4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853418"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="5f021-103">¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?</span><span class="sxs-lookup"><span data-stu-id="5f021-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="5f021-104">**No se puede crear o modificar las directivas (para mensajería, reuniones, etc.) que tienen un carácter especial en el nombre en el Microsoft Teams y Skype para el centro de administración de negocio.**</span><span class="sxs-lookup"><span data-stu-id="5f021-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams and Skype for Business Admin Center.**</span></span> 

<span data-ttu-id="5f021-105">Si un nombre de directiva contiene caracteres especiales, estará limitado en la administración de estas directivas en el Microsoft Teams y Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="5f021-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams and Skype for Business Admin Center.</span></span> <span data-ttu-id="5f021-106">**Por lo tanto, se recomienda encarecidamente que los nombres de directiva no incluir caracteres especiales**.</span><span class="sxs-lookup"><span data-stu-id="5f021-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="5f021-107">Nombres de directiva que se han creado mediante PowerShell para las reuniones y mensajería en los equipos pueden tener caracteres especiales, como @, #, $.</span><span class="sxs-lookup"><span data-stu-id="5f021-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="5f021-108">Sin embargo, si desea realizar cambios en la directiva en el Microsoft Teams y Skype para el centro de administración de negocio, no podrá a.</span><span class="sxs-lookup"><span data-stu-id="5f021-108">However, if you are wanting to make changes to the policy in the Microsoft Teams and Skype for Business Admin Center,you won't be able to.</span></span> 

<span data-ttu-id="5f021-109">Si tiene una directiva con caracteres especiales, debe editar la directiva de uso de Windows PowerShell (siempre) o crear una nueva directiva en el Microsoft Teams y Skype para el centro de administración de negocio con la misma configuración que la directiva anterior y asígnele el mismo grupo p de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5f021-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams and Skype for Business Admin Center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="5f021-110">Para quitar los caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="5f021-110">To remove special characters</span></span>



<span data-ttu-id="5f021-111">**Paso 1: establecer una conexión remota con PowerShell.** 
 [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) si no lo ha hecho todavía.</span><span class="sxs-lookup"><span data-stu-id="5f021-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="5f021-112">**Paso 2: obtener la configuración de la directiva anterior y capturar el resultado.**</span><span class="sxs-lookup"><span data-stu-id="5f021-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="5f021-113">En este ejemplo es para una directiva de [mensajería](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5f021-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="5f021-114">Los pasos sería el mismo para otros tipos de directiva, pero debe usar el cmdlet correcto.</span><span class="sxs-lookup"><span data-stu-id="5f021-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="5f021-115">**Paso 3: crear una nueva directiva.**</span><span class="sxs-lookup"><span data-stu-id="5f021-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="5f021-116">Puede crear la nueva directiva con la misma configuración mediante el Microsoft Teams y Skype para centro de administración de negocio o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f021-116">You can either create the new policy with the same setting using the Microsoft Teams and Skype for Business Admin Center or PowerShell.</span></span>

<span data-ttu-id="5f021-117">Ejecuta Esto creará una nueva directiva de pero necesita agregar la configuración correcta, vean [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) y, a continuación, si lo ejecuta:</span><span class="sxs-lookup"><span data-stu-id="5f021-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="5f021-118">**Paso 4: asignar la directiva.**</span><span class="sxs-lookup"><span data-stu-id="5f021-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="5f021-119">Vea, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5f021-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="5f021-120">**Paso 5: eliminar la directiva anterior.**</span><span class="sxs-lookup"><span data-stu-id="5f021-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="5f021-121">Esta acción eliminará la directiva anterior con los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="5f021-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="5f021-122">Vea, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5f021-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="5f021-123">Si este comando se ejecuta correctamente, haya terminado.</span><span class="sxs-lookup"><span data-stu-id="5f021-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="5f021-124">Si el comando anterior devuelve un error, es debido a que la directiva anterior se asigna a los usuarios por lo que necesita ejecutar para quitar todos los usuarios asignados de la directiva:</span><span class="sxs-lookup"><span data-stu-id="5f021-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5f021-125">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5f021-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="5f021-p105">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5f021-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5f021-129">¿Por qué necesita usar Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5f021-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5f021-130">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f021-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="5f021-p106">Windows PowerShell tiene muchas ventajas en velocidad, simplificidad y productividad respecto a utilizar únicamente el centro de administración de Office 365 como, por ejemplo, al realizar cambios de configuración para muchos usuarios en una única ubicación. Obtenga más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f021-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5f021-133">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5f021-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="5f021-134">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5f021-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5f021-135">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5f021-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="5f021-136">El módulo de Windows PowerShell para Skype para profesionales en línea le permite crear una sesión remota de Windows PowerShell que se conecta a Skype para profesionales en línea y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5f021-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="5f021-137">Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="5f021-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
### <a name="related-topics"></a><span data-ttu-id="5f021-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5f021-138">Related topics</span></span>
