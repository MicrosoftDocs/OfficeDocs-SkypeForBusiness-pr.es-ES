---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red. Después de migrar a su grupo piloto, debe realizar una transición de la ruta de Federación de sus servidores perimetrales de versiones anteriores a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.
ms.openlocfilehash: 71417307fd46c2c29535cea3a52f0286ad6dc951
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813818"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="64b50-104">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="64b50-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="64b50-105">La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red.</span><span class="sxs-lookup"><span data-stu-id="64b50-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="64b50-106">Después de migrar a su grupo piloto, debe realizar una transición de la ruta de Federación de los servidores perimetrales de la versión anterior a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64b50-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="64b50-107">Use los procedimientos siguientes para realizar la transición de la ruta de Federación y la ruta de tráfico multimedia desde el servidor perimetral y el director de la versión anterior de Skype 2019 empresarial para una implementación de sitio único.</span><span class="sxs-lookup"><span data-stu-id="64b50-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="64b50-108">El cambio de la ruta de Federación y el tráfico de multimedia requiere que programe el tiempo de inactividad de mantenimiento de los servidores de Skype empresarial Server 2019 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="64b50-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="64b50-109">Todo este proceso de transición también significa que el acceso federado no estará disponible durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="64b50-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="64b50-110">Debe programar el tiempo de inactividad para una hora en la que espera una actividad mínima de usuario.</span><span class="sxs-lookup"><span data-stu-id="64b50-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="64b50-111">También debe proporcionar una notificación suficiente a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="64b50-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="64b50-112">Planee en consecuencia para esta interrupción y establezca las expectativas apropiadas dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="64b50-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="64b50-113">Si el servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral a/V, no se admiten los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="64b50-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="64b50-114">Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios y luego retirar el servidor perimetral de las versiones anteriores antes de habilitar la Federación en el servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64b50-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="64b50-115">Si la Federación de XMPP se dirige a través de un servidor perimetral de Skype empresarial Server 2019, los usuarios de la versión anterior no podrán comunicarse con el socio de XMPP federado hasta que todos los usuarios hayan pasado a Skype empresarial Server 2019, directivas XMPP y se han configurado certificados, el socio de XMPP federado se ha configurado en Skype empresarial Server 2019 y, por último, se han actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="64b50-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="64b50-116">Para quitar la Asociación de Federación heredada de sitios de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="64b50-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="64b50-117">En el servidor front-end de Skype empresarial Server 2019, abra la topología existente en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="64b50-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="64b50-118">En el panel de la izquierda, vaya al nodo del sitio, que se encuentra directamente debajo **de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="64b50-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="64b50-119">Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b50-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="64b50-120">En el panel de la izquierda, seleccione **ruta de Federación**.</span><span class="sxs-lookup"><span data-stu-id="64b50-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="64b50-121">En **asignación de ruta de Federación de sitios**, desactive la casilla **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="64b50-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="64b50-122">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="64b50-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="64b50-123">En el **generador de topologías**, seleccione el nodo principal de **Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="64b50-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="64b50-124">En el menú **acción** , haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="64b50-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="64b50-125">Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando se haya completado el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="64b50-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="64b50-126">Para configurar el servidor perimetral heredado como servidor perimetral de no Federación</span><span class="sxs-lookup"><span data-stu-id="64b50-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="64b50-127">En el panel de la izquierda, navegue hasta el nodo instalación heredada y, a continuación, al nodo **contornos de borde** .</span><span class="sxs-lookup"><span data-stu-id="64b50-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="64b50-128">Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b50-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="64b50-129">Seleccione **General** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="64b50-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="64b50-130">Desactive la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="64b50-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="64b50-131">En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="64b50-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="64b50-132">Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="64b50-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="64b50-133">Compruebe que la Federación del servidor perimetral heredado está deshabilitada en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="64b50-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="64b50-134">Para configurar certificados en el servidor perimetral heredado</span><span class="sxs-lookup"><span data-stu-id="64b50-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="64b50-135">Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="64b50-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="64b50-136">En el servidor perimetral de Skype empresarial Server 2019 e importe el certificado externo del proxy de acceso del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="64b50-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="64b50-137">Asigne el certificado externo del proxy de acceso a la interfaz externa de Skype empresarial Server 2019 del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="64b50-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="64b50-138">El certificado de interfaz interno del servidor perimetral de Skype empresarial Server 2019 debe solicitarse a una entidad de certificación de confianza y asignarse.</span><span class="sxs-lookup"><span data-stu-id="64b50-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="64b50-139">Para cambiar la ruta de Federación de la versión anterior para usar Skype empresarial Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="64b50-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="64b50-140">Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, al nodo de **grupos de límites** .</span><span class="sxs-lookup"><span data-stu-id="64b50-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="64b50-141">Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b50-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="64b50-142">Seleccione **General** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="64b50-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="64b50-143">Active la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="64b50-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="64b50-144">En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="64b50-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="64b50-145">Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="64b50-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="64b50-146">Compruebe que la **Federación (puerto 5061)** está **habilitada** en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="64b50-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="64b50-147">Para actualizar el próximo salto de la Federación de Skype empresarial Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="64b50-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="64b50-148">Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, al nodo de **grupos de límites** .</span><span class="sxs-lookup"><span data-stu-id="64b50-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="64b50-149">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b50-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="64b50-150">En la página **General** , en **selección del próximo salto**, seleccione de la lista desplegable el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="64b50-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="64b50-151">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="64b50-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="64b50-152">En el **generador de topologías**, seleccione el nodo principal de **Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="64b50-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="64b50-153">En el menú **acción** , haga clic en **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="64b50-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="64b50-154">Para configurar la ruta multimedia de salida de Skype empresarial Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="64b50-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="64b50-155">Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, a la sección de **servidores de aplicaciones para usuario de la versión Standard Edition** o a la de las **agrupaciones front-end Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="64b50-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="64b50-156">Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b50-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="64b50-157">En la sección **asociaciones** , active la casilla **asociar grupo perimetral (para componentes multimedia)** .</span><span class="sxs-lookup"><span data-stu-id="64b50-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="64b50-158">En el cuadro desplegable, seleccione el servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64b50-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="64b50-159">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="64b50-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="64b50-160">Para activar la Federación de servidores perimetrales de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="64b50-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="64b50-161">Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, al nodo de **grupos de límites** .</span><span class="sxs-lookup"><span data-stu-id="64b50-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="64b50-162">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b50-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="64b50-163">La Federación solo se puede habilitar para un único grupo de borde.</span><span class="sxs-lookup"><span data-stu-id="64b50-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="64b50-164">Si tiene varios grupos de límites, seleccione uno para usarlo como el grupo de servidores perimetrales de Federación.</span><span class="sxs-lookup"><span data-stu-id="64b50-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="64b50-165">En la página **General** , compruebe que la casilla **de verificación Habilitar la Federación para este grupo perimetral (puerto 5061)** está activada.</span><span class="sxs-lookup"><span data-stu-id="64b50-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="64b50-166">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="64b50-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="64b50-167">Vaya al nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="64b50-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="64b50-168">Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="64b50-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="64b50-169">En el panel de la izquierda, haga clic en **ruta de Federación**.</span><span class="sxs-lookup"><span data-stu-id="64b50-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="64b50-170">En **asignación de ruta de Federación de sitios**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64b50-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="64b50-171">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="64b50-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="64b50-172">Para implementaciones de varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="64b50-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="64b50-173">Para publicar cambios en la configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="64b50-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="64b50-174">En el **generador de topologías**, seleccione el nodo principal de **Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="64b50-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="64b50-175">En el menú **acción** , seleccione **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="64b50-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="64b50-176">Espere a que se produzca la replicación de Active Directory en todos los grupos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="64b50-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64b50-177">Es posible que vea el siguiente mensaje: **ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la Federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de forma simultánea (es decir, no un escenario de migración), compruebe que todos los socios federados usen Skype empresarial Server. Compruebe que el registro SRV de DNS externo muestra todos los servidores perimetrales habilitados para la Federación.**</span><span class="sxs-lookup"><span data-stu-id="64b50-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="64b50-178">Esta advertencia es esperada y puede ignorarse de forma segura.</span><span class="sxs-lookup"><span data-stu-id="64b50-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="64b50-179">Para configurar el servidor EDGE 2019 de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="64b50-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="64b50-180">Conecte todos los servidores perimetrales de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64b50-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="64b50-181">Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar el tráfico SIP para acceso externo (generalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Skype empresarial Server 2019, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="64b50-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64b50-182">Si no tiene un equilibrador de carga de hardware, tendrá que actualizar el registro a de DNS para que la Federación se resuelva en el nuevo servidor perimetral de acceso de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="64b50-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="64b50-183">Para lograr esto con una interrupción mínima, reduzca el valor de TLL para el FQDN del perímetro externo de acceso de Skype empresarial Server de modo que, cuando se actualice DNS para que apunte al nuevo servidor perimetral de acceso de Skype empresarial, la Federación y el acceso remoto se actualizarán rápidamente.</span><span class="sxs-lookup"><span data-stu-id="64b50-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="64b50-184">Detenga el **acceso perimetral de Skype empresarial Server** desde cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="64b50-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="64b50-185">Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="64b50-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="64b50-186">En la lista servicios, busque la **tecnología perimetral de acceso de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="64b50-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="64b50-187">Haga clic con el botón secundario en el nombre de servicios y, a continuación, seleccione **detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="64b50-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="64b50-188">Establezca el tipo de inicio en **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="64b50-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="64b50-189">Haga clic en **Aceptar** para cerrar la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="64b50-189">Click **OK** to close the **Properties** window.</span></span> 
    

