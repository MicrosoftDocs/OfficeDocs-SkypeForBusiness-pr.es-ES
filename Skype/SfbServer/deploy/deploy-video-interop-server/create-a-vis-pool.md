---
title: Crear un grupo vis en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumen: cree un grupo de servidores de interoperabilidad de vídeo en Skype Empresarial Server con topology Builder.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802060"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="f66fc-103">Crear un grupo vis en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f66fc-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="f66fc-104">**Resumen:** Cree un grupo de servidores de interoperabilidad de vídeo en Skype Empresarial Server con topology Builder.</span><span class="sxs-lookup"><span data-stu-id="f66fc-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="f66fc-105">Crear un vis o un grupo vis mediante el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="f66fc-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="f66fc-106">Abra el Generador de topologías en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f66fc-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="f66fc-107">En el panel izquierdo del Generador  de topologías, haga clic con el botón secundario en Grupos de servidores de interoperabilidad de vídeo y elija Nuevo grupo de **servidores de interoperabilidad de vídeo.**</span><span class="sxs-lookup"><span data-stu-id="f66fc-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="f66fc-108">Se abrirá un asistente para crear **un nuevo grupo de servidores de interoperabilidad de** vídeo.</span><span class="sxs-lookup"><span data-stu-id="f66fc-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="f66fc-109">Proporcione el FQDN del grupo para el  nuevo servidor de  interoperabilidad de vídeo y seleccione Este grupo tiene un servidor o este grupo tiene varios servidores según sus requisitos y, a continuación, presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f66fc-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="f66fc-110">Si desea implementar un grupo de servidores de interoperabilidad de vídeo para proporcionar alta disponibilidad, seleccione **Este grupo tiene varios servidores.**</span><span class="sxs-lookup"><span data-stu-id="f66fc-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="f66fc-111">Tenga en cuenta esta opción que:</span><span class="sxs-lookup"><span data-stu-id="f66fc-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="f66fc-112">Debe implementar el equilibrio de carga de DNS para admitir grupos de servidores de interoperabilidad de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f66fc-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="f66fc-113">En la página siguiente, para definir los equipos de este elemento de grupo de servidores, escriba el **FQDN** del equipo de cada servidor del grupo en el campo de texto y, a continuación, haga clic en **Agregar**. </span><span class="sxs-lookup"><span data-stu-id="f66fc-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="f66fc-114">Repita este paso para agregar otro servidor de interoperabilidad de vídeo al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f66fc-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="f66fc-115">Cuando haya definido todos los equipos del grupo, presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f66fc-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="f66fc-116">Si desea implementar solo un servidor de interoperabilidad de vídeo en  el grupo porque no necesita alta disponibilidad, seleccione Este grupo tiene un servidor y presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f66fc-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="f66fc-117">Seleccione el grupo de servidores/FE del próximo salto de la lista desplegable y presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f66fc-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="f66fc-118">Seleccione un grupo de servidores perimetrales para asociar con el VIS y presione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f66fc-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="f66fc-119">Establecer un puerto TCP o TLS.</span><span class="sxs-lookup"><span data-stu-id="f66fc-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="f66fc-120">Seleccione el servidor de interoperabilidad de vídeo recién agregado en el panel izquierdo del Generador de topologías, haga clic con el botón secundario en él y elija **Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f66fc-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="f66fc-121">Habilite o actualice el puerto TCP o TLS según sus requisitos y elija **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="f66fc-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="f66fc-122">Aunque se agrega TLS de forma predeterminada, solo TCP se ha probado completamente con Cisco Unified Communications Manager (CallManager o CUCM).</span><span class="sxs-lookup"><span data-stu-id="f66fc-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="f66fc-123">Agregar una puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f66fc-123">Add a video gateway.</span></span> <span data-ttu-id="f66fc-124">Para ello, expanda Componentes compartidos, haga clic con el botón secundario en **Puertas de enlace de** vídeo y seleccione Nueva puerta de enlace de **vídeo.**</span><span class="sxs-lookup"><span data-stu-id="f66fc-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="f66fc-125">Proporcione el FQDN o la dirección IP de la puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f66fc-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="f66fc-126">La puerta de enlace de vídeo podría estar en un subdominio o en un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="f66fc-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="f66fc-127">Cucm usado por los VTC del sistema sirve como puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f66fc-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="f66fc-128">Seleccione IPv4 o IPv6 según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f66fc-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="f66fc-129">Puede usar todas las direcciones IP configuradas o limitar el uso del servicio a las direcciones IP seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="f66fc-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="f66fc-130">Seleccione el puerto de escucha de la puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f66fc-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="f66fc-131">Seleccione el protocolo de transporte (TCP o TLS) y asócialo con un servidor de interoperabilidad de vídeo configurado para un tronco SIP de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f66fc-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="f66fc-132">El protocolo de transporte para la puerta de enlace de vídeo debe coincidir con el protocolo de transporte configurado para el VIS.</span><span class="sxs-lookup"><span data-stu-id="f66fc-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="f66fc-133">Una vez completado el paso anterior, se agrega un tronco sip de vídeo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f66fc-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="f66fc-134">Haga clic con el botón secundario en el tronco de vídeo SIP y seleccione el tronco que se acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="f66fc-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="f66fc-135">El nombre del tronco SIP de vídeo, el servidor de interoperabilidad de vídeo asociado, el protocolo de transporte SIP y el puerto se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="f66fc-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="f66fc-136">Un servidor de interoperabilidad de vídeo admite troncos 1:N.</span><span class="sxs-lookup"><span data-stu-id="f66fc-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="f66fc-137">Por lo tanto, se pueden agregar varios troncos, que están asociados a un único servidor de interoperabilidad de vídeo, donde cada tronco termina en una puerta de enlace de vídeo diferente.</span><span class="sxs-lookup"><span data-stu-id="f66fc-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="f66fc-138">La limitación es que una puerta de enlace de vídeo en particular tiene un solo tronco que se puede definir para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f66fc-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="f66fc-139">Publique el documento de topología tal como se describe en Crear y publicar una nueva topología [en Skype Empresarial Server 2015.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="f66fc-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f66fc-140">Para mejorar la resistencia, es posible que desee configurar un segundo servidor de interoperabilidad de vídeo o un grupo vis, o un grupo de servidores front-end de reserva.</span><span class="sxs-lookup"><span data-stu-id="f66fc-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="f66fc-141">Vea [los mecanismos de resistencia para](../../plan-your-deployment/video-interop-server.md#resiliency) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f66fc-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="f66fc-142">Todas las tareas realizadas con el Generador de topologías ahora deben completarse.</span><span class="sxs-lookup"><span data-stu-id="f66fc-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="f66fc-143">Continúe con la instalación del software en el nuevo servidor o servidores VIS.</span><span class="sxs-lookup"><span data-stu-id="f66fc-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="f66fc-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f66fc-144">See also</span></span>

[<span data-ttu-id="f66fc-145">Implementar el rol de servidor VIS en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f66fc-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="f66fc-146">Planear el servidor de interoperabilidad de vídeo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f66fc-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="f66fc-147">Crear y publicar una nueva topología en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="f66fc-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
