---
title: 'Lync Server 2013: ver información de PIN de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb3d854f68e9e22e8d8fb1fa0d26f555f09af1ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a><span data-ttu-id="864fc-102">Ver información de PIN de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="864fc-102">View user PIN information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="864fc-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="864fc-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="864fc-104">Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Lync Server 2013 con credenciales de servicios de dominio de Active Directory (AD DS) necesita un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="864fc-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="864fc-105">Puede ver la información del PIN de un usuario desde el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="864fc-105">You can view a user’s PIN information from Lync Server 2013 Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="864fc-106">Puede ver información de estado del PIN como, por ejemplo, si se ha establecido el PIN o cuándo se modificó el PIN, pero no puede ver el PIN actual viendo su estado.</span><span class="sxs-lookup"><span data-stu-id="864fc-106">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="864fc-107">Si un usuario ha perdido su PIN, puede restablecerlo siguiendo los procedimientos de establecer el <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">PIN de conferencias de acceso telefónico local de un usuario en Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="864fc-107">If a user has lost their PIN, you can reset it by following the procedures in <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Set a user's dial-in conferencing PIN in Lync Server 2013</A></span></span>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="864fc-108">Para ver el PIN de un usuario en el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="864fc-108">To view a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="864fc-109">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="864fc-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="864fc-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="864fc-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="864fc-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="864fc-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="864fc-112">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="864fc-112">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="864fc-113">Use uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="864fc-113">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="864fc-114">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="864fc-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="864fc-115">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="864fc-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="864fc-116">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="864fc-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="864fc-117">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="864fc-117">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="864fc-118">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="864fc-118">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="864fc-119">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="864fc-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="864fc-120">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="864fc-120">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="864fc-121">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="864fc-121">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="864fc-122">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="864fc-122">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="864fc-p104">Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en <STRONG>Acción</STRONG>y en <STRONG>Desbloquear PIN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="864fc-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="864fc-125">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y luego en **Ver estado de PIN**.</span><span class="sxs-lookup"><span data-stu-id="864fc-125">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="864fc-126">Ver información de PIN de usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="864fc-126">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="864fc-127">Puede ver la información del PIN del usuario con el cmdlet Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="864fc-127">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="864fc-128">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="864fc-128">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="864fc-129">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="864fc-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-user-pin-information"></a><span data-ttu-id="864fc-130">Para ver la información del PIN del usuario</span><span class="sxs-lookup"><span data-stu-id="864fc-130">To view user PIN information</span></span>

  - <span data-ttu-id="864fc-131">Para ver la información de PIN de un usuario, escriba un comando similar al siguiente en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="864fc-131">To view PIN information for a user, type a command similar to the following in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    <span data-ttu-id="864fc-132">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="864fc-132">That will return information similar to this:</span></span>
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

<span data-ttu-id="864fc-133">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .</span><span class="sxs-lookup"><span data-stu-id="864fc-133">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="864fc-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="864fc-134">See Also</span></span>


[<span data-ttu-id="864fc-135">Configurar el PIN de conferencias de acceso telefónico local de un usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="864fc-135">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[<span data-ttu-id="864fc-136">Bloquear o desbloquear un PIN de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="864fc-136">Lock or unlock a user PIN in Lync Server 2013</span></span>](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

