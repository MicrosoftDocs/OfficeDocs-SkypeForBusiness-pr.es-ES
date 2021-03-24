---
title: Implementar y configurar la movilidad para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: En este artículo se le guían los pasos para configurar una instalación existente de Skype Empresarial Server para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de Movilidad de Skype Empresarial Server.
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103866"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="f4eff-103">Implementar y configurar la movilidad para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f4eff-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="f4eff-104">En este artículo se le guían los pasos para configurar una instalación existente de Skype Empresarial Server para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de Movilidad de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="f4eff-105">Una vez revisado el artículo [Plan for Mobility for Skype for Business Server,](../plan-your-deployment/mobility.md) debe estar listo para continuar con los pasos siguientes para implementar la movilidad en su entorno de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="f4eff-106">Los pasos son los siguientes (y estamos incluyendo en esta tabla una lista de permisos):</span><span class="sxs-lookup"><span data-stu-id="f4eff-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="f4eff-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="f4eff-107">**Phase**</span></span>|<span data-ttu-id="f4eff-108">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="f4eff-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f4eff-109">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="f4eff-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="f4eff-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="f4eff-110">Domain Admins</span></span>  <br/> <span data-ttu-id="f4eff-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="f4eff-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="f4eff-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="f4eff-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="f4eff-113">Administrador local</span><span class="sxs-lookup"><span data-stu-id="f4eff-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="f4eff-114">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f4eff-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="f4eff-115">Administrador local</span><span class="sxs-lookup"><span data-stu-id="f4eff-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="f4eff-116">Configurar detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f4eff-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="f4eff-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="f4eff-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="f4eff-118">Probar la implementación de movilidad</span><span class="sxs-lookup"><span data-stu-id="f4eff-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="f4eff-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4eff-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="f4eff-120">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f4eff-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="f4eff-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f4eff-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="f4eff-122">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="f4eff-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="f4eff-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4eff-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="f4eff-124">Todas las secciones siguientes contienen pasos que suponen que ha leído el tema Planeación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="f4eff-125">If anything's confusing you, feel free to check out the information there.</span><span class="sxs-lookup"><span data-stu-id="f4eff-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="f4eff-126">La compatibilidad con MCX (Servicio de movilidad) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f4eff-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f4eff-127">Todos los clientes móviles de Skype Empresarial actuales ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f4eff-128">Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="f4eff-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="f4eff-129">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="f4eff-129">Create DNS records</span></span>
<span data-ttu-id="f4eff-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eff-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="f4eff-131">Es posible que ya las tenga como parte de su entorno de Skype Empresarial Server, pero debe crear los siguientes registros para que la detección automática funcione:</span><span class="sxs-lookup"><span data-stu-id="f4eff-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="f4eff-132">Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="f4eff-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="f4eff-133">Un registro DNS externo (o público) para admitir usuarios móviles que se conectan desde fuera de la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="f4eff-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="f4eff-134">Estos registros pueden ser nombres A (host) o registros CNAME (no es necesario realizar ambos, estamos incluyendo los pasos para todo aquí).</span><span class="sxs-lookup"><span data-stu-id="f4eff-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="f4eff-135">Crear un registro CNAME dns interno</span><span class="sxs-lookup"><span data-stu-id="f4eff-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="f4eff-136">Inicie sesión en un servidor DNS de la red que sea miembro del grupo **Administradores** de dominio o del **grupo DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="f4eff-137">Haga **clic en** Inicio , Elija  Herramientas administrativas **(puede** que tenga que buscarla si no es una opción del menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo dns.</span><span class="sxs-lookup"><span data-stu-id="f4eff-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="f4eff-138">En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio que es el hogar  de los servidores front-end de Skype Empresarial Server y expandir las zonas de búsqueda directa allí.</span><span class="sxs-lookup"><span data-stu-id="f4eff-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="f4eff-139">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="f4eff-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f4eff-140">Cualquier registro A o AAAA de host para el servidor front-end (estándar o enterprise) o los grupo(s) front-end.</span><span class="sxs-lookup"><span data-stu-id="f4eff-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f4eff-141">Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f4eff-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="f4eff-142">Una vez que haya observado esto, haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, elija **Nuevo alias (CNAME)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="f4eff-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="f4eff-143">En el **cuadro de texto Nombre de** alias, escriba lyncdiscoverinternal para el nombre de host, para la dirección URL del servicio de detección automática interna.</span><span class="sxs-lookup"><span data-stu-id="f4eff-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="f4eff-144">En el nombre de dominio completo **(FQDN** para el host de destino), deberá escribir o examinar el FQDN interno de servicios web para el grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="f4eff-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="f4eff-145">Haga clic en Aceptar cuando se haya escrito esto.</span><span class="sxs-lookup"><span data-stu-id="f4eff-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="f4eff-146">Deberá crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa para cada dominio SIP admitido en su entorno de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="f4eff-147">Crear un registro CNAME DNS externo</span><span class="sxs-lookup"><span data-stu-id="f4eff-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="f4eff-148">Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público puede usar, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que podrá crear nuevos registros DNS allí.</span><span class="sxs-lookup"><span data-stu-id="f4eff-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="f4eff-149">En este momento, ya debería existir un dominio SIP para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="f4eff-150">Expanda la **zona de búsqueda directa** para este dominio SIP o, de lo contrario, ábrala.</span><span class="sxs-lookup"><span data-stu-id="f4eff-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="f4eff-151">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="f4eff-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f4eff-152">Cualquier registro A o AAAA de host para el servidor front-end (estándar o enterprise) o los grupo(s) front-end.</span><span class="sxs-lookup"><span data-stu-id="f4eff-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f4eff-153">Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f4eff-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="f4eff-154">Una vez que tenga esa información, debe poder seleccionar una opción para crear un **nuevo alias (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="f4eff-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="f4eff-155">Ahora debería poder escribir un **nombre de alias,** debe escribir lyncdiscover aquí para la dirección URL del servicio de detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="f4eff-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="f4eff-156">A continuación, debe haber un área para especificar un **FQDN** para el host de destino , este debe ser el FQDN del grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="f4eff-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="f4eff-157">Es posible que tenga que guardar aquí, o si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en su entorno de Skype Empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4eff-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="f4eff-158">Crear un registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="f4eff-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="f4eff-159">Inicie sesión en un servidor DNS de la red que sea miembro del grupo **Administradores** de dominio o del **grupo DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="f4eff-160">Haga **clic en** Inicio , Elija  Herramientas administrativas **(puede** que tenga que buscarla si no es una opción del menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo dns.</span><span class="sxs-lookup"><span data-stu-id="f4eff-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="f4eff-161">En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio que es el hogar  de los servidores front-end de Skype Empresarial Server y expandir las zonas de búsqueda directa allí.</span><span class="sxs-lookup"><span data-stu-id="f4eff-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="f4eff-162">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="f4eff-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f4eff-163">Cualquier registro A o AAAA de host para el servidor front-end (estándar o enterprise) o los grupo(s) front-end.</span><span class="sxs-lookup"><span data-stu-id="f4eff-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f4eff-164">Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f4eff-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="f4eff-165">Una vez que haya observado esto, haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, elija **Nuevo host (A o AAAA)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="f4eff-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="f4eff-166">En el **cuadro de** texto Nombre, escriba lyncdiscoverinternal para el nombre de host, para la dirección URL del servicio de detección automática interna.</span><span class="sxs-lookup"><span data-stu-id="f4eff-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="f4eff-167">En el cuadro de texto Dirección **IP,** escriba la dirección IP interna de servicios web para el grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="f4eff-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="f4eff-168">Cuando esto termine, haga clic **en Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="f4eff-169">Deberá crear nuevos registros A o AAAA de detección automática en la zona de búsqueda directa para cada dominio SIP admitido en su entorno de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="f4eff-170">Para ello, repita los pasos del 6 al 8 tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f4eff-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="f4eff-171">Cuando haya terminado, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="f4eff-172">Crear un registro A de DNS externo</span><span class="sxs-lookup"><span data-stu-id="f4eff-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="f4eff-173">Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público puede usar, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que podrá crear nuevos registros DNS allí.</span><span class="sxs-lookup"><span data-stu-id="f4eff-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="f4eff-174">En este momento, ya debería existir un dominio SIP para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="f4eff-175">Expanda la **zona de búsqueda directa** para este dominio SIP o, de lo contrario, ábrala.</span><span class="sxs-lookup"><span data-stu-id="f4eff-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="f4eff-176">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="f4eff-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f4eff-177">Cualquier registro A o AAAA de host para el servidor front-end (estándar o enterprise) o los grupo(s) front-end.</span><span class="sxs-lookup"><span data-stu-id="f4eff-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f4eff-178">Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f4eff-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="f4eff-179">Una vez que tenga esa información, debe poder seleccionar una opción para crear un nuevo **host A o AAAA**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="f4eff-180">Ahora debería poder escribir un **nombre,** debe escribir lyncdiscover aquí para la dirección URL del servicio de detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="f4eff-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="f4eff-181">A continuación, debe haber un área para especificar una dirección **IP,** que tendrá que ser la DIRECCIÓN IP del grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="f4eff-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="f4eff-182">Es posible que tenga que guardar aquí, o si necesita crear registros A o AAAA adicionales en la zona de búsqueda directa de cada dominio SIP para su entorno de Skype Empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4eff-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="f4eff-183">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="f4eff-183">Modify certificates</span></span>
<span data-ttu-id="f4eff-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eff-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="f4eff-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span><span class="sxs-lookup"><span data-stu-id="f4eff-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="f4eff-186">Una vez que hayas revisado esto, te haremos un recorrido por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4eff-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="f4eff-187">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="f4eff-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="f4eff-188">Solicitar nuevos certificados de la entidad de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="f4eff-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="f4eff-189">Actualizar los certificados locales con los reemplazos mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4eff-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="f4eff-190">Comprobación de los certificados mediante el complemento Certificados en Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="f4eff-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="f4eff-191">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="f4eff-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="f4eff-192">En primer lugar, es posible que deba comprobar y ver qué certificados están en su lugar y si tienen o no las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f4eff-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="f4eff-193">Para ello, deberá iniciar sesión en su Skype Empresarial Server con una cuenta que sea un administrador local.</span><span class="sxs-lookup"><span data-stu-id="f4eff-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="f4eff-194">Es posible que esta cuenta también necesite tener derechos sobre la entidad emisora de certificados (CA), para algunos de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="f4eff-195">Abra el Shell de administración de Skype Empresarial Server (puede usar la búsqueda para encontrarlo si no lo tiene anclado a su menú Inicio o barra de tareas).</span><span class="sxs-lookup"><span data-stu-id="f4eff-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="f4eff-196">Será esencial que sepa qué certificados se han asignado antes de intentar agregar un certificado actualizado.</span><span class="sxs-lookup"><span data-stu-id="f4eff-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="f4eff-197">Por lo tanto, en el comando, escriba:</span><span class="sxs-lookup"><span data-stu-id="f4eff-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="f4eff-198">La información del paso 3 será única para usted.</span><span class="sxs-lookup"><span data-stu-id="f4eff-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="f4eff-199">Debe buscarlo para determinar si tiene un único certificado que se ha asignado para varias cosas o si tiene un certificado diferente asignado para los distintos componentes que los necesitan.</span><span class="sxs-lookup"><span data-stu-id="f4eff-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="f4eff-200">El **parámetro Use** le dirá cómo se usa un certificado y el parámetro **Thumbprint** le dirá si es el mismo certificado o varios certificados.</span><span class="sxs-lookup"><span data-stu-id="f4eff-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="f4eff-201">Si tienes las entradas de SAN recomendadas en nuestra sección Planeación, estás bien.</span><span class="sxs-lookup"><span data-stu-id="f4eff-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="f4eff-202">Si no es así, deberá solicitar un nuevo certificado o varios certificados (según la configuración) de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="f4eff-203">Solicitar un nuevo certificado o certificados a la entidad de certificación (CA)</span><span class="sxs-lookup"><span data-stu-id="f4eff-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="f4eff-204">Después de comprobar qué entradas de SAN tiene, sabe que tiene un solo certificado **(después** de comprobar los pasos anteriores) y ha aprendido que no tiene todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f4eff-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="f4eff-205">Es necesario realizar una nueva solicitud de certificado a la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="f4eff-206">Abra PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f4eff-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="f4eff-207">Para un SAN de servicio de detección automática que falta (reemplazando el parámetro -Ca por su propia ruta de acceso de entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f4eff-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="f4eff-208">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f4eff-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="f4eff-209">Deberá usar el parámetro DomainName en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f4eff-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="f4eff-210">Y al usar el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="f4eff-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="f4eff-211">Un ejemplo sería (reemplazar el parámetro -Ca por su propia ruta de acceso de entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f4eff-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="f4eff-212">O bien, después de comprobar qué entradas de SAN tiene, encontró que tiene varios certificados que no tienen todas las entradas que necesita. </span><span class="sxs-lookup"><span data-stu-id="f4eff-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="f4eff-213">Es necesario realizar una nueva solicitud de certificado a la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="f4eff-214">Abra PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f4eff-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="f4eff-215">Para un SAN de servicio de detección automática que falta (reemplazando el parámetro -Ca por su propia ruta de acceso de entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f4eff-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="f4eff-216">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f4eff-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="f4eff-217">Deberá usar el parámetro DomainName en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f4eff-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="f4eff-218">Y al usar el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="f4eff-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="f4eff-219">Algunos ejemplos serían (reemplazando el parámetro -Ca por su propia ruta de acceso de entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f4eff-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="f4eff-220">Una vez que la ca haya generado los nuevos certificados, tendrá que asignarlos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f4eff-221">Asignar certificados con el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f4eff-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="f4eff-222">En función de lo que encontró en la sección ¿Necesito nuevas certificaciones? anterior, debe ejecutar **una** de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="f4eff-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="f4eff-223">Si tiene un único certificado para todo (las huellas digitales son idénticas), debe ejecutar esto:</span><span class="sxs-lookup"><span data-stu-id="f4eff-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="f4eff-224">Si tiene certificados diferentes para las cosas (las huellas digitales son todas diferentes), ejecute esto en su lugar:</span><span class="sxs-lookup"><span data-stu-id="f4eff-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="f4eff-225">Visualización de certificados en Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="f4eff-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="f4eff-226">Tiene una opción para ver los certificados mediante el complemento Certificados para MMC.</span><span class="sxs-lookup"><span data-stu-id="f4eff-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="f4eff-227">Simplemente escriba MMC en la búsqueda y debería mostrarse como una opción de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="f4eff-228">Para agregar el complemento Certificados, deberá hacer clic en Archivo y, a continuación, agregar o quitar **complemento...** (o el método abreviado **de teclado Ctrl+M** también funcionaría).</span><span class="sxs-lookup"><span data-stu-id="f4eff-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="f4eff-229">**Los certificados** serán una opción en el panel izquierdo, selecciónelo y, a continuación, Cuenta de equipo en la ventana emergente y, a continuación, **Siguiente**. </span><span class="sxs-lookup"><span data-stu-id="f4eff-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="f4eff-230">Todavía en la ventana emergente, con toda probabilidad lo está haciendo en el equipo que es el hogar de los certificados que necesita ver, así que deje la selección en Equipo **local** si es así.</span><span class="sxs-lookup"><span data-stu-id="f4eff-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="f4eff-231">Si está trabajando en un equipo remoto,  cambie el botón de radio a Otro  equipo y, a continuación, escriba el FQDN del equipo o use el botón Examinar para buscar ese equipo a través de AD.</span><span class="sxs-lookup"><span data-stu-id="f4eff-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="f4eff-232">Después de seleccionar el equipo, deberá  hacer clic en  Finalizar cuando esté listo y, a continuación, aceptar para agregar el complemento al MMC.</span><span class="sxs-lookup"><span data-stu-id="f4eff-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="f4eff-233">Expanda la **sección Certificados** en el panel izquierdo de MMC.</span><span class="sxs-lookup"><span data-stu-id="f4eff-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="f4eff-234">Expanda también **la carpeta** Personal y, a continuación, **seleccione Certificados**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="f4eff-235">Esto te permite ver los certificados en este almacén.</span><span class="sxs-lookup"><span data-stu-id="f4eff-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="f4eff-236">Debe buscar el certificado que desea ver, hacer clic con el botón secundario en él y elegir **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4eff-237">¿Cómo sabe qué certificado es?</span><span class="sxs-lookup"><span data-stu-id="f4eff-237">How do you know what certificate this is?</span></span> <span data-ttu-id="f4eff-238">Debe ser el único certificado asignado a todo para la granja de servidores, o puede tener varios certificados para cosas diferentes, como Default, Internal Web Services, etc., en cuyo caso es posible que deba buscar varios certificados.</span><span class="sxs-lookup"><span data-stu-id="f4eff-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="f4eff-239">Varios certificados tendrán la misma huella digital.</span><span class="sxs-lookup"><span data-stu-id="f4eff-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="f4eff-240">Una vez que haya llegado a la **vista Certificado,** elija **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="f4eff-241">Esto le permitirá ver el nombre del asunto del certificado al seleccionar **Asunto** y se muestran el nombre de sujeto asignado y las propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="f4eff-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="f4eff-242">También tendrá que comprobar las entradas **de Nombre alternativo** del sujeto.</span><span class="sxs-lookup"><span data-stu-id="f4eff-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="f4eff-243">Encontrará una o varias de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f4eff-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="f4eff-244">El nombre del grupo de servidores de este grupo o el nombre de servidor único si no es un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f4eff-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="f4eff-245">Nombre del servidor al que está asignado el certificado.</span><span class="sxs-lookup"><span data-stu-id="f4eff-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="f4eff-246">Registros de dirección URL simples, normalmente se reúnen y marcan.</span><span class="sxs-lookup"><span data-stu-id="f4eff-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="f4eff-247">Nombres internos y externos de Servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el Generador de topologías y selecciones de servicios web sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="f4eff-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="f4eff-248">Si ya está asignado, lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="f4eff-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="f4eff-249">y lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="f4eff-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="f4eff-250">registros.</span><span class="sxs-lookup"><span data-stu-id="f4eff-250">records.</span></span>
    
     <span data-ttu-id="f4eff-251">Deberá comprobar varios certificados si tiene más de un certificado asignado (compruebe la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="f4eff-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="f4eff-252">Por lo tanto, si encuentra lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="f4eff-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="f4eff-253">y lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="f4eff-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="f4eff-254">registros, ya tiene esto configurado.</span><span class="sxs-lookup"><span data-stu-id="f4eff-254">records, you've got this configured already.</span></span> <span data-ttu-id="f4eff-255">Puede cerrar el MMC.</span><span class="sxs-lookup"><span data-stu-id="f4eff-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="f4eff-256">Si no están asignados, deberá realizar una nueva solicitud de certificado (descrita anteriormente) o deberá instalarlas después de la solicitud (se recomienda lo siguiente en PowerShell anterior para ello).</span><span class="sxs-lookup"><span data-stu-id="f4eff-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="f4eff-257">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f4eff-257">Configure the reverse proxy</span></span>
<span data-ttu-id="f4eff-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eff-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="f4eff-259">Los pasos siguientes no están diseñados para seguirse exactamente.</span><span class="sxs-lookup"><span data-stu-id="f4eff-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="f4eff-260">Esto se debe a que en versiones anteriores del producto, le habríamos recorrido, por ejemplo, la configuración de la puerta de enlace de administración de amenazas (TMG) y, si no lo estuviera usando, tendría que trabajar su propia versión desde allí.</span><span class="sxs-lookup"><span data-stu-id="f4eff-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="f4eff-261">Microsoft ya no ofrece TMG como producto y, si aún necesita configurarlo, puede ver los pasos de [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility).</span><span class="sxs-lookup"><span data-stu-id="f4eff-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility).</span></span> <span data-ttu-id="f4eff-262">Pero la siguiente información está pensada para ser más útil en general, incluso si no hay ninguna forma de proporcionar pasos de tutorial específicos para cada proxy inverso que haya.</span><span class="sxs-lookup"><span data-stu-id="f4eff-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="f4eff-263">Tenemos que tener en cuenta dos aspectos principales:</span><span class="sxs-lookup"><span data-stu-id="f4eff-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="f4eff-264">¿Va a realizar la solicitud de detección automática inicial a través de HTTPS (que recomendamos)?</span><span class="sxs-lookup"><span data-stu-id="f4eff-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="f4eff-265">Si tiene una regla de publicación web, debe modificarla.</span><span class="sxs-lookup"><span data-stu-id="f4eff-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="f4eff-266">Si aún no tiene una regla de publicación web, debe crearla.</span><span class="sxs-lookup"><span data-stu-id="f4eff-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="f4eff-267">Si está realizando la solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.</span><span class="sxs-lookup"><span data-stu-id="f4eff-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f4eff-268">**Importante** Un valor de tiempo de espera de proxy es un número que variará de la implementación a la implementación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="f4eff-269">Debe supervisar la implementación y modificar el valor para la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="f4eff-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="f4eff-270">Es posible que pueda establecer el valor como 200.</span><span class="sxs-lookup"><span data-stu-id="f4eff-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="f4eff-271">Si admite clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificaciones de inserción de Office 365, que tienen un valor de tiempo de espera de 900.</span><span class="sxs-lookup"><span data-stu-id="f4eff-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="f4eff-272">Es muy probable que tenga que aumentar el valor de tiempo de espera para evitar las desconexiones del cliente cuando el valor es demasiado bajo, o disminuir el número si las conexiones a través del proxy no se desconectan, pero se borran mucho después de que el cliente se haya desconectado.</span><span class="sxs-lookup"><span data-stu-id="f4eff-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="f4eff-273">Supervisar y basar lo que es habitual para el entorno es la única forma precisa de determinar la configuración adecuada para este valor.</span><span class="sxs-lookup"><span data-stu-id="f4eff-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="f4eff-274">Modificar la regla de publicación web existente para el SAN y la dirección URL de detección automática externos</span><span class="sxs-lookup"><span data-stu-id="f4eff-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="f4eff-275">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4eff-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f4eff-276">Tendrás que buscar la regla de publicación web y elegir la opción Editar (puede estar en un menú o pestaña, según la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f4eff-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="f4eff-277">Debe haber un área que indica a qué se aplica esta regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="f4eff-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="f4eff-278">Debe modificar esta regla para los sitios entrantes o las solicitudes de sitios.</span><span class="sxs-lookup"><span data-stu-id="f4eff-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="f4eff-279">Agregará una **nueva** entrada.</span><span class="sxs-lookup"><span data-stu-id="f4eff-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="f4eff-280">Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o Guardar **,** según el formato del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4eff-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="f4eff-281">Es posible que tenga un nuevo certificado que tenga la entrada SAN de detección automática.</span><span class="sxs-lookup"><span data-stu-id="f4eff-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="f4eff-282">Esto también debe instalarse y configurarse para su uso según la configuración del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4eff-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="f4eff-283">Asegúrese de guardar todo cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="f4eff-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="f4eff-284">Si el proxy inverso tiene una **funcionalidad de** prueba, haga uso de ella para asegurarse de que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4eff-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="f4eff-285">Ahora, es posible que deba repetir estos pasos si tiene un director o un grupo de directores en su entorno (esto significaría que tiene una segunda regla).</span><span class="sxs-lookup"><span data-stu-id="f4eff-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="f4eff-286">Crear una regla de publicación web para la dirección URL de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="f4eff-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="f4eff-287">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4eff-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f4eff-288">Tendrás que buscar dónde en la interfaz creas las reglas  de  publicación web y elige la opción Nuevo o Crear (puede estar en un menú o pestaña, según la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f4eff-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="f4eff-289">Está buscando la opción para crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="f4eff-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="f4eff-290">Normalmente, deberá escribir la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f4eff-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="f4eff-291">**Nombre:** el nombre de la regla</span><span class="sxs-lookup"><span data-stu-id="f4eff-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="f4eff-292">**Acción de** regla: en este caso es una **regla Permitir,** está dejando que algo pase a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4eff-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="f4eff-293">La **regla u opción de** publicación que está eligiendo sería un solo sitio web o **equilibrador de carga.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="f4eff-294">Debe ser **SSL** para el acceso externo, elija esa opción.</span><span class="sxs-lookup"><span data-stu-id="f4eff-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="f4eff-295">Deberá publicar una ruta de acceso para **la** publicación interna y escribir el FQDN de los servicios web externos en el equilibrador de carga del grupo de servidores front-end (o el FQDN del equilibrador de carga del grupo de directores si tiene uno), un ejemplo sería sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="f4eff-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="f4eff-296">Debe escribir _ como la ruta de acceso que se va a publicar, pero también debe reenviar el encabezado **/\\** de host original\*\*.</span><span class="sxs-lookup"><span data-stu-id="f4eff-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="f4eff-297">Habrá una opción para información o **detalles de nombres** públicos o externos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="f4eff-298">Este es el lugar donde podrá escribir:</span><span class="sxs-lookup"><span data-stu-id="f4eff-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="f4eff-299">**Acepte solicitudes,** pero debe ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="f4eff-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="f4eff-300">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="f4eff-301"><sipdomain> (esta es la dirección URL del servicio de detección automática externa).</span><span class="sxs-lookup"><span data-stu-id="f4eff-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="f4eff-302">Ahora, si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, deberá escribir el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4eff-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="f4eff-303">Habrá una opción **Ruta** de acceso y tendrás que escribir **/\\** \* aquí.</span><span class="sxs-lookup"><span data-stu-id="f4eff-303">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="f4eff-304">Deberá seleccionar una escucha **SSL** con su certificado público actualizado.</span><span class="sxs-lookup"><span data-stu-id="f4eff-304">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="f4eff-305">**La delegación de** autenticación debe establecerse **en Sin delegación,** pero se debe permitir la autenticación **directa** de cliente.</span><span class="sxs-lookup"><span data-stu-id="f4eff-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="f4eff-306">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="f4eff-307">Esta debe ser toda la información que necesita para crear esta regla y permitir que continúe.</span><span class="sxs-lookup"><span data-stu-id="f4eff-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="f4eff-308">Deberá asegurarse de que se reenvía el encabezado **host** original.</span><span class="sxs-lookup"><span data-stu-id="f4eff-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="f4eff-309">Los **puertos del** servidor web también tendrán que establecerse, deberá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4eff-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="f4eff-310">**Redirigir solicitudes al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="f4eff-311">**Redirigir solicitudes al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="f4eff-312">Cuando todo esté configurado, tendrás que guardarlos o aplicarlos y, a continuación, querrás probar la regla.</span><span class="sxs-lookup"><span data-stu-id="f4eff-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="f4eff-313">Crear una regla de publicación web para el puerto 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="f4eff-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="f4eff-314">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4eff-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f4eff-315">Tendrás que buscar dónde en la interfaz creas las reglas  de  publicación web y elige la opción Nuevo o Crear (puede estar en un menú o pestaña, según la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f4eff-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="f4eff-316">Está buscando la opción para crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="f4eff-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="f4eff-317">Normalmente, deberá escribir la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f4eff-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="f4eff-318">**Nombre:** el nombre de la regla</span><span class="sxs-lookup"><span data-stu-id="f4eff-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="f4eff-319">**Acción de** regla: en este caso es una **regla Permitir,** está dejando que algo pase a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4eff-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="f4eff-320">La **regla u opción de** publicación que está eligiendo sería un solo sitio web o **equilibrador de carga.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="f4eff-321">Debe ser una conexión no protegida para conectarse al servidor web o granja de servidores **publicados.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="f4eff-322">Tendrá que publicar una ruta de acceso para **la** publicación interna y escribir el FQDN de la dirección **VIP** del equilibrador de carga del grupo de servidores front-end, un ejemplo sería sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="f4eff-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="f4eff-323">Debe escribir _ como la ruta de acceso que se va a publicar, pero también debe reenviar el encabezado **/\\** de host original\*\*.</span><span class="sxs-lookup"><span data-stu-id="f4eff-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="f4eff-324">Habrá una opción para información o **detalles de nombres** públicos o externos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="f4eff-325">Este es el lugar donde podrá escribir:</span><span class="sxs-lookup"><span data-stu-id="f4eff-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="f4eff-326">**Acepte solicitudes,** pero debe ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="f4eff-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="f4eff-327">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="f4eff-328"><sipdomain> (esta es la dirección URL del servicio de detección automática externa).</span><span class="sxs-lookup"><span data-stu-id="f4eff-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="f4eff-329">Habrá una opción **Ruta** de acceso y tendrás que escribir **/\\** \* aquí.</span><span class="sxs-lookup"><span data-stu-id="f4eff-329">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="f4eff-330">Deberá seleccionar un agente de escucha web o permitir que el proxy inverso cree uno por usted.</span><span class="sxs-lookup"><span data-stu-id="f4eff-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="f4eff-331">**La delegación de** autenticación debe establecerse **en Sin delegación,** pero no se debe permitir la autenticación **directa** del cliente.</span><span class="sxs-lookup"><span data-stu-id="f4eff-331">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="f4eff-332">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="f4eff-333">Esta debe ser toda la información que necesita para crear esta regla y permitir que continúe.</span><span class="sxs-lookup"><span data-stu-id="f4eff-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="f4eff-334">Los **puertos del** servidor web tendrán que establecerse, deberá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4eff-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="f4eff-335">**Redirigir solicitudes al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="f4eff-336">**Redirigir solicitudes al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="f4eff-337">Cuando todo esté configurado, tendrás que guardarlos o aplicarlos y, a continuación, querrás probar la regla.</span><span class="sxs-lookup"><span data-stu-id="f4eff-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="f4eff-338">Configurar detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f4eff-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="f4eff-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eff-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="f4eff-340">Los entornos híbridos en Skype Empresarial Server son entornos que combinan un entorno local y O365.</span><span class="sxs-lookup"><span data-stu-id="f4eff-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="f4eff-341">Cuando Skype Empresarial Server trabaja en un entorno híbrido, el servicio de detección automática debe poder localizar a un usuario de cualquiera de estos entornos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="f4eff-342">Para que los clientes móviles descubran dónde se encuentra un usuario, el servicio de detección automática debe configurarse con un nuevo localizador uniforme de recursos (URL).</span><span class="sxs-lookup"><span data-stu-id="f4eff-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="f4eff-343">Estos pasos son:</span><span class="sxs-lookup"><span data-stu-id="f4eff-343">The steps are:</span></span>
  
1. <span data-ttu-id="f4eff-344">Abra El Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f4eff-345">Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** para su entorno de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f4eff-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="f4eff-346">A continuación, aún en la ventana del shell, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f4eff-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="f4eff-347">Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="f4eff-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="f4eff-348">Probar la implementación de movilidad</span><span class="sxs-lookup"><span data-stu-id="f4eff-348">Test your Mobility deployment</span></span>
<span data-ttu-id="f4eff-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eff-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="f4eff-350">Una vez implementado el servicio de movilidad de Skype Empresarial Server y el servicio de detección automática de Skype Empresarial Server, querrá ejecutar una transacción de prueba para asegurarse de que la implementación funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4eff-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="f4eff-351">Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear, unirse y comunicarse en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="f4eff-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="f4eff-352">Necesitará dos usuarios (reales o de prueba) y sus credenciales completa para realizar esta prueba.</span><span class="sxs-lookup"><span data-stu-id="f4eff-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="f4eff-353">Este comando funcionará tanto para clientes de Skype Empresarial como para clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4eff-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="f4eff-354">Para los clientes de Lync Server 2010 en Skype Empresarial Server 2015, deberá ejecutar **Test-CsMcxP2PIM** para probar.</span><span class="sxs-lookup"><span data-stu-id="f4eff-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="f4eff-355">Los usuarios de Lync Server 2010 seguirán teniendo que ser usuarios reales o usuarios de prueba predefinidos, y necesitará sus credenciales de contraseña.</span><span class="sxs-lookup"><span data-stu-id="f4eff-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="f4eff-356">La compatibilidad con MCX (Servicio de movilidad) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f4eff-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f4eff-357">Todos los clientes móviles de Skype Empresarial actuales ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f4eff-358">Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="f4eff-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="f4eff-359">Probar conferencias para clientes móviles de Skype Empresarial y Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f4eff-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="f4eff-360">Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-361">Inicie el Shell de administración de **Skype Empresarial Server** (puede escribir el nombre en la búsqueda o ir a Todos los **programas** y elegirlo).</span><span class="sxs-lookup"><span data-stu-id="f4eff-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="f4eff-362">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f4eff-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="f4eff-363">También es posible establecer credenciales en un script y pasarlas al cmdlet de prueba.</span><span class="sxs-lookup"><span data-stu-id="f4eff-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="f4eff-364">Tenemos un ejemplo de esto a continuación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="f4eff-365">Probar conferencias para clientes móviles de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f4eff-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="f4eff-366">La compatibilidad con MCX (Servicio de movilidad) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f4eff-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f4eff-367">Todos los clientes móviles de Skype Empresarial actuales ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f4eff-368">Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="f4eff-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="f4eff-369">Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-370">Inicie el Shell de administración de **Skype Empresarial Server** (puede escribir el nombre en la búsqueda o ir a Todos los **programas** y elegirlo).</span><span class="sxs-lookup"><span data-stu-id="f4eff-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="f4eff-371">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f4eff-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="f4eff-372">También es posible establecer credenciales en un script y pasarlas al cmdlet de prueba.</span><span class="sxs-lookup"><span data-stu-id="f4eff-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="f4eff-373">Tenemos un ejemplo de esto a continuación.</span><span class="sxs-lookup"><span data-stu-id="f4eff-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="f4eff-374">Para revisar los procedimientos de comando más adelante, puede consultar [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) y [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f4eff-374">To review the command procedures further, you can check out [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="f4eff-375">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f4eff-375">Configure for push notifications</span></span>
<span data-ttu-id="f4eff-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eff-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="f4eff-377">Las notificaciones push, en forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil incluso cuando la aplicación de Skype o Lync está inactiva.</span><span class="sxs-lookup"><span data-stu-id="f4eff-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="f4eff-378">Pero, ¿qué son las notificaciones de inserción?</span><span class="sxs-lookup"><span data-stu-id="f4eff-378">But what are push notifications?</span></span> <span data-ttu-id="f4eff-379">Son alertas de eventos, como una invitación de mensajería instantánea nueva o perdida, o para un correo de voz recibido.</span><span class="sxs-lookup"><span data-stu-id="f4eff-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="f4eff-380">El servicio de movilidad de Skype Empresarial Server envía estas notificaciones al Servicio de notificaciones push de Skype Empresarial Server basado en la nube, que envía las notificaciones al Servicio de notificaciones push (MSNS) de Microsoft para usuarios de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="f4eff-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="f4eff-381">Esta funcionalidad no cambia respecto a Lync Server 2013, pero si tiene un Skype Empresarial Server, querrá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4eff-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="f4eff-382">Para un servidor perimetral de Skype Empresarial Server, agregue un nuevo proveedor de hospedaje, Microsoft Skype Empresarial Online y, a continuación, configure la federación de proveedores de hospedaje entre su organización y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="f4eff-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="f4eff-383">Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="f4eff-384">De manera predeterminada, las notificaciones de inserción están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="f4eff-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="f4eff-385">Pruebe la configuración de federación y las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="f4eff-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="f4eff-386">Configurar el servidor perimetral de Skype Empresarial para notificaciones push</span><span class="sxs-lookup"><span data-stu-id="f4eff-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="f4eff-387">Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-388">Inicie el **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4eff-389">Agregar un proveedor de hospedaje en línea de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f4eff-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="f4eff-390">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f4eff-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="f4eff-391">No puede tener más de una relación de federación con un único proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="f4eff-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="f4eff-392">Por lo tanto, si ya ha configurado un proveedor de hospedaje que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, incluso si la identidad del proveedor de hospedaje es otra que SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="f4eff-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="f4eff-393">Configure la federación de proveedores de hospedaje entre su organización y el Servicio de notificaciones de inserción en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="f4eff-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="f4eff-394">En la línea de comandos, deberá escribir:</span><span class="sxs-lookup"><span data-stu-id="f4eff-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="f4eff-395">Habilitar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f4eff-395">Enable push notifications</span></span>

1. <span data-ttu-id="f4eff-396">Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-397">Inicie el **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4eff-398">Habilitar notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="f4eff-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="f4eff-399">Habilitar federación:</span><span class="sxs-lookup"><span data-stu-id="f4eff-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="f4eff-400">Notificaciones de inserción y federación de pruebas</span><span class="sxs-lookup"><span data-stu-id="f4eff-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="f4eff-401">Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-402">Inicie el **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4eff-403">Probar la configuración de federación:</span><span class="sxs-lookup"><span data-stu-id="f4eff-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="f4eff-404">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f4eff-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="f4eff-405">Pruebe las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="f4eff-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="f4eff-406">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f4eff-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="f4eff-407">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="f4eff-407">Configure Mobility policy</span></span>
<span data-ttu-id="f4eff-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eff-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="f4eff-409">Tiene la capacidad de Skype Empresarial Server para determinar quién puede usar el servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o vídeo, así como si se requiere WiFi para VoIP o vídeo.</span><span class="sxs-lookup"><span data-stu-id="f4eff-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="f4eff-410">Llamar a través del trabajo permite a un usuario móvil usar su número de teléfono de trabajo, en lugar de su número de teléfono móvil, al realizar y recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="f4eff-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="f4eff-411">La persona del otro extremo de la línea no verá el número de teléfono móvil de ese usuario móvil y le permite evitar los cargos por llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="f4eff-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="f4eff-412">Cuando se configura VoIP y vídeo, los usuarios pueden realizar y realizar llamadas VoIP y vídeo.</span><span class="sxs-lookup"><span data-stu-id="f4eff-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="f4eff-413">La configuración del uso de WiFi determina si el dispositivo móvil de un usuario tendrá que usar una red WiFi a través de una red de datos móviles.</span><span class="sxs-lookup"><span data-stu-id="f4eff-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="f4eff-414">La movilidad, la llamada a través del trabajo y las características VoIP y vídeo están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f4eff-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="f4eff-415">La configuración para requerir WiFi para VoIP y vídeo está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f4eff-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="f4eff-416">Un administrador tiene la capacidad de cambiar esto, ya sea globalmente, por sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="f4eff-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="f4eff-417">Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben ser:</span><span class="sxs-lookup"><span data-stu-id="f4eff-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="f4eff-418">Habilitado para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f4eff-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="f4eff-419">Habilitado para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f4eff-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="f4eff-420">Se asignó una directiva de movilidad que tiene **la opción EnableMobility** establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="f4eff-421">Para que los usuarios puedan usar La llamada a través del trabajo, también deben ser:</span><span class="sxs-lookup"><span data-stu-id="f4eff-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="f4eff-422">Se asignó una directiva de voz que tiene seleccionada la opción Habilitar **llamadas simultáneas de** teléfonos.</span><span class="sxs-lookup"><span data-stu-id="f4eff-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="f4eff-423">Se asignó una directiva de movilidad que **tiene el enableOutsideVoice** establecido en **True**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f4eff-424">Los usuarios que no estén habilitados para Telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP de Skype a Skype o pueden unirse a conferencias mediante el vínculo Hacer clic para unirse mientras están en sus dispositivos móviles, si se establecen las opciones adecuadas para la directiva de voz a la que están asociados.</span><span class="sxs-lookup"><span data-stu-id="f4eff-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="f4eff-425">Hay más detalles en el tema PLANNING.</span><span class="sxs-lookup"><span data-stu-id="f4eff-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="f4eff-426">Modificar la directiva global de movilidad</span><span class="sxs-lookup"><span data-stu-id="f4eff-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="f4eff-427">Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-428">Inicie el **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4eff-429">Desactiva el acceso a Movilidad y Llamar a través del trabajo globalmente escribiendo:</span><span class="sxs-lookup"><span data-stu-id="f4eff-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="f4eff-430">Puedes desactivar La llamada a través del trabajo sin desactivar el acceso a Movilidad.</span><span class="sxs-lookup"><span data-stu-id="f4eff-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="f4eff-431">Pero no puedes desactivar Movilidad sin desactivar la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4eff-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="f4eff-432">Para obtener más información, [consulte Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f4eff-432">For more info, check out [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="f4eff-433">Modificar la directiva de movilidad por sitio</span><span class="sxs-lookup"><span data-stu-id="f4eff-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="f4eff-434">Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-435">Inicie el **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4eff-436">Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP y Requerir WiFi para vídeo IP por sitio.</span><span class="sxs-lookup"><span data-stu-id="f4eff-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="f4eff-437">Tipo:</span><span class="sxs-lookup"><span data-stu-id="f4eff-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="f4eff-438">Obtenga más información [en New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f4eff-438">Learn more at [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="f4eff-439">Modificar la directiva de movilidad por usuario</span><span class="sxs-lookup"><span data-stu-id="f4eff-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="f4eff-440">Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde esté instalado el Shell de administración de **Skype Empresarial Server** y **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="f4eff-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f4eff-441">Inicie el **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f4eff-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4eff-442">Cree directivas de movilidad de nivel de usuario y desactive Movilidad y Llamar a través del trabajo por usuario.</span><span class="sxs-lookup"><span data-stu-id="f4eff-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="f4eff-443">Tipo:</span><span class="sxs-lookup"><span data-stu-id="f4eff-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="f4eff-444">Otro ejemplo con datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f4eff-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="f4eff-445">Puedes desactivar La llamada a través del trabajo sin desactivar el acceso a Movilidad.</span><span class="sxs-lookup"><span data-stu-id="f4eff-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="f4eff-446">Pero no puedes desactivar Movilidad sin desactivar la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4eff-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
