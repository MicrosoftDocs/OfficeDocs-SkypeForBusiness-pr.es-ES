---
title: 'Lync Server 2013: Habilitar a los usuarios de Lync para el control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="8a34b-102">Habilitar a los usuarios de Lync para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a34b-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a34b-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8a34b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8a34b-104">Puede configurar los usuarios de Lync para el control remoto de llamadas mediante directivas de aprovisionamiento en banda basadas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8a34b-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="8a34b-105">Puede administrar la configuración de aprovisionamiento en banda con el panel de control de Lync Server o la interfaz de línea de comandos del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a34b-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="8a34b-106">Estas herramientas reemplazan al complemento instrumental de administración de Windows (WMI) que se usó para administrar la configuración de la Directiva de grupo en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="8a34b-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="8a34b-107">Si prefiere permitir que los usuarios configuren su propia configuración de control de llamadas remotas en Lync, puede configurar la configuración de control de llamadas remotas para los usuarios del servidor sin especificar valores **URI del servidor de líneas** y URI de **línea** .</span><span class="sxs-lookup"><span data-stu-id="8a34b-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="8a34b-108">Asegúrese de comunicar los valores correctos de **URI del servidor de línea** y URI de **línea** a los usuarios, y proporcione a los usuarios las instrucciones para establecer esta configuración.</span><span class="sxs-lookup"><span data-stu-id="8a34b-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="8a34b-109">Para obtener información sobre cómo configurar manualmente el control remoto de llamadas en Lync Server, consulte "set phone Options <http://go.microsoft.com/fwlink/p/?linkid=210132> and Numbers" en la documentación del cliente de Lync en el sitio web de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="8a34b-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="8a34b-110">Si tiene una implementación existente de Communications Server 2007 R2 o Communications Server 2007, los clientes de Communicator 2007 R2 y Communicator 2007 continuarán usando la Directiva de grupo durante la migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="8a34b-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="8a34b-111">Sin embargo, si desea que la configuración de directivas se lleve a cabo para los clientes de Lync, debe configurar la configuración de aprovisionamiento en banda de Lync Server equivalente.</span><span class="sxs-lookup"><span data-stu-id="8a34b-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a34b-112">Para habilitar un usuario para el control remoto de llamadas, debe proporcionar al usuario un URI de línea y un URI de servidor de línea.</span><span class="sxs-lookup"><span data-stu-id="8a34b-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="8a34b-113">Como se describe en <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tareas de implementación para el control remoto de llamadas en Lync Server 2013</A>, debe asegurarse de usar la sintaxis requerida por la puerta de enlace para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="8a34b-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="8a34b-114">Asegúrese de que el dominio del URI del servidor de línea es el mismo que el dominio de destino que especificó en el parámetro MatchUri cuando configuró la ruta estática a la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="8a34b-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="8a34b-115">El URI de línea especifica el número de teléfono asignado al usuario en formato E. 164, con el prefijo "TEL:" (por ejemplo, Tel: + 14255550150).</span><span class="sxs-lookup"><span data-stu-id="8a34b-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="8a34b-116">Si desea configurar un número de extensión, el formato es Tel: + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="8a34b-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="8a34b-117">Si previamente ha configurado el URI de la línea del usuario y el valor no ha cambiado, no es necesario especificar el URI de línea cuando habilita al usuario para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8a34b-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="8a34b-118">Para habilitar el control remoto de llamadas para los usuarios habilitados para Lync mediante el shell de administración</span><span class="sxs-lookup"><span data-stu-id="8a34b-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="8a34b-119">Inicie sesión en un equipo en el que esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o como un rol de control de acceso basado en roles al que haya asignado el cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="8a34b-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="8a34b-120">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8a34b-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8a34b-121">Para usar el cmdlet **set-CsUser** para configurar el control remoto de llamadas para un usuario existente habilitado para Lync, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a34b-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="8a34b-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a34b-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="8a34b-123">Para configurar usuarios para el control remoto de llamadas con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="8a34b-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8a34b-124">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8a34b-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8a34b-125">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a34b-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a34b-126">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8a34b-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a34b-127">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8a34b-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8a34b-128">En el cuadro **Buscar usuarios** , escriba todos (o la primera parte) del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en \*\* Buscar\*\*.</span><span class="sxs-lookup"><span data-stu-id="8a34b-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="8a34b-129">En la tabla, haga clic en la cuenta de usuario que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8a34b-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="8a34b-130">En el menú **Editar** , haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="8a34b-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="8a34b-131">En **telefonía**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8a34b-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="8a34b-132">Para habilitar el control remoto de llamadas para permitir que el usuario pueda controlar su teléfono de central de conmutación (PBX) de Lync 2013 para hacer llamadas de audio de PC a PC y llamadas de PC a teléfono, haga clic en **control remoto de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="8a34b-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="8a34b-133">En **URI de línea**, especifique el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="8a34b-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="8a34b-134">En **line URI del servidor**, especifique el URI de SIP de la puerta de enlace SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="8a34b-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="8a34b-135">Para habilitar el control remoto de llamadas, pero deshabilitar las llamadas de audio de PC a PC y permitir que solo el usuario controle su teléfono PBX desde Lync 2013 para hacer llamadas de equipo a teléfono, haga clic en **control remoto de llamadas únicamente**.</span><span class="sxs-lookup"><span data-stu-id="8a34b-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="8a34b-136">En **URI de línea**, especifique el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="8a34b-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="8a34b-137">En **line URI del servidor**, especifique el URI de SIP de la puerta de enlace SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="8a34b-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="8a34b-138">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8a34b-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

