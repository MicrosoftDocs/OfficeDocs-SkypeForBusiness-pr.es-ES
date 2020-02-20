---
title: 'Lync Server 2013: Planeación de implementaciones híbridas'
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
ms.openlocfilehash: c70002eb7be67c221997465b6cdd5d252df284db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="0aa4c-102">Planeación de implementaciones híbridas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0aa4c-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0aa4c-103">_**Última modificación del tema:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="0aa4c-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="0aa4c-104">Al planear una implementación híbrida, debe tener en cuenta los siguientes requisitos para los usuarios y la infraestructura de red.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="0aa4c-105">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="0aa4c-105">Infrastructure Requirements</span></span>

<span data-ttu-id="0aa4c-106">Debe tener la siguiente configuración en su entorno para implementar e implementar una implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="0aa4c-107">Un inquilino de Microsoft Office 365 con Skype empresarial online habilitado.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="0aa4c-108">Tenga en cuenta que solo puede usar un único inquilino para una configuración híbrida con su implementación local.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="0aa4c-109">Una única implementación local (infraestructura) de Skype empresarial Server o Lync Server que se implementa en una topología admitida.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="0aa4c-110">Consulte topología requirements.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="0aa4c-111">Para obtener información sobre cómo configurar la implementación de Lync Server 2013 o Lync Server 2010 para entornos híbridos, consulte [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="0aa4c-112">Herramientas administrativas de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="0aa4c-113">Si usa Lync Server 2013 o Lync Server 2010, puede usar las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="0aa4c-114">Para admitir el inicio de sesión único con Office 365 para que los usuarios puedan usar las mismas credenciales de inicio de sesión para iniciar sesión en Office de forma local, puede usar las características de sincronización de contraseñas de Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="0aa4c-115">También puede usar los servicios de Federación de Active Directory (AD FS) para el inicio de sesión único con Office 365.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="0aa4c-116">Para obtener más información, consulte [Integración de las identidades locales con Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="0aa4c-117">Una solución de sincronización de directorios única para mantener sincronizados los objetos de Active Directory locales y en línea.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="0aa4c-118">Para obtener más información acerca de la sincronización de directorios, consulte [herramientas de integración de directorios](https://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-118">For details about Directory Synchronization, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="0aa4c-119">Compatibilidad con clientes de Lync</span><span class="sxs-lookup"><span data-stu-id="0aa4c-119">Lync Client Support</span></span>

<span data-ttu-id="0aa4c-120">Existen algunas diferencias en las características admitidas en los clientes de Lync, así como las características disponibles en entornos locales y en línea.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="0aa4c-121">Antes de decidir dónde desea hospedar a los usuarios de su organización, puede ver la compatibilidad de clientes para las distintas configuraciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="0aa4c-122">Los siguientes clientes son compatibles con Skype empresarial online en una implementación híbrida de Lync:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="0aa4c-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0aa4c-123">Lync 2010</span></span>

  - <span data-ttu-id="0aa4c-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0aa4c-124">Lync 2013</span></span>

  - <span data-ttu-id="0aa4c-125">Aplicación Lync de la tienda Windows</span><span class="sxs-lookup"><span data-stu-id="0aa4c-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="0aa4c-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="0aa4c-126">Lync Web App</span></span>

  - <span data-ttu-id="0aa4c-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="0aa4c-127">Lync Mobile</span></span>

  - <span data-ttu-id="0aa4c-128">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="0aa4c-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="0aa4c-129">Sistema Lync Room</span><span class="sxs-lookup"><span data-stu-id="0aa4c-129">Lync Room System</span></span>

  - <span data-ttu-id="0aa4c-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="0aa4c-130">Lync Basic 2013</span></span>

<span data-ttu-id="0aa4c-131">Para obtener más información acerca de la compatibilidad de clientes, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="0aa4c-132">Clientes para Lync Online</span><span class="sxs-lookup"><span data-stu-id="0aa4c-132">Clients for Lync Online</span></span>](https://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="0aa4c-133">Tablas de comparación de clientes para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0aa4c-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="0aa4c-134">Tablas de comparación de clientes móviles para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0aa4c-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="0aa4c-135">Requisitos de topología</span><span class="sxs-lookup"><span data-stu-id="0aa4c-135">Topology Requirements</span></span>

<span data-ttu-id="0aa4c-136">Para configurar la implementación de en entornos híbridos con Skype empresarial online, debe disponer de una de las siguientes topologías admitidas:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="0aa4c-137">Una implementación de Skype empresarial Server 2015 con todos los servidores que ejecutan Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="0aa4c-138">Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="0aa4c-139">Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 con las actualizaciones acumulativas más recientes.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="0aa4c-140">El servidor perimetral de Federación y el servidor de próximo salto del servidor perimetral de Federación deben ejecutar Lync Server 2010 con las actualizaciones acumulativas más recientes.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="0aa4c-141">Las herramientas administrativas de Skype empresarial Server 2015 o Lync Server 2013 deben instalarse en al menos un servidor o una estación de trabajo de administración.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="0aa4c-142">Una implementación mixta de Lync Server 2013 y Skype empresarial Server 2015 con los siguientes roles de servidor en al menos un sitio que ejecute Skype empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="0aa4c-143">Al menos un grupo de servidores Enterprise o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0aa4c-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="0aa4c-144">El grupo de directores asociado con la Federación SIP, si existe</span><span class="sxs-lookup"><span data-stu-id="0aa4c-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="0aa4c-145">El grupo de servidores perimetrales asociado con la Federación SIP</span><span class="sxs-lookup"><span data-stu-id="0aa4c-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="0aa4c-146">Una implementación mixta de Lync Server 2010 y Skype empresarial Server 2015 con los siguientes roles de servidores en al menos un sitio que ejecute Skype empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="0aa4c-147">Al menos un grupo de servidores Enterprise o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0aa4c-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="0aa4c-148">El grupo de directores asociado con la Federación SIP, si existe</span><span class="sxs-lookup"><span data-stu-id="0aa4c-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="0aa4c-149">El grupo de servidores perimetrales asociado con la Federación SIP para el sitio</span><span class="sxs-lookup"><span data-stu-id="0aa4c-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="0aa4c-150">Una implementación mixta de Lync Server 2010 y Lync Server 2013 con los siguientes roles de servidor en al menos un sitio que ejecute Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="0aa4c-151">Al menos un grupo de servidores Enterprise o un servidor Standard Edition en el sitio</span><span class="sxs-lookup"><span data-stu-id="0aa4c-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="0aa4c-152">El grupo de directores asociado con la Federación SIP, si existe en el sitio</span><span class="sxs-lookup"><span data-stu-id="0aa4c-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="0aa4c-153">El grupo de servidores perimetrales asociado con la Federación SIP para el sitio</span><span class="sxs-lookup"><span data-stu-id="0aa4c-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0aa4c-154">Toda la administración de usuarios, incluidos los movimientos de usuario entre locales y UNRESOLVED_TOKEN_VAL (skypeforbusiness) en línea, debe realizarse con la última versión instalada de las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="0aa4c-155">Las herramientas administrativas deben instalarse en un servidor independiente que tenga acceso de conexión a la implementación local existente y a Internet.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="0aa4c-156">El cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> para mover usuarios desde la implementación local a UNRESOLVED_TOKEN_VAL (skype16_online) debe ejecutarse desde las herramientas administrativas conectadas a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="0aa4c-157">Para obtener más información acerca de las topologías admitidas, consulte topologías [admitidas en Lync server 2013](lync-server-2013-supported-topologies.md)y las [topologías de referencia de Lync Server 2013 para implementaciones híbridas empresariales](https://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="0aa4c-158">Para solucionar problemas de la información sobre implementaciones híbridas y conectar PowerShell a Lync Online, consulte [Lync Online: Lync PowerShell y Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="0aa4c-159">Requisitos para las listas de Federación permitidas/bloqueadas</span><span class="sxs-lookup"><span data-stu-id="0aa4c-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="0aa4c-160">La lista de dominios permitidos incluye los dominios que tienen configurado un nombre de dominio completo (FQDN) de un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="0aa4c-161">A veces se denominan *servidores asociados permitidos* o *socios de Federación directa*.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="0aa4c-162">Debe estar familiarizado con la diferencia entre la Federación abierta y la Federación cerrada, a las que se hace referencia como *detección de asociados* y lista de *dominios de asociados permitidos*, respectivamente, en implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="0aa4c-163">Se deben cumplir los siguientes requisitos para configurar correctamente una implementación híbrida:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="0aa4c-164">La coincidencia de dominios debe configurarse de la misma manera para la implementación local y el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-164">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant.</span></span> <span data-ttu-id="0aa4c-165">Si la detección de asociados está habilitada en la implementación local, se debe configurar la Federación abierta para el inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="0aa4c-166">Si la detección de asociados no está habilitada, la Federación cerrada debe configurarse para el inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="0aa4c-167">La lista de dominios bloqueados en la implementación local debe coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="0aa4c-168">La lista de dominios permitidos de la implementación local debe coincidir exactamente con la lista de dominios permitidos del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="0aa4c-169">La Federación debe estar habilitada para las comunicaciones externas del inquilino en línea, que se configura mediante el panel de control de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="0aa4c-170">Configuración de DNS</span><span class="sxs-lookup"><span data-stu-id="0aa4c-170">DNS Settings</span></span>

<span data-ttu-id="0aa4c-171">Al crear registros DNS para implementaciones híbridas, todos los registros DNS externos de Lync deben apuntar a la infraestructura local.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="0aa4c-172">Para obtener más información sobre los registros DNS necesarios, consulte [requisitos del sistema de nombres de dominio (DNS) para Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="0aa4c-173">Además, debe asegurarse de que la resolución DNS que se describe en la tabla siguiente funciona en su implementación local:</span><span class="sxs-lookup"><span data-stu-id="0aa4c-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0aa4c-174">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="0aa4c-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-175">Resuelto por</span><span class="sxs-lookup"><span data-stu-id="0aa4c-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-176">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="0aa4c-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aa4c-177">Registro SRV de DNS para _sipfederationtls. _tcp. &lt;sipdomain.com&gt; para todos los dominios SIP compatibles que se resuelven para obtener acceso a las IP externas perimetrales</span><span class="sxs-lookup"><span data-stu-id="0aa4c-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-178">Servidor (es) perimetral</span><span class="sxs-lookup"><span data-stu-id="0aa4c-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-179">Habilitar la comunicación federada en una configuración híbrida.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="0aa4c-180">El servidor perimetral tiene que saber dónde enrutar el tráfico federado para el dominio SIP que se divide entre las instalaciones locales y en línea.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aa4c-181">Registros A de DNS para el FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com para la resolución de direcciones IP externas del servidor perimetral de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="0aa4c-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-182">Equipos de usuarios conectados a la red corporativa interna</span><span class="sxs-lookup"><span data-stu-id="0aa4c-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-183">Permitir que los usuarios en línea presenten o vean contenido en las reuniones hospedadas locales.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="0aa4c-184">El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0aa4c-185">En función de la configuración de DNS en la organización, es posible que deba agregar estos registros a la zona DNS hospedada interna para los dominios SIP correspondientes para proporcionar resolución DNS interna a estos registros.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="0aa4c-186">Consideraciones de firewall</span><span class="sxs-lookup"><span data-stu-id="0aa4c-186">Firewall Considerations</span></span>

<span data-ttu-id="0aa4c-p113">Los equipos de la red deben ser capaces de realizar búsquedas de DNS de Internet estándar. Si estos equipos pueden tener acceso a sitios de Internet estándar, la red cumple este requisito.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="0aa4c-189">En función de la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de Firewall de red para que acepten conexiones basadas en nombres de dominio comodín (por \*ejemplo, todo el tráfico de. Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="0aa4c-190">Si los firewalls de su organización no admiten configuraciones de nombre comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="0aa4c-191">Consulte el tema de ayuda [Office 365 URL e intervalos de direcciones IP](https://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-191">Refer to the Help topic [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="0aa4c-192">Requisitos de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="0aa4c-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="0aa4c-193">Además de los requisitos de puertos para la comunicación interna de Lync Server 2013, también debe configurar los siguientes puertos.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0aa4c-194">Protocolo/puerto</span><span class="sxs-lookup"><span data-stu-id="0aa4c-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="0aa4c-195">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0aa4c-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0aa4c-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="0aa4c-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-197">Abrir entrante</span><span class="sxs-lookup"><span data-stu-id="0aa4c-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="0aa4c-198">Servicios de federación de Active Directory (rol de servidor de federación)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="0aa4c-199">Para obtener más información, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS role Services</a>.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-199">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="0aa4c-200">Servicios de federación de Active Directory (rol de servidor proxy)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="0aa4c-201">Portal de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="0aa4c-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="0aa4c-202">El portal de mi empresa</span><span class="sxs-lookup"><span data-stu-id="0aa4c-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="0aa4c-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="0aa4c-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="0aa4c-204">Cliente de Lync (comunicación a Lync Online desde Lync Server local)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aa4c-205">TCP 80 y 443</span><span class="sxs-lookup"><span data-stu-id="0aa4c-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-206">Abrir entrante</span><span class="sxs-lookup"><span data-stu-id="0aa4c-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="0aa4c-207">Herramienta de sincronización de directorios de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="0aa4c-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aa4c-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="0aa4c-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-209">Abrir entrada/salida en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="0aa4c-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aa4c-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="0aa4c-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-211">Abrir entrada/salida para sesiones de uso compartido de datos</span><span class="sxs-lookup"><span data-stu-id="0aa4c-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aa4c-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="0aa4c-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-213">Abrir entrada/salida para sesiones de audio, vídeo y uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0aa4c-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aa4c-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="0aa4c-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-215">Abrir entrada/salida para sesiones de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="0aa4c-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aa4c-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="0aa4c-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="0aa4c-217">Abrir salida para sesiones de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="0aa4c-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="0aa4c-218">Cuentas de usuarios y datos</span><span class="sxs-lookup"><span data-stu-id="0aa4c-218">User Accounts and Data</span></span>

<span data-ttu-id="0aa4c-219">En una implementación híbrida de Lync Server 2013, todos los usuarios que deseen hospedar en Lync Online deben crearse primero en la implementación local, de modo que la cuenta de usuario se cree en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="0aa4c-220">A continuación, puede mover el usuario a Skype empresarial online, que moverá la lista de contactos del usuario.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="0aa4c-221">Al sincronizar cuentas de usuario entre su Lync local y las implementaciones de Lync Online con AD FS y DirSync, debe sincronizar las cuentas de AD de todos los usuarios de Lync de la organización entre las implementaciones locales y en línea de Lync, incluso si los usuarios no se mueven a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="0aa4c-222">Si no sincroniza todos los usuarios, es posible que la comunicación entre los usuarios locales y en línea de su organización no funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0aa4c-223">Si el usuario se crea mediante el portal en línea para Office 365, la cuenta de usuario no se sincronizará con Active Directory local y el usuario no existirá en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="0aa4c-224">Si ya ha creado usuarios en Lync Online y desea configurar un entorno híbrido con un servidor de Lync local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="0aa4c-225">También debe tener en cuenta los siguientes problemas relacionados con los usuarios al planear una implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="0aa4c-226">**Contactos de usuario**   el límite para los contactos de Lync Online es de 250.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="0aa4c-227">Los contactos que superen este número se quitarán de la lista de contactos del usuario cuando la cuenta se mueva a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="0aa4c-228">**Mensajería instantánea y presencia**   las listas de contactos de usuarios, grupos y listas de control de acceso (ACL) se migran con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="0aa4c-229">**Datos de conferencia, contenido de reuniones y reuniones**   programadas este contenido no se migra con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="0aa4c-230">Los usuarios deben reprogramar reuniones una vez que estas cuentas migran a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="0aa4c-231">Directivas de usuario y características</span><span class="sxs-lookup"><span data-stu-id="0aa4c-231">User Policies and Features</span></span>

  - <span data-ttu-id="0aa4c-232">En un entorno híbrido de Lync Server 2013, los usuarios pueden estar habilitados para mensajería instantánea, voz y reuniones de forma local o en línea, pero no para ambas cosas a la vez.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="0aa4c-233">**Cliente de Lync**     es posible que algunos usuarios necesiten una nueva versión de cliente cuando se muevan a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="0aa4c-234">Para Office Communications Server 2007 R2, los usuarios deben moverse a un grupo de servidores de Lync Server 2013 antes de la migración a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="0aa4c-235">Para obtener más información acerca de la compatibilidad con clientes, consulte [clientes para Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) y [clientes y configuraciones de puertos de red compatibles con Lync](https://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="0aa4c-235">For more information about client support, see [Clients for Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="0aa4c-236">**Las directivas locales y de configuración (no del usuario)**   en línea y en las directivas locales requieren una configuración independiente.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="0aa4c-237">No se pueden configurar directivas globales que se apliquen a ambas.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

