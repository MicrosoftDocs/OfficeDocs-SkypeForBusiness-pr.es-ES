---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto, debe realizar la transición de la ruta de Federación de los servidores perimetrales de versiones anteriores a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754040"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="2223e-104">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="2223e-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="2223e-105">La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes.</span><span class="sxs-lookup"><span data-stu-id="2223e-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="2223e-106">Después de migrar al grupo piloto, debe realizar la transición de la ruta de Federación de los servidores perimetrales de la versión anterior a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2223e-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="2223e-107">Use los siguientes procedimientos para realizar la transición de la ruta de Federación y la ruta de tráfico de medios desde el servidor perimetral y el director de la versión anterior a su servidor perimetral de Skype empresarial Server 2019 para una implementación en un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="2223e-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2223e-108">Para cambiar la ruta de Federación y la ruta de tráfico de medios es necesario programar el tiempo de inactividad de mantenimiento para los servidores perimetrales de Skype empresarial Server 2019 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="2223e-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="2223e-109">Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="2223e-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="2223e-110">Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2223e-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="2223e-111">También debe notificar esta acción a los usuarios finales con antelación suficiente.</span><span class="sxs-lookup"><span data-stu-id="2223e-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="2223e-112">Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="2223e-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2223e-113">Si el servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="2223e-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="2223e-114">Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios y, a continuación, retirar el servidor perimetral de las versiones anteriores antes de habilitar la Federación en el servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2223e-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2223e-115">Si la Federación de XMPP se enruta a través de un servidor perimetral de Skype empresarial Server 2019, los usuarios de la versión anterior no podrán comunicarse con el socio federado de XMPP hasta que todos los usuarios se hayan movido a Skype empresarial Server 2019, se hayan configurado las directivas y los certificados de XMPP, el socio federado de XMPP se ha configurado en Skype empresarial Server 2019 y, por último, se han actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="2223e-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="2223e-116">Para quitar la Asociación de Federación heredada de los sitios de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="2223e-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="2223e-117">En el servidor front-end de Skype empresarial Server 2019, abra la topología existente en Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="2223e-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="2223e-118">En el panel izquierdo, vaya al nodo del sitio, que se encuentra justo debajo **de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="2223e-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="2223e-119">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="2223e-120">En el panel izquierdo, seleccione **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="2223e-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="2223e-121">En **asignación de ruta de Federación del sitio**, desactive la casilla **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="2223e-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="2223e-122">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="2223e-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="2223e-123">En **generador de topologías**, seleccione el nodo superior de **Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="2223e-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="2223e-124">En el menú **Acción**, haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="2223e-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="2223e-125">Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando se haya completado el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="2223e-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="2223e-126">Para configurar el servidor perimetral como servidor perimetral no federado</span><span class="sxs-lookup"><span data-stu-id="2223e-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="2223e-127">En el panel izquierdo, vaya al nodo instalación heredada y, a continuación, al nodo grupos de servidores **perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="2223e-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2223e-128">Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2223e-129">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="2223e-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="2223e-130">Desactive la casilla de verificación **Habilitar la Federación para este grupo de servidores perimetrales (puerto 5061)** y seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="2223e-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="2223e-131">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2223e-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2223e-132">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="2223e-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="2223e-133">Compruebe que la Federación del servidor perimetral heredado está deshabilitada en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="2223e-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="2223e-134">Para configurar certificados en el servidor perimetral heredado</span><span class="sxs-lookup"><span data-stu-id="2223e-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="2223e-135">Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="2223e-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="2223e-136">En el servidor perimetral de Skype empresarial Server 2019 e importe el certificado externo del servidor proxy de acceso del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="2223e-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="2223e-137">Asigne el certificado externo del proxy de acceso a la interfaz externa de Skype empresarial Server 2019 del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2223e-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="2223e-138">El certificado de interfaz interno del servidor perimetral de Skype empresarial Server 2019 debe solicitarse a una entidad de certificación de confianza y asignarse.</span><span class="sxs-lookup"><span data-stu-id="2223e-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="2223e-139">Para cambiar la ruta de Federación de la versión anterior para usar el servidor perimetral de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="2223e-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="2223e-140">En generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al nodo grupos de servidores **perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="2223e-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2223e-141">Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2223e-142">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="2223e-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="2223e-143">Active la casilla habilitar la **Federación para este grupo de servidores perimetrales (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="2223e-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="2223e-144">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2223e-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2223e-145">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="2223e-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="2223e-146">Compruebe que la **Federación (puerto 5061)** esté **habilitada** en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="2223e-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="2223e-147">Para actualizar el próximo salto de la Federación del servidor perimetral de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="2223e-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="2223e-148">En generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al nodo grupos de servidores **perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="2223e-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2223e-149">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="2223e-150">En la página **General** , en **selección**de próximo salto, seleccione en la lista desplegable el grupo de servidores de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2223e-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="2223e-151">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="2223e-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="2223e-152">En **generador de topologías**, seleccione el nodo superior de **Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="2223e-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="2223e-153">En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="2223e-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="2223e-154">Para configurar la ruta de medios de salida del servidor perimetral de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="2223e-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="2223e-155">En el generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al grupo de servidores que se encuentra debajo de **servidores front-end Standard Edition** o **grupos de servidores front-end Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="2223e-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="2223e-156">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2223e-157">En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="2223e-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="2223e-158">En el cuadro desplegable, seleccione el servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2223e-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="2223e-159">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="2223e-160">Para activar la Federación del servidor perimetral de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="2223e-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="2223e-161">En generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al nodo grupos de servidores **perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="2223e-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2223e-162">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2223e-163">La Federación solo se puede habilitar para un único grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="2223e-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="2223e-164">Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación.</span><span class="sxs-lookup"><span data-stu-id="2223e-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="2223e-165">En la página **General** , compruebe que la casilla de verificación **Habilitar la Federación para este grupo de servidores perimetrales (puerto 5061)** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2223e-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="2223e-166">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="2223e-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="2223e-167">Navegue hasta el nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="2223e-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="2223e-168">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="2223e-169">En el panel izquierdo, haga clic en **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="2223e-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="2223e-170">En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Skype empresarial Server 2019 que aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="2223e-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="2223e-171">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="2223e-172">Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="2223e-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="2223e-173">Para publicar cambios de configuración en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="2223e-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="2223e-174">En **generador de topologías**, seleccione el nodo superior de **Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="2223e-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="2223e-175">En el menú **Acción**, seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="2223e-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="2223e-176">Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="2223e-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2223e-177">Es posible que vea el siguiente mensaje de error: **ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría un servidor perimetral de forma activa para la Federación. Compruebe que el registro SRV de DNS externo apunte al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de manera simultánea (es decir, no es un escenario de migración), compruebe que todos los socios federados usan Skype empresarial Server. Compruebe que el registro SRV de DNS externo muestre todos los servidores perimetrales habilitados para la Federación.**</span><span class="sxs-lookup"><span data-stu-id="2223e-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="2223e-178">Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.</span><span class="sxs-lookup"><span data-stu-id="2223e-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="2223e-179">Para configurar el servidor perimetral de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="2223e-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="2223e-180">Conecte todos los servidores perimetrales de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2223e-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="2223e-181">Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Skype empresarial Server 2019, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="2223e-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2223e-182">Si no dispone de un equilibrador de carga de hardware, debe actualizar el registro a de DNS para que la Federación se resuelva en el nuevo servidor perimetral de acceso de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2223e-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="2223e-183">Para lograr esto con una interrupción mínima, reduzca el valor de TLL para el FQDN del servidor perimetral de acceso de Skype empresarial Server externo de modo que, cuando se actualice el DNS para que apunte al nuevo servidor perimetral de acceso de Skype empresarial Server, la Federación y el acceso remoto se actualizarán rápidamente.</span><span class="sxs-lookup"><span data-stu-id="2223e-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="2223e-184">Detenga el **servidor perimetral de acceso de Skype empresarial Server** de cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2223e-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="2223e-185">Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="2223e-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="2223e-186">En la lista de servicios, busque **servidor perimetral de acceso de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="2223e-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="2223e-187">Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="2223e-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="2223e-188">Establezca el Tipo de inicio en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="2223e-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="2223e-189">Haga clic en **Aceptar** para cerrar la ventana **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2223e-189">Click **OK** to close the **Properties** window.</span></span> 
    

