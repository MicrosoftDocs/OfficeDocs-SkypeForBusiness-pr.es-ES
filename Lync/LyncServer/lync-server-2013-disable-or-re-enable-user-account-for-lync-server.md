---
title: 'Lync Server 2013: deshabilitar o volver a habilitar la cuenta de usuario para Lync Server'
description: 'Lync Server 2013: deshabilitar o volver a habilitar la cuenta de usuario para Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568176"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="b962f-103">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b962f-103">Disable or re-enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b962f-104">_**Última modificación del tema:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="b962f-104">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="b962f-105">Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada previamente en Lync Server 2013 sin perder la configuración de Lync Server que ha configurado para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="b962f-105">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="b962f-106">Como no pierde la configuración de la cuenta de usuario de Lync Server, puede volver a habilitar una cuenta de usuario habilitada previamente sin tener que volver a configurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="b962f-106">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b962f-107">La simple deshabilitación de una cuenta de usuario en Active Directory <STRONG>no impedirá</STRONG> que un usuario pueda iniciar sesión en el servidor o usar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b962f-107">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="b962f-108">Esto se debe a que Lync usa la autenticación de certificados que simplifica el proceso de autenticación y estos certificados de cliente son válidos durante 180 días.</span><span class="sxs-lookup"><span data-stu-id="b962f-108">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="b962f-109">Si desea detener la deshabilitación de cuentas de Active Directory que se han habilitado para Lync para que tengan acceso a Lync Server, debe usar el cmdlet <STRONG>Disable-CsUser</STRONG> o usar el <STRONG>Panel de control de Lync Server</STRONG> tal y como se ha indicado en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b962f-109">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="b962f-110">Una vez que el usuario está deshabilitado en Lync y el almacén de administración central se ha replicado en el entorno, los usuarios ya no podrán iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="b962f-110">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="b962f-111">Además, se desconectarán los usuarios que hayan iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="b962f-111">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="b962f-112">Para deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Lync Server</span><span class="sxs-lookup"><span data-stu-id="b962f-112">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="b962f-113">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b962f-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b962f-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b962f-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b962f-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b962f-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b962f-116">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b962f-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b962f-117">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="b962f-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="b962f-118">En la tabla, haga clic en la cuenta de usuario que desee deshabilitar o volver a habilitar.</span><span class="sxs-lookup"><span data-stu-id="b962f-118">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="b962f-119">En el menú **acción** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b962f-119">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="b962f-120">Para deshabilitar temporalmente la cuenta de usuario para Lync Server 2013, haga clic en **deshabilitar temporalmente para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b962f-120">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="b962f-121">Para habilitar la cuenta de usuario para Lync Server 2013, haga clic en **volver a habilitar para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b962f-121">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="b962f-122">Uso de Windows PowerShell para deshabilitar o volver a habilitar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="b962f-122">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="b962f-123">Las cuentas de usuario se pueden deshabilitar temporalmente y, más adelante, volver a habilitarlas mediante el cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="b962f-123">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="b962f-124">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b962f-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b962f-125">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b962f-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="b962f-126">Para deshabilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="b962f-126">To disable a user account</span></span>

  - <span data-ttu-id="b962f-127">Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en false ($False).</span><span class="sxs-lookup"><span data-stu-id="b962f-127">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="b962f-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b962f-128">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="b962f-129">Para volver a habilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="b962f-129">To re-enable a user account</span></span>

  - <span data-ttu-id="b962f-130">Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en true ($True).</span><span class="sxs-lookup"><span data-stu-id="b962f-130">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="b962f-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b962f-131">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="b962f-132">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="b962f-132">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b962f-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b962f-133">See Also</span></span>


[<span data-ttu-id="b962f-134">Agregar y habilitar la cuenta de usuario para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b962f-134">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="b962f-135">Habilitación y deshabilitación de usuarios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b962f-135">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

