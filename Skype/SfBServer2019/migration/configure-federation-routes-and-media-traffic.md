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
description: La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto, debe realizar la transición de la ruta de federación de los servidores perimetrales de versiones anteriores a la ruta de federación de los servidores perimetrales de Skype Empresarial Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754040"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="c4d97-104">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="c4d97-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="c4d97-105">La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes.</span><span class="sxs-lookup"><span data-stu-id="c4d97-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="c4d97-106">Después de migrar al grupo piloto, debe realizar la transición de la ruta de federación de los servidores perimetrales de la versión anterior a la ruta de federación de los servidores perimetrales de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4d97-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="c4d97-107">Use los siguientes procedimientos para realizar la transición de la ruta de federación y la ruta de tráfico de medios desde el servidor perimetral y el director de la versión anterior al servidor perimetral de Skype Empresarial Server 2019, para una implementación de un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="c4d97-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c4d97-108">Cambiar la ruta de federación y la ruta de tráfico de medios requiere que programe el tiempo de inactividad de mantenimiento para los servidores perimetrales de Skype Empresarial Server 2019 y la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="c4d97-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="c4d97-109">Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="c4d97-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="c4d97-110">Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c4d97-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="c4d97-111">También debe notificar esta acción a los usuarios finales con antelación suficiente.</span><span class="sxs-lookup"><span data-stu-id="c4d97-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="c4d97-112">Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="c4d97-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c4d97-113">Si el servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="c4d97-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="c4d97-114">Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios y, a continuación, retirar las versiones anteriores del servidor perimetral antes de habilitar la federación en el servidor perimetral de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4d97-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c4d97-115">Si la federación XMPP se enruta a través de un servidor perimetral de Skype Empresarial Server 2019, los usuarios de la versión anterior no podrán comunicarse con el socio federado XMPP hasta que todos los usuarios se hayan movido a Skype Empresarial Server 2019, se hayan configurado directivas y certificados XMPP, el socio federado XMPP se ha configurado en Skype Empresarial Server 2019. y, por último, se han actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="c4d97-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="c4d97-116">Para quitar la asociación de federación heredada de los sitios de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c4d97-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="c4d97-117">En el servidor front-end de Skype Empresarial Server 2019, abra la topología existente en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="c4d97-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="c4d97-118">En el panel izquierdo, vaya al nodo de sitio, que se encuentra directamente debajo **de Skype Empresarial Server.**</span><span class="sxs-lookup"><span data-stu-id="c4d97-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="c4d97-119">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="c4d97-120">En el panel izquierdo, seleccione **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="c4d97-121">En **Asignación de ruta de federación de** sitio, desactive la casilla Habilitar federación **SIP** para deshabilitar la ruta de federación a través del entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="c4d97-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="c4d97-122">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="c4d97-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="c4d97-123">En **el Generador de topologías,** seleccione el nodo superior Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="c4d97-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="c4d97-124">En el menú **Acción**, haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="c4d97-125">Haga **clic en** Siguiente para completar  el proceso de publicación y, a continuación, haga clic en Finalizar cuando se haya completado el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="c4d97-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="c4d97-126">Para configurar el servidor perimetral como servidor perimetral no federado</span><span class="sxs-lookup"><span data-stu-id="c4d97-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="c4d97-127">En el panel izquierdo, vaya al nodo de instalación heredado y, a continuación, al nodo **de grupos de servidores** perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c4d97-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c4d97-128">Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="c4d97-129">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c4d97-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="c4d97-130">Desactive la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061)** y seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="c4d97-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="c4d97-131">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c4d97-132">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="c4d97-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="c4d97-133">Compruebe que la federación del servidor perimetral heredado está deshabilitada en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="c4d97-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="c4d97-134">Para configurar certificados en el servidor perimetral heredado</span><span class="sxs-lookup"><span data-stu-id="c4d97-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="c4d97-135">Exporte el certificado de proxy de acceso externo, con la clave privada, desde el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="c4d97-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="c4d97-136">En el servidor perimetral de Skype Empresarial Server 2019, e importe el certificado externo de proxy de acceso del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="c4d97-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="c4d97-137">Asigne el certificado externo de proxy de acceso a la interfaz externa de Skype Empresarial Server 2019 del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c4d97-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="c4d97-138">El certificado de interfaz interna del servidor perimetral de Skype Empresarial Server 2019 debe solicitarse a una CA de confianza y asignarse.</span><span class="sxs-lookup"><span data-stu-id="c4d97-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="c4d97-139">Para cambiar la ruta de federación de la versión anterior para usar el servidor perimetral de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c4d97-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="c4d97-140">En el Generador de topologías, en el panel izquierdo, vaya al nodo **de Skype Empresarial Server 2019** y, a continuación, al nodo grupos de **servidores** perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c4d97-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c4d97-141">Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="c4d97-142">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c4d97-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="c4d97-143">Active la casilla habilitar la federación para este grupo de servidores perimetrales **(puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="c4d97-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="c4d97-144">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c4d97-145">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="c4d97-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="c4d97-146">Compruebe que **la federación (puerto 5061)** está establecida en **Habilitado en** el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c4d97-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="c4d97-147">Para actualizar el próximo salto de federación del servidor perimetral de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c4d97-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="c4d97-148">En el Generador de topologías, en el panel izquierdo, vaya al nodo **de Skype Empresarial Server 2019** y, a continuación, al nodo grupos de **servidores** perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c4d97-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c4d97-149">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="c4d97-150">En la **página General,** **en** Selección del próximo salto, seleccione en la lista desplegable el grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4d97-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="c4d97-151">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="c4d97-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="c4d97-152">En **el Generador de topologías,** seleccione el nodo superior Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="c4d97-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="c4d97-153">En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="c4d97-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="c4d97-154">Para configurar la ruta de acceso de medios salientes del servidor perimetral de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c4d97-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="c4d97-155">En el Generador de topologías, en el panel izquierdo, vaya al nodo de Skype Empresarial **Server 2019** y, a continuación, al grupo de servidores que se encuentra debajo de los servidores **front-end Standard Edition** o los grupos de servidores **front-end Enterprise Edition.**</span><span class="sxs-lookup"><span data-stu-id="c4d97-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="c4d97-156">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="c4d97-157">En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="c4d97-158">En el cuadro desplegable, seleccione el servidor perimetral de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4d97-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="c4d97-159">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="c4d97-160">Para activar la federación del servidor perimetral de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c4d97-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="c4d97-161">En el Generador de topologías, en el panel izquierdo, vaya al nodo **de Skype Empresarial Server 2019** y, a continuación, al nodo grupos de **servidores** perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c4d97-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c4d97-162">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c4d97-163">La federación solo se puede habilitar para un único grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c4d97-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="c4d97-164">Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación.</span><span class="sxs-lookup"><span data-stu-id="c4d97-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="c4d97-165">En la **página General,** compruebe que la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061)** esté activada.</span><span class="sxs-lookup"><span data-stu-id="c4d97-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="c4d97-166">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="c4d97-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="c4d97-167">Vaya al nodo de sitio.</span><span class="sxs-lookup"><span data-stu-id="c4d97-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="c4d97-168">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="c4d97-169">En el panel izquierdo, haga clic en **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="c4d97-170">En **Asignación de ruta** de federación del sitio, seleccione Habilitar federación **SIP** y, a continuación, en la lista, seleccione el servidor perimetral de Skype Empresarial Server 2019 que aparece.</span><span class="sxs-lookup"><span data-stu-id="c4d97-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="c4d97-171">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="c4d97-172">Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="c4d97-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="c4d97-173">Para publicar cambios de configuración en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c4d97-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="c4d97-174">En **el Generador de topologías,** seleccione el nodo superior Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="c4d97-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="c4d97-175">En el menú **Acción**, seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="c4d97-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="c4d97-176">Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c4d97-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4d97-177">Es posible que vea el siguiente mensaje: **Advertencia: La topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (es decir, no un escenario de migración), compruebe que todos los socios federados usan Skype Empresarial Server. Compruebe que el registro SRV de DNS externo muestra todos los servidores perimetrales habilitados para federación.**</span><span class="sxs-lookup"><span data-stu-id="c4d97-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="c4d97-178">Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.</span><span class="sxs-lookup"><span data-stu-id="c4d97-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="c4d97-179">Para configurar el servidor perimetral de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c4d97-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="c4d97-180">Poner en línea todos los servidores perimetrales de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4d97-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="c4d97-181">Actualice las reglas de enrutamiento de firewall externo o la configuración del equilibrador de carga de hardware para enviar tráfico SIP para el acceso externo (normalmente el puerto 443) y la federación (normalmente el puerto 5061) al servidor perimetral de Skype Empresarial Server 2019, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="c4d97-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4d97-182">Si no tiene un equilibrador de carga de hardware, debe actualizar el registro A de DNS para que la federación se resuelva en el nuevo servidor perimetral de acceso de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c4d97-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="c4d97-183">Para lograr esto con una interrupción mínima, reduzca el valor de TLL para el FQDN perimetral de acceso externo de Skype Empresarial Server para que cuando se actualice DNS para que apunte al nuevo servidor perimetral de acceso de Skype Empresarial Server, la federación y el acceso remoto se actualizarán rápidamente.</span><span class="sxs-lookup"><span data-stu-id="c4d97-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="c4d97-184">Detenga el **servidor perimetral de acceso de Skype Empresarial Server** desde cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c4d97-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="c4d97-185">Desde cada equipo servidor perimetral heredado, abra el applet **Servicios** desde herramientas **administrativas.**</span><span class="sxs-lookup"><span data-stu-id="c4d97-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="c4d97-186">En la lista de servicios, busque **Skype Empresarial Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="c4d97-187">Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="c4d97-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="c4d97-188">Establezca el Tipo de inicio en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="c4d97-189">Haga clic en **Aceptar** para cerrar la ventana **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c4d97-189">Click **OK** to close the **Properties** window.</span></span> 
    

