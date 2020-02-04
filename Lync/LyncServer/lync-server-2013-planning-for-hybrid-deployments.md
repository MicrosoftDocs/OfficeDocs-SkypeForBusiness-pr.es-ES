---
title: 'Lync Server 2013: planeamiento de implementaciones híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="60ee6-102">Planeación de implementaciones híbridas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ee6-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60ee6-103">_**Última modificación del tema:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="60ee6-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="60ee6-104">Al planear una implementación híbrida, debe tener en cuenta los siguientes requisitos para los usuarios y su infraestructura de red.</span><span class="sxs-lookup"><span data-stu-id="60ee6-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="60ee6-105">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="60ee6-105">Infrastructure Requirements</span></span>

<span data-ttu-id="60ee6-106">Debe tener el siguiente configurado en su entorno para implementar e implementar una implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="60ee6-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="60ee6-107">Un inquilino de Microsoft Office 365 con Skype empresarial online habilitado.</span><span class="sxs-lookup"><span data-stu-id="60ee6-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="60ee6-108">Tenga en cuenta que solo puede usar un único inquilino para una configuración híbrida con su implementación local.</span><span class="sxs-lookup"><span data-stu-id="60ee6-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="60ee6-109">Una sola implementación local (infraestructura) de Skype empresarial Server o Lync Server implementada en una topología compatible.</span><span class="sxs-lookup"><span data-stu-id="60ee6-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="60ee6-110">Consulte requisitos de topología.</span><span class="sxs-lookup"><span data-stu-id="60ee6-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="60ee6-111">Para obtener información sobre cómo configurar su implementación de Lync Server 2013 o Lync Server 2010 para entornos híbridos, consulte [configuración de implementaciones híbridas de Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="60ee6-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="60ee6-112">Herramientas administrativas de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="60ee6-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="60ee6-113">Si está usando Lync Server 2013 o Lync Server 2010, puede usar las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60ee6-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="60ee6-114">Para admitir el inicio de sesión único con Office 365 de modo que los usuarios puedan usar las mismas credenciales de inicio de sesión para iniciar sesión en Office como locales, puede usar las características de sincronización de contraseñas de Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="60ee6-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="60ee6-115">También puede usar los Servicios de federación de Active Directory (AD FS) para el inicio de sesión único con Office 365.</span><span class="sxs-lookup"><span data-stu-id="60ee6-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="60ee6-116">Para obtener más información, consulte [integrar las identidades locales con Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="60ee6-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="60ee6-117">Una única solución de sincronización de directorios para mantener sincronizados los objetos de Active Directory locales y en línea.</span><span class="sxs-lookup"><span data-stu-id="60ee6-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="60ee6-118">Para obtener más información sobre la sincronización de directorios, consulte [herramientas de integración de directorios](http://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="60ee6-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="60ee6-119">Compatibilidad con clientes de Lync</span><span class="sxs-lookup"><span data-stu-id="60ee6-119">Lync Client Support</span></span>

<span data-ttu-id="60ee6-120">Existen algunas diferencias en las características compatibles con los clientes de Lync, así como las características disponibles en entornos locales y en línea.</span><span class="sxs-lookup"><span data-stu-id="60ee6-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="60ee6-121">Antes de decidir dónde desea alojar a los usuarios de su organización, puede ver la compatibilidad de cliente para las distintas configuraciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60ee6-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="60ee6-122">Los siguientes clientes son compatibles con Skype empresarial online en una implementación híbrida de Lync:</span><span class="sxs-lookup"><span data-stu-id="60ee6-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="60ee6-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="60ee6-123">Lync 2010</span></span>

  - <span data-ttu-id="60ee6-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="60ee6-124">Lync 2013</span></span>

  - <span data-ttu-id="60ee6-125">Aplicación de la Tienda Windows de Lync</span><span class="sxs-lookup"><span data-stu-id="60ee6-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="60ee6-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="60ee6-126">Lync Web App</span></span>

  - <span data-ttu-id="60ee6-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="60ee6-127">Lync Mobile</span></span>

  - <span data-ttu-id="60ee6-128">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="60ee6-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="60ee6-129">Sistema Lync Room</span><span class="sxs-lookup"><span data-stu-id="60ee6-129">Lync Room System</span></span>

  - <span data-ttu-id="60ee6-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="60ee6-130">Lync Basic 2013</span></span>

<span data-ttu-id="60ee6-131">Para obtener más información sobre la compatibilidad del cliente, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="60ee6-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="60ee6-132">Clientes de Lync Online</span><span class="sxs-lookup"><span data-stu-id="60ee6-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="60ee6-133">Tablas de comparación de clientes para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ee6-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="60ee6-134">Tablas de comparación de clientes móviles para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ee6-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="60ee6-135">Requisitos de topología</span><span class="sxs-lookup"><span data-stu-id="60ee6-135">Topology Requirements</span></span>

<span data-ttu-id="60ee6-136">Para configurar la implementación de un entorno híbrido con Skype empresarial online, debe tener una de las siguientes topologías compatibles:</span><span class="sxs-lookup"><span data-stu-id="60ee6-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="60ee6-137">Una implementación de Skype empresarial Server 2015 con todos los servidores que ejecutan Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="60ee6-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="60ee6-138">Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60ee6-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="60ee6-139">Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 y las últimas actualizaciones acumulativas.</span><span class="sxs-lookup"><span data-stu-id="60ee6-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="60ee6-140">El servidor perimetral de Federación y el servidor de próximo salto del servidor perimetral de Federación deben ejecutar Lync Server 2010 con las últimas actualizaciones acumulativas.</span><span class="sxs-lookup"><span data-stu-id="60ee6-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="60ee6-141">Las herramientas administrativas de Skype empresarial Server 2015 o Lync Server 2013 deben instalarse en al menos un servidor o en una estación de trabajo de administración.</span><span class="sxs-lookup"><span data-stu-id="60ee6-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="60ee6-142">Una implementación mixta de Lync Server 2013 y Skype empresarial Server 2015 con los siguientes roles de servidor en al menos un sitio que ejecute Skype empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="60ee6-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="60ee6-143">Al menos un grupo de servidores Enterprise o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="60ee6-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="60ee6-144">El grupo de directores asociado con la federación SIP, si existe</span><span class="sxs-lookup"><span data-stu-id="60ee6-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="60ee6-145">El grupo de servidores perimetrales asociado con la federación SIP</span><span class="sxs-lookup"><span data-stu-id="60ee6-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="60ee6-146">Una implementación mixta de Lync Server 2010 y Skype empresarial Server 2015 con los siguientes servidores en al menos un sitio que ejecute Skype empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="60ee6-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="60ee6-147">Al menos un grupo de servidores Enterprise o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="60ee6-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="60ee6-148">El grupo de directores asociado con la federación SIP, si existe</span><span class="sxs-lookup"><span data-stu-id="60ee6-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="60ee6-149">El grupo de servidores perimetrales asociado con la federación SIP para el sitio</span><span class="sxs-lookup"><span data-stu-id="60ee6-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="60ee6-150">Una implementación mixta de Lync Server 2010 y Lync Server 2013 con los siguientes roles de servidor en al menos un sitio que ejecute Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="60ee6-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="60ee6-151">Al menos un grupo de servidores Enterprise o un servidor Standard Edition en el sitio</span><span class="sxs-lookup"><span data-stu-id="60ee6-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="60ee6-152">El grupo de directores asociado con la federación SIP, si existe en el sitio</span><span class="sxs-lookup"><span data-stu-id="60ee6-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="60ee6-153">El grupo de servidores perimetrales asociado con la federación SIP para el sitio</span><span class="sxs-lookup"><span data-stu-id="60ee6-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="60ee6-154">Toda la administración de usuarios, incluidos los movimientos de usuario locales y UNRESOLVED_TOKEN_VAL (skypeforbusiness) en línea, debe realizarse con la última versión instalada de las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="60ee6-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="60ee6-155">Las herramientas administrativas deben instalarse en un servidor independiente que tenga acceso de conexión a la implementación local existente y a Internet.</span><span class="sxs-lookup"><span data-stu-id="60ee6-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="60ee6-156">El cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> para mover usuarios de la implementación local a UNRESOLVED_TOKEN_VAL (skype16_online) debe ejecutarse desde las herramientas administrativas conectadas a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="60ee6-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="60ee6-157">Para obtener más información sobre las topologías admitidas, consulte topologías [admitidas en Lync server 2013](lync-server-2013-supported-topologies.md)y [topologías de referencia de Lync Server 2013 para implementaciones híbridas empresariales](http://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="60ee6-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="60ee6-158">Para obtener información sobre la solución de problemas de implementaciones híbridas y sobre cómo conectar PowerShell a Lync Online, vea [Lync Online: Lync PowerShell y solución de problemas híbrida](http://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="60ee6-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="60ee6-159">Requisitos para las listas de Federación permitida/bloqueada</span><span class="sxs-lookup"><span data-stu-id="60ee6-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="60ee6-p108">La lista de dominios permitidos incluye los dominios que tienen configurado un nombre de dominio completo (FQDN) del perímetro de asociado. En ocasiones, se conocen como *servidores de asociado permitidos* o *asociados directos de federación*. Familiarícese con la diferencia entre las federaciones abiertas y cerradas, conocidas respectivamente como *detección de asociado* o *lista de dominios de asociado permitidos* en las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="60ee6-p108">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured. These are sometimes referred to as *allowed partner servers* or *direct federation partners*. You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="60ee6-163">Los requisitos siguientes necesitan cumplirse para configurar correctamente una implementación híbrida:</span><span class="sxs-lookup"><span data-stu-id="60ee6-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="60ee6-p109">La coincidencia de dominios necesita configurarse de la misma manera para la implementación local y para el inquilino de Office 365. Si la detección de asociado está habilitada en la implementación local, configure una federación abierta para el inquilino en línea. Si, por el contrario, la detección de asociado no está habilitada, configure una federación cerrada para el inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="60ee6-p109">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="60ee6-167">La lista de dominios bloqueados de la implementación local necesita coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="60ee6-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="60ee6-168">La lista de dominios permitidos de la implementación local necesita coincidir exactamente con la lista de dominios permitidos del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="60ee6-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="60ee6-169">La Federación debe habilitarse para las comunicaciones externas del inquilino en línea, que se configura con el panel de control de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="60ee6-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="60ee6-170">Configuración DNS</span><span class="sxs-lookup"><span data-stu-id="60ee6-170">DNS Settings</span></span>

<span data-ttu-id="60ee6-171">Al crear registros DNS para implementaciones híbridas, todos los registros DNS externos de Lync deberían apuntar a la infraestructura local.</span><span class="sxs-lookup"><span data-stu-id="60ee6-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="60ee6-172">Para obtener más información sobre los registros DNS necesarios, consulte [los requisitos del sistema de nombres de dominio (DNS) de Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60ee6-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="60ee6-173">Además, debe asegurarse de que la resolución DNS que se describe en la siguiente tabla funciona en su implementación local:</span><span class="sxs-lookup"><span data-stu-id="60ee6-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60ee6-174">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="60ee6-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="60ee6-175">Lo puede resolver</span><span class="sxs-lookup"><span data-stu-id="60ee6-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="60ee6-176">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="60ee6-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60ee6-177">Registro SRV de DNS para _sipfederationtls. _tcp. &lt;sipdomain.com&gt; para todos los dominios SIP compatibles que se resuelven para acceder a las IP externas perimetrales</span><span class="sxs-lookup"><span data-stu-id="60ee6-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="60ee6-178">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="60ee6-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="60ee6-p111">Habilite la comunicación federada en una configuración híbrida. El servidor perimetral tiene que saber hacia dónde redirigir el tráfico federado para el dominio SIP que se divide entre las formas local y en línea.</span><span class="sxs-lookup"><span data-stu-id="60ee6-p111">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60ee6-181">DNS un registro (s) para el servicio de conferencias web perimetrales FQDN, por ejemplo, webcon.contoso.com la resolución de las IP externas perimetrales de la conferencia Web</span><span class="sxs-lookup"><span data-stu-id="60ee6-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="60ee6-182">Equipos de usuarios conectados a la red corporativa interna</span><span class="sxs-lookup"><span data-stu-id="60ee6-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="60ee6-183">Permitir que los usuarios en línea presenten o vean contenido en reuniones hospedadas en el entorno.</span><span class="sxs-lookup"><span data-stu-id="60ee6-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="60ee6-184">El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="60ee6-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="60ee6-185">Según el modo en que se configure DNS en su organización, es posible que tenga que agregar estos registros a la zona DNS hospedada interna de los dominios SIP correspondientes para proporcionar resolución DNS interna a estos registros.</span><span class="sxs-lookup"><span data-stu-id="60ee6-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="60ee6-186">Consideraciones sobre el Firewall</span><span class="sxs-lookup"><span data-stu-id="60ee6-186">Firewall Considerations</span></span>

<span data-ttu-id="60ee6-187">Los equipos de la red deben poder realizar búsquedas DNS estándar de Internet.</span><span class="sxs-lookup"><span data-stu-id="60ee6-187">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="60ee6-188">Si estos equipos pueden comunicarse con sitios de Internet estándar, su red cumple con este requisito.</span><span class="sxs-lookup"><span data-stu-id="60ee6-188">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="60ee6-189">En función de la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de Firewall de red para que acepten conexiones basadas en nombres de dominio con comodín ( \*por ejemplo, todo el tráfico de. Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="60ee6-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="60ee6-190">Si los firewalls de su organización no admiten configuraciones de nombre comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.</span><span class="sxs-lookup"><span data-stu-id="60ee6-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="60ee6-191">Consulte el tema de ayuda [Office 365 URL e intervalos de direcciones IP](http://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="60ee6-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="60ee6-192">Requisitos de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="60ee6-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="60ee6-193">Además de los requisitos de puerto para la comunicación interna de Lync Server 2013, también debe configurar los siguientes puertos.</span><span class="sxs-lookup"><span data-stu-id="60ee6-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60ee6-194">Protocolo/puerto</span><span class="sxs-lookup"><span data-stu-id="60ee6-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="60ee6-195">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="60ee6-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60ee6-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="60ee6-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="60ee6-197">Entrada abierta</span><span class="sxs-lookup"><span data-stu-id="60ee6-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="60ee6-198">Servicios de Federación de Active Directory (rol de servidor de Federación)</span><span class="sxs-lookup"><span data-stu-id="60ee6-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="60ee6-199">Para obtener más información, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS role Services</a>.</span><span class="sxs-lookup"><span data-stu-id="60ee6-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="60ee6-200">Servicios de Federación de Active Directory (rol de servidor proxy)</span><span class="sxs-lookup"><span data-stu-id="60ee6-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="60ee6-201">Portal de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="60ee6-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="60ee6-202">Portal de mi empresa</span><span class="sxs-lookup"><span data-stu-id="60ee6-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="60ee6-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="60ee6-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="60ee6-204">Cliente de Lync (comunicación a Lync Online desde Lync Server local)</span><span class="sxs-lookup"><span data-stu-id="60ee6-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60ee6-205">TCP 80 y 443</span><span class="sxs-lookup"><span data-stu-id="60ee6-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="60ee6-206">Entrada abierta</span><span class="sxs-lookup"><span data-stu-id="60ee6-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="60ee6-207">Herramienta de sincronización de directorios de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="60ee6-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60ee6-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="60ee6-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="60ee6-209">Entrada o salida abierta en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="60ee6-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60ee6-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="60ee6-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="60ee6-211">Entrada o salida abierta para sesiones de uso compartido de datos</span><span class="sxs-lookup"><span data-stu-id="60ee6-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60ee6-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="60ee6-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="60ee6-213">Entrada o salida abierta para sesiones de uso compartido de aplicaciones, vídeo y audio</span><span class="sxs-lookup"><span data-stu-id="60ee6-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60ee6-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="60ee6-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="60ee6-215">Entrada o salida abierta para sesiones de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="60ee6-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60ee6-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="60ee6-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="60ee6-217">Salida abierta para sesiones de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="60ee6-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="60ee6-218">Cuentas de usuario y datos</span><span class="sxs-lookup"><span data-stu-id="60ee6-218">User Accounts and Data</span></span>

<span data-ttu-id="60ee6-219">En una implementación híbrida de Lync Server 2013, todos los usuarios que desee que se encontrarán en Lync Online deben crearse en la implementación local, de modo que la cuenta de usuario se cree en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="60ee6-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="60ee6-220">Después, puede mover el usuario a Skype empresarial online, que moverá la lista de contactos del usuario.</span><span class="sxs-lookup"><span data-stu-id="60ee6-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="60ee6-221">Al sincronizar cuentas de usuario entre su Lync local y las implementaciones de Lync Online con AD FS y DirSync, debe sincronizar las cuentas de AD de todos los usuarios de Lync de su organización entre las implementaciones de Lync locales y en línea, incluso si los usuarios no se mueven a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="60ee6-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="60ee6-222">Si no sincroniza todos los usuarios, puede ser que la comunicación entre los usuarios locales y en línea de su organización no funcione como se podría esperar.</span><span class="sxs-lookup"><span data-stu-id="60ee6-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="60ee6-223">Si el usuario se crea mediante el portal en línea para Office 365, la cuenta de usuario no se sincronizará con Active Directory local y el usuario no existirá en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="60ee6-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="60ee6-224">Si ya ha creado usuarios en Lync Online y desea configurar un entorno híbrido con un servidor de Lync local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">mover usuarios de Lync Online a Lync local en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="60ee6-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="60ee6-225">También debe tener en cuenta los siguientes problemas relacionados con el usuario al planear una implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="60ee6-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="60ee6-226">**Contactos de usuarios**   el límite de contactos para los usuarios de Lync Online es 250.</span><span class="sxs-lookup"><span data-stu-id="60ee6-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="60ee6-227">Los contactos que se encuentren por encima de ese número se eliminarán de la lista de contactos del usuario cuando se mueva la cuenta a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="60ee6-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="60ee6-228">**Mensajería instantánea y presencia**   las listas de contactos, los grupos y las listas de control de acceso (ACL) se migran con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="60ee6-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="60ee6-229">**Datos de conferencia, contenido de la reunión y reuniones**   programadas este contenido no se migra con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="60ee6-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="60ee6-230">Los usuarios deben reprogramar las reuniones después de migrar sus cuentas a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="60ee6-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="60ee6-231">Directivas de usuario y características</span><span class="sxs-lookup"><span data-stu-id="60ee6-231">User Policies and Features</span></span>

  - <span data-ttu-id="60ee6-232">En un entorno híbrido de Lync Server 2013, se puede habilitar a los usuarios para mensajería instantánea, voz y reuniones locales o en línea, pero no ambos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="60ee6-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="60ee6-233">**Cliente de Lync**     es posible que algunos usuarios necesiten una nueva versión de cliente cuando se muevan a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="60ee6-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="60ee6-234">Para Office Communications Server 2007 R2, los usuarios deben moverse a un grupo de servidores de Lync Server 2013 antes de la migración a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="60ee6-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="60ee6-235">Para obtener más información sobre la compatibilidad del cliente, consulte [clientes para Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) y [configuración de puertos de red y clientes de Lync compatibles](http://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="60ee6-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="60ee6-236">**Las directivas locales y de configuración (no de usuario)**   en línea y en las directivas locales requieren una configuración independiente.</span><span class="sxs-lookup"><span data-stu-id="60ee6-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="60ee6-237">No puede establecer directivas globales que se apliquen a ambos.</span><span class="sxs-lookup"><span data-stu-id="60ee6-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

