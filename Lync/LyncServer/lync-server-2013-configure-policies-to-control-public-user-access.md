---
title: 'Lync Server 2013: Configurar directivas para controlar el acceso de usuarios públicos'
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
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="0dea5-102">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dea5-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dea5-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="0dea5-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="0dea5-104">La conectividad de mensajería instantánea pública (mi) permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería\!instantánea pública, como Windows Live Network de servicios de Internet, Yahoo y AOL.</span><span class="sxs-lookup"><span data-stu-id="0dea5-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="0dea5-105">Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios públicos pueden colaborar con usuarios internos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0dea5-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="0dea5-106">La conectividad de mensajería instantánea pública es una característica agregada que se basa en la configuración de la implementación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0dea5-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="0dea5-107">También depende del suministro del servicio en el proveedor de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="0dea5-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="0dea5-108">Para obtener más información sobre cómo aprovisionar su implementación para usar los proveedores públicos, consulte la guía de aprovisionamiento de la conectividad de mensajería instantánea pública para Microsoft Lync Server, Office Communications Server y Live Communications Server.[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="0dea5-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="0dea5-109">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="0dea5-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="0dea5-110">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="0dea5-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="0dea5-111">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="0dea5-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="0dea5-112">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="0dea5-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="0dea5-113">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="0dea5-113">has been announced.</span></span> <span data-ttu-id="0dea5-114">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0dea5-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="0dea5-115">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="0dea5-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="0dea5-116">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="0dea5-116">Messenger.</span></span> <span data-ttu-id="0dea5-117">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="0dea5-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="0dea5-118">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="0dea5-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="0dea5-119">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="0dea5-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="0dea5-120">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="0dea5-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="0dea5-121">Para acceder al sitio de aprovisionamiento de la conectividad de mensajería instantánea pública de Microsoft Lync Server, use el siguiente vínculo:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="0dea5-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="0dea5-122">Para controlar el acceso de los usuarios públicos, puede configurar directivas en el nivel global, de sitio y de usuario.</span><span class="sxs-lookup"><span data-stu-id="0dea5-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="0dea5-123">Para obtener más información sobre los tipos de directivas que puede configurar, vea [configurar la compatibilidad del acceso de usuarios externos en Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) en la documentación de implementación o en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="0dea5-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="0dea5-124">La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="0dea5-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="0dea5-125">La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="0dea5-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="0dea5-126">Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="0dea5-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="0dea5-127">En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software de cliente.</span><span class="sxs-lookup"><span data-stu-id="0dea5-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="0dea5-128">La solicitud se acepta a menos que los remitentes externos se bloquean explícitamente mediante una regla configurada por el usuario (es decir, la configuración de las listas **permitir** o **bloquear** del cliente del usuario).</span><span class="sxs-lookup"><span data-stu-id="0dea5-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="0dea5-129">Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario decide bloquear todos los mensajes instantáneos de usuarios que no estén en su lista de **permitidos** .</span><span class="sxs-lookup"><span data-stu-id="0dea5-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0dea5-130">Puede configurar directivas para controlar el acceso de usuarios públicos, incluso si no ha habilitado la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="0dea5-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="0dea5-131">Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitada la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="0dea5-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="0dea5-132">Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="0dea5-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="0dea5-133">Además, si especifica una directiva de usuario para controlar el acceso de los usuarios públicos, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server y que usan la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0dea5-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="0dea5-134">Para obtener detalles sobre cómo especificar usuarios públicos que pueden iniciar sesión en Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync server 2013</A> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="0dea5-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="0dea5-135">Use el procedimiento siguiente para configurar una directiva que admita el acceso de usuarios de uno o más proveedores de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="0dea5-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="0dea5-136">Para configurar una directiva de acceso externo para admitir el acceso de usuarios públicos</span><span class="sxs-lookup"><span data-stu-id="0dea5-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="0dea5-137">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0dea5-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0dea5-138">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0dea5-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0dea5-139">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0dea5-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0dea5-140">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="0dea5-141">En la página **Directiva de acceso externo** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0dea5-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="0dea5-142">Para configurar la directiva global para admitir el acceso de usuarios públicos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="0dea5-143">Para crear una nueva Directiva de sitio, haga clic en **nueva**y, a continuación, haga clic en **Directiva del sitio**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="0dea5-144">En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="0dea5-145">Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="0dea5-146">En **nueva Directiva de acceso externo**, cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita la comunicación para usuarios públicos).</span><span class="sxs-lookup"><span data-stu-id="0dea5-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="0dea5-147">Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0dea5-148">Faculta Si desea agregar o editar una descripción, especifique la información de la Directiva en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="0dea5-149">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0dea5-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="0dea5-150">Para habilitar el acceso de usuarios públicos para la Directiva, active la casilla **Habilitar comunicaciones con usuarios públicos** .</span><span class="sxs-lookup"><span data-stu-id="0dea5-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="0dea5-151">Para deshabilitar el acceso de usuarios públicos para la Directiva, desactive la casilla **Habilitar comunicaciones con usuarios públicos** .</span><span class="sxs-lookup"><span data-stu-id="0dea5-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="0dea5-152">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0dea5-152">Click **Commit**.</span></span>

<span data-ttu-id="0dea5-153">Para habilitar el acceso de usuarios públicos, también debe habilitar la compatibilidad con la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="0dea5-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="0dea5-154">Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0dea5-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="0dea5-155">Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios públicos que desee que puedan colaborar con los usuarios públicos.</span><span class="sxs-lookup"><span data-stu-id="0dea5-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="0dea5-156">Para obtener más información, consulte [asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0dea5-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0dea5-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dea5-157">See Also</span></span>


[<span data-ttu-id="0dea5-158">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dea5-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="0dea5-159">Administrar proveedores federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dea5-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

