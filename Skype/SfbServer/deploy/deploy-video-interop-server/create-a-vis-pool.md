---
title: Crear un grupo de VIS en Skype empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumen: cree un grupo de servidores de interoperabilidad de vídeo en Skype empresarial Server con el generador de topologías.'
ms.openlocfilehash: 474752253312b58b87a3d01f445bd93eabdaf203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798057"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="609a5-103">Crear un grupo de VIS en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="609a5-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="609a5-104">**Resumen:** Cree un grupo de servidores de interoperabilidad de vídeo en Skype empresarial Server con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="609a5-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="609a5-105">Crear un VIS o un grupo de VIS con el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="609a5-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="609a5-106">Abra el Generador de topologías en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="609a5-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="609a5-107">En el panel izquierdo del creador de topología, haga clic con el botón secundario en **grupos de servidores de interoperabilidad** y seleccione **nuevo grupo de servidores de interoperabilidad**de vídeo.</span><span class="sxs-lookup"><span data-stu-id="609a5-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="609a5-108">De este modo, se abrirá un asistente para **Crear un grupo de servidores de interoperabilidad de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="609a5-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="609a5-109">Proporcione el FQDN del grupo para el nuevo servidor de interoperabilidad de vídeo y seleccione **este grupo tiene un servidor** o **este grupo tiene varios servidores** en función de su requisito y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="609a5-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="609a5-110">Si desea implementar un grupo de servidores de interoperabilidad de vídeo para proporcionar alta disponibilidad, seleccione **este grupo tiene varios servidores**.</span><span class="sxs-lookup"><span data-stu-id="609a5-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="609a5-111">Recuerde lo siguiente en relación con esta opción:</span><span class="sxs-lookup"><span data-stu-id="609a5-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="609a5-112">Debe implementar el equilibrio de carga de DNS para admitir grupos de servidores de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="609a5-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="609a5-113">En la siguiente página, en el elemento **Definir los equipos de este grupo de servidores**, escriba el **FQDN de equipo** de cada servidor del grupo en el campo de texto y, luego, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="609a5-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="609a5-114">Repita este paso para agregar otro servidor de interoperabilidad de vídeo al grupo.</span><span class="sxs-lookup"><span data-stu-id="609a5-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="609a5-115">Cuando haya definido todos los equipos en el grupo, presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="609a5-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="609a5-116">Si desea implementar solo un servidor de interoperabilidad de vídeo en el grupo porque no necesita alta disponibilidad, seleccione **este grupo tiene un servidor** y pulse **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="609a5-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="609a5-117">Seleccione el grupo de servidores del próximo salto/FE de la lista desplegable y presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="609a5-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="609a5-118">Seleccione un grupo de servidores perimetrales para asociarlo al VIS y presione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="609a5-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="609a5-119">Defina un puerto TCP o TLS.</span><span class="sxs-lookup"><span data-stu-id="609a5-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="609a5-120">Seleccione el servidor de interoperabilidad de vídeo recién agregado en el panel izquierdo del generador de topología, haga clic con el botón secundario en él y elija **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="609a5-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="609a5-121">Habilite o actualice el puerto TCP o TLS (lo que corresponda en su caso) y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="609a5-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="609a5-122">Aunque se agrega TLS de forma predeterminada, solo se ha probado TCP con Cisco Unified Communications Manager (CallManager o CUCM).</span><span class="sxs-lookup"><span data-stu-id="609a5-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="609a5-p106">Agregue una puerta de enlace de vídeo. Para ello, expanda Componentes compartidos, haga clic con el botón secundario en **Puertas de enlace de vídeo** y, luego, seleccione **Nueva puerta de enlace de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="609a5-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="609a5-p107">Escriba el FQDN o la dirección IP para la puerta de enlace de vídeo. Esta puerta de enlace de vídeo puede estar en un subdominio o en un dominio distinto. El CUCM que usan los VTC del sistema puede servir como puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="609a5-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="609a5-p108">Seleccione IPv4 o IPv6, lo que corresponda. Puede usar todas las direcciones IP configuradas o acotar el uso del servicio a determinadas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="609a5-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="609a5-130">Seleccione el puerto de escucha de la puerta de enlace de vídeo.</span><span class="sxs-lookup"><span data-stu-id="609a5-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="609a5-131">Seleccione el protocolo de transporte (TCP o TLS) y asócielo con un servidor de interoperabilidad de video configurado para un tronco de video SIP.</span><span class="sxs-lookup"><span data-stu-id="609a5-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="609a5-132">El protocolo de transporte de la puerta de enlace de vídeo tiene que ser el mismo que el que se ha configurado para el VIS.</span><span class="sxs-lookup"><span data-stu-id="609a5-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="609a5-133">Tras completar el paso anterior, se agrega el tronco SIP de vídeo pertinente.</span><span class="sxs-lookup"><span data-stu-id="609a5-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="609a5-134">Haga clic con el botón secundario en el tronco SIP de vídeo y seleccione el tronco que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="609a5-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="609a5-135">Se puede cambiar el nombre del tronco del SIP de video, el servidor de interoperabilidad del video asociado, el protocolo de transporte SIP y el puerto.</span><span class="sxs-lookup"><span data-stu-id="609a5-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="609a5-136">Un servidor de interoperabilidad de vídeo admite los troncos de 1: N.</span><span class="sxs-lookup"><span data-stu-id="609a5-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="609a5-137">Por eso se pueden agregar varios troncos, que están asociados con un único servidor de interoperabilidad de video, en el que cada tronco termina en una puerta de enlace de video diferente.</span><span class="sxs-lookup"><span data-stu-id="609a5-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="609a5-138">La limitación es que una puerta de enlace de vídeo determinada tiene solo un tronco que puede definirse para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="609a5-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="609a5-139">Publique el documento de topología como se describe en [crear y publicar una nueva topología en Skype empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="609a5-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="609a5-140">Para mejorar la resistencia, es posible que desee configurar un segundo servidor de interoperabilidad de vídeo o un grupo de servidores de interoperabilidad de copia de seguridad o un grupo de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="609a5-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="609a5-141">Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para más información.</span><span class="sxs-lookup"><span data-stu-id="609a5-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="609a5-142">Todas las tareas realizadas con el Generador de topologías tendrían que finalizar aquí.</span><span class="sxs-lookup"><span data-stu-id="609a5-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="609a5-143">Continúe con la instalación del software en el nuevo servidor o en los nuevos servidores VIS.</span><span class="sxs-lookup"><span data-stu-id="609a5-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="609a5-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="609a5-144">See also</span></span>

[<span data-ttu-id="609a5-145">Implementar el rol de servidor VIS en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="609a5-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="609a5-146">Planear el servidor de interoperabilidad de vídeo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="609a5-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="609a5-147">Crear y publicar una nueva topología en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="609a5-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
