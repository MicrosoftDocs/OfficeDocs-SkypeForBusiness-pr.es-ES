---
title: 'Lync Server 2013: configurar la compatibilidad con dominios externos bloqueados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf1b7b1da08a8c573b782474d7f2deb4ea9358a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="7055b-102">Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7055b-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7055b-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7055b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7055b-104">Si ha configurado la compatibilidad para socios federados, puede administrar los dominios que se bloquearán de la federación con su organización.</span><span class="sxs-lookup"><span data-stu-id="7055b-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="7055b-105">La lista de dominios bloqueados actuará como una lista de bloqueo (lista de entradas explícitas que no se van a permitir) y se aplicará en la detección de dominios federados, si tiene activada esta opción.</span><span class="sxs-lookup"><span data-stu-id="7055b-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="7055b-106">Para obtener más información, consulte [habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="7055b-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="7055b-p102">Bloquee uno o más dominios externos para que no puedan conectarse a su organización. Para hacerlo, agregue el dominio a la lista de dominios bloqueados.</span><span class="sxs-lookup"><span data-stu-id="7055b-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="7055b-109">Para agregar un dominio externo a la lista de dominios bloqueados</span><span class="sxs-lookup"><span data-stu-id="7055b-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="7055b-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7055b-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7055b-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7055b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7055b-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7055b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7055b-113">En la barra de navegación izquierda, haga clic en \*\*Acceso de usuarios externos \*\*.</span><span class="sxs-lookup"><span data-stu-id="7055b-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="7055b-114">Seleccione \*\*Dominios federados \*\*, haga clic en \*\*Nuevo \*\* y, a continuación, seleccione \*\*Dominio bloqueado \*\*.</span><span class="sxs-lookup"><span data-stu-id="7055b-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="7055b-115">En \*\*Nuevos dominios federados \*\*, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7055b-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="7055b-116">En \*\*Nombre de dominio (o FQDN) \*\*, escriba el nombre de dominio de socio federado que desea bloquear.</span><span class="sxs-lookup"><span data-stu-id="7055b-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7055b-117">El nombre no puede superar los 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7055b-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="7055b-p104">La búsqueda del dominio de socio federado busca la coincidencia de sufijos. Por ejemplo, si escribe <STRONG>contoso.com</STRONG>, la búsqueda devolverá el dominio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7055b-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="7055b-120">Un dominio de socio federado no puede bloquearse y permitirse simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="7055b-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="7055b-121">Lync Server 2013 impide que esto suceda, por lo que no es necesario sincronizar las listas.</span><span class="sxs-lookup"><span data-stu-id="7055b-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="7055b-122">(Opcional) En \*\*Comentario \*\*, escriba la información que desea compartir con otros administradores del sistema sobre esta configuración.</span><span class="sxs-lookup"><span data-stu-id="7055b-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="7055b-123">Haga clic en \*\*Confirmar \*\*.</span><span class="sxs-lookup"><span data-stu-id="7055b-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="7055b-124">Repita los pasos del 4 al 6 para cada socio federado que desee bloquear.</span><span class="sxs-lookup"><span data-stu-id="7055b-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="7055b-125">Para habilitar el acceso de usuarios federados, también debe permitir el acceso de usuarios federados en su organización.</span><span class="sxs-lookup"><span data-stu-id="7055b-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="7055b-126">Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7055b-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="7055b-127">Además, debe configurar y aplicar la directiva a los usuarios que quiera permitir que colaboren con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="7055b-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="7055b-128">Para obtener más información, consulte [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7055b-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

