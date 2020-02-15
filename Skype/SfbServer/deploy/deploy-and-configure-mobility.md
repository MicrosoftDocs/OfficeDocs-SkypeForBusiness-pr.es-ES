---
title: Implementación y configuración de la movilidad para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artículo le guiará por los pasos necesarios para configurar una instalación existente de Skype empresarial Server para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029071"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="91e4a-103">Implementación y configuración de la movilidad para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="91e4a-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="91e4a-104">Este artículo le guiará por los pasos necesarios para configurar una instalación existente de Skype empresarial Server para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91e4a-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="91e4a-105">Tras haber revisado el artículo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , debe estar listo para continuar con los pasos siguientes para implementar la movilidad en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91e4a-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="91e4a-106">Los pasos son los siguientes (y estamos incluyendo en esta tabla una lista de permisos):</span><span class="sxs-lookup"><span data-stu-id="91e4a-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="91e4a-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="91e4a-107">**Phase**</span></span>|<span data-ttu-id="91e4a-108">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="91e4a-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="91e4a-109">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="91e4a-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="91e4a-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="91e4a-110">Domain Admins</span></span>  <br/> <span data-ttu-id="91e4a-111">Administradores</span><span class="sxs-lookup"><span data-stu-id="91e4a-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="91e4a-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="91e4a-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="91e4a-113">Administrador local</span><span class="sxs-lookup"><span data-stu-id="91e4a-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="91e4a-114">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="91e4a-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="91e4a-115">Administrador local</span><span class="sxs-lookup"><span data-stu-id="91e4a-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="91e4a-116">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="91e4a-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="91e4a-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="91e4a-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="91e4a-118">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="91e4a-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="91e4a-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e4a-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="91e4a-120">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="91e4a-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="91e4a-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="91e4a-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="91e4a-122">Configurar la Directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="91e4a-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="91e4a-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e4a-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="91e4a-124">Todas las secciones siguientes contienen pasos que suponen que ha leído el tema de planeación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="91e4a-125">Si algo confuso, no dude en consultar la información allí.</span><span class="sxs-lookup"><span data-stu-id="91e4a-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="91e4a-126">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="91e4a-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="91e4a-127">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="91e4a-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="91e4a-128">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="91e4a-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="91e4a-129">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="91e4a-129">Create DNS records</span></span>
<span data-ttu-id="91e4a-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="91e4a-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="91e4a-131">Puede que ya los tenga como parte de su entorno de Skype empresarial Server, pero debe crear los siguientes registros para que la detección automática funcione:</span><span class="sxs-lookup"><span data-stu-id="91e4a-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="91e4a-132">Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="91e4a-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="91e4a-133">Un registro DNS externo (o público) para admitir usuarios móviles que se conectan desde fuera de la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="91e4a-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="91e4a-134">Estos registros pueden ser nombres de (host) o registros CNAME (no es necesario hacer ambas cosas, ya que estamos incluyendo los pasos para todo esto).</span><span class="sxs-lookup"><span data-stu-id="91e4a-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="91e4a-135">Crear un registro CNAME de DNS interno</span><span class="sxs-lookup"><span data-stu-id="91e4a-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="91e4a-136">Inicie sesión en un servidor DNS de la red que sea miembro del grupo **administradores de dominio** o del grupo **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="91e4a-137">Haga clic en **Inicio**, elija **herramientas administrativas** (es posible que deba **buscarla** si no se encuentra una opción en el menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo DNS.</span><span class="sxs-lookup"><span data-stu-id="91e4a-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="91e4a-138">En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio principal de los servidores front-end de Skype empresarial Server y, a continuación, ampliar las zonas de **búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="91e4a-139">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="91e4a-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="91e4a-140">Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="91e4a-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="91e4a-141">Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="91e4a-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="91e4a-142">Una vez que lo haya anotado, haga clic con el botón derecho en el nombre de dominio SIP y, a continuación, elija **nuevo alias (CNAME)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="91e4a-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="91e4a-143">En el cuadro de texto **nombre de alias** , escriba lyncdiscoverinternal para el nombre de host de la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="91e4a-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="91e4a-144">En el **nombre de dominio completo (FQDN para el host de destino**, debe escribir o buscar el FQDN de servicios Web internos del grupo de servidores front-end (o el servidor front-end único o el grupo o director de Director) identificado en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="91e4a-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="91e4a-145">Haga clic en Aceptar cuando se especifique.</span><span class="sxs-lookup"><span data-stu-id="91e4a-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="91e4a-146">Tendrá que crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa para cada dominio SIP que se admita en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91e4a-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="91e4a-147">Crear un registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="91e4a-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="91e4a-148">Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público podría estar usando, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que pueda crear nuevos registros DNS allí.</span><span class="sxs-lookup"><span data-stu-id="91e4a-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="91e4a-149">En este momento, ya debe existir un dominio SIP en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91e4a-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="91e4a-150">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala de otro modo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="91e4a-151">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="91e4a-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="91e4a-152">Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="91e4a-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="91e4a-153">Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="91e4a-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="91e4a-154">Una vez que tenga esa información, podrá seleccionar una opción para crear un **nuevo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="91e4a-155">Ahora debería poder escribir un **nombre de alias**, debe escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="91e4a-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="91e4a-156">A continuación, debe haber un área que especificar en un **FQDN para el host de destino**, que tendrá que ser el FQDN del grupo de servidores front-end (o el servidor front-end único o el grupo o director de Director) identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="91e4a-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="91e4a-157">Es posible que tenga que guardar aquí o, si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en su entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="91e4a-158">Crear un registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="91e4a-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="91e4a-159">Inicie sesión en un servidor DNS de la red que sea miembro del grupo **administradores de dominio** o del grupo **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="91e4a-160">Haga clic en **Inicio**, elija **herramientas administrativas** (es posible que deba **buscarla** si no se encuentra una opción en el menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo DNS.</span><span class="sxs-lookup"><span data-stu-id="91e4a-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="91e4a-161">En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio principal de los servidores front-end de Skype empresarial Server y, a continuación, ampliar las zonas de **búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="91e4a-162">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="91e4a-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="91e4a-163">Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="91e4a-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="91e4a-164">Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="91e4a-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="91e4a-165">Una vez que lo haya anotado, haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, elija **nuevo host (a o aaaa)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="91e4a-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="91e4a-166">En el cuadro de texto **nombre** , escriba lyncdiscoverinternal para el nombre de host de la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="91e4a-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="91e4a-167">En el cuadro de texto **dirección IP** , escriba la dirección IP de servicios Web internos del grupo de servidores front-end (o el servidor front-end único, o el grupo o director de Director) que se identificó en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="91e4a-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="91e4a-168">Cuando termine, haga clic en **Agregar host**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="91e4a-169">Tendrá que crear un nuevo registro de A o AAAA de detección automática en la zona de búsqueda directa para cada dominio SIP que se admita en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91e4a-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="91e4a-170">Para ello, repita los pasos del 6-8 al tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="91e4a-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="91e4a-171">Cuando haya terminado, haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="91e4a-172">Crear un registro A de DNS externo</span><span class="sxs-lookup"><span data-stu-id="91e4a-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="91e4a-173">Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público podría estar usando, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que pueda crear nuevos registros DNS allí.</span><span class="sxs-lookup"><span data-stu-id="91e4a-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="91e4a-174">En este momento, ya debe existir un dominio SIP en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91e4a-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="91e4a-175">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala de otro modo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="91e4a-176">Tómese un momento para ver cuál de las siguientes opciones tiene:</span><span class="sxs-lookup"><span data-stu-id="91e4a-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="91e4a-177">Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="91e4a-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="91e4a-178">Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="91e4a-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="91e4a-179">Una vez que tenga esa información, podrá seleccionar una opción para crear un **nuevo host a o AAAA**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="91e4a-180">Ahora debería poder escribir un **nombre**, debe escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="91e4a-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="91e4a-181">A continuación, debe haber un área que especificar en las **direcciones IP**, que tendrá que ser la IP del grupo de servidores front-end (o el servidor front-end único o el grupo o director de Director) identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="91e4a-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="91e4a-182">Es posible que tenga que guardar aquí o, si tiene que crear registros A o AAAA adicionales en la zona de búsqueda directa de cada dominio SIP para su entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="91e4a-183">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="91e4a-183">Modify certificates</span></span>
<span data-ttu-id="91e4a-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="91e4a-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="91e4a-185">Si tiene preguntas sobre la planeación de los certificados, nos hemos documentado en nuestro artículo sobre [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="91e4a-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="91e4a-186">Una vez que lo haya revisado, le guiaremos a través de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91e4a-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="91e4a-187">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="91e4a-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="91e4a-188">Solicitar certificados nuevos a la entidad de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="91e4a-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="91e4a-189">Actualizar los certificados locales con los reemplazos mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91e4a-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="91e4a-190">Comprobar los certificados con el complemento certificados en Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="91e4a-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="91e4a-191">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="91e4a-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="91e4a-192">En primer lugar, es posible que necesite comprobar qué certificados están en el lugar y si tienen las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="91e4a-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="91e4a-193">Para ello, debe iniciar sesión en su Skype empresarial Server con una cuenta que sea un administrador local.</span><span class="sxs-lookup"><span data-stu-id="91e4a-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="91e4a-194">Es posible que esta cuenta también necesite tener derechos sobre la entidad emisora de certificados (CA) para algunos de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="91e4a-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="91e4a-195">Abra el shell de administración de Skype empresarial Server (puede usar la búsqueda para encontrarla si no la tiene anclada al menú Inicio o la barra de tareas).</span><span class="sxs-lookup"><span data-stu-id="91e4a-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="91e4a-196">Será esencial que sepa qué certificados se han asignado antes de intentar agregar un certificado actualizado.</span><span class="sxs-lookup"><span data-stu-id="91e4a-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="91e4a-197">Por lo tanto, en el comando, escriba:</span><span class="sxs-lookup"><span data-stu-id="91e4a-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="91e4a-198">La información del paso 3 será exclusiva para usted.</span><span class="sxs-lookup"><span data-stu-id="91e4a-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="91e4a-199">Necesita buscarla para determinar si tiene un único certificado que se ha asignado para varios elementos o si tiene asignado un certificado diferente para los distintos componentes que los necesiten.</span><span class="sxs-lookup"><span data-stu-id="91e4a-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="91e4a-200">El parámetro **use** le dirá cómo se está usando un certificado y el parámetro **Thumbprint** le dirá si es todo el mismo certificado o varios certificados.</span><span class="sxs-lookup"><span data-stu-id="91e4a-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="91e4a-201">Si tiene las entradas de SAN recomendadas en nuestra sección de planeación, está bien.</span><span class="sxs-lookup"><span data-stu-id="91e4a-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="91e4a-202">Si no es así, deberá solicitar un nuevo certificado o varios certificados (según la configuración) de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="91e4a-203">Solicitar un nuevo certificado o certificados de la entidad de certificación (CA)</span><span class="sxs-lookup"><span data-stu-id="91e4a-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="91e4a-204">Una vez que haya comprobado qué entradas de SAN tiene, sabrá que tiene un **único certificado** (después de comprobar los pasos anteriores) y que ha aprendido que no tiene todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="91e4a-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="91e4a-205">Se debe realizar una nueva solicitud de certificado a la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="91e4a-206">Abra el PowerShell de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="91e4a-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="91e4a-207">Para que falte un servicio de detección automática de SAN (reemplazando el parámetro-CA por su propia ruta de acceso de la entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="91e4a-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="91e4a-208">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="91e4a-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="91e4a-209">Deberá usar el parámetro DomainName en su lugar.</span><span class="sxs-lookup"><span data-stu-id="91e4a-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="91e4a-210">Y, cuando usa el parámetro DomainName, tiene que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="91e4a-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="91e4a-211">Un ejemplo sería (reemplazar el parámetro-CA por su propia ruta de acceso de la entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="91e4a-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="91e4a-212">O bien, una vez que haya comprobado qué entradas de SAN tiene, verá que tiene **varios certificados** que no tienen todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="91e4a-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="91e4a-213">Se debe realizar una nueva solicitud de certificado a la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="91e4a-214">Abra el PowerShell de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="91e4a-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="91e4a-215">Para que falte un servicio de detección automática de SAN (reemplazando el parámetro-CA por su propia ruta de acceso de la entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="91e4a-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="91e4a-216">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="91e4a-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="91e4a-217">Deberá usar el parámetro DomainName en su lugar.</span><span class="sxs-lookup"><span data-stu-id="91e4a-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="91e4a-218">Y, cuando usa el parámetro DomainName, tiene que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="91e4a-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="91e4a-219">Algunos ejemplos serían reemplazar el parámetro-CA por su propia ruta de acceso de la entidad de certificación:</span><span class="sxs-lookup"><span data-stu-id="91e4a-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="91e4a-220">Una vez que la entidad de certificación haya generado los nuevos certificados, tendrá que asignarlos.</span><span class="sxs-lookup"><span data-stu-id="91e4a-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="91e4a-221">Asignar certificados mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="91e4a-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="91e4a-222">Según lo que haya encontrado en la sección ¿necesito nuevas certificaciones? anterior, debe ejecutar **una** de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="91e4a-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="91e4a-223">Si tiene un único certificado para todo (las huellas digitales son idénticas), debe ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91e4a-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="91e4a-224">Si tiene diferentes certificados para cosas (las huellas digitales son todas diferentes), ejecute esto en su lugar:</span><span class="sxs-lookup"><span data-stu-id="91e4a-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="91e4a-225">Ver certificados en Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="91e4a-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="91e4a-226">Tiene una opción para ver los certificados con el complemento certificados para MMC.</span><span class="sxs-lookup"><span data-stu-id="91e4a-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="91e4a-227">Simplemente escriba MMC en la búsqueda y debería aparecer como una opción de aplicación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="91e4a-228">Para agregar el complemento certificados, tendrá que hacer clic en **archivo**y, a continuación, **Agregar o quitar complemento...** (o método abreviado de teclado **Ctrl + M** también funcionará).</span><span class="sxs-lookup"><span data-stu-id="91e4a-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="91e4a-229">Los **certificados** serán una opción en el panel izquierdo, selecciónelo y, a continuación, **cuenta de equipo** en la ventana emergente y, a continuación, **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="91e4a-230">Todavía en la ventana emergente, en todas las probabilidades tiene que hacerlo en el equipo principal para los certificados que necesita ver, así que deje la selección en **equipo local** si es así.</span><span class="sxs-lookup"><span data-stu-id="91e4a-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="91e4a-231">Si está trabajando en un equipo remoto, cambie el botón de opción a **otro equipo** y, a continuación, escriba el FQDN de ese equipo o use el botón **examinar** para buscar el equipo a través de ad.</span><span class="sxs-lookup"><span data-stu-id="91e4a-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="91e4a-232">Después de seleccionar el equipo, deberá hacer clic en **Finalizar** cuando esté listo y, después, en **Aceptar** para agregar el complemento a MMC.</span><span class="sxs-lookup"><span data-stu-id="91e4a-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="91e4a-233">Expanda la sección **certificados** en el panel izquierdo de MMC.</span><span class="sxs-lookup"><span data-stu-id="91e4a-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="91e4a-234">Expanda también la carpeta **personal** y, a continuación, seleccione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="91e4a-235">Esto le permite ver los certificados en este almacén.</span><span class="sxs-lookup"><span data-stu-id="91e4a-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="91e4a-236">Debe buscar el certificado que desea ver, hacer clic con el botón derecho en él y elegir **abrir**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91e4a-237">¿Cómo saber qué certificado es?</span><span class="sxs-lookup"><span data-stu-id="91e4a-237">How do you know what certificate this is?</span></span> <span data-ttu-id="91e4a-238">Debe ser el único certificado asignado a todo el conjunto o la granja de servidores, o bien puede tener varios certificados para cosas diferentes, como la predeterminada, los servicios Web internos, etc., en cuyo caso es posible que necesite mirar varios certificados.</span><span class="sxs-lookup"><span data-stu-id="91e4a-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="91e4a-239">Varios certificados tendrán la misma huella digital.</span><span class="sxs-lookup"><span data-stu-id="91e4a-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="91e4a-240">Una vez que haya llegado a la vista del **certificado** , elija **detalles**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="91e4a-241">Esto le permitirá ver el nombre del firmante del certificado cuando seleccione **asunto**, y se mostrará el nombre del sujeto asignado y las propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="91e4a-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="91e4a-242">También necesitará comprobar las entradas de **nombre alternativo de sujeto** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="91e4a-243">Encontrará uno o varios de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="91e4a-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="91e4a-244">El nombre del grupo para este grupo o el nombre de servidor único si no se trata de un grupo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="91e4a-245">El nombre del servidor al que está asignado el certificado.</span><span class="sxs-lookup"><span data-stu-id="91e4a-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="91e4a-246">Registros de direcciones URL simples, que suelen reunirse y marcar.</span><span class="sxs-lookup"><span data-stu-id="91e4a-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="91e4a-247">Nombres externos de servicios Web internos y servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el generador de topologías y las selecciones de servicios web invalidadas.</span><span class="sxs-lookup"><span data-stu-id="91e4a-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="91e4a-248">Si ya está asignado, el lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="91e4a-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="91e4a-249">Tendrá que comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="91e4a-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="91e4a-250">Por lo tanto, si encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ya tiene configurada.</span><span class="sxs-lookup"><span data-stu-id="91e4a-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="91e4a-251">Puede cerrar MMC.</span><span class="sxs-lookup"><span data-stu-id="91e4a-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="91e4a-252">Si no están asignados, necesitará crear una nueva solicitud de certificado (que se indica más arriba) o debe instalarla después de la solicitud (se recomienda realizar el siguiente PowerShell para ello).</span><span class="sxs-lookup"><span data-stu-id="91e4a-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="91e4a-253">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="91e4a-253">Configure the reverse proxy</span></span>
<span data-ttu-id="91e4a-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="91e4a-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="91e4a-255">Los pasos siguientes no están pensados para seguirlos exactamente.</span><span class="sxs-lookup"><span data-stu-id="91e4a-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="91e4a-256">Esto se debe a que en las versiones anteriores del producto, nos hemos pasado por el paso de, por ejemplo, la configuración de Threat Management Gateway (TMG) y, si no lo estuviera usando, tendría que crear su propia versión desde allí.</span><span class="sxs-lookup"><span data-stu-id="91e4a-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="91e4a-257">Microsoft ya no ofrece TMG como producto y, si todavía necesita configurarlo, puede consultar los [pasos de 2013 de Lync Server](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="91e4a-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="91e4a-258">Pero la siguiente información suele ser más útil, incluso si no hay forma de proporcionar pasos de tutoriales específicos para cada proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="91e4a-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="91e4a-259">Tenemos dos cosas importantes que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="91e4a-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="91e4a-260">¿Va a realizar la solicitud de detección automática inicial a través de HTTPS (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="91e4a-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="91e4a-261">Si tiene una regla de publicación Web, debe modificarla.</span><span class="sxs-lookup"><span data-stu-id="91e4a-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="91e4a-262">Si aún no tiene una regla de publicación Web, debe crearla.</span><span class="sxs-lookup"><span data-stu-id="91e4a-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="91e4a-263">Si va a realizar la solicitud de detección automática inicial a través de HTTP, tendrá que crear o modificar también esa regla.</span><span class="sxs-lookup"><span data-stu-id="91e4a-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91e4a-264">**Importante** Un valor de tiempo de espera de proxy es un número que variará de una implementación a una implementación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="91e4a-265">Debe supervisar la implementación y modificar el valor de la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="91e4a-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="91e4a-266">Es posible que pueda establecer el valor como mínimo como 200.</span><span class="sxs-lookup"><span data-stu-id="91e4a-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="91e4a-267">Si va a admitir clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificaciones de inserción de Office 365, que tienen un valor de tiempo de espera de 900.</span><span class="sxs-lookup"><span data-stu-id="91e4a-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="91e4a-268">Es muy probable que tenga que aumentar el valor de tiempo de espera para evitar desconexiones de clientes cuando el valor es demasiado bajo, o disminuir el número si las conexiones a través del proxy no se desconectan, sino más lentas después de que el cliente se haya desconectado.</span><span class="sxs-lookup"><span data-stu-id="91e4a-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="91e4a-269">La supervisión y la definición de una estructura en su entorno es la única forma precisa de determinar la configuración adecuada para este valor.</span><span class="sxs-lookup"><span data-stu-id="91e4a-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="91e4a-270">Modificar la regla de publicación web existente para la dirección URL y el SAN de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="91e4a-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="91e4a-271">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="91e4a-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="91e4a-272">Deberá buscar la regla de publicación web y elegir la opción Editar (puede estar en un menú o una pestaña, según la configuración del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="91e4a-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="91e4a-273">Debe haber un área que indique a qué se aplica esta regla de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="91e4a-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="91e4a-274">Debe modificar esta regla para los sitios o solicitudes entrantes de los sitios.</span><span class="sxs-lookup"><span data-stu-id="91e4a-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="91e4a-275">Va a **Agregar** una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="91e4a-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="91e4a-276">Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato de su proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="91e4a-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="91e4a-277">Es posible que tenga un nuevo certificado que contenga la entrada SAN de detección automática.</span><span class="sxs-lookup"><span data-stu-id="91e4a-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="91e4a-278">También debe instalarse y configurarse para usarlo de acuerdo con la configuración del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="91e4a-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="91e4a-279">Asegúrese de guardar todo cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="91e4a-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="91e4a-280">Si el proxy inverso tiene una funcionalidad de **prueba** , úselo para asegurarse de que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="91e4a-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="91e4a-281">Ahora, es posible que tenga que repetir estos pasos si tiene un director o un grupo de servidores de Director en su entorno (esto significa que tendrá una segunda regla).</span><span class="sxs-lookup"><span data-stu-id="91e4a-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="91e4a-282">Crear una regla de publicación web para la dirección URL externa de detección automática</span><span class="sxs-lookup"><span data-stu-id="91e4a-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="91e4a-283">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="91e4a-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="91e4a-284">Deberá buscar en el lugar de la interfaz en el que cree las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una ficha, según la configuración del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="91e4a-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="91e4a-285">Busca la opción de crear una nueva regla de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="91e4a-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="91e4a-286">Normalmente, tendrá que escribir la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="91e4a-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="91e4a-287">**Name**: el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="91e4a-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="91e4a-288">**Acción de regla**: en este caso, se trata de una regla de **permiso** , que permite que un servidor proxy inverso pase algo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="91e4a-289">La regla de **publicación** o la opción que elija será **un único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="91e4a-290">Debe ser **SSL** para el acceso externo; elija esa opción.</span><span class="sxs-lookup"><span data-stu-id="91e4a-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="91e4a-291">Tendrá que publicar una ruta de acceso para la **publicación interna**y especificar el FQDN de los servicios web externos en el equilibrador de carga del grupo de servidores front-end (o el FQDN del equilibrador de carga del grupo de directores, si tiene uno), un ejemplo sería sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="91e4a-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="91e4a-292">Debe escribir \*\* / \*\*\* como la ruta de acceso que se va a publicar, pero también debe **reenviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="91e4a-293">Habrá una opción para obtener información o información detallada sobre los **nombres públicos o externos** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="91e4a-294">Este es el lugar en el que podrá escribir:</span><span class="sxs-lookup"><span data-stu-id="91e4a-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="91e4a-295">**Aceptar solicitudes**, pero debe ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="91e4a-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="91e4a-296">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="91e4a-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="91e4a-297"><sipdomain>(esta es la dirección URL externa del servicio Detección automática).</span><span class="sxs-lookup"><span data-stu-id="91e4a-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="91e4a-298">Ahora, si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, tendrá que escribir el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="91e4a-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="91e4a-299">Habrá una opción de **ruta de acceso** y deberá escribir \*\* / \*\*\* aquí.</span><span class="sxs-lookup"><span data-stu-id="91e4a-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="91e4a-300">Deberá seleccionar un **agente de escucha de SSL** con el certificado público actualizado.</span><span class="sxs-lookup"><span data-stu-id="91e4a-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="91e4a-301">La **delegación de autenticación** debe establecerse en **sin delegación**, pero **debe** permitirse la autenticación directa de clientes.</span><span class="sxs-lookup"><span data-stu-id="91e4a-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="91e4a-302">La regla debe establecerse en **todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="91e4a-303">Esta es la información que necesita para crear esta regla y permitirle continuar.</span><span class="sxs-lookup"><span data-stu-id="91e4a-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="91e4a-304">Necesitará asegurarse de que el **encabezado de host original** se reenvía.</span><span class="sxs-lookup"><span data-stu-id="91e4a-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="91e4a-305">Los puertos del **servidor Web** también deben establecerse, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91e4a-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="91e4a-306">**Las solicitudes de redireccionamiento al puerto http** y el número de Puerto deberían ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="91e4a-307">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="91e4a-308">Cuando todo está configurado, necesitará guardar o aplicar estos y, después, querrá probar la regla.</span><span class="sxs-lookup"><span data-stu-id="91e4a-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="91e4a-309">Crear una regla de publicación web para el puerto 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="91e4a-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="91e4a-310">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="91e4a-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="91e4a-311">Deberá buscar en el lugar de la interfaz en el que cree las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una ficha, según la configuración del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="91e4a-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="91e4a-312">Busca la opción de crear una nueva regla de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="91e4a-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="91e4a-313">Normalmente, tendrá que escribir la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="91e4a-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="91e4a-314">**Name**: el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="91e4a-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="91e4a-315">**Acción de regla**: en este caso, se trata de una regla de **permiso** , que permite que un servidor proxy inverso pase algo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="91e4a-316">La regla de **publicación** o la opción que elija será **un único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="91e4a-317">Debe ser una **conexión no segura para conectarse al servidor web o la granja de servidores publicada**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="91e4a-318">Tendrá que publicar una ruta de acceso para la **publicación interna**y escribir el FQDN de la **Dirección VIP** del equilibrador de carga del grupo de servidores front-end, un ejemplo sería sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="91e4a-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="91e4a-319">Debe escribir \*\* / \*\*\* como la ruta de acceso que se va a publicar, pero también debe **reenviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="91e4a-320">Habrá una opción para obtener información o información detallada sobre los **nombres públicos o externos** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="91e4a-321">Este es el lugar en el que podrá escribir:</span><span class="sxs-lookup"><span data-stu-id="91e4a-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="91e4a-322">**Aceptar solicitudes**, pero debe ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="91e4a-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="91e4a-323">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="91e4a-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="91e4a-324"><sipdomain>(esta es la dirección URL externa del servicio Detección automática).</span><span class="sxs-lookup"><span data-stu-id="91e4a-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="91e4a-325">Habrá una opción de **ruta de acceso** y deberá escribir \*\* / \*\*\* aquí.</span><span class="sxs-lookup"><span data-stu-id="91e4a-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="91e4a-326">Deberá seleccionar una escucha de web o permitir que el proxy inverso cree una.</span><span class="sxs-lookup"><span data-stu-id="91e4a-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="91e4a-327">La **delegación de autenticación** debe establecerse en **sin delegación**, pero **no debe** permitirse la autenticación directa de clientes.</span><span class="sxs-lookup"><span data-stu-id="91e4a-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="91e4a-328">La regla debe establecerse en **todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="91e4a-329">Esta es la información que necesita para crear esta regla y permitirle continuar.</span><span class="sxs-lookup"><span data-stu-id="91e4a-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="91e4a-330">Se deben establecer los puertos del **servidor Web** , deberá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91e4a-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="91e4a-331">**Las solicitudes de redireccionamiento al puerto http** y el número de Puerto deberían ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="91e4a-332">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="91e4a-333">Cuando todo está configurado, necesitará guardar o aplicar estos y, después, querrá probar la regla.</span><span class="sxs-lookup"><span data-stu-id="91e4a-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="91e4a-334">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="91e4a-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="91e4a-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="91e4a-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="91e4a-336">Los entornos híbridos de Skype empresarial Server son entornos que combinan un entorno local y de O365.</span><span class="sxs-lookup"><span data-stu-id="91e4a-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="91e4a-337">Cuando se trabaja en un entorno híbrido de Skype empresarial Server, el servicio de detección automática necesita poder encontrar a un usuario de cualquiera de estos entornos.</span><span class="sxs-lookup"><span data-stu-id="91e4a-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="91e4a-338">Para permitir que los clientes móviles detecten dónde se encuentra un usuario, el servicio de detección automática debe configurarse con un nuevo localizador de recursos uniforme (URL).</span><span class="sxs-lookup"><span data-stu-id="91e4a-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="91e4a-339">Estos pasos son:</span><span class="sxs-lookup"><span data-stu-id="91e4a-339">The steps are:</span></span>
  
1. <span data-ttu-id="91e4a-340">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91e4a-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="91e4a-341">Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** para su entorno de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="91e4a-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="91e4a-342">A continuación, en la ventana del shell, ejecute:</span><span class="sxs-lookup"><span data-stu-id="91e4a-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="91e4a-343">Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="91e4a-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="91e4a-344">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="91e4a-344">Test your Mobility deployment</span></span>
<span data-ttu-id="91e4a-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="91e4a-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="91e4a-346">Una vez que haya implementado el servicio de movilidad de Skype empresarial Server y el servicio Detección automática de Skype empresarial Server, querrá ejecutar una transacción de prueba para asegurarse de que la implementación funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="91e4a-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="91e4a-347">Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear, unirse y comunicarse en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="91e4a-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="91e4a-348">Necesitará dos usuarios (reales o de prueba) y sus credenciales completas para realizar esta prueba.</span><span class="sxs-lookup"><span data-stu-id="91e4a-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="91e4a-349">Este comando funcionará para clientes de Skype empresarial, así como para clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91e4a-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="91e4a-350">Para los clientes de Lync Server 2010 en Skype empresarial Server 2015, deberá ejecutar **Test-CsMcxP2PIM** para probar.</span><span class="sxs-lookup"><span data-stu-id="91e4a-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="91e4a-351">Los usuarios de Lync Server 2010 todavía tendrán que ser usuarios reales o usuarios de prueba predefinidos, y necesitará sus credenciales de contraseña.</span><span class="sxs-lookup"><span data-stu-id="91e4a-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="91e4a-352">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="91e4a-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="91e4a-353">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="91e4a-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="91e4a-354">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="91e4a-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="91e4a-355">Conferencias de prueba para clientes móviles de Skype empresarial y Lync 2013</span><span class="sxs-lookup"><span data-stu-id="91e4a-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="91e4a-356">Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-357">Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).</span><span class="sxs-lookup"><span data-stu-id="91e4a-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="91e4a-358">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="91e4a-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="91e4a-359">También es posible establecer credenciales en un script y pasarlas al cmdlet test.</span><span class="sxs-lookup"><span data-stu-id="91e4a-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="91e4a-360">Se incluye un ejemplo a continuación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="91e4a-361">Conferencia de prueba para clientes móviles de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="91e4a-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="91e4a-362">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="91e4a-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="91e4a-363">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="91e4a-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="91e4a-364">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="91e4a-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="91e4a-365">Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-366">Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).</span><span class="sxs-lookup"><span data-stu-id="91e4a-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="91e4a-367">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="91e4a-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="91e4a-368">También es posible establecer credenciales en un script y pasarlas al cmdlet test.</span><span class="sxs-lookup"><span data-stu-id="91e4a-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="91e4a-369">Se incluye un ejemplo a continuación.</span><span class="sxs-lookup"><span data-stu-id="91e4a-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="91e4a-370">Para revisar los procedimientos de comando, puede consultar [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) y [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="91e4a-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="91e4a-371">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="91e4a-371">Configure for push notifications</span></span>
<span data-ttu-id="91e4a-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="91e4a-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="91e4a-373">Las notificaciones de inserción, en forma de identificadores, iconos o alertas, se pueden enviar a un dispositivo móvil incluso cuando la aplicación de Skype o Lync está inactiva.</span><span class="sxs-lookup"><span data-stu-id="91e4a-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="91e4a-374">Pero ¿qué son las notificaciones de inserción?</span><span class="sxs-lookup"><span data-stu-id="91e4a-374">But what are push notifications?</span></span> <span data-ttu-id="91e4a-375">Se trata de alertas de eventos, como una invitación de mi nueva o perdida, o de un correo de voz recibido.</span><span class="sxs-lookup"><span data-stu-id="91e4a-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="91e4a-376">El servicio de movilidad de Skype empresarial Server envía estas notificaciones al servicio de notificación de inserción basado en la nube de Skype empresarial Server, que a su vez envía las notificaciones al servicio de notificación de inserción de Microsoft (MSNS) para los usuarios de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="91e4a-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="91e4a-377">Esta funcionalidad no ha cambiado en Lync Server 2013, pero si tiene un servidor de Skype empresarial, querrá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91e4a-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="91e4a-378">Para un servidor perimetral de Skype empresarial Server, agregue un nuevo proveedor de hospedaje, Microsoft Skype empresarial online y, a continuación, configure la Federación del proveedor de hospedaje entre su organización y Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="91e4a-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="91e4a-379">Habilite las notificaciones de inserción mediante la ejecución del cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="91e4a-380">De manera predeterminada, las notificaciones de inserción están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="91e4a-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="91e4a-381">Pruebe la configuración de Federación y las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="91e4a-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="91e4a-382">Configurar el servidor perimetral de Skype empresarial para las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="91e4a-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="91e4a-383">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-384">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="91e4a-385">Agregue un proveedor de hospedaje de Skype empresarial Server online.</span><span class="sxs-lookup"><span data-stu-id="91e4a-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="91e4a-386">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91e4a-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="91e4a-387">No puede tener más de una relación de Federación con un solo proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="91e4a-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="91e4a-388">Por lo tanto, si ya ha configurado un proveedor de hospedaje que tiene una relación de Federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, incluso si la identidad del proveedor de hospedaje no es SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="91e4a-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="91e4a-389">Configure la Federación del proveedor de hospedaje entre su organización y el servicio de notificaciones de inserción en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="91e4a-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="91e4a-390">En la línea de comandos, tendrá que escribir:</span><span class="sxs-lookup"><span data-stu-id="91e4a-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="91e4a-391">Habilitar las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="91e4a-391">Enable push notifications</span></span>

1. <span data-ttu-id="91e4a-392">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-393">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="91e4a-394">Habilitar notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="91e4a-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="91e4a-395">Habilitar Federación:</span><span class="sxs-lookup"><span data-stu-id="91e4a-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="91e4a-396">Probar la Federación y las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="91e4a-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="91e4a-397">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-398">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="91e4a-399">Pruebe la configuración de Federación:</span><span class="sxs-lookup"><span data-stu-id="91e4a-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="91e4a-400">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91e4a-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="91e4a-401">Pruebe las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="91e4a-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="91e4a-402">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91e4a-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="91e4a-403">Configurar la Directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="91e4a-403">Configure Mobility policy</span></span>
<span data-ttu-id="91e4a-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="91e4a-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="91e4a-405">Tiene la capacidad de Skype empresarial Server para determinar quién puede usar el servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o vídeo, así como si se necesitará Wi-Fi para VoIP o vídeo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="91e4a-406">Llamar a través del trabajo permite a un usuario móvil usar su número de teléfono del trabajo, en lugar de su número de teléfono móvil, al colocar y recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="91e4a-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="91e4a-407">La persona que se encuentra en el otro extremo de la línea no verá el número de teléfono móvil del usuario y le permitirá evitar gastos de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="91e4a-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="91e4a-408">Cuando se configuran VoIP y vídeo, los usuarios pueden realizar llamadas y vídeos de VoIP.</span><span class="sxs-lookup"><span data-stu-id="91e4a-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="91e4a-409">La configuración del uso de WiFi determina si el dispositivo móvil de un usuario será necesario para usar una red WiFi a través de una red de datos móviles.</span><span class="sxs-lookup"><span data-stu-id="91e4a-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="91e4a-410">La movilidad, la llamada a través del trabajo y las características de VoIP y vídeo están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="91e4a-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="91e4a-411">La configuración para requerir WiFi para VoIP y vídeo está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="91e4a-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="91e4a-412">Un administrador tiene la capacidad de cambiar esto, ya sea de forma global, por sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="91e4a-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="91e4a-413">Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben:</span><span class="sxs-lookup"><span data-stu-id="91e4a-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="91e4a-414">Habilitado para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="91e4a-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="91e4a-415">Habilitado para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="91e4a-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="91e4a-416">Se le asigna una directiva de movilidad que tiene la opción **enablemobility configurada** establecida en **true**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="91e4a-417">Para que los usuarios puedan usar la llamada a través del trabajo, también deben:</span><span class="sxs-lookup"><span data-stu-id="91e4a-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="91e4a-418">Se le asigna una directiva de voz que tiene seleccionada la opción **Habilitar llamadas simultáneas en teléfonos** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="91e4a-419">Se le ha asignado una directiva de movilidad que tiene la **EnableOutsideVoice** establecida en **true**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91e4a-420">Los usuarios que no están habilitados para telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP de Skype a Skype o pueden unirse a conferencias mediante el vínculo haga clic para unirse mientras están en sus dispositivos móviles, si las opciones adecuadas están definidas para la Directiva de voz a la que están asociadas con.</span><span class="sxs-lookup"><span data-stu-id="91e4a-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="91e4a-421">Hay más detalles en el tema de PLANEAción.</span><span class="sxs-lookup"><span data-stu-id="91e4a-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="91e4a-422">Modificar la Directiva de movilidad global</span><span class="sxs-lookup"><span data-stu-id="91e4a-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="91e4a-423">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-424">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="91e4a-425">Desactive el acceso a la movilidad y llame a través del trabajo de forma global; para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91e4a-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="91e4a-426">Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="91e4a-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="91e4a-427">Pero no se puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="91e4a-428">Para obtener más información, consulte [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="91e4a-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="91e4a-429">Modificar la Directiva de movilidad por sitio</span><span class="sxs-lookup"><span data-stu-id="91e4a-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="91e4a-430">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-431">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="91e4a-432">Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar la opción de requerir Wi-Fi para audio IP y requerir WiFi para vídeo IP por sitio.</span><span class="sxs-lookup"><span data-stu-id="91e4a-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="91e4a-433">Tipo:</span><span class="sxs-lookup"><span data-stu-id="91e4a-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="91e4a-434">Para obtener más información [, vea New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="91e4a-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="91e4a-435">Modificar la Directiva de movilidad por usuario</span><span class="sxs-lookup"><span data-stu-id="91e4a-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="91e4a-436">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="91e4a-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="91e4a-437">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="91e4a-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="91e4a-438">Cree directivas de movilidad de nivel de usuario y desactive la movilidad y llame a través del trabajo por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="91e4a-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="91e4a-439">Tipo:</span><span class="sxs-lookup"><span data-stu-id="91e4a-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="91e4a-440">Otro ejemplo con datos de muestra:</span><span class="sxs-lookup"><span data-stu-id="91e4a-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="91e4a-441">Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="91e4a-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="91e4a-442">Pero no se puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="91e4a-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

