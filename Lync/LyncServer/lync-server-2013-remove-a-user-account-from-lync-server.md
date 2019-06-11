---
title: 'Lync Server 2013: quitar una cuenta de usuario de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780e19fb608855d9c820285cc87582787ff896d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="7e150-102">Quitar una cuenta de usuario de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e150-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e150-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7e150-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7e150-104">Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada previamente en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e150-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e150-105">Si quita un usuario, perderá la configuración que haya configurado para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7e150-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="7e150-106">Si desea deshabilitar temporalmente una cuenta de usuario, vea el tema <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">sobre cómo deshabilitar o volver a habilitar una cuenta de usuario para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7e150-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="7e150-107">Para quitar una cuenta de usuario mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="7e150-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="7e150-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7e150-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7e150-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e150-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7e150-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7e150-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7e150-111">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="7e150-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="7e150-112">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="7e150-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="7e150-113">En la tabla, haga clic en la cuenta de usuario que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="7e150-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="7e150-114">En el menú **acción** , seleccione **quitar de Lync Server**y aparecerá un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7e150-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="7e150-115">En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.</span><span class="sxs-lookup"><span data-stu-id="7e150-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7e150-116">Quitar cuentas de usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e150-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7e150-117">Puede quitar cuentas de usuario mediante el cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="7e150-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="7e150-118">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e150-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="7e150-119">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="7e150-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="7e150-120">Para quitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="7e150-120">To remove a user account</span></span>

  - <span data-ttu-id="7e150-121">Para quitar una cuenta de usuario, use el cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="7e150-121">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="7e150-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7e150-122">For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="7e150-123">Después de ejecutar este comando, no hay ninguna forma de volver a habilitar la cuenta y su configuración anterior.</span><span class="sxs-lookup"><span data-stu-id="7e150-123">After this command has run there is no way to re-enable the account and its previous settings.</span></span> <span data-ttu-id="7e150-124">En su lugar, tendrá que usar el cmdlet enable-CsUser para crear una cuenta nueva para Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="7e150-124">Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="7e150-125">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="7e150-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e150-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e150-126">See Also</span></span>


[<span data-ttu-id="7e150-127">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e150-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="7e150-128">Habilitar y deshabilitar usuarios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e150-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

