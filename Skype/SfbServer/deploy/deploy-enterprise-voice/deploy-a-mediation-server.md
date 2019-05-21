---
title: Implementar un servidor de mediación en el generador de topología en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumen: Aprenda a definir e implementar un servidor de mediación en el generador de topologías de Skype empresarial Server.'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284651"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="c5252-103">Implementar un servidor de mediación en el generador de topología en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c5252-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="c5252-104">**Resumen:** Aprenda a definir e implementar un servidor de mediación en el generador de topologías de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c5252-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="c5252-105">La carga de trabajo de telefonía empresarial, las conferencias de acceso telefónico local y las aplicaciones de voz avanzadas para empresas (aplicación de grupo de respuesta, aplicación de Parque de llamadas, control de admisión de llamadas (CAC), etc.) están disponibles en los grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c5252-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="c5252-106">La funcionalidad del servidor de mediación está integrada en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="c5252-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="c5252-107">No es necesario disponer de un servidor de mediación independiente independiente.</span><span class="sxs-lookup"><span data-stu-id="c5252-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="c5252-108">La única excepción es si se configura un tronco SIP para conectar un controlador de borde de sesión en un proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="c5252-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="c5252-109">Para conectar su infraestructura de voz empresarial con su proveedor de troncal de SIP, se debe implementar un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="c5252-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="c5252-110">La conexión entre Skype empresarial Server (ya sea un servidor de Mediaización en un grupo de servidores front-end o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica denominada tronco.</span><span class="sxs-lookup"><span data-stu-id="c5252-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="c5252-111">En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente, si se conecta a un tronco de SIP.</span><span class="sxs-lookup"><span data-stu-id="c5252-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="c5252-112">Definir un servidor de mediación en el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="c5252-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="c5252-113">Puede Agregar un servidor de mediación como un rol colocado en un grupo de servidores front-end o definir un grupo independiente de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="c5252-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="c5252-114">Para agregar un servidor de mediación a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="c5252-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="c5252-115">Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="c5252-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="c5252-116">En el generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c5252-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="c5252-117">En el árbol de consola, haga clic con el botón secundario en el tipo de grupo de servidores front-end que desee y, a continuación, haga clic en **nuevo grupo de servidores front-end.**..</span><span class="sxs-lookup"><span data-stu-id="c5252-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="c5252-118">Avance por el asistente para **Definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados**.</span><span class="sxs-lookup"><span data-stu-id="c5252-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="c5252-119">En **Seleccionar roles de servidor**colocados, active la opción servidor de mediación de **Collocate**.</span><span class="sxs-lookup"><span data-stu-id="c5252-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c5252-120">Si el tipo de grupo de front-end que seleccionó es Enterprise Edition, el componente de servidor de mediación se instalará en todos los servidores front-end de ese grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c5252-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="c5252-121">El **grupo de próximos saltos** usado por el servidor de mediación será el grupo de servidores front-end en el que se encuentra el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c5252-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="c5252-122">El **Grupo perimetral** usado por el servidor de mediación será el mismo grupo perimetral asociado al grupo de servidores front-end en el que se encuentra el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c5252-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="c5252-123">Haga clic en **predeterminado** para usar este grupo de servidores front-end para enrutar llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="c5252-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="c5252-124">Haga clic en **Finalizar** cuando haya terminado de asociar uno o más elementos del mismo nivel al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c5252-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c5252-125">Antes de continuar con el siguiente paso del proceso de implementación de voz de empresa, asegúrese de que el grupo de servidores de mediación (es decir, el grupo front-end con el componente de servidor de mediación colocado) esté usando los FQDN que especificó.</span><span class="sxs-lookup"><span data-stu-id="c5252-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="c5252-126">Haga clic con el botón secundario en el nodo **de Skype empresarial Server 2015** y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="c5252-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="c5252-127">Para agregar un servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="c5252-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="c5252-128">Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="c5252-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="c5252-129">En el generador de topologías, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c5252-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="c5252-130">En el árbol de consola, haga clic con el botón derecho en el nodo de **grupos** de mediación y en **grupo de servidores**de mediación.</span><span class="sxs-lookup"><span data-stu-id="c5252-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="c5252-131">En **definir nuevo grupo**de mediación, escriba el nombre de dominio completo (FQDN) del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="c5252-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="c5252-132">A continuación, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5252-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="c5252-133">Si desea implementar varios servidores de mediación en el grupo para proporcionar alta disponibilidad, seleccione **varios grupos de equipos**.</span><span class="sxs-lookup"><span data-stu-id="c5252-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="c5252-134">Debe [implementarlo](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para admitir grupos de servidores de mediación que tengan varios servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="c5252-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="c5252-135">Si desea implementar solo un servidor de mediación en el grupo porque no necesita alta disponibilidad, seleccione **grupo de equipos únicos**.</span><span class="sxs-lookup"><span data-stu-id="c5252-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="c5252-136">Omita el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="c5252-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="c5252-137">Si ha seleccionado **Grupo de varios equipos** en el paso anterior, en el elemento **Definir equipos de este grupo**, haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c5252-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="c5252-138">Repita este paso para todos los demás servidores de mediación que desee agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="c5252-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="c5252-139">Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c5252-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="c5252-140">En la página **seleccionar el próximo salto** , haga clic en **grupo de próximos saltos**, haga clic en el FQDN del grupo de servidores front-end que usará este grupo de servidores de mediación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c5252-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="c5252-141">En la página **Seleccionar un servidor perimetral**, realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5252-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="c5252-142">Si desea proporcionar conectividad RTC a usuarios externos habilitados para telefonía IP empresarial, en **Seleccionar grupo perimetral usado por este servidor**de mediación, haga clic en el FQDN del grupo de servidores perimetrales que usarán este grupo de servidores de mediación para proporcionar conectividad RTC a esos usuarios externos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c5252-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="c5252-143">Si no tiene previsto habilitar usuarios externos para telefonía IP empresarial, o si no desea proporcionar conectividad RTC a los usuarios cuando se encuentren fuera de la red interna, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c5252-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="c5252-144">Haga clic con el botón secundario en el nodo **de Skype empresarial Server 2015** y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="c5252-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="c5252-145">Definir los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="c5252-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="c5252-146">Siga los pasos que se indican en este tema para usar el generador de topología para definir los puertos de escucha que un servidor de mediación o grupo aceptará las conexiones entrantes de una puerta de enlace del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c5252-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="c5252-147">Para modificar los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="c5252-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="c5252-148">Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="c5252-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="c5252-149">En el generador de topología, en el árbol de consola, expanda el nodo **grupos** de mediación y haga clic con el botón secundario en el servidor de mediación creado previamente.</span><span class="sxs-lookup"><span data-stu-id="c5252-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="c5252-150">De forma predeterminada, los puertos de escucha SIP en el servidor de mediación son 5070 para el tráfico de TLS desde Skype empresarial Server y 5067 para el tráfico TLS de homólogos (como puertas de enlace, PBXes o SBCs).</span><span class="sxs-lookup"><span data-stu-id="c5252-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="c5252-151">El puerto TCP está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c5252-151">TCP port is disabled by default.</span></span> <span data-ttu-id="c5252-152">Debe habilitar el puerto TCP si tiene puertas de enlace que no son compatibles con TLS.</span><span class="sxs-lookup"><span data-stu-id="c5252-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="c5252-153">Especifique el intervalo de puerto de escucha TLS o TCP que desee el servidor de mediación aceptará conexiones entrantes de puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="c5252-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c5252-p107">No es necesario indicar este intervalo si no se ha seleccionado **Habilitar puerto TCP**. Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="c5252-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

