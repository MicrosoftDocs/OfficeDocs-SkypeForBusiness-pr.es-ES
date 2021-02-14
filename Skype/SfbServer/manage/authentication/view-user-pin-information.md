---
title: Ver información de PIN de usuario en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumen: ver información de PIN de usuario en Skype Empresarial Server.'
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806510"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="4a8da-103">Ver información de PIN de usuario en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4a8da-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="4a8da-104">**Resumen:** Ver información de PIN de usuario en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4a8da-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="4a8da-105">Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Skype Empresarial Server con credenciales de Servicios de dominio de Active Directory (AD DS) necesita un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="4a8da-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="4a8da-106">Puede ver la información de PIN de un usuario desde el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4a8da-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a8da-107">Puede ver información de estado de PIN, como si el PIN se ha establecido o cuándo se modificó por última vez, pero no puede ver el PIN actual mirando el estado del PIN.</span><span class="sxs-lookup"><span data-stu-id="4a8da-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="4a8da-108">Si un usuario ha perdido su PIN, puede restablecerlo siguiendo los procedimientos descritos en Establecer el PIN de conferencia de acceso telefónico local de un usuario en [Skype Empresarial Server](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="4a8da-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4a8da-109">Para ver el PIN de un usuario en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4a8da-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4a8da-110">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4a8da-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4a8da-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4a8da-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4a8da-112">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4a8da-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4a8da-113">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="4a8da-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="4a8da-114">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4a8da-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="4a8da-115">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4a8da-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="4a8da-116">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="4a8da-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="4a8da-117">a.</span><span class="sxs-lookup"><span data-stu-id="4a8da-117">a.</span></span> <span data-ttu-id="4a8da-118">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="4a8da-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="4a8da-119">b.</span><span class="sxs-lookup"><span data-stu-id="4a8da-119">b.</span></span> <span data-ttu-id="4a8da-120">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4a8da-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="4a8da-121">c.</span><span class="sxs-lookup"><span data-stu-id="4a8da-121">c.</span></span> <span data-ttu-id="4a8da-122">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="4a8da-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="4a8da-123">d.</span><span class="sxs-lookup"><span data-stu-id="4a8da-123">d.</span></span> <span data-ttu-id="4a8da-124">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4a8da-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="4a8da-125">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="4a8da-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="4a8da-126">e.</span><span class="sxs-lookup"><span data-stu-id="4a8da-126">e.</span></span> <span data-ttu-id="4a8da-127">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4a8da-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4a8da-p108">Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en **Acción** y en **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="4a8da-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="4a8da-130">Haga clic en un usuario en los resultados de la búsqueda, haga clic en **Acción** y, a continuación, haga clic **en Ver estado de PIN.**</span><span class="sxs-lookup"><span data-stu-id="4a8da-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4a8da-131">Visualización de la información del PIN del usuario mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="4a8da-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4a8da-132">Puede ver la información del PIN del usuario con el cmdlet Get-CsClientPinInfo usuario.</span><span class="sxs-lookup"><span data-stu-id="4a8da-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="4a8da-133">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a8da-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4a8da-134">Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="4a8da-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4a8da-135">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4a8da-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="4a8da-136">Para ver la información del PIN del usuario</span><span class="sxs-lookup"><span data-stu-id="4a8da-136">To view user PIN information</span></span>

<span data-ttu-id="4a8da-137">Para ver la información de PIN de un usuario, escriba un comando similar al siguiente en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="4a8da-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="4a8da-138">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a8da-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="4a8da-139">Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsConferenceDisclaimer.](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4a8da-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a8da-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a8da-140">See also</span></span>

[<span data-ttu-id="4a8da-141">Establecer el PIN de conferencia de acceso telefónico local de un usuario en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4a8da-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="4a8da-142">Bloquear o desbloquear un PIN de usuario en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4a8da-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
