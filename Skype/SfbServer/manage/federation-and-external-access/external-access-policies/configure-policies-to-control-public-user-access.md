---
title: Configurar directivas para controlar el acceso de usuarios públicos
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La conectividad de mensajería instantánea (MI) permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública.
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823596"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="d869a-103">Configurar directivas para controlar el acceso de usuarios públicos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d869a-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="d869a-104">La conectividad de mensajería instantánea (MI) pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="d869a-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="d869a-105">Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con usuarios internos de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d869a-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="d869a-106">La conectividad de mensajería instantánea pública es una característica adicional que se basa en la configuración de la implementación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d869a-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="d869a-107">También depende del aprovisionamiento del servicio en el proveedor de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="d869a-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="d869a-108">Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios públicos.</span><span class="sxs-lookup"><span data-stu-id="d869a-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="d869a-109">La configuración de directiva de Skype Empresarial Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="d869a-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d869a-110">La prioridad de las directivas de Skype Empresarial Server es: la directiva de usuario (mayor influencia) invalida una directiva de sitio y una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="d869a-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d869a-111">Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="d869a-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="d869a-p103">En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software cliente. Se acepta la solicitud a menos que los remitentes externos queden explícitamente bloqueados por una regla configurada por el usuario (es decir, la configuración de las listas **Permitir** y **Bloquear** del cliente del usuario). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario opta por bloquear todos los mensajes instantáneos de los usuarios que no estén en su lista **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="d869a-p103">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="d869a-115">Puede configurar directivas para controlar el acceso de usuarios públicos, incluso aunque no haya habilitado una federación para la organización.</span><span class="sxs-lookup"><span data-stu-id="d869a-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="d869a-116">Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización.</span><span class="sxs-lookup"><span data-stu-id="d869a-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="d869a-117">Para obtener más información sobre cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="d869a-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="d869a-118">Además, si especifica una directiva de usuario para controlar el acceso de usuarios públicos, la directiva solo se aplica a los usuarios habilitados para Skype Empresarial Server y configurados para usar la directiva.</span><span class="sxs-lookup"><span data-stu-id="d869a-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="d869a-119">Para obtener más información sobre cómo especificar usuarios públicos que pueden iniciar sesión en Skype Empresarial Server, consulte [Asignar una directiva de acceso de usuarios externos.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="d869a-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="d869a-120">Use el procedimiento que se describe a continuación para configurar una directiva que admita el acceso de usuarios de uno o varios proveedores de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="d869a-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="d869a-121">Para configurar una directiva de acceso externo para permitir el acceso de usuarios públicos</span><span class="sxs-lookup"><span data-stu-id="d869a-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="d869a-122">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d869a-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d869a-123">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d869a-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d869a-124">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="d869a-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="d869a-125">En la página  **Directiva de acceso externo**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="d869a-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d869a-126">Para configurar la directiva global para permitir el acceso de usuarios públicos, haga clic en la directiva global, en  **Editar** y en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d869a-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="d869a-p105">Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d869a-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="d869a-p106">Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita comunicaciones para usuarios públicos).</span><span class="sxs-lookup"><span data-stu-id="d869a-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="d869a-131">Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en  **Editar** y, a continuación en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d869a-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d869a-132">(Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="d869a-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="d869a-133">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="d869a-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="d869a-134">Para habilitar el acceso de usuarios públicos para la directiva, active la casilla  **Habilitar comunicaciones con usuarios públicos**.</span><span class="sxs-lookup"><span data-stu-id="d869a-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="d869a-135">Para deshabilitar el acceso de usuarios públicos para la directiva, desactive la casilla  **Habilitar comunicaciones con usuarios públicos**.</span><span class="sxs-lookup"><span data-stu-id="d869a-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="d869a-136">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d869a-136">Click **Commit**.</span></span>

<span data-ttu-id="d869a-137">Para habilitar el acceso de usuarios públicos, también debe permitir la federación en su organización.</span><span class="sxs-lookup"><span data-stu-id="d869a-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="d869a-138">Para obtener más información, [consulte Configurar directivas para controlar el acceso de usuarios federados en Skype Empresarial Server.](configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="d869a-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="d869a-139">Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios públicos que desee que puedan colaborar con usuarios públicos.</span><span class="sxs-lookup"><span data-stu-id="d869a-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d869a-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="d869a-140">See Also</span></span>

[<span data-ttu-id="d869a-141">Administrar proveedores federados SIP para la organización</span><span class="sxs-lookup"><span data-stu-id="d869a-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
