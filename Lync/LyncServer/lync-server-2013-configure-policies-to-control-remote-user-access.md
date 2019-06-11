---
title: 'Lync Server 2013: Configurar directivas para el control del acceso de usuarios remotos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="cf79e-102">Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf79e-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf79e-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="cf79e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="cf79e-104">Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con usuarios internos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf79e-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="cf79e-105">Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario.</span><span class="sxs-lookup"><span data-stu-id="cf79e-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="cf79e-106">Las directivas de sitio invalidan la directiva global y las directivas de usuario invalidan las directivas globales y del sitio.</span><span class="sxs-lookup"><span data-stu-id="cf79e-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="cf79e-107">Para obtener más información sobre los tipos de directivas que puede configurar, consulte [administrar la Federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="cf79e-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="cf79e-108">La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="cf79e-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="cf79e-109">La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="cf79e-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="cf79e-110">Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="cf79e-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf79e-111">Puede configurar directivas para controlar el acceso de usuarios remotos, incluso si no ha habilitado el acceso de usuarios remotos para su organización.</span><span class="sxs-lookup"><span data-stu-id="cf79e-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="cf79e-112">Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitado el acceso de usuarios remotos en su organización.</span><span class="sxs-lookup"><span data-stu-id="cf79e-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="cf79e-113">Para obtener más información sobre cómo habilitar el acceso de usuarios remotos, vea <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf79e-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="cf79e-114">Además, si especifica una directiva de usuario para controlar el acceso de usuarios remotos, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server y que usan la Directiva.</span><span class="sxs-lookup"><span data-stu-id="cf79e-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="cf79e-115">Para más información sobre cómo especificar usuarios que pueden iniciar sesión en Lync Server desde ubicaciones remotas, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf79e-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="cf79e-116">Use el procedimiento siguiente para configurar cada directiva de acceso externo que desee usar para controlar el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="cf79e-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf79e-117">Este procedimiento describe cómo configurar una directiva solo para habilitar las comunicaciones con usuarios remotos, pero cada directiva que se configura para admitir el acceso de usuarios remotos también puede configurar el acceso de usuarios federados y el acceso de usuarios públicos.</span><span class="sxs-lookup"><span data-stu-id="cf79e-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="cf79e-118">Para obtener más información sobre cómo configurar directivas para admitir usuarios federados, vea <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf79e-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="cf79e-119">Para obtener más información sobre cómo configurar directivas para admitir usuarios públicos, consulte <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">crear o editar proveedores federados de SIP públicos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf79e-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="cf79e-120">Para configurar una directiva de acceso externo para admitir el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="cf79e-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="cf79e-121">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="cf79e-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cf79e-122">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf79e-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cf79e-123">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cf79e-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf79e-124">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="cf79e-125">En la página **Directiva de acceso externo** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cf79e-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="cf79e-126">Para configurar la directiva global para que admita el acceso de usuarios remotos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="cf79e-127">Para crear una nueva Directiva de sitio, haga clic en **nueva**y, a continuación, haga clic en **Directiva del sitio**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="cf79e-128">En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="cf79e-129">Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="cf79e-130">En **nueva Directiva de acceso externo**, cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnableRemoteUsers** para una directiva de usuario que permita comunicaciones para usuarios remotos).</span><span class="sxs-lookup"><span data-stu-id="cf79e-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="cf79e-131">Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cf79e-132">Faculta Si desea agregar o editar una descripción, especifique la información de la Directiva en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="cf79e-133">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cf79e-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="cf79e-134">Para habilitar el acceso de usuarios remotos para la Directiva, active la casilla **habilitar las comunicaciones con usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="cf79e-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="cf79e-135">Para deshabilitar el acceso de usuarios remotos para la Directiva, desactive la casilla **Habilitar comunicaciones con usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="cf79e-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="cf79e-136">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cf79e-136">Click **Commit**.</span></span>

<span data-ttu-id="cf79e-137">Para habilitar el acceso de usuarios remotos, también debe habilitar el soporte técnico para el acceso de usuarios remotos en su organización.</span><span class="sxs-lookup"><span data-stu-id="cf79e-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="cf79e-138">Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="cf79e-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="cf79e-139">Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios que desee que puedan conectarse de forma remota.</span><span class="sxs-lookup"><span data-stu-id="cf79e-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="cf79e-140">Para obtener más información, vea [asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="cf79e-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

