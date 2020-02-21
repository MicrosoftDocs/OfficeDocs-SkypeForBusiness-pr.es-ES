---
title: 'Lync Server 2013: asignar directivas de conferencia para admitir usuarios anónimos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 167fe5c772e765c5f78ac2253c23d66550e0e712
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="f271a-102">Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f271a-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f271a-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f271a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f271a-104">De forma predeterminada, ningún usuario tiene permitido invitar a usuarios anónimos a participar en una reunión.</span><span class="sxs-lookup"><span data-stu-id="f271a-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="f271a-105">Para controlar quién puede invitar a usuarios anónimos, se debe configurar una directiva de conferencias que admita la participación de usuarios anónimos, y aplicar dicha directiva a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="f271a-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="f271a-106">Para obtener más información sobre cómo configurar directivas de conferencia para admitir usuarios anónimos, vea [crear o modificar una directiva de conferencia en Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) y [administrar la Federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="f271a-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="f271a-107">Use el procedimiento descrito en esta sección para aplicar una directiva de conferencia que ya haya creado a uno o más usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f271a-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f271a-108">Además de configurar y aplicar una directiva para permitir que los usuarios inviten a usuarios anónimos, también debe habilitar la compatibilidad con usuarios anónimos en su organización.</span><span class="sxs-lookup"><span data-stu-id="f271a-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="f271a-109">Para obtener más información, consulte <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f271a-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="f271a-110">Para configurar una directiva de usuario para la participación anónima en las reuniones</span><span class="sxs-lookup"><span data-stu-id="f271a-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="f271a-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f271a-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f271a-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f271a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f271a-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f271a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f271a-114">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="f271a-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="f271a-115">Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f271a-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="f271a-116">Cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnableAnonymous** para una directiva de usuario que permita las comunicaciones con usuarios anónimos).</span><span class="sxs-lookup"><span data-stu-id="f271a-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="f271a-117">Para configurar una directiva de usuario existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="f271a-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="f271a-118">En el cuadro de diálogo **directivas de conferencia** , active la casilla de verificación **permitir que los participantes inviten a usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="f271a-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="f271a-119">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f271a-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="f271a-120">En la barra de navegación izquierda, haga clic en **usuarios**y busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="f271a-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="f271a-121">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  \*\*Editar \*\* y, a continuación, en  \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="f271a-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="f271a-122">En **Editar usuario de Lync Server** en **Directiva de conferencia**, seleccione la Directiva de usuario con la configuración de acceso de usuario anónimo que desea aplicar a este usuario.</span><span class="sxs-lookup"><span data-stu-id="f271a-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f271a-123">La <STRONG> &lt;configuración&gt; automática</STRONG> aplica la configuración de la instalación del servidor predeterminada y el servidor la aplica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f271a-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="f271a-124">Para permitir a los usuarios invitar a usuarios anónimos a conferencias, también tiene que habilitar la compatibilidad con usuarios anónimos en la organización.</span><span class="sxs-lookup"><span data-stu-id="f271a-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="f271a-125">Para obtener más información, consulte [configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f271a-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

