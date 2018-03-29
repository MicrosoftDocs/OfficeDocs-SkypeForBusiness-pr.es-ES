---
title: Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumen: Aprender a definir e implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015.'
ms.openlocfilehash: bfb915528ba73851d3bd60cc8ff3b33b968376e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="40b42-103">Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="40b42-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="40b42-104">**Resumen:** Aprenda a definir e implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="40b42-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="40b42-105">La carga de trabajo de la Telefonía IP empresarial, conferencias de acceso telefónico y aplicaciones avanzadas de Telefonía IP empresarial (aplicación de grupo de respuesta, aplicación llamada Park, control de admisión de llamadas (CAC) y así sucesivamente), están disponibles en grupos de Front-End.</span><span class="sxs-lookup"><span data-stu-id="40b42-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="40b42-106">La funcionalidad del servidor de mediación está integrada en el servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="40b42-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="40b42-107">No es necesario un servidor de mediación de independiente independiente.</span><span class="sxs-lookup"><span data-stu-id="40b42-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="40b42-108">La única excepción es si se configura un tronco SIP para conectar un controlador de borde de sesión en un proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="40b42-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="40b42-109">Para conectar la infraestructura de Telefonía IP empresarial con su proveedor de tronco SIP, se debe implementar un servidor de mediación de independiente.</span><span class="sxs-lookup"><span data-stu-id="40b42-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="40b42-110">La conexión entre Skype para Business Server (un servidor de mediación ubicado en un grupo de servidores Front-End o un servidor de mediación de independiente) y una puerta de enlace se define como una asociación lógica que se denomina un tronco.</span><span class="sxs-lookup"><span data-stu-id="40b42-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="40b42-111">En los temas de esta sección describen cómo definir un tronco y cómo implementar un servidor de mediación de independiente, si se conecta a un troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="40b42-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="40b42-112">Definir un servidor de mediación en el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="40b42-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="40b42-113">Puede agregar el servidor de mediación como una función colocada en un grupo de servidores Front-End, o definir un grupo de servidor de mediación de independiente.</span><span class="sxs-lookup"><span data-stu-id="40b42-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="40b42-114">Para agregar un servidor de mediación a un grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="40b42-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="40b42-115">Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="40b42-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="40b42-116">Generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="40b42-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="40b42-117">En el árbol de consola, haga clic en el tipo de grupo de servidores Front-End que desee y, a continuación, haga clic en **grupo nuevo Front-End..**.</span><span class="sxs-lookup"><span data-stu-id="40b42-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="40b42-118">Avance por el asistente para **Definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados**.</span><span class="sxs-lookup"><span data-stu-id="40b42-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="40b42-119">En **funciones de servidor colocadas Select**, seleccione la opción **Colocar el servidor de mediación**.</span><span class="sxs-lookup"><span data-stu-id="40b42-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40b42-120">Si el tipo de grupo de Front-End que seleccionó es la edición Enterprise, se instalará el componente de servidor de mediación en todos los servidores frontales de ese grupo de Front-End.</span><span class="sxs-lookup"><span data-stu-id="40b42-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="40b42-121">El **siguiente grupo de salto** utilizado por el servidor de mediación será donde está ubicado el servidor de mediación en el grupo de Front-End.</span><span class="sxs-lookup"><span data-stu-id="40b42-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="40b42-122">La **piscina de borde** utilizado por el servidor de mediación será el mismo grupo de borde que se asociado con el grupo de Front-End donde está ubicado el servidor de mediación en.</span><span class="sxs-lookup"><span data-stu-id="40b42-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="40b42-123">Haga clic en **Establecer como predeterminado** para utilizar este grupo de servidores Front-End para enrutar las llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="40b42-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="40b42-124">Haga clic en **Finalizar** cuando haya terminado de asociar uno o varios elementos del mismo nivel para el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="40b42-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40b42-125">Antes de continuar con el siguiente paso en el proceso de implementación de Telefonía IP empresarial, asegúrese de que el grupo de servidor de mediación (es decir, Front-End ubicado de grupo con el componente de servidor de mediación) utiliza el FQDN que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="40b42-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="40b42-126">Haga clic en el nodo de **Skype para Business Server 2015** y, a continuación, haga clic en **Publicar la topología**.</span><span class="sxs-lookup"><span data-stu-id="40b42-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="40b42-127">Para agregar un servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="40b42-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="40b42-128">Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="40b42-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="40b42-129">Generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="40b42-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="40b42-130">En el árbol de consola, haga clic en el nodo **grupos de mediación** y, a continuación, haga clic en **grupo de servidor de mediación**.</span><span class="sxs-lookup"><span data-stu-id="40b42-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="40b42-131">En **Definir agrupación de mediación**, escriba el nombre de dominio completo del grupo de servidor de mediación (FQDN).</span><span class="sxs-lookup"><span data-stu-id="40b42-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="40b42-132">A continuación, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="40b42-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="40b42-133">Si desea implementar varios servidores de mediación en el grupo para proporcionar alta disponibilidad, a continuación, seleccione el **grupo de equipo múltiple**.</span><span class="sxs-lookup"><span data-stu-id="40b42-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40b42-134">Debe desplegar (.. /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para admitir grupos de servidores de mediación que tienen varios servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="40b42-134">You must deploy  (../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="40b42-135">Si desea implementar sólo un servidor de mediación en el grupo, ya que no requieren alta disponibilidad, a continuación, seleccione el **grupo de equipo único**.</span><span class="sxs-lookup"><span data-stu-id="40b42-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="40b42-136">Omita el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="40b42-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="40b42-137">Si ha seleccionado **Grupo de varios equipos** en el paso anterior, en el elemento **Definir equipos de este grupo**, haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40b42-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="40b42-138">Repita este paso para todos los demás servidores de mediación que desea agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="40b42-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="40b42-139">Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40b42-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="40b42-140">En la página **Seleccionar el siguiente salto** , haga clic en **grupo de salto siguiente**, el FQDN del grupo de servidores Front-End que utilizará este grupo de servidores de mediación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40b42-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="40b42-141">En la página **Seleccionar un servidor perimetral**, realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="40b42-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="40b42-142">Si desea proporcionar conectividad PSTN a usuarios externos habilitados para Telefonía IP empresarial, **Seleccione grupo de borde utilizado por este servidor de mediación**, haga clic en el FQDN del grupo de servidores de borde que se va a utilizar este grupo de servidores de mediación para proporcionar conectividad PSTN a los usuarios externos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40b42-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="40b42-143">Si no va a permitir que los usuarios externos para Telefonía IP empresarial, o si no desea proporcionar conectividad RTC a los usuarios cuando se encuentran fuera de la red interna, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40b42-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="40b42-144">Haga clic en el nodo de **Skype para Business Server 2015** y, a continuación, haga clic en **Publicar la topología**.</span><span class="sxs-lookup"><span data-stu-id="40b42-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="40b42-145">Definir los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="40b42-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="40b42-146">Siga los pasos de este tema para utilizar el generador de topología para definir los puertos de escucha de un servidor de mediación o grupo aceptará conexiones entrantes de un interlocutor de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="40b42-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="40b42-147">Para modificar los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="40b42-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="40b42-148">Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="40b42-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="40b42-149">En el generador de topología, en el árbol de consola, expanda el nodo **grupos de mediación** y (ratón) en el servidor de mediación creado previamente.</span><span class="sxs-lookup"><span data-stu-id="40b42-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="40b42-150">De forma predeterminada, los puertos de escucha de SIP en el servidor de mediación son 5070 para el tráfico TLS de Skype para Business Server y 5067 para tráfico TLS de colegas (como puertas de enlace, PBXe o SBCs).</span><span class="sxs-lookup"><span data-stu-id="40b42-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="40b42-151">El puerto TCP está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="40b42-151">TCP port is disabled by default.</span></span> <span data-ttu-id="40b42-152">Debe habilitar el puerto TCP si dispone de puertas de enlace que no admitan TLS.</span><span class="sxs-lookup"><span data-stu-id="40b42-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="40b42-153">Especificar que el deseado TLS o TCP escucha intervalo de puertos del servidor de mediación aceptará conexiones entrantes de puertas de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="40b42-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40b42-p107">No es necesario indicar este intervalo si no se ha seleccionado **Habilitar puerto TCP**. Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="40b42-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

