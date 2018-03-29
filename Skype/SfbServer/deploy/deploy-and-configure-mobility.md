---
title: Implementar y configurar la movilidad para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artículo le guiará por los pasos para configurar un Skype existente para la instalación de Business Server 2015 para utilizar el servicio de movilidad, que permite a los dispositivos móviles poder aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.
ms.openlocfilehash: c23974477ec815fca9c0cd3d78ac7acc0b81912e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server-2015"></a><span data-ttu-id="f21c0-103">Implementar y configurar la movilidad para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="f21c0-103">Deploy and Configure Mobility for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f21c0-104">Este artículo le guiará por los pasos para configurar un Skype existente para la instalación de Business Server 2015 para utilizar el servicio de movilidad, que permite a los dispositivos móviles poder aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f21c0-104">This article will walk you through the steps to configure an existing Skype for Business Server 2015 installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="f21c0-105">Después de reconsiderar el artículo [Plan para la movilidad de Skype para Business Server 2015](../plan-your-deployment/mobility.md) , debería estar listo para continuar con los pasos siguientes para implementar la movilidad en su Skype para entorno Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f21c0-105">Having reviewed the [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server 2015 environment.</span></span> <span data-ttu-id="f21c0-106">Los pasos son los siguientes (e incluimos en esta tabla una lista de permisos):</span><span class="sxs-lookup"><span data-stu-id="f21c0-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="f21c0-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="f21c0-107">**Phase**</span></span>|<span data-ttu-id="f21c0-108">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="f21c0-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f21c0-109">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="f21c0-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="f21c0-110">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="f21c0-110">Domain Admins</span></span>  <br/> <span data-ttu-id="f21c0-111">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="f21c0-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="f21c0-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="f21c0-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="f21c0-113">Administrador local</span><span class="sxs-lookup"><span data-stu-id="f21c0-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="f21c0-114">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f21c0-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="f21c0-115">Administrador local</span><span class="sxs-lookup"><span data-stu-id="f21c0-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="f21c0-116">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f21c0-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="f21c0-117">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="f21c0-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="f21c0-118">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="f21c0-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="f21c0-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f21c0-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="f21c0-120">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f21c0-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="f21c0-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f21c0-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="f21c0-122">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="f21c0-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="f21c0-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f21c0-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="f21c0-p102">Todas las secciones siguientes contienen pasos que dan por sentado que ha leído el tema sobre planificación. Si algo le resulta confuso, consulte la información contenida en dicho tema.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="f21c0-126">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="f21c0-126">Create DNS records</span></span>
<span data-ttu-id="f21c0-127"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="f21c0-127"></span></span>

<span data-ttu-id="f21c0-128">Es posible que tenga como parte de su Skype para entorno Business Server, pero debe crear los siguientes registros de Autodiscovery funcione:</span><span class="sxs-lookup"><span data-stu-id="f21c0-128">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="f21c0-129">Un registro DNS interno para dar soporte a los usuarios móviles que se conectan desde la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="f21c0-129">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="f21c0-130">Un registro DNS externo (o público) para dar soporte a los usuarios móviles que se conectan desde fuera de la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="f21c0-130">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="f21c0-131">Estos registros pueden ser registros CNAME o nombres (de host) A (no tiene que crear ambos; únicamente estamos incluyendo los pasos necesarios para todo aquí).</span><span class="sxs-lookup"><span data-stu-id="f21c0-131">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="f21c0-132">Crear un registro CNAME de DNS interno</span><span class="sxs-lookup"><span data-stu-id="f21c0-132">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="f21c0-133">Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-133">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="f21c0-134">Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.</span><span class="sxs-lookup"><span data-stu-id="f21c0-134">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="f21c0-135">En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que inicio a su Skype para servidores de Business Server frontales y expanda las **Zonas de búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-135">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="f21c0-136">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f21c0-136">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f21c0-137">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="f21c0-137">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f21c0-138">Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f21c0-138">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="f21c0-139">Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Nuevo alias (CNAME)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="f21c0-139">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="f21c0-140">En el cuadro de texto **Nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f21c0-140">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="f21c0-141">En el **nombre de dominio completo (FQDN para host de destino**, debe escribir o buscar el FQDN interno de servicios Web Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificó en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="f21c0-141">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="f21c0-142">Haga clic en Aceptar cuando ya lo haya introducido.</span><span class="sxs-lookup"><span data-stu-id="f21c0-142">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="f21c0-143">Debe crear un nuevo registro de Autodiscover CNAME en la zona de búsqueda directa para cada dominio SIP de su Skype para entorno Business Server admite.</span><span class="sxs-lookup"><span data-stu-id="f21c0-143">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="f21c0-144">Crear un registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="f21c0-144">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="f21c0-145">Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.</span><span class="sxs-lookup"><span data-stu-id="f21c0-145">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="f21c0-146">En este momento, un dominio SIP ya debe existir allí para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f21c0-146">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="f21c0-147">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.</span><span class="sxs-lookup"><span data-stu-id="f21c0-147">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="f21c0-148">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f21c0-148">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f21c0-149">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="f21c0-149">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f21c0-150">Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f21c0-150">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="f21c0-151">Cuando ya tenga esa información, podrá seleccionar una opción para crear un **alias nuevo (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-151">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="f21c0-152">Ahora debería poder introducir un **nombre de alias**. Para ello, tiene que escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f21c0-152">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="f21c0-153">A continuación, debe haber un área para escribir en un **nombre de dominio completo para host de destino**, deberá ser el FQDN para el Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="f21c0-153">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="f21c0-154">Puede que necesite guardar aquí, o si necesita crear más registros CNAME en la zona de búsqueda directa de cada dominio SIP en su Skype para entorno Business Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.</span><span class="sxs-lookup"><span data-stu-id="f21c0-154">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="f21c0-155">Crear un registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="f21c0-155">Create an internal DNS A record</span></span>

1. <span data-ttu-id="f21c0-156">Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-156">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="f21c0-157">Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.</span><span class="sxs-lookup"><span data-stu-id="f21c0-157">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="f21c0-158">En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que inicio a su Skype para servidores de Business Server frontales y expanda las **Zonas de búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-158">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="f21c0-159">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f21c0-159">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f21c0-160">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="f21c0-160">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f21c0-161">Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f21c0-161">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="f21c0-162">Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Host nuevo (A o AAAA)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="f21c0-162">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="f21c0-163">En el cuadro de texto **Nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f21c0-163">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="f21c0-164">En el cuadro de texto **Dirección IP** , escriba la dirección IP de servicios Web interna para el Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="f21c0-164">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="f21c0-165">Una vez hecho esto, haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-165">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="f21c0-166">Debe crear nuevos registros de Autodiscover A o AAAA en la zona de búsqueda directa para cada dominio SIP de su Skype para entorno Business Server admite.</span><span class="sxs-lookup"><span data-stu-id="f21c0-166">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="f21c0-167">Para ello, repita los pasos 6 a 8 tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f21c0-167">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="f21c0-168">Cuando haya terminado, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-168">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="f21c0-169">Crear un registro A de DNS externo</span><span class="sxs-lookup"><span data-stu-id="f21c0-169">Create an external DNS A record</span></span>

1. <span data-ttu-id="f21c0-170">Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.</span><span class="sxs-lookup"><span data-stu-id="f21c0-170">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="f21c0-171">En este momento, un dominio SIP ya debe existir allí para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f21c0-171">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="f21c0-172">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.</span><span class="sxs-lookup"><span data-stu-id="f21c0-172">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="f21c0-173">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="f21c0-173">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="f21c0-174">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="f21c0-174">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="f21c0-175">Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).</span><span class="sxs-lookup"><span data-stu-id="f21c0-175">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="f21c0-176">Cuando ya tenga esa información, podrá seleccionar una opción para crear un **nuevo host A o AAAA**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-176">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="f21c0-177">Ahora debería poder introducir un **nombre**. Para ello, tiene que escribir lyncdiscover para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f21c0-177">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="f21c0-178">A continuación, debe haber un área para escribir en una **Dirección IP**, esto deberá ser la IP Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="f21c0-178">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="f21c0-179">Puede que necesite guardar aquí, o si necesita crear más registros A o AAAA en la zona de búsqueda directa de cada dominio SIP para su Skype para entorno Business Server, debe hacer eso, pero una vez esté listo, guarde el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f21c0-179">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="f21c0-180">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="f21c0-180">Modify certificates</span></span>
<span data-ttu-id="f21c0-181"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="f21c0-181"></span></span>

<span data-ttu-id="f21c0-182">Si tiene preguntas acerca de la planificación alrededor de certificados, nos hemos documentado en nuestro artículo de [Plan para la movilidad de Skype para Business Server 2015](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="f21c0-182">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="f21c0-183">Cuando lo revise, le guiaremos por los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f21c0-183">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="f21c0-184">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="f21c0-184">Do I need new certificates?</span></span>
    
- <span data-ttu-id="f21c0-185">Solicitud de nuevos certificados de su entidad de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="f21c0-185">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="f21c0-186">Actualización de certificados locales con los reemplazos mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f21c0-186">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="f21c0-187">Comprobación de los certificados mediante el complemento certificados en Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="f21c0-187">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="f21c0-188">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="f21c0-188">Do I need new certificates?</span></span>

1. <span data-ttu-id="f21c0-189">Primero, es probable que necesite comprobar qué certificados tiene en local y si tienen las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f21c0-189">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="f21c0-190">Para ello, debe iniciar sesión en tu Skype para Business Server 2015 server con una cuenta que sea un administrador local.</span><span class="sxs-lookup"><span data-stu-id="f21c0-190">To do that, you'll need to log into your Skype for Business Server 2015 server with an account that's a local Administrator.</span></span> <span data-ttu-id="f21c0-191">Para algunos de estos pasos, es posible que esta cuenta necesite tener derechos para la entidad emisora de certificados (CA).</span><span class="sxs-lookup"><span data-stu-id="f21c0-191">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="f21c0-192">Abra el Skype para el Shell de administración de servidor empresarial (puede utilizar Buscar para encontrarlo si no lo tiene anclado a la barra de tarea o del menú Inicio).</span><span class="sxs-lookup"><span data-stu-id="f21c0-192">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="f21c0-p109">Te va a resultar esencial saber qué certificados se han asignado antes de intentar agregar uno actualizado. Por ello, en el comando, escriba:</span><span class="sxs-lookup"><span data-stu-id="f21c0-p109">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="f21c0-p110">La información del paso 3 será exclusiva para usted. Tiene que analizarla para determinar si cuenta con un certificado único asignado a varias cosas o si tiene un certificado distinto asignado a cada uno de los diferentes componentes que lo necesitan. El parámetro **Use** le indicará cómo se ha estado usando un certificado, mientras que el parámetro **Thumbprint** le indicará si se trata del mismo certificado o de varios.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p110">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="f21c0-p111">Si tiene las entradas SAN recomendadas en nuestra sección Planificación, está en el camino correcto. En caso contrario, tendrá que solicitar un certificado nuevo o varios certificados (según su configuración) a la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p111">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="f21c0-200">Solicitar uno o varios certificados nuevos a una entidad de certificación (CA)</span><span class="sxs-lookup"><span data-stu-id="f21c0-200">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="f21c0-201">Después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene un **único certificado** (mediante los pasos anteriores) y sabrá que no tiene todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f21c0-201">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="f21c0-202">En ese caso, se debe solicitar a la CA un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="f21c0-202">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="f21c0-203">Abra su Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f21c0-203">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="f21c0-204">En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f21c0-204">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="f21c0-p113">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. En cambio, tendrá que usar el parámetro DomainName y, en tal caso, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Un ejemplo sería (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f21c0-p113">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="f21c0-209">O bien, después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene **varios certificados** que no tienen todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f21c0-209">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="f21c0-210">Si es así, se debe solicitar a la CA un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="f21c0-210">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="f21c0-211">Abra su Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f21c0-211">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="f21c0-212">En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f21c0-212">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="f21c0-p115">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. En cambio, tendrá que usar el parámetro DomainName y, en tal caso, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Algunos ejemplos serían (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="f21c0-p115">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="f21c0-217">Cuando la CA haya generado los nuevos certificados, tendrá que asignarlos.</span><span class="sxs-lookup"><span data-stu-id="f21c0-217">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f21c0-218">Asignar certificados usando el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f21c0-218">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="f21c0-219">Según qué haya encontrado en la sección anterior relativa a si necesita certificados nuevos, tendrá que ejecutar **uno** de los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="f21c0-219">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="f21c0-220">Si tiene un solo certificado para todo (las huellas digitales son idénticas), tiene que ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-220">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="f21c0-221">Si tiene diferentes certificados (las huellas digitales son todas diferentes), ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-221">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="f21c0-222">Ver certificados en Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="f21c0-222">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="f21c0-p116">Tiene la opción de mirar los certificados con el complemento Certificados para MMC. Solo tiene que escribir MMC en el cuadro de búsqueda y aparecerá como una opción de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p116">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="f21c0-p117">Para agregar el complemento Certificados, debe hacer clic en **Archivo** y después en **Agregar o quitar complemento...** (o el método abreviado de teclado **Ctrl+M** también funcionará). **Certificados** será una de las opciones en el panel izquierdo. Selecciónela y, a continuación, seleccione **Cuenta de equipo** en la ventana emergente y **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p117">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="f21c0-227">En la ventana emergente, con toda probabilidad que hace esto en el equipo que ha el hogar de los certificados debe mirar, así que deje la selección en el **equipo Local** si es así.</span><span class="sxs-lookup"><span data-stu-id="f21c0-227">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="f21c0-228">Si está trabajando en un equipo remoto, cambie el botón de radio a **Otro equipo** y escriba el FQDN del equipo o utilizar el botón **Examinar** para buscar dicho equipo a través de AD.</span><span class="sxs-lookup"><span data-stu-id="f21c0-228">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="f21c0-229">Después de seleccionar el equipo, debe hacer clic en **Finalizar** cuando esté listo y en **Aceptar** para agregar el complemento a la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="f21c0-229">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="f21c0-230">Expanda la sección **certificados** en el panel izquierdo de MMC.</span><span class="sxs-lookup"><span data-stu-id="f21c0-230">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="f21c0-231">Expanda la carpeta **Personal** también y seleccione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-231">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="f21c0-232">Esto le permitirá ver los certificados de esta tienda.</span><span class="sxs-lookup"><span data-stu-id="f21c0-232">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="f21c0-233">Tiene que ubicar el certificado que quiere ver, hacer clic con el botón derecho en él y elegir **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-233">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f21c0-234">¿Cómo puede saber qué certificado es?</span><span class="sxs-lookup"><span data-stu-id="f21c0-234">How do you know what certificate this is?</span></span> <span data-ttu-id="f21c0-235">Debe ser el certificado de único asignado a todos los elementos de su granja, o puede tener varios certificados para cosas diferentes, al igual que de forma predeterminada, los servicios Web internos, etc., en cuyo caso debe mirar varios certificados.</span><span class="sxs-lookup"><span data-stu-id="f21c0-235">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="f21c0-236">Varios certificados tendrán la misma huella digital.</span><span class="sxs-lookup"><span data-stu-id="f21c0-236">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="f21c0-p121">Cuando haya llegado a la vista **Certificado**, elija **Detalles**. Esto le permitirá ver el nombre del firmante del certificado al seleccionar **Sujeto** y se mostrará el nombre del sujeto asignado y sus propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p121">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="f21c0-p122">También necesitará comprobar las entradas de **Nombres alternativos de firmante**. Encontrará uno o varios de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-p122">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="f21c0-241">El nombre del grupo para este grupo, o el nombre de servidor único si este no es un grupo.</span><span class="sxs-lookup"><span data-stu-id="f21c0-241">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="f21c0-242">Nombre del servidor al que está asignado el certificado.</span><span class="sxs-lookup"><span data-stu-id="f21c0-242">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="f21c0-243">Registros de direcciones URL simples, normalmente de reunión y marcación.</span><span class="sxs-lookup"><span data-stu-id="f21c0-243">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="f21c0-244">Servicios Web internos y los servicios Web externos los nombres (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), basados en las elecciones realizadas en el generador de topología y las selecciones de servicios Web reemplazadas.</span><span class="sxs-lookup"><span data-stu-id="f21c0-244">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="f21c0-245">Si ya ha asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="f21c0-245">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="f21c0-246">Necesitará comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="f21c0-246">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="f21c0-247">Por lo tanto, si se encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ha elegido ya configurado.</span><span class="sxs-lookup"><span data-stu-id="f21c0-247">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="f21c0-248">Puede cerrar MMC.</span><span class="sxs-lookup"><span data-stu-id="f21c0-248">You can close the MMC.</span></span>
    
9. <span data-ttu-id="f21c0-249">Si no están asignados, tendrá que realizar una nueva solicitud de certificado (como se detalla anteriormente) o deberá instalarlos después de la solicitud (para ello recomendamos seguir los pasos para Powershell detallados anteriormente).</span><span class="sxs-lookup"><span data-stu-id="f21c0-249">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="f21c0-250">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f21c0-250">Configure the reverse proxy</span></span>
<span data-ttu-id="f21c0-251"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="f21c0-251"></span></span>

<span data-ttu-id="f21c0-p124">No es necesario seguir al pie de la letra los pasos que se explican a continuación. En las versiones anteriores del producto, le hemos guiado, por ejemplo, en el proceso de configuración de Threat Management Gateway (TMG) y, si no lo estaba utilizando, tenía que encontrar la forma de adaptarlo a su propia versión a partir de la información con la que contaba.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p124">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="f21c0-254">TMG ya no se ofrece por Microsoft como un producto y, si aún necesita configurarlo, puede mirar los [pasos de Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f21c0-254">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="f21c0-255">Pero la siguiente información ha sido diseñada ser generalmente más útil, incluso si no hay ninguna manera podemos proporcionar los pasos del tutorial específico para cada proxy inverso por ahí.</span><span class="sxs-lookup"><span data-stu-id="f21c0-255">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="f21c0-256">Debemos considerar dos aspectos:</span><span class="sxs-lookup"><span data-stu-id="f21c0-256">We have two main things to consider:</span></span>
  
- <span data-ttu-id="f21c0-257">¿Hará su solicitud de detección automática inicial a través de HTTPS (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="f21c0-257">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="f21c0-258">Si tiene una regla de publicación web, debe modificarla.</span><span class="sxs-lookup"><span data-stu-id="f21c0-258">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="f21c0-259">Si no tiene una regla de publicación web todavía, debe crearla.</span><span class="sxs-lookup"><span data-stu-id="f21c0-259">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="f21c0-260">Si está realizando una solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.</span><span class="sxs-lookup"><span data-stu-id="f21c0-260">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f21c0-261">**Importante** Un valor de tiempo de espera de servidor Proxy es un número que puede variar de una implementación a otra.</span><span class="sxs-lookup"><span data-stu-id="f21c0-261">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="f21c0-262">Debe supervisar la implementación y modifique el valor de la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="f21c0-262">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="f21c0-263">Puede establecer un valor tan bajo como 200.</span><span class="sxs-lookup"><span data-stu-id="f21c0-263">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="f21c0-264">Si admite a clientes móviles Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificación de inserción de Office 365, que tienen un valor de tiempo de espera de 900.</span><span class="sxs-lookup"><span data-stu-id="f21c0-264">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="f21c0-265">Es muy probable que tendrá que aumentar el valor de tiempo de espera para evitar el cliente se desconecta cuando el valor es demasiado bajo, o reducir el número, si las conexiones a través del proxy no desconecten pero desactive mucho después de que el cliente se desconectó.</span><span class="sxs-lookup"><span data-stu-id="f21c0-265">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="f21c0-266">Supervisión y nivel de referencia lo habitual en su entorno es la única forma precisa para determinar la configuración adecuada para este valor.</span><span class="sxs-lookup"><span data-stu-id="f21c0-266">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="f21c0-267">Modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="f21c0-267">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="f21c0-268">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f21c0-268">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f21c0-269">Debe encontrar la regla de publicación web y elegir la opción Editar (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f21c0-269">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="f21c0-270">Debe haber un área que indica lo que se aplica esta regla de publicación de web para.</span><span class="sxs-lookup"><span data-stu-id="f21c0-270">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="f21c0-271">Tendrá que modificar la regla para los sitios de entrada o las solicitudes de sitios.</span><span class="sxs-lookup"><span data-stu-id="f21c0-271">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="f21c0-272">Deberá **agregar** una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="f21c0-272">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="f21c0-273">Escriba el nombre de su sitio de detección automática (en el ejemplo que utilizaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato del servidor de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f21c0-273">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="f21c0-274">Es probable que cuente con un certificado nuevo que contenga la entrada SAN de detección automática.</span><span class="sxs-lookup"><span data-stu-id="f21c0-274">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="f21c0-275">Que debe ser también instalado y configurado para su uso según la configuración del servidor de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f21c0-275">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="f21c0-276">Asegúrese de guardar todo cuando haya completado la configuración.</span><span class="sxs-lookup"><span data-stu-id="f21c0-276">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="f21c0-277">Si el proxy inverso tiene una funcionalidad de **prueba** , por favor haga uso de él, para garantizar que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="f21c0-277">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="f21c0-278">Ahora, puede que necesite repetir estos pasos si tiene un Director o Director de grupo en su entorno (Esto significaría tener una segunda regla).</span><span class="sxs-lookup"><span data-stu-id="f21c0-278">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="f21c0-279">Crear una regla de publicación de web para la dirección URL de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="f21c0-279">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="f21c0-280">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f21c0-280">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f21c0-281">Debe localizar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f21c0-281">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="f21c0-282">Debe buscar la opción que le permita crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="f21c0-282">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="f21c0-283">Generalmente necesitará especificar la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-283">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="f21c0-284">**Nombre**: el nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="f21c0-284">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="f21c0-285">**La acción de regla**: en este caso es una regla de **permiso** , algo permite que pase a través de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f21c0-285">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="f21c0-286">La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-286">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="f21c0-287">Tiene que ser **SSL** para acceso interno. Elija esa opción.</span><span class="sxs-lookup"><span data-stu-id="f21c0-287">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="f21c0-288">Va a necesitar una ruta de publicación para **Publicación en interno**y escriba el FQDN para los servicios Web externos de equilibrador de carga de la agrupación de Front-End (o el FQDN del equilibrador de carga del grupo Director si tiene uno), un ejemplo sería sfb_ pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="f21c0-288">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="f21c0-289">Debe escribir ** / ** como la ruta de acceso que se publiquen, pero también debe **enviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-289">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="f21c0-p130">Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-p130">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="f21c0-292">**Solicitudes de aceptación**, pero debería ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="f21c0-292">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="f21c0-293">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="f21c0-293">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="f21c0-294"><sipdomain>(ésta es la dirección URL del servicio Detección automática externos).</span><span class="sxs-lookup"><span data-stu-id="f21c0-294"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="f21c0-295">Ahora, si está creando una regla para la URL de servicios Web externos en el grupo de servidores Front-End, debe escribir el nombre completo de los servicios Web externos en el grupo de servidores Front-End (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f21c0-295">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="f21c0-296">Habrá una opción de **ruta de acceso** y tendrá que escribir ** / ** aquí.</span><span class="sxs-lookup"><span data-stu-id="f21c0-296">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="f21c0-297">Tendrá que seleccionar un **agente de escucha SSL** con el certificado público actualizado.</span><span class="sxs-lookup"><span data-stu-id="f21c0-297">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="f21c0-298">**Delegación de autenticación** debe establecerse en **Sin delegación**, pero **debe** permitirse la autenticación directa de cliente.</span><span class="sxs-lookup"><span data-stu-id="f21c0-298">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="f21c0-299">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-299">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="f21c0-300">Esta es toda la información que puede necesitar para crear esta regla y poder continuar.</span><span class="sxs-lookup"><span data-stu-id="f21c0-300">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="f21c0-301">Necesitará asegurarse de que se transfiera el **encabezado host original**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-301">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="f21c0-302">También será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-302">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="f21c0-303">**Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-303">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="f21c0-304">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-304">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="f21c0-305">Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.</span><span class="sxs-lookup"><span data-stu-id="f21c0-305">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="f21c0-306">Crear una regla de publicación web para el puerto 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="f21c0-306">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="f21c0-307">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f21c0-307">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="f21c0-308">Debe localizar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="f21c0-308">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="f21c0-309">Debe buscar la opción que le permita crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="f21c0-309">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="f21c0-310">Generalmente necesitará especificar la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-310">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="f21c0-311">**Nombre**: el nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="f21c0-311">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="f21c0-312">**La acción de regla**: en este caso es una regla de **permiso** , algo permite que pase a través de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f21c0-312">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="f21c0-313">La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-313">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="f21c0-314">Tiene que ser una **conexión no segura para conectarse con la granja o el servidor web publicado**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-314">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="f21c0-315">Va a necesitar una ruta de publicación para **Publicación en interno**y escriba el FQDN de la **dirección VIP** del equilibrador de carga de la agrupación de Front-End, un ejemplo sería sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="f21c0-315">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="f21c0-316">Debe escribir ** / ** como la ruta de acceso que se publiquen, pero también debe **enviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-316">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="f21c0-p133">Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-p133">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="f21c0-319">**Solicitudes de aceptación**, pero debería ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="f21c0-319">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="f21c0-320">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="f21c0-320">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="f21c0-321"><sipdomain>(ésta es la dirección URL del servicio Detección automática externos).</span><span class="sxs-lookup"><span data-stu-id="f21c0-321"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="f21c0-322">Habrá una opción de **ruta de acceso** y tendrá que escribir ** / ** aquí.</span><span class="sxs-lookup"><span data-stu-id="f21c0-322">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="f21c0-323">Debe seleccionar un agente de escucha de web, o permitir que el proxy inverso crear uno.</span><span class="sxs-lookup"><span data-stu-id="f21c0-323">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="f21c0-324">**Delegación de autenticación** debe establecerse en **Sin delegación**, pero **no debe** permitirse la autenticación directa de cliente.</span><span class="sxs-lookup"><span data-stu-id="f21c0-324">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="f21c0-325">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-325">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="f21c0-326">Esta es toda la información que puede necesitar para crear esta regla y poder continuar.</span><span class="sxs-lookup"><span data-stu-id="f21c0-326">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="f21c0-327">Será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-327">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="f21c0-328">**Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-328">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="f21c0-329">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-329">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="f21c0-330">Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.</span><span class="sxs-lookup"><span data-stu-id="f21c0-330">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="f21c0-331">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f21c0-331">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="f21c0-332"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="f21c0-332"></span></span>

<span data-ttu-id="f21c0-333">Entornos híbridos en Skype para Business Server 2015 son entornos que combinen una local y entorno de O365.</span><span class="sxs-lookup"><span data-stu-id="f21c0-333">Hybrid environments in Skype for Business Server 2015 are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="f21c0-334">Cuando tenga Skype para trabajar en un entorno híbrido de Business Server, el servicio Detección automática debe poder localizar a un usuario de cualquiera de estos entornos.</span><span class="sxs-lookup"><span data-stu-id="f21c0-334">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="f21c0-p136">Para permitir que los clientes móviles descubran dónde se encuentra un usuario, el servicio Detección automática tiene que configurarse con un nuevo localizador uniforme de recursos (URL). Los pasos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f21c0-p136">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="f21c0-337">Abre Skype para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f21c0-337">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f21c0-338">Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** de su Skype para entorno Business Server:</span><span class="sxs-lookup"><span data-stu-id="f21c0-338">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
  ```
  Get-CsHostingProvider
  ```

3. <span data-ttu-id="f21c0-339">A continuación, todavía desde la ventana del shell, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f21c0-339">Then, still in the shell window, run:</span></span>
    
  ```
  Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
  ```

    <span data-ttu-id="f21c0-340">Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="f21c0-340">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="f21c0-341">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="f21c0-341">Test your Mobility deployment</span></span>
<span data-ttu-id="f21c0-342"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="f21c0-342"></span></span>

<span data-ttu-id="f21c0-343">Una vez que haya implementado Skype para servicio de movilidad Business Server y Skype para el servicio de detección automática del servidor de negocios, desea ejecutar una transacción de prueba, para asegurarse de que trabajo de la implementación es correcta.</span><span class="sxs-lookup"><span data-stu-id="f21c0-343">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="f21c0-344">Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear una conferencia, unirse a ella y comunicarse dentro.</span><span class="sxs-lookup"><span data-stu-id="f21c0-344">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="f21c0-345">Necesitará dos usuarios (real o de prueba) y sus credenciales completas para realizar esta prueba.</span><span class="sxs-lookup"><span data-stu-id="f21c0-345">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="f21c0-346">Este comando funcionará para ambos Skype para clientes empresariales, así como los clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f21c0-346">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="f21c0-347">Para los clientes de Lync Server 2010, debe ejecutar **CsMcxP2PIM de prueba** para probar.</span><span class="sxs-lookup"><span data-stu-id="f21c0-347">For Lync Server 2010 clients, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="f21c0-348">Los usuarios de Lync Server 2010 todavía tendrá que ser usuarios reales, o los usuarios de prueba predefinidas y tendrá sus credenciales de contraseña.</span><span class="sxs-lookup"><span data-stu-id="f21c0-348">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="f21c0-349">Probar las conferencias para clientes móviles de Lync 2013 y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f21c0-349">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="f21c0-350">Inicie sesión como un miembro de la función **CsAdministrator** en cualquier equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-350">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-351">Iniciar **Skype para el Shell de administración de servidor de negocio** (que podría escribir el nombre en la búsqueda o vaya a **Todos los programas** y elige).</span><span class="sxs-lookup"><span data-stu-id="f21c0-351">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="f21c0-352">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f21c0-352">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="f21c0-p139">También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p139">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="f21c0-355">Probar las conferencias para clientes móviles de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f21c0-355">Test conferencing for Lync 2010 mobile clients</span></span>

1. <span data-ttu-id="f21c0-356">Inicie sesión como un miembro de la función **CsAdministrator** en cualquier equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-357">Iniciar **Skype para el Shell de administración de servidor de negocio** (que podría escribir el nombre en la búsqueda o vaya a **Todos los programas** y elige).</span><span class="sxs-lookup"><span data-stu-id="f21c0-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="f21c0-358">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f21c0-358">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="f21c0-p140">También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p140">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
  ```
  $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
  $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
  $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
  $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
  Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
  ```

<span data-ttu-id="f21c0-361">Para revisar los procedimientos de comando aún más, puede desproteger [Prueba CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) y [CsMcxP2PIM de prueba](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f21c0-361">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="f21c0-362">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f21c0-362">Configure for push notifications</span></span>
<span data-ttu-id="f21c0-363"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="f21c0-363"></span></span>

<span data-ttu-id="f21c0-364">Las notificaciones de inserción, que tienen la forma de notificaciones, iconos o alertas, pueden enviarse a un dispositivo móvil incluso cuando la aplicación Skype o Lync está inactiva.</span><span class="sxs-lookup"><span data-stu-id="f21c0-364">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="f21c0-365">¿En qué consisten las notificaciones de inserción?</span><span class="sxs-lookup"><span data-stu-id="f21c0-365">But what are pusn notifications?</span></span> <span data-ttu-id="f21c0-366">Son alertas de eventos, como una invitación de mensajería instantánea perdida o nueva, o un correo de voz recibido.</span><span class="sxs-lookup"><span data-stu-id="f21c0-366">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="f21c0-367">El Skype para servicio Business Server 2015 movilidad envía esas notificaciones al Skype en la nube para Business Server Push servicio de notificación, que envía las notificaciones a Microsoft Push Notification Service (MSNS) para los usuarios de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="f21c0-367">The Skype for Business Server 2015 Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="f21c0-368">Esta funcionalidad se ha modificado desde Lync Server 2013, pero si tienes un Skype para Business Server, deberá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f21c0-368">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="f21c0-369">Para un Skype para Business Server 2015 Edge Server, agregar un nuevo proveedor de hospedaje, Microsoft Skype para los negocios en línea y configure la federación de proveedor entre la organización y Skype para los negocios en línea de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="f21c0-369">For a Skype for Business Server 2015 Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="f21c0-p142">Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p142">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="f21c0-372">Pruebe la configuración de federación y las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="f21c0-372">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="f21c0-373">Configurar el servidor perimetral de Skype Empresarial para notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f21c0-373">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="f21c0-374">Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-374">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-375">Iniciar el **Skype para el Shell de administración de servidor de empresa**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-375">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f21c0-376">Agregue un Skype para el proveedor de hospedaje en línea Business Server.</span><span class="sxs-lookup"><span data-stu-id="f21c0-376">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="f21c0-377">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f21c0-377">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="f21c0-p143">No puede tener más de una relación de federación con un solo proveedor de host. Es decir, si ya ha configurado un proveedor de host que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de host para él, aunque la identidad del proveedor de host no sea SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p143">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="f21c0-380">Configurar la federación proveedor hospedaje entre la organización y el servicio de notificación Push en Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="f21c0-380">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="f21c0-381">En la línea de comando, deberá escribir:</span><span class="sxs-lookup"><span data-stu-id="f21c0-381">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="f21c0-382">Habilitar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f21c0-382">Enable push notifications</span></span>

1. <span data-ttu-id="f21c0-383">Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-384">Iniciar el **Skype para el Shell de administración de servidor de empresa**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f21c0-385">Habilite las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="f21c0-385">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="f21c0-386">Habilite la federación:</span><span class="sxs-lookup"><span data-stu-id="f21c0-386">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="f21c0-387">Probar la federación y las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="f21c0-387">Test federation and push notifications</span></span>

1. <span data-ttu-id="f21c0-388">Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-388">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-389">Iniciar el **Skype para el Shell de administración de servidor de empresa**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-389">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f21c0-390">Pruebe la configuración de la federación:</span><span class="sxs-lookup"><span data-stu-id="f21c0-390">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="f21c0-391">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f21c0-391">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="f21c0-392">Pruebe las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="f21c0-392">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="f21c0-393">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f21c0-393">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="f21c0-394">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="f21c0-394">Configure Mobility policy</span></span>
<span data-ttu-id="f21c0-395"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="f21c0-395"></span></span>

<span data-ttu-id="f21c0-396">Tiene la posibilidad de con Skype para Business Server 2015 determinar quién puede usar el servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o de vídeo, así como si va a ser necesario para VoIP o vídeo WiFi.</span><span class="sxs-lookup"><span data-stu-id="f21c0-396">You have the ability with Skype for Business Server 2015 to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="f21c0-397">Vía trabajo permite a un usuario móvil realizar y recibir llamadas con el número de teléfono de su trabajo en lugar de su número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="f21c0-397">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="f21c0-398">La persona en el otro extremo de la línea no verá el número del teléfono móvil de ese usuario móvil y se evitarán los cargos por llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="f21c0-398">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="f21c0-399">Cuando se configuran VoIP y vídeo, los usuarios pueden recibir y realizar llamadas de VoIP y vídeo.</span><span class="sxs-lookup"><span data-stu-id="f21c0-399">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="f21c0-400">La configuración del uso de WiFi define si será necesario que el dispositivo móvil de un usuario use una red WiFi además de una red de datos de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="f21c0-400">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="f21c0-401">Movilidad, llamada a través del trabajo y el VoIP y funciones de vídeo están habilitados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f21c0-401">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="f21c0-402">La opción de requerir WiFi para VoIP y vídeo están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="f21c0-402">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="f21c0-403">Un administrador tiene la capacidad para cambiar esto, globalmente, por sitio, o por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f21c0-403">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="f21c0-404">Para poder utilizar las características de movilidad y llamada a través del trabajo, los usuarios deben:</span><span class="sxs-lookup"><span data-stu-id="f21c0-404">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="f21c0-405">Habilitado para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f21c0-405">Enabled for Skype for Business Server 2015</span></span>
    
- <span data-ttu-id="f21c0-406">estar habilitados para telefonía IP empresarial;</span><span class="sxs-lookup"><span data-stu-id="f21c0-406">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="f21c0-407">Asignar una directiva de movilidad que tiene la opción de **EnableMobility** establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-407">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="f21c0-408">Para que los usuarios puedan usar Vía trabajo, también deben:</span><span class="sxs-lookup"><span data-stu-id="f21c0-408">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="f21c0-409">tener asignada una directiva de voz que tenga la opción **Habilitar llamadas simultáneas** seleccionada;</span><span class="sxs-lookup"><span data-stu-id="f21c0-409">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="f21c0-410">Asignar una directiva de movilidad que tiene la **EnableOutsideVoice** establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-410">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f21c0-p147">Los usuarios que no están habilitados para la telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP entre usuarios de Skype o pueden unirse a conferencias mediante el uso del vínculo Hacer clic para unirse mientras estén en sus dispositivos móviles, siempre y cuando estén configuradas las opciones apropiadas para la directiva de voz con la que están asociados. En el tema PLANIFICACIÓN encontrará más detalles.</span><span class="sxs-lookup"><span data-stu-id="f21c0-p147">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="f21c0-413">Modificar la directiva de movilidad global</span><span class="sxs-lookup"><span data-stu-id="f21c0-413">Modify global Mobility policy</span></span>

1. <span data-ttu-id="f21c0-414">Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-414">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-415">Iniciar el **Skype para el Shell de administración de servidor de empresa**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-415">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f21c0-416">Desactivar el acceso a la movilidad y la llamada a través de trabajo globalmente escribiendo:</span><span class="sxs-lookup"><span data-stu-id="f21c0-416">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="f21c0-417">Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="f21c0-417">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="f21c0-418">Pero no puede desactivar movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f21c0-418">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="f21c0-419">Para obtener más información, consulte [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f21c0-419">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="f21c0-420">Modificar la directiva de movilidad por sitio</span><span class="sxs-lookup"><span data-stu-id="f21c0-420">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="f21c0-421">Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-421">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-422">Iniciar el **Skype para el Shell de administración de servidor de empresa**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-422">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f21c0-p149">Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP, y Requerir WiFi para vídeo IP por sitio. Escriba:</span><span class="sxs-lookup"><span data-stu-id="f21c0-p149">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="f21c0-425">Obtenga más información en [CsMobilityPolicy de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f21c0-425">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="f21c0-426">Modificar la directiva de movilidad por usuario</span><span class="sxs-lookup"><span data-stu-id="f21c0-426">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="f21c0-427">Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="f21c0-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="f21c0-428">Iniciar el **Skype para el Shell de administración de servidor de empresa**.</span><span class="sxs-lookup"><span data-stu-id="f21c0-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f21c0-429">Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y la llamada a través de trabajo por usuario.</span><span class="sxs-lookup"><span data-stu-id="f21c0-429">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="f21c0-430">Escriba:</span><span class="sxs-lookup"><span data-stu-id="f21c0-430">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="f21c0-431">Otro ejemplo con datos de muestra:</span><span class="sxs-lookup"><span data-stu-id="f21c0-431">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="f21c0-432">Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="f21c0-432">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="f21c0-433">Pero no puede desactivar movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f21c0-433">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

