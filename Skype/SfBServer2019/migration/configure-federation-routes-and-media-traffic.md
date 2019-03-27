---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de red. Después de migrar a su grupo piloto, necesitará para la transición desde la ruta de federación de las versiones anteriores de los servidores perimetrales para la ruta de federación de su Skype para los servidores perimetrales de Business Server 2019.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880231"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="fc97d-104">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="fc97d-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="fc97d-105">La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de red.</span><span class="sxs-lookup"><span data-stu-id="fc97d-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="fc97d-106">Después de migrar a su grupo piloto, necesitará para la transición desde la ruta de federación de los servidores perimetrales de la versión anterior a la ruta de federación de su Skype para los servidores perimetrales de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fc97d-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="fc97d-107">Use los siguientes procedimientos para realizar la transición de la ruta de federación y la ruta de tráfico de medios de servidor perimetral y Director de la versión anterior a su Skype para servidor perimetral de Business Server 2019, para una implementación de sitio único.</span><span class="sxs-lookup"><span data-stu-id="fc97d-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fc97d-108">Cambiar la ruta de federación y la ruta de tráfico multimedia requiere programar el tiempo de inactividad de mantenimiento para la Skype para Business Server 2019 y los servidores perimetrales de versión anterior.</span><span class="sxs-lookup"><span data-stu-id="fc97d-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="fc97d-109">Este proceso de transición completa también significa que acceso federado dejarán de estar disponible para la duración de la interrupción del servicio.</span><span class="sxs-lookup"><span data-stu-id="fc97d-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="fc97d-110">Debe programar el tiempo de inactividad durante un tiempo cuando se espera actividad mínima del usuario.</span><span class="sxs-lookup"><span data-stu-id="fc97d-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="fc97d-111">También debe proporcionar suficiente notificación a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="fc97d-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="fc97d-112">Planear en consecuencia para esta interrupción y el conjunto adecuado las expectativas dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="fc97d-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fc97d-113">Si su servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio de servidor perimetral de acceso, servicio perimetral de conferencia Web y el servicio perimetral A/v, los procedimientos descritos en esta sección no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="fc97d-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="fc97d-114">Si los Servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios luego dé de baja el servidor perimetral de versiones anteriores antes de habilitar la federación en el Skype para servidor perimetral de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fc97d-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fc97d-115">Si la federación XMPP se enruta a través de un Skype para servidor perimetral de Business Server 2019, los usuarios en la versión anterior no podrán comunicarse con el socio federado XMPP hasta que todos los usuarios se han movido a Skype para Business Server 2019, directivas de XMPP y se han configurado los certificados, se ha configurado el socio federado XMPP en Skype para Business Server 2019 y, por último, se han actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="fc97d-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="fc97d-116">Para quitar la asociación de federación heredada de Skype para sitios de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fc97d-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="fc97d-117">En Skype para servidor Front-End de Business Server 2019, abra la topología existente en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="fc97d-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="fc97d-118">En el panel izquierdo, desplácese hasta el nodo del sitio, que se encuentra justo debajo de **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="fc97d-119">Haga clic en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="fc97d-120">En el panel izquierdo, seleccione **ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="fc97d-121">En **asignación de ruta de federación de sitio**, desactive la casilla de verificación **Habilitar federación SIP** para deshabilitar la ruta de federación a través del entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="fc97d-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="fc97d-122">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="fc97d-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="fc97d-123">En **El generador de topología**, seleccione el nodo superior **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="fc97d-124">En el menú **acción** , haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="fc97d-125">Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando haya finalizado el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="fc97d-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="fc97d-126">Para configurar el servidor perimetral heredado como un servidor perimetral no federado</span><span class="sxs-lookup"><span data-stu-id="fc97d-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="fc97d-127">En el panel izquierdo, desplácese al nodo instalar heredado y, a continuación, en el nodo de **perimetral grupos de servidores** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="fc97d-128">Haga clic en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="fc97d-129">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="fc97d-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="fc97d-130">Desactive la casilla de verificación **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="fc97d-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="fc97d-131">En el menú **acción** , seleccione **Publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="fc97d-132">Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar** para cerrar al asistente.</span><span class="sxs-lookup"><span data-stu-id="fc97d-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="fc97d-133">Compruebe que está deshabilitada la federación para el servidor perimetral heredado en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="fc97d-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="fc97d-134">Para configurar certificados en el servidor perimetral heredado</span><span class="sxs-lookup"><span data-stu-id="fc97d-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="fc97d-135">Exporte el certificado externo del Proxy de acceso, con la clave privada, desde el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="fc97d-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="fc97d-136">En el Skype para servidor perimetral de Business Server 2019 e importar el Proxy de acceso externo de certificados desde el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="fc97d-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="fc97d-137">Asignar el certificado externo del Proxy de acceso a la Skype para Business Server 2019 la interfaz externa del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fc97d-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="fc97d-138">El certificado de la interfaz interna de la Skype para servidor perimetral de Business Server 2019 debe solicitar a una CA de confianza y asignarse.</span><span class="sxs-lookup"><span data-stu-id="fc97d-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="fc97d-139">Para cambiar la ruta de federación de la versión anterior para usar Skype para servidor perimetral de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fc97d-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="fc97d-140">En Topology Builder, en el panel izquierdo, desplácese al nodo de **Skype para Business Server 2019** y, a continuación, en el nodo de **grupos de servidores perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="fc97d-141">Haga clic en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="fc97d-142">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="fc97d-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="fc97d-143">Seleccione la casilla de verificación para **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="fc97d-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="fc97d-144">En el menú **acción** , seleccione **Publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="fc97d-145">Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar** para cerrar al asistente.</span><span class="sxs-lookup"><span data-stu-id="fc97d-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="fc97d-146">Compruebe que **federación (puerto 5061)** se establece en **habilitado** en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="fc97d-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="fc97d-147">Para actualizar Skype para el próximo salto de federación de servidor perimetral de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fc97d-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="fc97d-148">En Topology Builder, en el panel izquierdo, desplácese al nodo de **Skype para Business Server 2019** y, a continuación, en el nodo de **grupos de servidores perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="fc97d-149">Expanda el nodo, haga clic en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="fc97d-150">En la página **General** , en **selección de próximo salto**, seleccione en la lista desplegable el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fc97d-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="fc97d-151">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="fc97d-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="fc97d-152">En **El generador de topología**, seleccione el nodo superior **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="fc97d-153">En el menú **acción** , haga clic en **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="fc97d-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="fc97d-154">Para configurar Skype para la ruta de acceso de servidor perimetral de Business Server 2019 medios de salida</span><span class="sxs-lookup"><span data-stu-id="fc97d-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="fc97d-155">En Topology Builder, en el panel izquierdo, desplácese al nodo **Skype para Business Server 2019** y, a continuación, en el grupo de servidores por debajo de **Standard Edition servidor front-end** o **grupos de servidores Front-End de Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="fc97d-156">Haga clic en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="fc97d-157">En la sección **asociaciones** , active la casilla de verificación de **grupo de servidores perimetrales asociados (para componentes multimedia)** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="fc97d-158">En el cuadro de lista desplegable, seleccione el Skype para servidor perimetral de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fc97d-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="fc97d-159">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="fc97d-160">Para activar Skype para la federación del servidor perimetral de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fc97d-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="fc97d-161">En Topology Builder, en el panel izquierdo, desplácese al nodo de **Skype para Business Server 2019** y, a continuación, en el nodo de **grupos de servidores perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="fc97d-162">Expanda el nodo, haga clic en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fc97d-163">Sólo se puede habilitar la federación para un único grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="fc97d-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="fc97d-164">Si tiene varios grupos de servidores perimetrales, seleccione una nueva para usarla como el grupo de servidores perimetrales federación.</span><span class="sxs-lookup"><span data-stu-id="fc97d-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="fc97d-165">En la página **General** , compruebe que está activada la casilla de verificación **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="fc97d-166">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="fc97d-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="fc97d-167">Vaya al nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="fc97d-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="fc97d-168">Haga clic en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="fc97d-169">En el panel izquierdo, haga clic en **ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="fc97d-170">En **asignación de ruta de federación de sitio**, seleccione **Habilitar federación SIP**y, a continuación, en la lista Seleccione la Skype para Business Server 2019 perimetral Server enumerados.</span><span class="sxs-lookup"><span data-stu-id="fc97d-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="fc97d-171">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="fc97d-172">Para las implementaciones de varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="fc97d-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="fc97d-173">Para publicar los cambios de configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fc97d-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="fc97d-174">En **El generador de topología**, seleccione el nodo superior **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="fc97d-175">En el menú **acción** , seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="fc97d-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="fc97d-176">Espere a que la replicación de Active Directory que se produzca a todos los grupos de servidores en la implementación.</span><span class="sxs-lookup"><span data-stu-id="fc97d-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc97d-177">Es posible que aparezca el siguiente mensaje: **Advertencia: la topología contiene más de un servidor perimetral federados. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, un solo servidor perimetral se usaría activamente para la federación. Compruebe que el registro SRV de DNS externo señala al servidor perimetral correcto. Si desea implementar varios federación servidor perimetral para ser al mismo tiempo activo (es decir, no un escenario de migración), compruebe que todos los socios federados usa Skype para Business Server. Compruebe que el registro SRV de DNS externo enumera todos los servidores perimetrales de federación habilitada.**</span><span class="sxs-lookup"><span data-stu-id="fc97d-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="fc97d-178">Se espera y se puede omitir esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="fc97d-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="fc97d-179">Para configurar Skype para servidor perimetral de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fc97d-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="fc97d-180">Conecte todos los de la Skype para los servidores perimetrales de Business Server 2019 en línea.</span><span class="sxs-lookup"><span data-stu-id="fc97d-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="fc97d-181">Actualizar las reglas de enrutamiento de firewall externo o la configuración de equilibrador de carga de hardware para enviar el tráfico SIP para el acceso externo (normalmente el puerto 443) y federación (normalmente el puerto 5061) a la Skype para Business Server 2019 perimetral Server, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="fc97d-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc97d-182">Si no es necesario un equilibrador de carga de hardware, debe actualizar el registro A DNS para la federación resolver en el nuevo Skype para servidor perimetral de acceso de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="fc97d-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="fc97d-183">Para hacerlo con una interrupción mínima, reducir el valor TLL para el Skype externo de Business Server acceso perimetral FQDN para que cuando se actualiza DNS para que apunte a la nueva Skype para el servidor perimetral de acceso de servidor empresarial, la federación y el acceso remoto se actualizarán rápidamente.</span><span class="sxs-lookup"><span data-stu-id="fc97d-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="fc97d-184">Detener la **Skype para el servidor perimetral de acceso de servidor empresarial** desde cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fc97d-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="fc97d-185">En cada equipo servidor perimetral heredado, abra el subprograma **Servicios** desde las **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="fc97d-186">En la lista de servicios, busque **Skype para el servidor perimetral de acceso de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="fc97d-187">Haga clic en el nombre de los servicios y, a continuación, seleccione **Detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="fc97d-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="fc97d-188">Establezca el tipo de inicio en **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="fc97d-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="fc97d-189">Haga clic en **Aceptar** para cerrar la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="fc97d-189">Click **OK** to close the **Properties** window.</span></span> 
    

