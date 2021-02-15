---
title: Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumen: obtenga información sobre cómo definir e implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server.'
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836920"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="d12b6-103">Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d12b6-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="d12b6-104">**Resumen:** Obtenga información sobre cómo definir e implementar un servidor de mediación en topology Builder en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d12b6-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="d12b6-105">La carga Telefonía IP empresarial de trabajo de Telefonía IP empresarial, las conferencias de acceso telefónico local y las aplicaciones avanzadas de Telefonía IP empresarial (aplicación grupo de respuesta, aplicación de estacionamiento de llamadas, control de admisión de llamadas, entre otros) están disponibles en los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d12b6-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="d12b6-106">La funcionalidad del servidor de mediación está integrada en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d12b6-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="d12b6-107">No es necesario un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="d12b6-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="d12b6-108">La única excepción es si configura un tronco SIP para conectarse a un controlador de borde de sesión para un proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="d12b6-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="d12b6-109">Para conectar la infraestructura Telefonía IP empresarial con el proveedor de troncos SIP, debe implementarse un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="d12b6-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="d12b6-110">La conexión entre Skype Empresarial Server (un servidor de mediación que se coloca en un grupo de servidores front-end o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica denominada tronco.</span><span class="sxs-lookup"><span data-stu-id="d12b6-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="d12b6-111">En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente si se conecta a un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="d12b6-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="d12b6-112">Definir un servidor de mediación en el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="d12b6-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="d12b6-113">Puede agregar un servidor de mediación como rol de instalación en un grupo de servidores front-end o definir un grupo de servidores de mediación independiente independiente.</span><span class="sxs-lookup"><span data-stu-id="d12b6-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="d12b6-114">Para agregar un servidor de mediación a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="d12b6-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="d12b6-115">Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="d12b6-116">En el Generador de topologías, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d12b6-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="d12b6-117">En el árbol de consola, haga clic con el botón secundario en el tipo de grupo de servidores front-end que desee y, a continuación, haga clic en Nuevo grupo **de servidores front-end.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="d12b6-118">Navegue por el Asistente para definir nuevo grupo **de servidores front-end** hasta que llegue a la página Seleccionar **roles de servidor juntos.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="d12b6-119">En **Select collocated server roles**, active la opción **Collocate Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="d12b6-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d12b6-120">Si el tipo de grupo de servidores front-end que seleccionó es Enterprise Edition, el componente de servidor de mediación se instalará en todos los servidores front-end de ese grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d12b6-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="d12b6-121">El **grupo de servidores del** próximo salto usado por el servidor de mediación será el grupo de servidores front-end en el que se coloca el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d12b6-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="d12b6-122">El **grupo de servidores perimetrales** usado por el servidor de mediación será el mismo grupo de servidores perimetrales asociado al grupo de servidores front-end en el que se coloca el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d12b6-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="d12b6-123">Haga **clic en Convertir en** predeterminado para usar este grupo de servidores front-end para enrutar las llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="d12b6-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="d12b6-124">Haga **clic en** Finalizar cuando haya terminado de asociar uno o varios sistemas del mismo nivel al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d12b6-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d12b6-125">Antes de continuar con el siguiente paso del proceso de implementación de Telefonía IP empresarial, asegúrese de que el grupo de servidores de mediación (es decir, el grupo de servidores front-end con el componente de servidor de mediación junto) usa los FQDN especificados.</span><span class="sxs-lookup"><span data-stu-id="d12b6-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="d12b6-126">Haga clic con el botón secundario en el nodo **de Skype Empresarial Server 2015** y, a continuación, haga clic en Publicar **topología.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="d12b6-127">Para agregar un servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="d12b6-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="d12b6-128">Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="d12b6-129">En el Generador de topologías, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d12b6-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="d12b6-130">En el árbol de consola, haga clic con el botón secundario en el nodo **Grupos de servidores de** mediación y, a continuación, haga clic en Grupo de servidores de **mediación.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="d12b6-131">En **Definir nuevo grupo de servidores de mediación,** escriba el nombre de dominio completo (FQDN) del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="d12b6-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="d12b6-132">A continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d12b6-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="d12b6-133">Si desea implementar varios servidores de mediación en el grupo de servidores para proporcionar alta disponibilidad, seleccione **Grupo de varios equipos.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="d12b6-134">Debe implementar [para admitir grupos](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) de servidores de mediación que tengan varios servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="d12b6-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="d12b6-135">Si desea implementar solo un servidor de mediación en el grupo de servidores porque no necesita alta disponibilidad, seleccione Grupo **de servidores de un solo equipo.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="d12b6-136">Omita el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="d12b6-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="d12b6-137">Si seleccionó grupo de varios equipos  en el paso anterior, en Definir los equipos de este elemento de grupo, haga clic en **FQDN** del equipo, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en Agregar **.** </span><span class="sxs-lookup"><span data-stu-id="d12b6-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="d12b6-138">Repita este paso para todos los demás servidores de mediación que desee agregar al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d12b6-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="d12b6-139">Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="d12b6-140">En **la** página Seleccionar el próximo salto, haga clic en Grupo de servidores del próximo **salto,** en el FQDN del grupo de servidores front-end que usará este grupo de servidores de mediación y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d12b6-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d12b6-141">En la **página Seleccionar un servidor perimetral,** realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d12b6-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="d12b6-142">Si desea proporcionar conectividad RTC a usuarios externos habilitados para Telefonía IP empresarial, en Seleccionar grupo de servidores perimetrales usado por este servidor de mediación, haga clic en el FQDN del grupo de servidores perimetrales que usará este grupo de servidores de mediación para proporcionar conectividad RTC a esos usuarios externos y, a continuación, haga clic en Siguiente **.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="d12b6-143">Si no tiene previsto habilitar usuarios externos para Telefonía IP empresarial, o si no desea proporcionar conectividad RTC a los usuarios cuando están fuera de la red interna, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d12b6-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="d12b6-144">Haga clic con el botón secundario en el nodo **de Skype Empresarial Server 2015** y, a continuación, haga clic en Publicar **topología.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="d12b6-145">Definir los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d12b6-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="d12b6-146">Siga los pasos descritos en este tema para usar el Generador de topologías para definir los puertos de escucha que un servidor o grupo de servidores de mediación aceptará conexiones entrantes desde un sistema del mismo nivel de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d12b6-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="d12b6-147">Para modificar los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d12b6-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="d12b6-148">Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**</span><span class="sxs-lookup"><span data-stu-id="d12b6-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="d12b6-149">En el Generador de topologías,  en el árbol de consola, expanda el nodo Grupos de servidores de mediación y haga clic con el botón secundario en el servidor de mediación creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d12b6-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="d12b6-150">De forma predeterminada, los puertos de escucha SIP en el servidor de mediación son 5070 para el tráfico TLS de Skype Empresarial Server y 5067 para el tráfico TLS desde sistemas del mismo nivel (como puertas de enlace, PBX o SBC).</span><span class="sxs-lookup"><span data-stu-id="d12b6-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="d12b6-151">El puerto TCP está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d12b6-151">TCP port is disabled by default.</span></span> <span data-ttu-id="d12b6-152">Debe habilitar el puerto TCP si tiene puertas de enlace que no admiten TLS.</span><span class="sxs-lookup"><span data-stu-id="d12b6-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="d12b6-153">Especifique el intervalo de puertos de escucha TCP o TLS deseado que el servidor de mediación aceptará conexiones entrantes de puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="d12b6-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d12b6-154">No es necesario especificar un intervalo de puertos TCP si **no** se ha activado Habilitar puerto TCP.</span><span class="sxs-lookup"><span data-stu-id="d12b6-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="d12b6-155">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="d12b6-155">This setting is optional.</span></span>
  

