---
title: Implementar y configurar la movilidad en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artículo le guiará a través de los pasos para configurar una instalación existente de Skype empresarial Server con el fin de usar el servicio de movilidad, de modo que sus dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.
ms.openlocfilehash: 910e23e8aec18d36c3a7e4bda9e97828fb498802
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234579"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="f2b82-103">Implementar y configurar la movilidad en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f2b82-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="f2b82-104">Este artículo le guiará a través de los pasos para configurar una instalación existente de Skype empresarial Server con el fin de usar el servicio de movilidad, de modo que sus dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="f2b82-105">Una vez que haya revisado el [plan de movilidad de Skype empresarial Server](../plan-your-deployment/mobility.md) , debe estar listo para continuar con los pasos siguientes para implementar la movilidad en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="f2b82-106">Los pasos son los siguientes (e incluimos en esta tabla una lista de permisos):</span><span class="sxs-lookup"><span data-stu-id="f2b82-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="f2b82-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="f2b82-107">**Phase**</span></span>|<span data-ttu-id="f2b82-108">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="f2b82-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f2b82-109">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="f2b82-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="f2b82-110">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="f2b82-110">Domain Admins</span></span>  <br/> <span data-ttu-id="f2b82-111">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="f2b82-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="f2b82-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="f2b82-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="f2b82-113">Administrador local</span><span class="sxs-lookup"><span data-stu-id="f2b82-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="f2b82-114">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f2b82-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="f2b82-115">Administrador local</span><span class="sxs-lookup"><span data-stu-id="f2b82-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="f2b82-116">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f2b82-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="f2b82-117">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="f2b82-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="f2b82-118">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="f2b82-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="f2b82-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f2b82-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="f2b82-120">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f2b82-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="f2b82-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f2b82-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="f2b82-122">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="f2b82-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="f2b82-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f2b82-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="f2b82-p102">Todas las secciones siguientes contienen pasos que dan por sentado que ha leído el tema sobre planificación. Si algo le resulta confuso, consulte la información contenida en dicho tema.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="f2b82-126">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f2b82-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f2b82-127">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="f2b82-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f2b82-128">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="f2b82-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="f2b82-129">Crear registros de DNS</span><span class="sxs-lookup"><span data-stu-id="f2b82-129">Create DNS records</span></span>
<span data-ttu-id="f2b82-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b82-130"></span></span>

<span data-ttu-id="f2b82-131">Es posible que ya tenga estas como parte de su entorno de Skype empresarial Server, pero es necesario crear los siguientes registros para que funcione AutoDiscovery:</span><span class="sxs-lookup"><span data-stu-id="f2b82-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="f2b82-132">Un registro DNS interno para dar soporte a los usuarios móviles que se conectan desde la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2b82-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="f2b82-133">Un registro DNS externo (o público) para dar soporte a los usuarios móviles que se conectan desde fuera de la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2b82-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="f2b82-134">Estos registros pueden ser registros CNAME o nombres (de host) A (no tiene que crear ambos; únicamente estamos incluyendo los pasos necesarios para todo aquí).</span><span class="sxs-lookup"><span data-stu-id="f2b82-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="f2b82-135">Crear un registro CNAME de DNS interno</span><span class="sxs-lookup"><span data-stu-id="f2b82-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="f2b82-136">Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="f2b82-137">Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.</span><span class="sxs-lookup"><span data-stu-id="f2b82-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="f2b82-138">En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio que está en el hogar de los servidores front-end de Skype empresarial Server y expandir allí las **zonas de búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="f2b82-139">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f2b82-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f2b82-140">Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.</span><span class="sxs-lookup"><span data-stu-id="f2b82-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f2b82-141">Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).</span><span class="sxs-lookup"><span data-stu-id="f2b82-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="f2b82-142">Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Nuevo alias (CNAME)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="f2b82-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="f2b82-143">En el cuadro de texto **Nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f2b82-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="f2b82-144">En el **nombre de dominio completo (FQDN para el host de destino**, tendrá que escribir o examinar el FQDN de los servicios Web internos de su grupo de servidores front-end (o un único servidor front-end, o director o director), identificado en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="f2b82-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="f2b82-145">Haga clic en Aceptar cuando ya lo haya introducido.</span><span class="sxs-lookup"><span data-stu-id="f2b82-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="f2b82-146">Tendrá que crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa para cada dominio SIP admitido en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="f2b82-147">Crear un registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="f2b82-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="f2b82-148">Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.</span><span class="sxs-lookup"><span data-stu-id="f2b82-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="f2b82-149">En este momento, ya debería existir un dominio SIP en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="f2b82-150">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.</span><span class="sxs-lookup"><span data-stu-id="f2b82-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="f2b82-151">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f2b82-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f2b82-152">Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.</span><span class="sxs-lookup"><span data-stu-id="f2b82-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f2b82-153">Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).</span><span class="sxs-lookup"><span data-stu-id="f2b82-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="f2b82-154">Cuando ya tenga esa información, podrá seleccionar una opción para crear un **alias nuevo (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="f2b82-155">Ahora debería poder introducir un **nombre de alias**. Para ello, tiene que escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f2b82-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="f2b82-156">A continuación, debe haber un área para especificar en un **FQDN para el host de destino**, lo cual deberá ser el FQDN para el grupo de servidores front-end (o un único servidor frontal o director o director), identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="f2b82-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="f2b82-157">Es posible que tenga que guardarlos aquí o, si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en el entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2b82-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="f2b82-158">Crear un registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="f2b82-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="f2b82-159">Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="f2b82-160">Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.</span><span class="sxs-lookup"><span data-stu-id="f2b82-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="f2b82-161">En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio que está en el hogar de los servidores front-end de Skype empresarial Server y expandir allí las **zonas de búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="f2b82-162">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f2b82-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f2b82-163">Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.</span><span class="sxs-lookup"><span data-stu-id="f2b82-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f2b82-164">Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).</span><span class="sxs-lookup"><span data-stu-id="f2b82-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="f2b82-165">Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Host nuevo (A o AAAA)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="f2b82-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="f2b82-166">En el cuadro de texto **Nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f2b82-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="f2b82-167">En el cuadro de texto **dirección IP** , escriba la dirección IP de los servicios Web internos para el grupo de servidores front-end (o un solo servidor front-end o un grupo de directores o director) identificada en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="f2b82-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="f2b82-168">Una vez hecho esto, haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="f2b82-169">Tendrá que crear nuevos registros A o AAAA de Autodiscover en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="f2b82-170">Para ello, repita los pasos 6 a 8 tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f2b82-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="f2b82-171">Cuando haya terminado, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="f2b82-172">Crear un registro A de DNS externo</span><span class="sxs-lookup"><span data-stu-id="f2b82-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="f2b82-173">Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.</span><span class="sxs-lookup"><span data-stu-id="f2b82-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="f2b82-174">En este momento, ya debería existir un dominio SIP en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="f2b82-175">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.</span><span class="sxs-lookup"><span data-stu-id="f2b82-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="f2b82-176">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f2b82-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f2b82-177">Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.</span><span class="sxs-lookup"><span data-stu-id="f2b82-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f2b82-178">Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).</span><span class="sxs-lookup"><span data-stu-id="f2b82-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="f2b82-179">Cuando ya tenga esa información, podrá seleccionar una opción para crear un **nuevo host A o AAAA**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="f2b82-180">Ahora debería poder introducir un **nombre**. Para ello, tiene que escribir lyncdiscover para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f2b82-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="f2b82-181">A continuación, debe haber un área para escribir en una **dirección IP**, lo cual tendrá que ser la dirección IP del grupo de servidores front-end (o un único servidor front-end o un director o director) identificada en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="f2b82-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="f2b82-182">Es posible que tenga que guardarla aquí o, si necesita crear registros A o AAAA adicionales en la zona de búsqueda directa de cada dominio SIP para el entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2b82-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="f2b82-183">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="f2b82-183">Modify certificates</span></span>
<span data-ttu-id="f2b82-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b82-184"></span></span>

<span data-ttu-id="f2b82-185">Si tiene preguntas sobre cómo planear los certificados, nos hemos documentado en el artículo sobre el [plan de movilidad para Skype empresarial Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="f2b82-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="f2b82-186">Cuando lo revise, le guiaremos por los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f2b82-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="f2b82-187">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="f2b82-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="f2b82-188">Solicitud de nuevos certificados de su entidad de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="f2b82-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="f2b82-189">Actualización de certificados locales con los reemplazos mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2b82-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="f2b82-190">Comprobar los certificados con el complemento certificados en Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="f2b82-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="f2b82-191">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="f2b82-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="f2b82-192">Primero, es probable que necesite comprobar qué certificados tiene en local y si tienen las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f2b82-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="f2b82-193">Para ello, tendrá que iniciar sesión en su servidor de Skype empresarial con una cuenta que sea un administrador local.</span><span class="sxs-lookup"><span data-stu-id="f2b82-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="f2b82-194">Para algunos de estos pasos, es posible que esta cuenta necesite tener derechos para la entidad emisora de certificados (CA).</span><span class="sxs-lookup"><span data-stu-id="f2b82-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="f2b82-195">Abra el shell de administración de Skype empresarial Server (puede usar buscar para encontrarlo si no está anclado al menú Inicio o a la barra de tareas).</span><span class="sxs-lookup"><span data-stu-id="f2b82-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="f2b82-p110">Te va a resultar esencial saber qué certificados se han asignado antes de intentar agregar uno actualizado. Por ello, en el comando, escriba:</span><span class="sxs-lookup"><span data-stu-id="f2b82-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="f2b82-p111">La información del paso 3 será exclusiva para usted. Tiene que analizarla para determinar si cuenta con un certificado único asignado a varias cosas o si tiene un certificado distinto asignado a cada uno de los diferentes componentes que lo necesitan. El parámetro **Use** le indicará cómo se ha estado usando un certificado, mientras que el parámetro **Thumbprint** le indicará si se trata del mismo certificado o de varios.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="f2b82-p112">Si tiene las entradas SAN recomendadas en nuestra sección Planificación, está en el camino correcto. En caso contrario, tendrá que solicitar un certificado nuevo o varios certificados (según su configuración) a la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="f2b82-203">Solicitar uno o varios certificados nuevos a una entidad de certificación (CA)</span><span class="sxs-lookup"><span data-stu-id="f2b82-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="f2b82-204">Después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene un **único certificado** (mediante los pasos anteriores) y sabrá que no tiene todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f2b82-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="f2b82-205">En ese caso, se debe solicitar a la CA un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="f2b82-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="f2b82-206">Abra el PowerShell de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f2b82-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="f2b82-207">En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f2b82-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="f2b82-208">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f2b82-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="f2b82-209">En su lugar, tendrá que usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="f2b82-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="f2b82-210">Y cuando use el parámetro DomainName, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="f2b82-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="f2b82-211">Un ejemplo sería (reemplazar el parámetro-CA por su propia ruta de acceso de la entidad emisora de certificados):</span><span class="sxs-lookup"><span data-stu-id="f2b82-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="f2b82-212">O bien, después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene **varios certificados** que no tienen todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f2b82-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="f2b82-213">Si es así, se debe solicitar a la CA un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="f2b82-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="f2b82-214">Abra el PowerShell de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f2b82-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="f2b82-215">En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f2b82-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="f2b82-216">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f2b82-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="f2b82-217">En su lugar, tendrá que usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="f2b82-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="f2b82-218">Y cuando use el parámetro DomainName, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="f2b82-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="f2b82-219">Los ejemplos serían reemplazar el parámetro-CA por su propia ruta de acceso de la entidad emisora de certificados:</span><span class="sxs-lookup"><span data-stu-id="f2b82-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="f2b82-220">Cuando la CA haya generado los nuevos certificados, tendrá que asignarlos.</span><span class="sxs-lookup"><span data-stu-id="f2b82-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f2b82-221">Asignar certificados usando el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f2b82-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="f2b82-222">Según qué haya encontrado en la sección anterior relativa a si necesita certificados nuevos, tendrá que ejecutar **uno** de los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="f2b82-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="f2b82-223">Si tiene un solo certificado para todo (las huellas digitales son idénticas), tiene que ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="f2b82-224">Si tiene diferentes certificados (las huellas digitales son todas diferentes), ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="f2b82-225">Ver certificados en Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="f2b82-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="f2b82-p117">Tiene la opción de mirar los certificados con el complemento Certificados para MMC. Solo tiene que escribir MMC en el cuadro de búsqueda y aparecerá como una opción de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="f2b82-p118">Para agregar el complemento Certificados, debe hacer clic en **Archivo** y después en **Agregar o quitar complemento...** (o el método abreviado de teclado **Ctrl+M** también funcionará). **Certificados** será una de las opciones en el panel izquierdo. Selecciónela y, a continuación, seleccione **Cuenta de equipo** en la ventana emergente y **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="f2b82-230">Aún en la ventana emergente, en todas las probabilidades está haciendo esto en el equipo que está en el hogar con los certificados que necesita consultar, así que deje la selección en el **equipo local** si es así.</span><span class="sxs-lookup"><span data-stu-id="f2b82-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="f2b82-231">Si está trabajando en un equipo remoto, cambie el botón de radio a **otro equipo** y, a continuación, escriba el FQDN de ese equipo o use el botón **examinar** para buscar ese equipo a través de ad.</span><span class="sxs-lookup"><span data-stu-id="f2b82-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="f2b82-232">Después de seleccionar el equipo, tendrá que hacer clic en **Finalizar** cuando esté listo y, después, en **Aceptar** para agregar el complemento a MMC.</span><span class="sxs-lookup"><span data-stu-id="f2b82-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="f2b82-233">Expanda la sección **certificados** en el panel izquierdo de MMC.</span><span class="sxs-lookup"><span data-stu-id="f2b82-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="f2b82-234">Expanda la carpeta **Personal** también y seleccione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="f2b82-235">Esto le permitirá ver los certificados de esta tienda.</span><span class="sxs-lookup"><span data-stu-id="f2b82-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="f2b82-236">Tiene que ubicar el certificado que quiere ver, hacer clic con el botón derecho en él y elegir **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2b82-237">¿Cómo puede saber qué certificado es?</span><span class="sxs-lookup"><span data-stu-id="f2b82-237">How do you know what certificate this is?</span></span> <span data-ttu-id="f2b82-238">Debe ser el único certificado asignado a cada una de las granjas de servidores o puede tener varios certificados para diferentes aspectos, como predeterminado, servicios Web internos, etc., en cuyo caso es posible que tenga que consultar varios certificados.</span><span class="sxs-lookup"><span data-stu-id="f2b82-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="f2b82-239">Varios certificados tendrán la misma huella digital.</span><span class="sxs-lookup"><span data-stu-id="f2b82-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="f2b82-p122">Cuando haya llegado a la vista **Certificado**, elija **Detalles**. Esto le permitirá ver el nombre del firmante del certificado al seleccionar **Sujeto** y se mostrará el nombre del sujeto asignado y sus propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="f2b82-p123">También necesitará comprobar las entradas de **Nombres alternativos de firmante**. Encontrará uno o varios de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="f2b82-244">El nombre del grupo para este grupo o el nombre de servidor único si no se trata de un grupo.</span><span class="sxs-lookup"><span data-stu-id="f2b82-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="f2b82-245">Nombre del servidor al que está asignado el certificado.</span><span class="sxs-lookup"><span data-stu-id="f2b82-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="f2b82-246">Registros de direcciones URL simples, normalmente de reunión y marcación.</span><span class="sxs-lookup"><span data-stu-id="f2b82-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="f2b82-247">Nombres externos de servicios web y internos de servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones seleccionadas en las selecciones del generador de topología y de los servicios web reemplazados.</span><span class="sxs-lookup"><span data-stu-id="f2b82-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="f2b82-248">Si ya está asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="f2b82-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="f2b82-249">Necesitará comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="f2b82-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="f2b82-250">Por lo tanto, si encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ya tienes configurado.</span><span class="sxs-lookup"><span data-stu-id="f2b82-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="f2b82-251">Puede cerrar MMC.</span><span class="sxs-lookup"><span data-stu-id="f2b82-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="f2b82-252">Si no están asignados, tendrá que realizar una nueva solicitud de certificado (como se detalla anteriormente) o deberá instalarlos después de la solicitud (para ello recomendamos seguir los pasos para Powershell detallados anteriormente).</span><span class="sxs-lookup"><span data-stu-id="f2b82-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="f2b82-253">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f2b82-253">Configure the reverse proxy</span></span>
<span data-ttu-id="f2b82-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b82-254"></span></span>

<span data-ttu-id="f2b82-p125">No es necesario seguir al pie de la letra los pasos que se explican a continuación. En las versiones anteriores del producto, le hemos guiado, por ejemplo, en el proceso de configuración de Threat Management Gateway (TMG) y, si no lo estaba utilizando, tenía que encontrar la forma de adaptarlo a su propia versión a partir de la información con la que contaba.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="f2b82-257">Ya no ofrece Microsoft TMG como producto y, si aún necesita configurarlo, puede consultar los [pasos de 2013 de Lync Server](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f2b82-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="f2b82-258">Sin embargo, la siguiente información es más útil, incluso si no hay forma de que podamos proporcionar pasos de tutoriales específicos para cada proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="f2b82-259">Debemos considerar dos aspectos:</span><span class="sxs-lookup"><span data-stu-id="f2b82-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="f2b82-260">¿Hará su solicitud de detección automática inicial a través de HTTPS (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="f2b82-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="f2b82-261">Si tiene una regla de publicación web, debe modificarla.</span><span class="sxs-lookup"><span data-stu-id="f2b82-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="f2b82-262">Si no tiene una regla de publicación web todavía, debe crearla.</span><span class="sxs-lookup"><span data-stu-id="f2b82-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="f2b82-263">Si está realizando una solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.</span><span class="sxs-lookup"><span data-stu-id="f2b82-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f2b82-264">**Importante** Un valor de tiempo de espera de proxy es un número que variará de una implementación a la de implementación.</span><span class="sxs-lookup"><span data-stu-id="f2b82-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="f2b82-265">Debe supervisar la implementación y modificar el valor de la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="f2b82-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="f2b82-266">Es posible que pueda configurar el valor como mínimo como 200.</span><span class="sxs-lookup"><span data-stu-id="f2b82-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="f2b82-267">Si admite clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificaciones de inserción en Office 365, que tienen un valor de tiempo de espera de 900.</span><span class="sxs-lookup"><span data-stu-id="f2b82-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="f2b82-268">Es muy probable que tenga que aumentar el valor de tiempo de espera para evitar desconexiones de cliente cuando el valor es demasiado bajo, o disminuir el número si las conexiones a través del proxy no se desconectan, pero no más tiempo después de que el cliente se haya desconectado.</span><span class="sxs-lookup"><span data-stu-id="f2b82-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="f2b82-269">La supervisión y la determinación de las características habituales de su entorno es la única forma precisa de determinar la configuración adecuada para este valor.</span><span class="sxs-lookup"><span data-stu-id="f2b82-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="f2b82-270">Modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="f2b82-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="f2b82-271">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f2b82-272">Tendrá que ubicar su regla de publicación web y elegir la opción de edición (puede estar en un menú o pestaña, según la configuración del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f2b82-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="f2b82-273">Debe haber un área que indique a qué se aplica esta regla de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="f2b82-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="f2b82-274">Tendrá que modificar la regla para los sitios de entrada o las solicitudes de sitios.</span><span class="sxs-lookup"><span data-stu-id="f2b82-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="f2b82-275">Deberá **agregar** una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="f2b82-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="f2b82-276">Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="f2b82-277">Es probable que cuente con un certificado nuevo que contenga la entrada SAN de detección automática.</span><span class="sxs-lookup"><span data-stu-id="f2b82-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="f2b82-278">Además, debe instalarse y configurarse para su uso según la configuración de su proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="f2b82-279">Asegúrese de guardar todo cuando haya completado la configuración.</span><span class="sxs-lookup"><span data-stu-id="f2b82-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="f2b82-280">Si su proxy inverso tiene una funcionalidad de **prueba** , hágalo para asegurarse de que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="f2b82-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="f2b82-281">Ahora, es posible que tenga que repetir estos pasos si tiene un grupo de directores o directores en su entorno (esto significa que tiene una segunda regla).</span><span class="sxs-lookup"><span data-stu-id="f2b82-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="f2b82-282">Crear una regla de publicación web para la dirección URL externa de detección automática</span><span class="sxs-lookup"><span data-stu-id="f2b82-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="f2b82-283">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f2b82-284">Tendrá que localizar en qué lugar de la interfaz crea las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una pestaña, según la configuración del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f2b82-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="f2b82-285">Debe buscar la opción que le permita crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="f2b82-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="f2b82-286">Generalmente necesitará especificar la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="f2b82-287">**Nombre**: el nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="f2b82-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="f2b82-288">**Acción de regla**: en este caso, se trata de una regla de **permiso** que permite que un objeto pase por el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="f2b82-289">La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="f2b82-290">Tiene que ser **SSL** para acceso interno. Elija esa opción.</span><span class="sxs-lookup"><span data-stu-id="f2b82-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="f2b82-291">Tendrá que publicar una ruta de acceso para la **publicación interna**e introducir el FQDN de los servicios web externos en el equilibrador de carga del grupo de servidores front-end (o el FQDN del equilibrador de carga del grupo de directores, si tiene uno), un ejemplo sería sfb_ pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f2b82-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="f2b82-292">Debe escribir \*\* / \*\*\* como la ruta de acceso que se va a publicar, pero también debe reenviar **el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="f2b82-p131">Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="f2b82-295">**Solicitudes de aceptación**, pero debería ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="f2b82-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="f2b82-296">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="f2b82-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="f2b82-297"><sipdomain>(esta es la dirección URL externa del servicio de detección automática).</span><span class="sxs-lookup"><span data-stu-id="f2b82-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="f2b82-298">Ahora, si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, tendrá que escribir el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f2b82-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="f2b82-299">Habrá una opción de **ruta de acceso** y tendrá que escribir \*\* / \*\*\* aquí.</span><span class="sxs-lookup"><span data-stu-id="f2b82-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="f2b82-300">Tendrá que seleccionar un **agente de escucha SSL** con el certificado público actualizado.</span><span class="sxs-lookup"><span data-stu-id="f2b82-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="f2b82-301">**Delegación de autenticación** debe establecerse en **Sin delegación**, pero **debe** permitirse la autenticación directa de cliente.</span><span class="sxs-lookup"><span data-stu-id="f2b82-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="f2b82-302">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="f2b82-303">Esta es toda la información que puede necesitar para crear esta regla y poder continuar.</span><span class="sxs-lookup"><span data-stu-id="f2b82-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="f2b82-304">Necesitará asegurarse de que se transfiera el **encabezado host original**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="f2b82-305">También será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="f2b82-306">**Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="f2b82-307">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="f2b82-308">Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.</span><span class="sxs-lookup"><span data-stu-id="f2b82-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="f2b82-309">Crear una regla de publicación web para el puerto 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="f2b82-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="f2b82-310">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f2b82-311">Tendrá que localizar en qué lugar de la interfaz crea las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una pestaña, según la configuración del proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f2b82-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="f2b82-312">Debe buscar la opción que le permita crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="f2b82-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="f2b82-313">Generalmente necesitará especificar la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="f2b82-314">**Nombre**: el nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="f2b82-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="f2b82-315">**Acción de regla**: en este caso, se trata de una regla de **permiso** que permite que un objeto pase por el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f2b82-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="f2b82-316">La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="f2b82-317">Tiene que ser una **conexión no segura para conectarse con la granja o el servidor web publicado**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="f2b82-318">Tendrá que publicar una ruta de acceso para la **publicación interna**y especificar el FQDN de la **Dirección VIP** de su equilibrador de carga del grupo de servidores front-end, un ejemplo sería sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f2b82-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="f2b82-319">Debe escribir \*\* / \*\*\* como la ruta de acceso que se va a publicar, pero también debe reenviar **el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="f2b82-p134">Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="f2b82-322">**Solicitudes de aceptación**, pero debería ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="f2b82-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="f2b82-323">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="f2b82-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="f2b82-324"><sipdomain>(esta es la dirección URL externa del servicio de detección automática).</span><span class="sxs-lookup"><span data-stu-id="f2b82-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="f2b82-325">Habrá una opción de **ruta de acceso** y tendrá que escribir \*\* / \*\*\* aquí.</span><span class="sxs-lookup"><span data-stu-id="f2b82-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="f2b82-326">Tendrá que seleccionar una escucha de web o permitir que su proxy inverso cree una.</span><span class="sxs-lookup"><span data-stu-id="f2b82-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="f2b82-327">**Delegación de autenticación** debe establecerse en **Sin delegación**, pero **no debe** permitirse la autenticación directa de cliente.</span><span class="sxs-lookup"><span data-stu-id="f2b82-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="f2b82-328">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="f2b82-329">Esta es toda la información que puede necesitar para crear esta regla y poder continuar.</span><span class="sxs-lookup"><span data-stu-id="f2b82-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="f2b82-330">Será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="f2b82-331">**Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="f2b82-332">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="f2b82-333">Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.</span><span class="sxs-lookup"><span data-stu-id="f2b82-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="f2b82-334">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f2b82-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="f2b82-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b82-335"></span></span>

<span data-ttu-id="f2b82-336">Los entornos híbridos de Skype empresarial Server son entornos que combinan un entorno local y de O365.</span><span class="sxs-lookup"><span data-stu-id="f2b82-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="f2b82-337">Cuando tiene Skype empresarial Server funcionando en un entorno híbrido, el servicio de detección automática debe poder localizar a un usuario de cualquiera de estos entornos.</span><span class="sxs-lookup"><span data-stu-id="f2b82-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="f2b82-p137">Para permitir que los clientes móviles descubran dónde se encuentra un usuario, el servicio Detección automática tiene que configurarse con un nuevo localizador uniforme de recursos (URL). Los pasos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f2b82-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="f2b82-340">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f2b82-341">Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** para su entorno de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f2b82-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="f2b82-342">A continuación, todavía desde la ventana del shell, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f2b82-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="f2b82-343">Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="f2b82-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="f2b82-344">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="f2b82-344">Test your Mobility deployment</span></span>
<span data-ttu-id="f2b82-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b82-345"></span></span>

<span data-ttu-id="f2b82-346">Una vez que haya implementado el servicio de movilidad de Skype empresarial Server y el servicio Detección automática de Skype empresarial Server, querrá ejecutar una transacción de prueba para asegurarse de que el funcionamiento de su implementación es correcto.</span><span class="sxs-lookup"><span data-stu-id="f2b82-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="f2b82-347">Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear una conferencia, unirse a ella y comunicarse dentro.</span><span class="sxs-lookup"><span data-stu-id="f2b82-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="f2b82-348">Necesitará dos usuarios (real o de prueba) y sus credenciales completas para realizar esta prueba.</span><span class="sxs-lookup"><span data-stu-id="f2b82-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="f2b82-349">Este comando funciona tanto para los clientes de Skype empresarial como para los clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2b82-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="f2b82-350">Para los clientes de Lync Server 2010 en Skype empresarial Server 2015, tendrá que ejecutar **Test-CsMcxP2PIM** para realizar la prueba.</span><span class="sxs-lookup"><span data-stu-id="f2b82-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="f2b82-351">Sus usuarios de Lync Server 2010 seguirán teniendo que ser usuarios reales o usuarios de prueba predefinidos y necesitarán sus credenciales de contraseña.</span><span class="sxs-lookup"><span data-stu-id="f2b82-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="f2b82-352">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f2b82-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f2b82-353">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="f2b82-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f2b82-354">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="f2b82-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="f2b82-355">Probar las conferencias para clientes móviles de Lync 2013 y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f2b82-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="f2b82-356">Inicie sesión como miembro del rol de **CsAdministrator** en cualquier equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-357">Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).</span><span class="sxs-lookup"><span data-stu-id="f2b82-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="f2b82-358">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f2b82-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="f2b82-p141">También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="f2b82-361">Probar las conferencias para clientes móviles de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f2b82-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="f2b82-362">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f2b82-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f2b82-363">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="f2b82-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f2b82-364">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="f2b82-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="f2b82-365">Inicie sesión como miembro del rol de **CsAdministrator** en cualquier equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-366">Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).</span><span class="sxs-lookup"><span data-stu-id="f2b82-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="f2b82-367">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f2b82-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="f2b82-p143">También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="f2b82-370">Para revisar en detalle los procedimientos de comando, puede consultar [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) y [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2b82-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="f2b82-371">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f2b82-371">Configure for push notifications</span></span>
<span data-ttu-id="f2b82-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b82-372"></span></span>

<span data-ttu-id="f2b82-373">Las notificaciones de inserción, que tienen la forma de notificaciones, iconos o alertas, pueden enviarse a un dispositivo móvil incluso cuando la aplicación Skype o Lync está inactiva.</span><span class="sxs-lookup"><span data-stu-id="f2b82-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="f2b82-374">Pero, ¿qué son las notificaciones push?</span><span class="sxs-lookup"><span data-stu-id="f2b82-374">But what are push notifications?</span></span> <span data-ttu-id="f2b82-375">Son alertas de eventos, como una invitación de mensajería instantánea perdida o nueva, o un correo de voz recibido.</span><span class="sxs-lookup"><span data-stu-id="f2b82-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="f2b82-376">El servicio de movilidad de Skype empresarial Server envía estas notificaciones al servicio de notificaciones de inserción basado en la nube de Skype empresarial Server, que después envía las notificaciones al servicio de notificaciones push de Microsoft (MSNS) para los usuarios de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="f2b82-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="f2b82-377">Esta funcionalidad no ha sido modificada en Lync Server 2013, pero si tiene un servidor de Skype empresarial, querrá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b82-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="f2b82-378">Para un servidor perimetral de Skype empresarial Server, agregue un nuevo proveedor de hospedaje, Microsoft Skype empresarial online y, a continuación, configure la Federación de proveedores de hospedaje entre su organización y Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="f2b82-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="f2b82-p145">Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="f2b82-381">Pruebe la configuración de federación y las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="f2b82-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="f2b82-382">Configurar el servidor perimetral de Skype Empresarial para notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f2b82-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="f2b82-383">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-384">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f2b82-385">Agregue un proveedor de hospedaje en línea de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f2b82-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="f2b82-386">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2b82-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="f2b82-p146">No puede tener más de una relación de federación con un solo proveedor de host. Es decir, si ya ha configurado un proveedor de host que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de host para él, aunque la identidad del proveedor de host no sea SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="f2b82-389">Configure la Federación de proveedores de hospedaje entre su organización y el servicio de notificaciones de inserción en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="f2b82-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="f2b82-390">En la línea de comando, deberá escribir:</span><span class="sxs-lookup"><span data-stu-id="f2b82-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="f2b82-391">Habilitar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f2b82-391">Enable push notifications</span></span>

1. <span data-ttu-id="f2b82-392">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-393">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f2b82-394">Habilite las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="f2b82-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="f2b82-395">Habilite la federación:</span><span class="sxs-lookup"><span data-stu-id="f2b82-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="f2b82-396">Probar la federación y las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f2b82-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="f2b82-397">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-398">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f2b82-399">Pruebe la configuración de la federación:</span><span class="sxs-lookup"><span data-stu-id="f2b82-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="f2b82-400">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2b82-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="f2b82-401">Pruebe las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="f2b82-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="f2b82-402">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2b82-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="f2b82-403">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="f2b82-403">Configure Mobility policy</span></span>
<span data-ttu-id="f2b82-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b82-404"></span></span>

<span data-ttu-id="f2b82-405">Tiene la capacidad de usar Skype empresarial Server para determinar quién puede usar su servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o video, así como si se necesitará WiFi para VoIP o video.</span><span class="sxs-lookup"><span data-stu-id="f2b82-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="f2b82-406">Vía trabajo permite a un usuario móvil realizar y recibir llamadas con el número de teléfono de su trabajo en lugar de su número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="f2b82-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="f2b82-407">La persona en el otro extremo de la línea no verá el número del teléfono móvil de ese usuario móvil y se evitarán los cargos por llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="f2b82-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="f2b82-408">Cuando se configuran VoIP y vídeo, los usuarios pueden recibir y realizar llamadas de VoIP y vídeo.</span><span class="sxs-lookup"><span data-stu-id="f2b82-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="f2b82-409">La configuración del uso de WiFi define si será necesario que el dispositivo móvil de un usuario use una red WiFi además de una red de datos de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="f2b82-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="f2b82-410">La movilidad, la llamada a través del trabajo y las características de VoIP y vídeo están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f2b82-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="f2b82-411">La configuración para requerir WiFi para VoIP y vídeo está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f2b82-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="f2b82-412">Un administrador tiene la capacidad de cambiar esto, ya sea de forma global, por sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="f2b82-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="f2b82-413">Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben:</span><span class="sxs-lookup"><span data-stu-id="f2b82-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="f2b82-414">Habilitado para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f2b82-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="f2b82-415">estar habilitados para telefonía IP empresarial;</span><span class="sxs-lookup"><span data-stu-id="f2b82-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="f2b82-416">Se le asignó una directiva de movilidad que tiene la opción **EnableMobility** establecida en **true**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="f2b82-417">Para que los usuarios puedan usar Vía trabajo, también deben:</span><span class="sxs-lookup"><span data-stu-id="f2b82-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="f2b82-418">tener asignada una directiva de voz que tenga la opción **Habilitar llamadas simultáneas** seleccionada;</span><span class="sxs-lookup"><span data-stu-id="f2b82-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="f2b82-419">Se le asignó una directiva de movilidad que tiene la **EnableOutsideVoice** establecida en **true**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f2b82-p150">Los usuarios que no están habilitados para la telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP entre usuarios de Skype o pueden unirse a conferencias mediante el uso del vínculo Hacer clic para unirse mientras estén en sus dispositivos móviles, siempre y cuando estén configuradas las opciones apropiadas para la directiva de voz con la que están asociados. En el tema PLANIFICACIÓN encontrará más detalles.</span><span class="sxs-lookup"><span data-stu-id="f2b82-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="f2b82-422">Modificar la directiva de movilidad global</span><span class="sxs-lookup"><span data-stu-id="f2b82-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="f2b82-423">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-424">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f2b82-425">Para desactivar el acceso a la movilidad y las llamadas a través del trabajo, escribe:</span><span class="sxs-lookup"><span data-stu-id="f2b82-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="f2b82-426">Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="f2b82-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="f2b82-427">Pero no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2b82-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="f2b82-428">Para obtener más información, consulta [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2b82-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="f2b82-429">Modificar Directiva de movilidad por sitio</span><span class="sxs-lookup"><span data-stu-id="f2b82-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="f2b82-430">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-431">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f2b82-p152">Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP, y Requerir WiFi para vídeo IP por sitio. Escriba:</span><span class="sxs-lookup"><span data-stu-id="f2b82-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="f2b82-434">Más información en [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2b82-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="f2b82-435">Modificar Directiva de movilidad por usuario</span><span class="sxs-lookup"><span data-stu-id="f2b82-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="f2b82-436">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .</span><span class="sxs-lookup"><span data-stu-id="f2b82-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f2b82-437">Inicie el **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f2b82-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f2b82-438">Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y la llamada a través del trabajo por usuario.</span><span class="sxs-lookup"><span data-stu-id="f2b82-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="f2b82-439">Escriba:</span><span class="sxs-lookup"><span data-stu-id="f2b82-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="f2b82-440">Otro ejemplo con datos de muestra:</span><span class="sxs-lookup"><span data-stu-id="f2b82-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="f2b82-441">Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="f2b82-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="f2b82-442">Pero no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2b82-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

