---
title: Vista de usuario información del PIN en Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumen: Ver la información de PIN de usuario en Skype para Business Server.'
ms.openlocfilehash: 4b0eda76e4429ee5c6d658f4d161783bc4d356a3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21008562"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="0955b-103">Vista de usuario información del PIN en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0955b-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="0955b-104">**Resumen:** Vista de usuario información del PIN en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0955b-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="0955b-105">Para unirse a una conferencia de acceso telefónico como un usuario autenticado, una Skype para usuario Business Server con las credenciales de los servicios de dominio de Active Directory (AD DS) requiere un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="0955b-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="0955b-106">Puede ver información de PIN de un usuario de Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0955b-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0955b-107">Puede ver información de estado del PIN como, por ejemplo, si se ha establecido el PIN o cuándo se modificó el PIN, pero no puede ver el PIN actual viendo su estado.</span><span class="sxs-lookup"><span data-stu-id="0955b-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="0955b-108">Si un usuario ha perdido su NIP, puede restablecer siguiendo los procedimientos descritos en [establecer telefónico un usuario PIN en Skype para Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="0955b-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="0955b-109">Para ver un PIN de usuario de Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0955b-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0955b-110">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0955b-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0955b-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0955b-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0955b-112">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0955b-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0955b-113">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="0955b-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="0955b-114">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0955b-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="0955b-115">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0955b-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="0955b-116">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="0955b-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="0955b-117">a.</span><span class="sxs-lookup"><span data-stu-id="0955b-117">a.</span></span> <span data-ttu-id="0955b-118">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="0955b-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="0955b-119">b.</span><span class="sxs-lookup"><span data-stu-id="0955b-119">b.</span></span> <span data-ttu-id="0955b-120">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0955b-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="0955b-121">c.</span><span class="sxs-lookup"><span data-stu-id="0955b-121">c.</span></span> <span data-ttu-id="0955b-122">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="0955b-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="0955b-123">d.</span><span class="sxs-lookup"><span data-stu-id="0955b-123">d.</span></span> <span data-ttu-id="0955b-124">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0955b-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0955b-125">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="0955b-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="0955b-126">e.</span><span class="sxs-lookup"><span data-stu-id="0955b-126">e.</span></span> <span data-ttu-id="0955b-127">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0955b-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0955b-p108">Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en **Acción**y en **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="0955b-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="0955b-130">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y luego en **Ver estado de PIN**.</span><span class="sxs-lookup"><span data-stu-id="0955b-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0955b-131">Visualización de información de PIN de usuario mediante cmdlets de uso de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0955b-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0955b-132">Puede ver la información del PIN del usuario con el cmdlet Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="0955b-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="0955b-133">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0955b-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0955b-134">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="0955b-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0955b-135">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0955b-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="0955b-136">Para ver la información del PIN del usuario</span><span class="sxs-lookup"><span data-stu-id="0955b-136">To view user PIN information</span></span>

<span data-ttu-id="0955b-137">Para ver información de PIN de un usuario, escriba un comando similar al siguiente en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="0955b-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="0955b-138">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0955b-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="0955b-139">Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0955b-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0955b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0955b-140">See also</span></span>

[<span data-ttu-id="0955b-141">Establecer telefónico un usuario PIN en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0955b-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="0955b-142">Bloquear o desbloquear un usuario PIN en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0955b-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)