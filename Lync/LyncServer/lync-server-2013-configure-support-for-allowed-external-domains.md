---
title: 'Lync Server 2013: configurar la compatibilidad con dominios externos permitidos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8926bd9cdbc64b336b72c62c5171047ae096868
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="3e938-102">Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e938-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e938-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3e938-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3e938-p101">Si ha configurado la compatibilidad para socios federados, puede administrar qué dominios específicos pueden federar con su organización. Se configuran uno o más dominios externos específicos como dominios federados permitidos. Para hacerlo, agregue cada uno de los dominios a la lista de dominios admitidos. Incluso en el caso de que la detección de socios esté habilitada en la organización, haga lo anterior si el dominio es un socio federado que podría necesitar comunicarse con más de 1.000 usuarios o enviar más de 20 mensajes por segundo. Si la detección de socios no está habilitada en la organización, solo los usuarios de dominios externos que agregue a la lista de dominios permitidos podrán participar en reuniones y compartir mensajería instantánea con usuarios de su organización. Si desea restringir el acceso de un dominio federado a un servidor específico que ejecuta el servicio perimetral de acceso del socio federado, puede especificar el nombre de dominio del servidor que ejecuta el servicio perimetral de acceso para cada dominio de la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="3e938-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e938-110">Este procedimiento describe cómo configurar la compatibilidad para dominios específicos, pero para permitir usuarios federados es necesario habilitar también dicha compatibilidad en la organización y, además, configurar y aplicar directivas para determinar qué usuarios pueden colaborar con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="3e938-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="3e938-111">Para obtener más información sobre cómo habilitar la compatibilidad con usuarios federados, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e938-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="3e938-112">Para más información sobre la configuración de directivas para controlar la Federación, vea <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure Policies to control Federated User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e938-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="3e938-113">Para agregar un dominio externo a la lista de dominios permitidos</span><span class="sxs-lookup"><span data-stu-id="3e938-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="3e938-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3e938-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e938-115">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e938-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e938-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e938-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e938-117">En el barra de navegación izquierda, haga clic en **Acceso de usuarios externos** y, a continuación, en **Dominios federados**.</span><span class="sxs-lookup"><span data-stu-id="3e938-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="3e938-118">En la página **Dominios federados**, haga clic en **Nuevo** y, a continuación, seleccione **Dominio permitido**.</span><span class="sxs-lookup"><span data-stu-id="3e938-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="3e938-119">En **Nuevos dominios federados**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e938-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="3e938-120">En **Nombre de dominio (o FQDN)**, escriba el nombre de dominio de socio federado.</span><span class="sxs-lookup"><span data-stu-id="3e938-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3e938-p104">El nombre debe ser único y no puede haber otro dominio permitido con el mismo nombre en el servidor que ejecuta el servicio perimetral de acceso. El nombre no puede superar los 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3e938-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="3e938-p105">La búsqueda del dominio de socio federado busca la coincidencia de sufijos. Por ejemplo, si escribe <STRONG>contoso.com</STRONG>, la búsqueda devolverá el dominio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3e938-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="3e938-125">Un dominio de socio federado no puede bloquearse y permitirse simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="3e938-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="3e938-126">Lync Server 2013 impide que esto suceda, por lo que no es necesario sincronizar las listas.</span><span class="sxs-lookup"><span data-stu-id="3e938-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="3e938-127">Si desea restringir el acceso de este dominio federado a usuarios de un servidor específico que ejecuta el servicio perimetral de acceso, en **Servicio perimetral de acceso(FQDN)**, escriba el FQDN del servidor del dominio federado que ejecuta el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="3e938-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="3e938-128">Si desea proporcionar información adicional, en **Comentario**, escriba la información que desee compartir con otros administradores del sistema sobre esta configuración.</span><span class="sxs-lookup"><span data-stu-id="3e938-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="3e938-129">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3e938-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="3e938-130">Repita los pasos del 4 al 6 para cada dominio de socio federado que desee permitir.</span><span class="sxs-lookup"><span data-stu-id="3e938-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="3e938-131">Para habilitar el acceso de usuarios federados, también debe permitir el acceso de usuarios federados en su organización.</span><span class="sxs-lookup"><span data-stu-id="3e938-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="3e938-132">Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3e938-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="3e938-133">Además, debe configurar y aplicar la directiva a los usuarios que quiera permitir que colaboren con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="3e938-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="3e938-134">Para obtener más información, consulte [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3e938-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

