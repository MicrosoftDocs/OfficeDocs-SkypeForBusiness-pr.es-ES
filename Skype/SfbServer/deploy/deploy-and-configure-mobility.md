---
title: Implementación y configuración de movilidad de Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: En este artículo le guiará a través de los pasos para configurar un Skype existente para la instalación de Business Server para usar el servicio de movilidad, lo que permite a los dispositivos móviles que puedan aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.
ms.openlocfilehash: c9203bb90f4d4659819a4336c21f08e58785dfde
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233264"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="bfd6a-103">Implementación y configuración de movilidad de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="bfd6a-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="bfd6a-104">En este artículo le guiará a través de los pasos para configurar un Skype existente para la instalación de Business Server para usar el servicio de movilidad, lo que permite a los dispositivos móviles que puedan aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="bfd6a-105">Después de reconsiderar el artículo [planeación de movilidad de Skype para Business Server](../plan-your-deployment/mobility.md) , deberá estar preparado para continuar con los pasos siguientes para implementar la movilidad en su Skype para el entorno de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="bfd6a-106">Los pasos son los siguientes (e incluimos en esta tabla una lista de permisos):</span><span class="sxs-lookup"><span data-stu-id="bfd6a-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="bfd6a-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="bfd6a-107">**Phase**</span></span>|<span data-ttu-id="bfd6a-108">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="bfd6a-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="bfd6a-109">Crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="bfd6a-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="bfd6a-110">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="bfd6a-110">Domain Admins</span></span>  <br/> <span data-ttu-id="bfd6a-111">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="bfd6a-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="bfd6a-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="bfd6a-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="bfd6a-113">Administrador local</span><span class="sxs-lookup"><span data-stu-id="bfd6a-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="bfd6a-114">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="bfd6a-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="bfd6a-115">Administrador local</span><span class="sxs-lookup"><span data-stu-id="bfd6a-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="bfd6a-116">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="bfd6a-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="bfd6a-117">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="bfd6a-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="bfd6a-118">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="bfd6a-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="bfd6a-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bfd6a-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="bfd6a-120">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="bfd6a-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="bfd6a-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bfd6a-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="bfd6a-122">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="bfd6a-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="bfd6a-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bfd6a-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="bfd6a-p102">Todas las secciones siguientes contienen pasos que dan por sentado que ha leído el tema sobre planificación. Si algo le resulta confuso, consulte la información contenida en dicho tema.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="bfd6a-126">Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="bfd6a-127">Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="bfd6a-128">Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="bfd6a-129">Crear registros de DNS</span><span class="sxs-lookup"><span data-stu-id="bfd6a-129">Create DNS records</span></span>
<span data-ttu-id="bfd6a-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd6a-130"></span></span>

<span data-ttu-id="bfd6a-131">Es posible que ya tiene estos como parte de su Skype para el entorno de servidor empresarial, pero es necesario crear los siguientes registros para la detección automática para que funcione:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="bfd6a-132">Un registro DNS interno para dar soporte a los usuarios móviles que se conectan desde la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="bfd6a-133">Un registro DNS externo (o público) para dar soporte a los usuarios móviles que se conectan desde fuera de la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="bfd6a-134">Estos registros pueden ser registros CNAME o nombres (de host) A (no tiene que crear ambos; únicamente estamos incluyendo los pasos necesarios para todo aquí).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="bfd6a-135">Crear un registro CNAME de DNS interno</span><span class="sxs-lookup"><span data-stu-id="bfd6a-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="bfd6a-136">Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="bfd6a-137">Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="bfd6a-138">En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que principal a su Skype para servidores de Front-End del servidor empresarial y expanda las **Zonas de búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="bfd6a-139">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="bfd6a-140">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="bfd6a-141">Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="bfd6a-142">Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Nuevo alias (CNAME)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="bfd6a-143">En el cuadro de texto **Nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="bfd6a-144">En el **nombre de dominio completo (FQDN para el host de destino**, que necesitará para escriba o busque el FQDN de servicios Web internos para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="bfd6a-145">Haga clic en Aceptar cuando ya lo haya introducido.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="bfd6a-146">Debe crear un nuevo registro CNAME de Autodiscover en la zona de búsqueda directa para cada dominio SIP compatibles con su Skype para el entorno de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="bfd6a-147">Crear un registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="bfd6a-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="bfd6a-148">Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="bfd6a-149">En este momento, un dominio SIP ya debe existir existe para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="bfd6a-150">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="bfd6a-151">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="bfd6a-152">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="bfd6a-153">Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="bfd6a-154">Cuando ya tenga esa información, podrá seleccionar una opción para crear un **alias nuevo (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="bfd6a-155">Ahora debería poder introducir un **nombre de alias**. Para ello, tiene que escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="bfd6a-156">A continuación, debería haber un área para escribir en un **nombre de dominio completo para el host de destino**, deberá ser el FQDN para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="bfd6a-157">Es posible que necesite guardar aquí, o si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en su Skype para entorno Business Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="bfd6a-158">Crear un registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="bfd6a-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="bfd6a-159">Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="bfd6a-160">Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="bfd6a-161">En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que principal a su Skype para servidores de Front-End del servidor empresarial y expanda las **Zonas de búsqueda directa** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="bfd6a-162">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="bfd6a-163">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="bfd6a-164">Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="bfd6a-165">Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Host nuevo (A o AAAA)** en el menú.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="bfd6a-166">En el cuadro de texto **Nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="bfd6a-167">En el cuadro de texto **Dirección IP** , escriba la dirección IP de servicios Web interna para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="bfd6a-168">Una vez hecho esto, haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="bfd6a-169">Debe crear un nuevo registros de Autodiscover A o AAAA en la zona de búsqueda directa para cada dominio SIP compatibles con su Skype para el entorno de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="bfd6a-170">Para ello, repita los pasos 6 a 8 tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="bfd6a-171">Cuando haya terminado, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="bfd6a-172">Crear un registro A de DNS externo</span><span class="sxs-lookup"><span data-stu-id="bfd6a-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="bfd6a-173">Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="bfd6a-174">En este momento, un dominio SIP ya debe existir existe para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="bfd6a-175">Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="bfd6a-176">Dedique un momento a ver cuáles de los siguientes registros tiene:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="bfd6a-177">Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="bfd6a-178">Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="bfd6a-179">Cuando ya tenga esa información, podrá seleccionar una opción para crear un **nuevo host A o AAAA**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="bfd6a-180">Ahora debería poder introducir un **nombre**. Para ello, tiene que escribir lyncdiscover para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="bfd6a-181">A continuación, debería haber un área para escribir en una **Dirección IP**, esto deberá ser la dirección IP para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="bfd6a-182">Es posible que necesite guardar aquí, o si necesita crear más registros A o AAAA en la zona de búsqueda directa de cada dominio SIP para su Skype para el entorno de servidor empresarial, debe hacer, pero una vez esté listo, guarde el trabajo.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="bfd6a-183">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="bfd6a-183">Modify certificates</span></span>
<span data-ttu-id="bfd6a-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd6a-184"></span></span>

<span data-ttu-id="bfd6a-185">Si tiene alguna pregunta sobre la planeación alrededor de certificados, nos hemos documentado en nuestro artículo de [planeación de movilidad de Skype para Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="bfd6a-186">Cuando lo revise, le guiaremos por los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="bfd6a-187">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="bfd6a-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="bfd6a-188">Solicitud de nuevos certificados de su entidad de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="bfd6a-189">Actualización de certificados locales con los reemplazos mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="bfd6a-190">Comprobación de los certificados mediante el complemento de certificados en Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="bfd6a-191">¿Necesito certificados nuevos?</span><span class="sxs-lookup"><span data-stu-id="bfd6a-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="bfd6a-192">Primero, es probable que necesite comprobar qué certificados tiene en local y si tienen las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="bfd6a-193">Para ello, debe iniciar sesión en su Skype para Business Server con una cuenta que sea un administrador local.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="bfd6a-194">Para algunos de estos pasos, es posible que esta cuenta necesite tener derechos para la entidad emisora de certificados (CA).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="bfd6a-195">Abra el Skype para Shell de administración de servidor empresarial (puede usar búsqueda buscarla si no lo tiene anclados a la barra de tareas o el menú de inicio).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="bfd6a-p110">Te va a resultar esencial saber qué certificados se han asignado antes de intentar agregar uno actualizado. Por ello, en el comando, escriba:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="bfd6a-p111">La información del paso 3 será exclusiva para usted. Tiene que analizarla para determinar si cuenta con un certificado único asignado a varias cosas o si tiene un certificado distinto asignado a cada uno de los diferentes componentes que lo necesitan. El parámetro **Use** le indicará cómo se ha estado usando un certificado, mientras que el parámetro **Thumbprint** le indicará si se trata del mismo certificado o de varios.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="bfd6a-p112">Si tiene las entradas SAN recomendadas en nuestra sección Planificación, está en el camino correcto. En caso contrario, tendrá que solicitar un certificado nuevo o varios certificados (según su configuración) a la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="bfd6a-203">Solicitar uno o varios certificados nuevos a una entidad de certificación (CA)</span><span class="sxs-lookup"><span data-stu-id="bfd6a-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="bfd6a-204">Después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene un **único certificado** (mediante los pasos anteriores) y sabrá que no tiene todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="bfd6a-205">En ese caso, se debe solicitar a la CA un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="bfd6a-206">Abra su Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="bfd6a-207">En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="bfd6a-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="bfd6a-208">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="bfd6a-209">Debe usar el parámetro DomainName en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="bfd6a-210">Y cuando se utiliza el parámetro DomainName, tiene que definir el FQDN de los registros de lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="bfd6a-211">Un ejemplo sería (reemplazando el parámetro -Ca con su propia ruta de acceso de la entidad emisora de certificados):</span><span class="sxs-lookup"><span data-stu-id="bfd6a-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="bfd6a-212">O bien, después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene **varios certificados** que no tienen todas las entradas que necesita.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="bfd6a-213">Si es así, se debe solicitar a la CA un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="bfd6a-214">Abra su Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="bfd6a-215">En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):</span><span class="sxs-lookup"><span data-stu-id="bfd6a-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="bfd6a-216">Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="bfd6a-217">Debe usar el parámetro DomainName en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="bfd6a-218">Y cuando se utiliza el parámetro DomainName, tiene que definir el FQDN de los registros de lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="bfd6a-219">Algunos ejemplos serían (reemplazando el parámetro -Ca con su propia ruta de acceso de la entidad emisora de certificados):</span><span class="sxs-lookup"><span data-stu-id="bfd6a-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="bfd6a-220">Cuando la CA haya generado los nuevos certificados, tendrá que asignarlos.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bfd6a-221">Asignar certificados usando el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bfd6a-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="bfd6a-222">Según qué haya encontrado en la sección anterior relativa a si necesita certificados nuevos, tendrá que ejecutar **uno** de los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="bfd6a-223">Si tiene un solo certificado para todo (las huellas digitales son idénticas), tiene que ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="bfd6a-224">Si tiene diferentes certificados (las huellas digitales son todas diferentes), ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="bfd6a-225">Ver certificados en Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="bfd6a-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="bfd6a-p117">Tiene la opción de mirar los certificados con el complemento Certificados para MMC. Solo tiene que escribir MMC en el cuadro de búsqueda y aparecerá como una opción de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="bfd6a-p118">Para agregar el complemento Certificados, debe hacer clic en **Archivo** y después en **Agregar o quitar complemento...** (o el método abreviado de teclado **Ctrl+M** también funcionará). **Certificados** será una de las opciones en el panel izquierdo. Selecciónela y, a continuación, seleccione **Cuenta de equipo** en la ventana emergente y **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="bfd6a-230">En la ventana emergente, en probabilidad todos los que hace esto en el equipo que se encarga a los certificados que necesita para mirar, deje es así la selección en el **equipo Local** si lo.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="bfd6a-231">Si está trabajando en un equipo remoto, cambie el botón de radio a **Otro equipo** y escriba el FQDN de ese equipo o utilice el botón **Examinar** para buscar dicho equipo a través de AD.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="bfd6a-232">Después de seleccionar el equipo, debe hacer clic en **Finalizar** cuando esté listo y, a continuación, **Aceptar** para agregar el complemento a la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="bfd6a-233">Expanda la sección de **certificados** en el panel izquierdo de MMC.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="bfd6a-234">Expanda la carpeta **Personal** también y seleccione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="bfd6a-235">Esto le permitirá ver los certificados de esta tienda.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="bfd6a-236">Tiene que ubicar el certificado que quiere ver, hacer clic con el botón derecho en él y elegir **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bfd6a-237">¿Cómo puede saber qué certificado es?</span><span class="sxs-lookup"><span data-stu-id="bfd6a-237">How do you know what certificate this is?</span></span> <span data-ttu-id="bfd6a-238">Debe ser puede ser el único certificado asignado a todo el contenido de la granja de servidores, o puede tener varios certificados para cosas diferentes, al igual que de forma predeterminada, los servicios Web internos, etc., en cuyo caso es posible que deba ver varios certificados.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="bfd6a-239">Varios certificados tendrán la misma huella digital.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="bfd6a-p122">Cuando haya llegado a la vista **Certificado**, elija **Detalles**. Esto le permitirá ver el nombre del firmante del certificado al seleccionar **Sujeto** y se mostrará el nombre del sujeto asignado y sus propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="bfd6a-p123">También necesitará comprobar las entradas de **Nombres alternativos de firmante**. Encontrará uno o varios de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="bfd6a-244">El nombre del grupo para este grupo de servidores o el nombre del servidor si este no es un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="bfd6a-245">Nombre del servidor al que está asignado el certificado.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="bfd6a-246">Registros de direcciones URL simples, normalmente de reunión y marcación.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="bfd6a-247">Servicios Web internos y los servicios Web externos los nombres (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones elegidas en el generador de topología y reemplazadas selecciones de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="bfd6a-248">Si ya está asignado, el lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="bfd6a-249">Necesitará comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="bfd6a-250">Por lo tanto, si se encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ha elegido ya configurado.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="bfd6a-251">Puede cerrar MMC.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="bfd6a-252">Si no están asignados, tendrá que realizar una nueva solicitud de certificado (como se detalla anteriormente) o deberá instalarlos después de la solicitud (para ello recomendamos seguir los pasos para Powershell detallados anteriormente).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="bfd6a-253">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="bfd6a-253">Configure the reverse proxy</span></span>
<span data-ttu-id="bfd6a-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd6a-254"></span></span>

<span data-ttu-id="bfd6a-p125">No es necesario seguir al pie de la letra los pasos que se explican a continuación. En las versiones anteriores del producto, le hemos guiado, por ejemplo, en el proceso de configuración de Threat Management Gateway (TMG) y, si no lo estaba utilizando, tenía que encontrar la forma de adaptarlo a su propia versión a partir de la información con la que contaba.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="bfd6a-257">Microsoft como un producto ya no ofrece TMG y, si aún necesita configurarlo, puede consultar los [pasos de Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="bfd6a-258">Pero la siguiente información de pretende ser útiles de forma más general, incluso si no hay ninguna forma podemos proporcionar pasos del tutorial específico para cada proxy inverso ahí.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="bfd6a-259">Debemos considerar dos aspectos:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="bfd6a-260">¿Hará su solicitud de detección automática inicial a través de HTTPS (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="bfd6a-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="bfd6a-261">Si tiene una regla de publicación web, debe modificarla.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="bfd6a-262">Si no tiene una regla de publicación web todavía, debe crearla.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="bfd6a-263">Si está realizando una solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bfd6a-264">**Importante** Un valor de tiempo de espera de servidor Proxy es un número que puede variar de una implementación a otra.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="bfd6a-265">Debe supervisar la implementación y modifique el valor de la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="bfd6a-266">Es posible que pueda establecer el valor tan bajo como 200.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="bfd6a-267">Si admite a clientes móviles de Lync en su entorno, debe establecer el valor a 960 para permitir tiempos de espera de notificación de inserción de Office 365, que tiene un valor de tiempo de espera de 900.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="bfd6a-268">Es muy probable que tendrá que aumentar el valor de tiempo de espera para evitar el cliente se desconecta cuando el valor es demasiado bajo o reduzca el número si las conexiones a través del proxy no desconecten pero desactive mucho después de que el cliente ha desconectado.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="bfd6a-269">Supervisión y líneas de base lo habitual para su entorno es la única forma precisa para determinar la configuración adecuada para este valor.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="bfd6a-270">Modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="bfd6a-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="bfd6a-271">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="bfd6a-272">Necesitará para localizar la regla de publicación de web y elija la opción de Editar (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="bfd6a-273">Debe haber un área que indica lo que se aplica esta regla de publicación de web a.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="bfd6a-274">Tendrá que modificar la regla para los sitios de entrada o las solicitudes de sitios.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="bfd6a-275">Deberá **agregar** una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="bfd6a-276">Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato del servidor de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="bfd6a-277">Es probable que cuente con un certificado nuevo que contenga la entrada SAN de detección automática.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="bfd6a-278">Que debe también ha instalado y configurado para su uso de acuerdo con la configuración del servidor de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="bfd6a-279">Asegúrese de guardar todo cuando haya completado la configuración.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="bfd6a-280">Si el proxy inverso tiene una funcionalidad de **prueba** , a continuación, asegúrese de uso del mismo, para garantizar que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="bfd6a-281">Ahora, es posible que necesite Repita estos pasos si tiene un Director o el Director de grupo de servidores en su entorno (Esto significa que tiene una segunda regla).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="bfd6a-282">Crear una regla de publicación de web para la dirección URL de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="bfd6a-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="bfd6a-283">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="bfd6a-284">Debe buscar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="bfd6a-285">Debe buscar la opción que le permita crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="bfd6a-286">Generalmente necesitará especificar la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="bfd6a-287">**Nombre**: el nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="bfd6a-288">**La acción de regla**: en este caso se trata de una regla de **permiso** , algo que permite que pase a través de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="bfd6a-289">La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="bfd6a-290">Tiene que ser **SSL** para acceso interno. Elija esa opción.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="bfd6a-291">Va a necesitar publicar una ruta de acceso para **Publicación interna**y escriba el FQDN para los servicios Web externos en el equilibrador de carga de su Front-End del grupo de servidores (o el FQDN del equilibrador de carga del grupo de servidores del Director si tiene uno), un ejemplo sería sfb_ pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="bfd6a-292">Debe escribir \*\* / \*\*\* como la ruta de acceso para su publicación, pero también debe **Reenviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="bfd6a-p131">Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="bfd6a-295">**Solicitudes de aceptación**, pero debería ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="bfd6a-296">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="bfd6a-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="bfd6a-297"><sipdomain>(Esto es la dirección URL del servicio Detección automática externo).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="bfd6a-298">Ahora, si está creando una regla para la URL de servicios Web externos en el grupo de servidores Front-End, debe escribir el FQDN para los servicios Web externos en el grupo de servidores Front-End (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="bfd6a-299">Habrá una opción de **ruta de acceso** y necesita escribir \*\* / \*\*\* aquí.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="bfd6a-300">Tendrá que seleccionar un **agente de escucha SSL** con el certificado público actualizado.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="bfd6a-301">**Delegación de autenticación** debe establecerse en **Sin delegación**, pero **debe** permitirse la autenticación directa de cliente.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="bfd6a-302">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="bfd6a-303">Esta es toda la información que puede necesitar para crear esta regla y poder continuar.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="bfd6a-304">Necesitará asegurarse de que se transfiera el **encabezado host original**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="bfd6a-305">También será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="bfd6a-306">**Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="bfd6a-307">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="bfd6a-308">Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="bfd6a-309">Crear una regla de publicación web para el puerto 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="bfd6a-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="bfd6a-310">Abra la interfaz de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="bfd6a-311">Debe buscar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="bfd6a-312">Debe buscar la opción que le permita crear una nueva regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="bfd6a-313">Generalmente necesitará especificar la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="bfd6a-314">**Nombre**: el nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="bfd6a-315">**La acción de regla**: en este caso se trata de una regla de **permiso** , algo que permite que pase a través de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="bfd6a-316">La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="bfd6a-317">Tiene que ser una **conexión no segura para conectarse con la granja o el servidor web publicado**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="bfd6a-318">Va a necesitar publicar una ruta de acceso para **Publicación interna**y escriba el FQDN de la **dirección VIP** del equilibrador de carga de su Front-End del grupo de servidores, un ejemplo sería sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="bfd6a-319">Debe escribir \*\* / \*\*\* como la ruta de acceso para su publicación, pero también debe **Reenviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="bfd6a-p134">Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="bfd6a-322">**Solicitudes de aceptación**, pero debería ser para el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="bfd6a-323">Para el **nombre**, debe escribir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="bfd6a-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="bfd6a-324"><sipdomain>(Esto es la dirección URL del servicio Detección automática externo).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="bfd6a-325">Habrá una opción de **ruta de acceso** y necesita escribir \*\* / \*\*\* aquí.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="bfd6a-326">Debe seleccionar una escucha de web, o permitir que el proxy inverso crear uno.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="bfd6a-327">**Delegación de autenticación** debe establecerse en **Sin delegación**, pero **no debe** permitirse la autenticación directa de cliente.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="bfd6a-328">La regla debe establecerse en **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="bfd6a-329">Esta es toda la información que puede necesitar para crear esta regla y poder continuar.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="bfd6a-330">Será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="bfd6a-331">**Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="bfd6a-332">**Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="bfd6a-333">Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="bfd6a-334">Configurar la detección automática para movilidad con implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="bfd6a-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="bfd6a-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd6a-335"></span></span>

<span data-ttu-id="bfd6a-336">Entornos híbridos de Skype para Business Server son entornos que combinan un local y el entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="bfd6a-337">Cuando tenga Skype para trabajar en un entorno híbrido de Business Server, el servicio Detección automática debe ser capaz de encontrar a un usuario de cualquiera de estos entornos.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="bfd6a-p137">Para permitir que los clientes móviles descubran dónde se encuentra un usuario, el servicio Detección automática tiene que configurarse con un nuevo localizador uniforme de recursos (URL). Los pasos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="bfd6a-340">Abra Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="bfd6a-341">Ejecute el siguiente procedimiento para obtener el valor del atributo **ProxyFQDN** para su Skype para entorno Business Server:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="bfd6a-342">A continuación, todavía desde la ventana del shell, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="bfd6a-343">Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="bfd6a-344">Probar la implementación de la movilidad</span><span class="sxs-lookup"><span data-stu-id="bfd6a-344">Test your Mobility deployment</span></span>
<span data-ttu-id="bfd6a-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd6a-345"></span></span>

<span data-ttu-id="bfd6a-346">Una vez haya implementado Skype para el servicio de movilidad de Business Server y Skype para servicio de detección automática de servidor empresarial, desea ejecutar una transacción de prueba, para asegurarse de trabajo de la implementación adecuada.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="bfd6a-347">Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear una conferencia, unirse a ella y comunicarse dentro.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="bfd6a-348">Necesitará dos usuarios (real o de prueba) y sus credenciales completas para realizar esta prueba.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="bfd6a-349">Este comando funcionará para ambos Skype para clientes empresariales, así como los clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="bfd6a-350">Para los clientes de Lync Server 2010 en Skype para Business Server 2015, debe ejecutar **Test-CsMcxP2PIM** para probar.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="bfd6a-351">Los usuarios de Lync Server 2010 aún se tienen que ser usuarios reales o usuarios de prueba predefinidos y necesitará sus credenciales de contraseña.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="bfd6a-352">Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="bfd6a-353">Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="bfd6a-354">Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="bfd6a-355">Probar las conferencias para clientes móviles de Lync 2013 y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bfd6a-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="bfd6a-356">Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-357">Iniciar **Skype para Shell de administración de negocio Server** (que es posible que escriba el nombre de la búsqueda o vaya a **Todos los programas** y lo elija).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="bfd6a-358">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="bfd6a-p141">También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="bfd6a-361">Probar las conferencias para clientes móviles de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bfd6a-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="bfd6a-362">Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="bfd6a-363">Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="bfd6a-364">Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="bfd6a-365">Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-366">Iniciar **Skype para Shell de administración de negocio Server** (que es posible que escriba el nombre de la búsqueda o vaya a **Todos los programas** y lo elija).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="bfd6a-367">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="bfd6a-p143">También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="bfd6a-370">Para revisar en detalle los procedimientos de comando, puede consultar [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) y [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="bfd6a-371">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="bfd6a-371">Configure for push notifications</span></span>
<span data-ttu-id="bfd6a-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd6a-372"></span></span>

<span data-ttu-id="bfd6a-373">Las notificaciones de inserción, que tienen la forma de notificaciones, iconos o alertas, pueden enviarse a un dispositivo móvil incluso cuando la aplicación Skype o Lync está inactiva.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="bfd6a-374">Pero ¿qué son las notificaciones de inserción?</span><span class="sxs-lookup"><span data-stu-id="bfd6a-374">But what are push notifications?</span></span> <span data-ttu-id="bfd6a-375">Son alertas de eventos, como una invitación de mensajería instantánea perdida o nueva, o un correo de voz recibido.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="bfd6a-376">El Skype para servicio de movilidad de Business Server envía estas notificaciones a la Skype basados en la nube para servidor de inserción notificación servicio empresarial, que, a continuación, envía las notificaciones para el servicio de notificación de inserción de Microsoft (MSNS) para los usuarios de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="bfd6a-377">Esta funcionalidad se ha modificado desde Lync Server 2013, pero si tiene un Skype para Business Server, querrá hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="bfd6a-378">Para un Skype para servidor perimetral de Business Server, agregar un nuevo proveedor de hospedaje, Microsoft Skype para profesionales en línea y, a continuación, configurar la federación de hospedaje entre su organización y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="bfd6a-p145">Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="bfd6a-381">Pruebe la configuración de federación y las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="bfd6a-382">Configurar el servidor perimetral de Skype Empresarial para notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="bfd6a-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="bfd6a-383">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-384">Inicie el **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bfd6a-385">Agregar un Skype para el proveedor de hospedaje en línea Business Server.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="bfd6a-386">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="bfd6a-p146">No puede tener más de una relación de federación con un solo proveedor de host. Es decir, si ya ha configurado un proveedor de host que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de host para él, aunque la identidad del proveedor de host no sea SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="bfd6a-389">Configurar la federación del proveedor de hospedaje entre su organización y el servicio de notificación de inserción en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="bfd6a-390">En la línea de comando, deberá escribir:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="bfd6a-391">Habilitar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="bfd6a-391">Enable push notifications</span></span>

1. <span data-ttu-id="bfd6a-392">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-393">Inicie el **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bfd6a-394">Habilite las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="bfd6a-395">Habilite la federación:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="bfd6a-396">Probar la federación y las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="bfd6a-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="bfd6a-397">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-398">Inicie el **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bfd6a-399">Pruebe la configuración de la federación:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="bfd6a-400">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="bfd6a-401">Pruebe las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="bfd6a-402">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="bfd6a-403">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="bfd6a-403">Configure Mobility policy</span></span>
<span data-ttu-id="bfd6a-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd6a-404"></span></span>

<span data-ttu-id="bfd6a-405">Tiene la posibilidad de con Skype para Business Server determinar quién puede usar el servicio de movilidad, llamar vía trabajo, voz sobre IP (VoIP), o de vídeo, así como si va a ser necesario para VoIP o vídeo WiFi.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="bfd6a-406">Vía trabajo permite a un usuario móvil realizar y recibir llamadas con el número de teléfono de su trabajo en lugar de su número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="bfd6a-407">La persona en el otro extremo de la línea no verá el número del teléfono móvil de ese usuario móvil y se evitarán los cargos por llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="bfd6a-408">Cuando se configuran VoIP y vídeo, los usuarios pueden recibir y realizar llamadas de VoIP y vídeo.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="bfd6a-409">La configuración del uso de WiFi define si será necesario que el dispositivo móvil de un usuario use una red WiFi además de una red de datos de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="bfd6a-410">Movilidad, llamada vía trabajo y VoIP y las características de vídeo están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="bfd6a-411">Esta opción de requerir WiFi para VoIP y vídeo están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="bfd6a-412">Un administrador tiene la capacidad para cambiar esto, globalmente, por sitio, o por usuario.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="bfd6a-413">Para poder usar las características de movilidad y llamada vía trabajo, los usuarios deben ser:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="bfd6a-414">Habilitado para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="bfd6a-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="bfd6a-415">estar habilitados para telefonía IP empresarial;</span><span class="sxs-lookup"><span data-stu-id="bfd6a-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="bfd6a-416">Asigna una directiva de movilidad que tiene la opción **enablemobility configurada** en **True**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="bfd6a-417">Para que los usuarios puedan usar Vía trabajo, también deben:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="bfd6a-418">tener asignada una directiva de voz que tenga la opción **Habilitar llamadas simultáneas** seleccionada;</span><span class="sxs-lookup"><span data-stu-id="bfd6a-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="bfd6a-419">Asigna una directiva de movilidad que tiene la **enableoutsidevoice configurada** establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bfd6a-p150">Los usuarios que no están habilitados para la telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP entre usuarios de Skype o pueden unirse a conferencias mediante el uso del vínculo Hacer clic para unirse mientras estén en sus dispositivos móviles, siempre y cuando estén configuradas las opciones apropiadas para la directiva de voz con la que están asociados. En el tema PLANIFICACIÓN encontrará más detalles.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="bfd6a-422">Modificar la directiva de movilidad global</span><span class="sxs-lookup"><span data-stu-id="bfd6a-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="bfd6a-423">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-424">Inicie el **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bfd6a-425">Desactivar el acceso a la movilidad y vía trabajo globalmente escribiendo:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="bfd6a-426">Puede desactivar llamada vía trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="bfd6a-427">Pero no se puede desactivar la movilidad sin desactivar también llamada vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="bfd6a-428">Para obtener más información, consulte [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="bfd6a-429">Modificar la directiva de movilidad por sitio</span><span class="sxs-lookup"><span data-stu-id="bfd6a-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="bfd6a-430">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-431">Inicie el **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bfd6a-p152">Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP, y Requerir WiFi para vídeo IP por sitio. Escriba:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="bfd6a-434">Más información en [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bfd6a-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="bfd6a-435">Modificar la directiva de movilidad por usuario</span><span class="sxs-lookup"><span data-stu-id="bfd6a-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="bfd6a-436">Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="bfd6a-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="bfd6a-437">Inicie el **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bfd6a-438">Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y llamada vía trabajo por usuario.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="bfd6a-439">Escriba:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="bfd6a-440">Otro ejemplo con datos de muestra:</span><span class="sxs-lookup"><span data-stu-id="bfd6a-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="bfd6a-441">Puede desactivar llamada vía trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="bfd6a-442">Pero no se puede desactivar la movilidad sin desactivar también llamada vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="bfd6a-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

