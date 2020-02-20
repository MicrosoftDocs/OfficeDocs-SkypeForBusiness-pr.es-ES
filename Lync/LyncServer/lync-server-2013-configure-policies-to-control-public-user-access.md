---
title: 'Lync Server 2013: configurar directivas para controlar el acceso de usuarios públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a6e5d94cef7c9f25bb1c4091a981603f66da82
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="09e35-102">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e35-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09e35-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="09e35-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="09e35-104">La conectividad de mensajería instantánea pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por los proveedores de servicios de mensajería instantánea pública\!, incluida la red de Windows Live de servicios de Internet, Yahoo y AOL.</span><span class="sxs-lookup"><span data-stu-id="09e35-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="09e35-105">Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con usuarios internos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09e35-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="09e35-106">La conectividad de mensajería instantánea pública es una característica agregada que se basa en la configuración de la implementación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="09e35-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="09e35-107">También depende del aprovisionamiento del servicio en el proveedor de mi pública.</span><span class="sxs-lookup"><span data-stu-id="09e35-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="09e35-108">Para obtener información sobre cómo aprovisionar la implementación para usar los proveedores públicos, consulte la guía de aprovisionamiento de la conectividad de mensajería instantánea pública para Microsoft Lync Server, Office Communications Server y Live Communications Server.[https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="09e35-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="09e35-109">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="09e35-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="09e35-110">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="09e35-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="09e35-111">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="09e35-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="09e35-112">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="09e35-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="09e35-113">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="09e35-113">has been announced.</span></span> <span data-ttu-id="09e35-114">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="09e35-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="09e35-115">La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="09e35-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="09e35-116">Service.</span><span class="sxs-lookup"><span data-stu-id="09e35-116">Messenger.</span></span> <span data-ttu-id="09e35-117">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</span><span class="sxs-lookup"><span data-stu-id="09e35-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="09e35-118">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="09e35-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="09e35-119">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="09e35-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="09e35-120">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="09e35-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="09e35-121">Para obtener acceso al sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Microsoft Lync Server, use el siguiente vínculo:[https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="09e35-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="09e35-122">Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios públicos.</span><span class="sxs-lookup"><span data-stu-id="09e35-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="09e35-123">Para obtener más información sobre los tipos de directivas que puede configurar, consulte [Configuring Support for external User Access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) en la documentación sobre implementación o la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="09e35-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="09e35-124">La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="09e35-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="09e35-125">La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="09e35-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="09e35-126">Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="09e35-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="09e35-p106">En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software cliente. Se acepta la solicitud a menos que los remitentes externos queden explícitamente bloqueados por una regla configurada por el usuario (es decir, la configuración de las listas **Permitir** y **Bloquear** del cliente del usuario). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario opta por bloquear todos los mensajes instantáneos de los usuarios que no estén en su lista **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="09e35-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09e35-130">Puede configurar directivas para controlar el acceso de usuarios públicos, incluso aunque no haya habilitado una federación para la organización.</span><span class="sxs-lookup"><span data-stu-id="09e35-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="09e35-131">Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización.</span><span class="sxs-lookup"><span data-stu-id="09e35-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="09e35-132">Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="09e35-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="09e35-133">Además, si especifica una directiva de usuario para controlar el acceso de los usuarios públicos, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server y que están configurados para usar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="09e35-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="09e35-134">Para obtener información detallada sobre cómo especificar usuarios públicos que pueden iniciar sesión en Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync server 2013</A> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="09e35-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="09e35-135">Use el procedimiento que se describe a continuación para configurar una directiva que admita el acceso de usuarios de uno o varios proveedores de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="09e35-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="09e35-136">Para configurar una directiva de acceso externo para permitir el acceso de usuarios públicos</span><span class="sxs-lookup"><span data-stu-id="09e35-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="09e35-137">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="09e35-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09e35-138">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09e35-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="09e35-139">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09e35-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="09e35-140">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="09e35-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="09e35-141">En la página  \*\*Directiva de acceso externo \*\*, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="09e35-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="09e35-142">Para configurar la directiva global para permitir el acceso de usuarios públicos, haga clic en la directiva global, en  \*\*Editar \*\* y en  \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="09e35-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="09e35-p109">Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="09e35-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="09e35-p110">Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita comunicaciones para usuarios públicos).</span><span class="sxs-lookup"><span data-stu-id="09e35-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="09e35-147">Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en  \*\*Editar \*\* y, a continuación en  \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="09e35-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="09e35-148">(Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="09e35-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="09e35-149">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="09e35-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="09e35-150">Para habilitar el acceso de usuarios públicos para la directiva, active la casilla  \*\*Habilitar comunicaciones con usuarios públicos \*\*.</span><span class="sxs-lookup"><span data-stu-id="09e35-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="09e35-151">Para deshabilitar el acceso de usuarios públicos para la directiva, desactive la casilla  \*\*Habilitar comunicaciones con usuarios públicos \*\*.</span><span class="sxs-lookup"><span data-stu-id="09e35-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="09e35-152">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="09e35-152">Click **Commit**.</span></span>

<span data-ttu-id="09e35-153">Para habilitar el acceso de usuarios públicos, también debe permitir la federación en su organización.</span><span class="sxs-lookup"><span data-stu-id="09e35-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="09e35-154">Para obtener más información, consulte [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="09e35-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="09e35-155">Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios públicos que desee que puedan colaborar con usuarios públicos.</span><span class="sxs-lookup"><span data-stu-id="09e35-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="09e35-156">Para obtener más información, consulte [asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="09e35-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09e35-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="09e35-157">See Also</span></span>


[<span data-ttu-id="09e35-158">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e35-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="09e35-159">Administrar proveedores federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e35-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

