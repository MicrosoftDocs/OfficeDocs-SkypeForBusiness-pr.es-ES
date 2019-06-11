---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842784"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="56be8-102">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="56be8-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="56be8-103">La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red.</span><span class="sxs-lookup"><span data-stu-id="56be8-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="56be8-104">Después de migrar a su grupo piloto de Lync Server 2013, tendrá que realizar una transición de la ruta de Federación de los servidores perimetrales de Microsoft Office Communications Server 2007 R2 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56be8-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="56be8-105">Use los procedimientos que se describen a continuación para realizar la transición de la ruta de Federación y la ruta de tráfico multimedia desde el servidor perimetral de Office Communications Server 2007 R2 y el director a su servidor perimetral de Lync Server 2013, para una implementación de un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="56be8-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="56be8-106">Cambiar la ruta de Federación y la ruta del tráfico multimedia requiere que programe el tiempo de mantenimiento de los servidores perimetrales de Lync Server 2013 y de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="56be8-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="56be8-107">Todo este proceso de transición también significa que el acceso federado no estará disponible durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="56be8-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="56be8-108">Debe programar el tiempo de inactividad para una hora en la que espera una actividad mínima de usuario.</span><span class="sxs-lookup"><span data-stu-id="56be8-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="56be8-109">También debe proporcionar una notificación suficiente a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="56be8-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="56be8-110">Planee en consecuencia para esta interrupción y establezca las expectativas apropiadas dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="56be8-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="56be8-111">Si el servidor perimetral de Office Communications Server 2007 R2 heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral a/V, los procedimientos de esta sección para realizar la transición de la configuración de Federación a un servidor de Lync 2013 servidor perimetral no es compatible.</span><span class="sxs-lookup"><span data-stu-id="56be8-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="56be8-112">Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Office Communications Server 2007 R2 a Lync Server 2013 y, después, retirar el servidor perimetral de Office Communications Server 2007 R2 antes de habilitar la Federación en Servidor perimetral 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56be8-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="56be8-113">Para obtener más información, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="56be8-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="56be8-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Mover los usuarios restantes a Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="56be8-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="56be8-115">"Quitar los servidores y roles de servidor" en<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="56be8-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="56be8-116">Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Office Communications Server 2007 R2 no podrán comunicarse con el socio de XMPP federado hasta que todos los usuarios hayan movido a Lync Server 2013, directivas XMPP y se han configurado certificados, el socio XMPP federado se ha configurado en Lync Server 2013 y, por último, se han actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="56be8-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="56be8-117">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="56be8-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="56be8-118">También es posible delegar los derechos de usuario y permisos adecuados para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="56be8-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="56be8-119">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="56be8-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="56be8-120">Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="56be8-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="56be8-121">Para quitar la Asociación de Federación heredada de sitios de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="56be8-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="56be8-122">Abra la topología de la agrupación piloto con el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="56be8-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="56be8-123">En el panel de la izquierda, vaya al nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="56be8-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="56be8-124">Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="56be8-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="56be8-125">Seleccione **ruta de Federación** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="56be8-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="56be8-126">En asignación de enrutamiento de Federación de sitios, desactive la casilla situada junto a **Habilitar la Federación SIP** para deshabilitar la ruta de Federación a través de la **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="56be8-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="56be8-127">![Editar propiedades, ruta de Federación] (images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Editar propiedades, ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="56be8-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="56be8-128">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="56be8-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="56be8-129">En el **generador**de topologías, seleccione el nodo de nivel superior de **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56be8-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="56be8-130">En el menú **acción** , haga clic en **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="56be8-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="56be8-131">Para configurar el servidor perimetral heredado como servidor perimetral de no Federación</span><span class="sxs-lookup"><span data-stu-id="56be8-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="56be8-132">Desde el **generador**de topologías, en el menú **acción** haga clic en **combinar topología de Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="56be8-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="56be8-133">Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="56be8-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="56be8-134">En la **configuración de especificar Edge**, seleccione el **FQDN interno del servidor perimetral** que está configurado actualmente para la Federación y, a continuación, haga clic en **cambiar**.</span><span class="sxs-lookup"><span data-stu-id="56be8-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="56be8-135">![Combinar OCS 2007 R2 Topology, especificar configuración perimetral] (images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Combinar OCS 2007 R2 Topology, especificar configuración perimetral")</span><span class="sxs-lookup"><span data-stu-id="56be8-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="56be8-136">Haga clic en **siguiente** y acepte la configuración predeterminada hasta llegar a la página **especificar borde externo** :</span><span class="sxs-lookup"><span data-stu-id="56be8-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="56be8-137">El ![generador de topología especifica la página de borde externo] El (images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "generador de topología especifica la página de borde externo")</span><span class="sxs-lookup"><span data-stu-id="56be8-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="56be8-138">En **especificar borde externo**, desactive la casilla **este grupo perimetral se usa para la Federación y la conectividad de mensajería instantánea pública** .</span><span class="sxs-lookup"><span data-stu-id="56be8-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="56be8-139">Esto quitará la Asociación de Federación con el BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="56be8-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56be8-140">Este paso es importante.</span><span class="sxs-lookup"><span data-stu-id="56be8-140">This step is important.</span></span> <span data-ttu-id="56be8-141">Debe desactivar esta opción para quitar la Asociación de Federación heredada.</span><span class="sxs-lookup"><span data-stu-id="56be8-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="56be8-142">Haga clic en **siguiente** y acepte la configuración predeterminada de las páginas restantes del asistente.</span><span class="sxs-lookup"><span data-stu-id="56be8-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="56be8-143">En **Resumen**, haga clic en **siguiente** para empezar a combinar las topologías.</span><span class="sxs-lookup"><span data-stu-id="56be8-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="56be8-144">En la columna **Estado** , compruebe que el valor es **correcto**y, a continuación, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="56be8-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="56be8-145">En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="56be8-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="56be8-146">Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="56be8-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="56be8-147">![Generador de topología con sitio que se muestra después de la combinación] (images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generador de topología con sitio que se muestra después de la combinación")</span><span class="sxs-lookup"><span data-stu-id="56be8-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="56be8-148">Tal como se muestra en la ilustración anterior, la **Federación SIP** , ubicada en asignación de la **ruta de Federación de sitios** , se establece en deshabilitado. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="56be8-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="56be8-149">Para configurar certificados en el servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56be8-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="56be8-150">Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="56be8-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="56be8-151">En el servidor perimetral de Lync Server 2013, importe el certificado externo del proxy de acceso del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="56be8-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="56be8-152">Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="56be8-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="56be8-153">El certificado de interfaz interno del servidor perimetral de Lync Server 2013 no debe cambiarse.</span><span class="sxs-lookup"><span data-stu-id="56be8-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="56be8-154">Para cambiar la ruta de Federación de Office Communications Server 2007 R2 para usar Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="56be8-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="56be8-155">En el servidor de Office Communications Server 2007 R2 Standard Edition o el servidor front-end, abra la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="56be8-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="56be8-156">En el panel izquierdo, expanda el nodo superior y, a continuación, haga clic con el botón derecho en el nodo del **bosque** .</span><span class="sxs-lookup"><span data-stu-id="56be8-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="56be8-157">Seleccione **propiedades**y, a continuación, haga clic en **propiedades globales**.</span><span class="sxs-lookup"><span data-stu-id="56be8-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="56be8-158">Haga clic en la pestaña **Federación** .</span><span class="sxs-lookup"><span data-stu-id="56be8-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="56be8-159">Active la casilla para habilitar la Federación y la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="56be8-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="56be8-160">Escriba el FQDN del servidor perimetral de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="56be8-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="56be8-161">![Propiedades globales de OCS, ficha Federación] (images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propiedades globales de OCS, ficha Federación")</span><span class="sxs-lookup"><span data-stu-id="56be8-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="56be8-162">Para activar la Federación de Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="56be8-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="56be8-163">Desde el generador de topologías, en el panel izquierdo, vaya al nodo de \*\*\*\* las agrupaciones perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56be8-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="56be8-164">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="56be8-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="56be8-165">La Federación solo se puede habilitar para un único grupo de borde.</span><span class="sxs-lookup"><span data-stu-id="56be8-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="56be8-166">Si tiene varios grupos de límites, seleccione uno para usarlo como el grupo de servidores perimetrales de Federación.</span><span class="sxs-lookup"><span data-stu-id="56be8-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="56be8-167">En la página **General** , active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** .</span><span class="sxs-lookup"><span data-stu-id="56be8-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="56be8-168">![Editar propiedades, general, habilitar Federación perimetral] (images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propiedades, general, habilitar Federación perimetral")</span><span class="sxs-lookup"><span data-stu-id="56be8-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="56be8-169">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="56be8-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="56be8-170">A continuación, vaya al nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="56be8-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="56be8-171">Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="56be8-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="56be8-172">En el panel de la izquierda, haga clic en **ruta de Federación**.</span><span class="sxs-lookup"><span data-stu-id="56be8-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="56be8-173">En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, en la lista, seleccione el servidor perimetral 2013 de Lync Server en la lista.</span><span class="sxs-lookup"><span data-stu-id="56be8-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="56be8-174">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="56be8-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="56be8-175">![Editar propiedades, general, asociar grupo Edge] (images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propiedades, general, asociar grupo Edge")</span><span class="sxs-lookup"><span data-stu-id="56be8-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="56be8-176">Para implementaciones de varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="56be8-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="56be8-177">Para configurar la ruta multimedia de salida de Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="56be8-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="56be8-178">Desde el **generador**de topologías, vaya al grupo de servidores de Lync Server 2013, debajo de **los servidores de aplicaciones para** el usuario de la edición Standard o **Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="56be8-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="56be8-179">Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="56be8-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="56be8-180">En la sección **asociaciones** , active la casilla **asociar grupo perimetral (para componentes multimedia)** .</span><span class="sxs-lookup"><span data-stu-id="56be8-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="56be8-181">En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56be8-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="56be8-182">![Cuadro de diálogo Editar propiedades, asociar grupo perimetral] (images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Cuadro de diálogo Editar propiedades, asociar grupo perimetral")</span><span class="sxs-lookup"><span data-stu-id="56be8-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="56be8-183">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="56be8-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="56be8-184">Para publicar cambios en la configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="56be8-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="56be8-185">En el **generador**de topologías, seleccione el nodo de nivel superior de **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56be8-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="56be8-186">En el menú **acción** , seleccione **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="56be8-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="56be8-187">Espere a que se produzca la replicación de Active Directory en todos los grupos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="56be8-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="56be8-188">Es posible que vea el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="56be8-188">You may see the following message:</span></span><BR><span data-ttu-id="56be8-189"><STRONG>ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la Federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de forma simultánea (es decir, no un escenario de migración), compruebe que todos los socios federados usen Office Communications Server 2007 R2 o Lync Server. Compruebe que el registro SRV de DNS externo muestra todos los servidores perimetrales habilitados para la Federación.</STRONG></span><span class="sxs-lookup"><span data-stu-id="56be8-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="56be8-190">Esta advertencia es esperada y puede ignorarse de forma segura.</span><span class="sxs-lookup"><span data-stu-id="56be8-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="56be8-191">Para comprobar la Federación y el acceso remoto para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="56be8-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="56be8-192">En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56be8-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="56be8-193">Para comprobar el estado de la Federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56be8-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="56be8-194">Para habilitar la Federación y el acceso remoto, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56be8-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="56be8-195">Para obtener más información sobre estos cmdlets, vea los siguientes temas: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) y [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="56be8-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="56be8-196">Espere hasta que se haya completado la replicación antes de conectar los servidores perimetrales de Lync Server 2013 y pruebe la Federación y el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="56be8-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="56be8-197">Para configurar el servidor perimetral 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="56be8-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="56be8-198">Conecte todos los servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56be8-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="56be8-199">Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar el tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="56be8-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="56be8-200">Si no tiene un equilibrador de carga de hardware, tendrá que actualizar el registro A de DNS para que la Federación resuelva el nuevo servidor perimetral de acceso de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56be8-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="56be8-201">Para lograr esto con el mínimo de interrupciones, reduzca el valor de TTL para el FQDN de perimetral de acceso de Lync Server externo de modo que, cuando se actualice DNS para que apunte al nuevo servidor perimetral de acceso de Lync Server, la Federación y el acceso remoto se actualizarán rápidamente.</span><span class="sxs-lookup"><span data-stu-id="56be8-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="56be8-202">Después, detenga la aplicación **perimetral de acceso de Lync Server** desde cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="56be8-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="56be8-203">Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="56be8-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="56be8-204">En la lista servicios, busque **Office Communications Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="56be8-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="56be8-205">Haga clic con el botón secundario en el nombre de servicios y, a continuación, seleccione **detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="56be8-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="56be8-206">Establezca el tipo de inicio \*\*\*\* en deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="56be8-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="56be8-207">Haga clic en **Aceptar** para cerrar la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="56be8-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="56be8-208">Para probar la conectividad de usuarios externos y acceso externo</span><span class="sxs-lookup"><span data-stu-id="56be8-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="56be8-209">Usuarios de al menos un dominio federado, un usuario interno de Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="56be8-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="56be8-210">Prueba la mensajería instantánea (mi), la presencia, el audio/vídeo (A/V) y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="56be8-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="56be8-211">Los usuarios de cada proveedor de servicios de mensajería instantánea pública que su organización admita (y para el que se haya completado el aprovisionamiento) se comuniquen con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="56be8-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="56be8-212">Comprobar que los usuarios anónimos pueden unirse a conferencias.</span><span class="sxs-lookup"><span data-stu-id="56be8-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="56be8-213">Un usuario alojado en Office Communications Server 2007 R2 con acceso de usuario remoto (que inicia sesión en Office Communications Server 2007 R2 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="56be8-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="56be8-214">Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="56be8-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="56be8-215">Un usuario hospedado en Lync Server 2013 con acceso de usuario remoto (iniciar sesión en Lync Server 2013 desde fuera de la intranet pero sin conexión VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="56be8-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="56be8-216">Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="56be8-216">Test IM, presence, A/V, and desktop sharing.</span></span>

