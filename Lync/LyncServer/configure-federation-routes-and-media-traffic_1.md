---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754966"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="b9834-102">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="b9834-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="b9834-103">La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes.</span><span class="sxs-lookup"><span data-stu-id="b9834-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="b9834-104">Después de migrar al grupo piloto de Lync Server 2013, debe realizar la transición de la ruta de Federación de los servidores perimetrales de Microsoft Office Communications Server 2007 R2 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9834-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="b9834-105">Use los procedimientos que se describen a continuación para realizar la transición de la ruta de Federación y la ruta de tráfico de medios desde el servidor perimetral y el director de Office Communications Server 2007 R2 a su servidor perimetral de Lync Server 2013 para una implementación en un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="b9834-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="b9834-106">Para cambiar la ruta de Federación y la ruta de tráfico de medios es necesario programar el tiempo de inactividad de mantenimiento para los servidores perimetrales de Lync Server 2013 y Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b9834-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="b9834-107">Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="b9834-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="b9834-108">Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b9834-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="b9834-109">También debe notificar esta acción a los usuarios finales con antelación suficiente.</span><span class="sxs-lookup"><span data-stu-id="b9834-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="b9834-110">Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="b9834-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="b9834-111">Si el servidor perimetral de Office Communications Server 2007 R2 heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos de esta sección para realizar la transición de la configuración de Federación a un servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9834-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="b9834-112">Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Office Communications Server 2007 R2 a Lync Server 2013 y, a continuación, retirar el servidor perimetral de Office Communications Server 2007 R2 antes de habilitar la Federación en el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9834-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="b9834-113">Para obtener más información, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9834-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b9834-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Mover los usuarios restantes a Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="b9834-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="b9834-115">"Quitar servidores y roles de servidor" en<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="b9834-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="b9834-116">Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Office Communications Server 2007 R2 no podrán comunicarse con el socio federado de XMPP hasta que todos los usuarios se hayan movido a Lync Server 2013, se hayan configurado las directivas y los certificados XMPP, se haya configurado el socio federado de XMPP en Lync Server 2013 y se hayan actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="b9834-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="b9834-117">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, es necesario haber iniciado sesión como usuario miembro de los grupos Admins del dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b9834-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="b9834-118">También es posible delegar los derechos de usuario y los permisos adecuados para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="b9834-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="b9834-119">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b9834-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="b9834-120">Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b9834-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="b9834-121">Para quitar la asociación de federación heredada de los sitios de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9834-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="b9834-122">Abra la topología del grupo piloto en Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="b9834-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="b9834-123">En el panel izquierdo, vaya al nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="b9834-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="b9834-124">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b9834-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="b9834-125">Seleccione **Ruta de federación** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b9834-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="b9834-126">En Asignación de ruta de federación del sitio, desactive la casilla de verificación situada junto a **Habilitar federación SIP** para deshabilitar la ruta de federación mediante **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="b9834-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="b9834-127">![Cuadro de diálogo Editar propiedades, ruta de Federación](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Cuadro de diálogo Editar propiedades, ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="b9834-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="b9834-128">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="b9834-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="b9834-129">En **Topology Builder**, seleccione el nodo en primera posición **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b9834-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="b9834-130">En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="b9834-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="b9834-131">Para configurar el servidor perimetral heredado como servidor perimetral no federado</span><span class="sxs-lookup"><span data-stu-id="b9834-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="b9834-132">En **Generador de topologías**, en el menú **Acción**, haga clic en **Combinar la topología de Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="b9834-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="b9834-133">Haga clic en \*\*Siguiente \*\* para continuar.</span><span class="sxs-lookup"><span data-stu-id="b9834-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="b9834-134">En **Especificar configuración perimetral**, seleccione el **FQDN interno del servidor perimetral** que actualmente está configurado para la federación y, a continuación, haga clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="b9834-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="b9834-135">![Fusionar la topología de OCS 2007 R2, especificar la configuración perimetral](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Fusionar la topología de OCS 2007 R2, especificar la configuración perimetral")</span><span class="sxs-lookup"><span data-stu-id="b9834-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="b9834-136">Haga clic en **Siguiente** y acepte los valores predeterminados hasta llegar a la página **Especificar perímetro externo**:</span><span class="sxs-lookup"><span data-stu-id="b9834-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="b9834-137">![Página especificar borde externo en el generador de topologías](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Página especificar borde externo en el generador de topologías")</span><span class="sxs-lookup"><span data-stu-id="b9834-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="b9834-p105">En **Especificar perímetro externo**, desactive la casilla **Este grupo de servidores perimetrales se usa para federación y conectividad de mensajería instantánea pública**. Se quitará la asociación de federación con BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="b9834-p105">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b9834-p106">Este paso es importante. Debe desactivar esta opción para quitar la asociación de federación heredada.</span><span class="sxs-lookup"><span data-stu-id="b9834-p106">This step is important. You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="b9834-142">Haga clic en **Siguiente** y acepte los valores predeterminados de las demás páginas del asistente.</span><span class="sxs-lookup"><span data-stu-id="b9834-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="b9834-143">En **Resumen**, haga clic en **Siguiente** para comenzar a combinar las topologías.</span><span class="sxs-lookup"><span data-stu-id="b9834-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="b9834-144">En la columna **Estado** , compruebe que el valor sea **correcto**y, a continuación, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="b9834-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="b9834-145">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9834-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="b9834-146">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="b9834-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="b9834-147">![Generador de topologías con sitio mostrado después de la combinación](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generador de topologías con sitio mostrado después de la combinación")</span><span class="sxs-lookup"><span data-stu-id="b9834-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="b9834-148">Como se muestra en la figura anterior, la **federación SIP** ubicada en **Asignación de ruta de federación del sitio** está definida en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b9834-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="b9834-149">Para configurar certificados en el servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9834-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="b9834-150">Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="b9834-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="b9834-151">En el servidor perimetral de Lync Server 2013, importe el certificado externo del servidor proxy de acceso del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b9834-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="b9834-152">Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b9834-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="b9834-153">El certificado de interfaz interno del servidor perimetral de Lync Server 2013 no debe cambiarse.</span><span class="sxs-lookup"><span data-stu-id="b9834-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="b9834-154">Para cambiar la ruta de federación de Office Communications Server 2007 R2 para que use el servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9834-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="b9834-155">En el servidor de Office Communications Server 2007 R2 Standard Edition o el servidor front-end, abra la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b9834-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="b9834-p107">En el panel izquierdo, expanda el nodo en primera posición y, a continuación, haga clic con el botón secundario en el nodo **Bosque**. Seleccione **Propiedades** y haga clic en **Propiedades globales**.</span><span class="sxs-lookup"><span data-stu-id="b9834-p107">In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="b9834-158">Haga clic en la pestaña **Federación**.</span><span class="sxs-lookup"><span data-stu-id="b9834-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="b9834-159">Seleccione la casilla para habilitar la federación y la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="b9834-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="b9834-160">Escriba el FQDN del servidor perimetral de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b9834-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="b9834-161">![Propiedades globales de OCS, ficha Federación](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propiedades globales de OCS, ficha Federación")</span><span class="sxs-lookup"><span data-stu-id="b9834-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="b9834-162">Para activar la federación del servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9834-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="b9834-163">En generador de topologías, en el panel izquierdo, vaya al nodo grupos de servidores **perimetrales** de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9834-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="b9834-164">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b9834-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b9834-165">La Federación solo se puede habilitar para un único grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="b9834-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="b9834-166">Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación.</span><span class="sxs-lookup"><span data-stu-id="b9834-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="b9834-167">En la página **General**, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="b9834-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="b9834-168">![Editar propiedades, general, habilitar Federación perimetral](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propiedades, general, habilitar Federación perimetral")</span><span class="sxs-lookup"><span data-stu-id="b9834-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="b9834-169">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="b9834-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="b9834-170">A continuación, navegue hasta el nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="b9834-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="b9834-171">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b9834-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="b9834-172">En el panel izquierdo, haga clic en **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="b9834-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="b9834-173">En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Lync Server 2013 que aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="b9834-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="b9834-174">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b9834-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="b9834-175">![Editar propiedades, general, asociar grupo de servidores perimetrales](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propiedades, general, asociar grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="b9834-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="b9834-176">Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="b9834-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="b9834-177">Para configurar la ruta de medios de salida del servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9834-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="b9834-178">En el **generador de topologías**, navegue hasta el grupo de servidores de Lync Server 2013 debajo de **servidores front-end Standard Edition** o **grupos de servidores front-end Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="b9834-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="b9834-179">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b9834-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="b9834-180">En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="b9834-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="b9834-181">En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9834-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="b9834-182">![Cuadro de diálogo Editar propiedades, asociar grupo de servidores perimetrales](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Cuadro de diálogo Editar propiedades, asociar grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="b9834-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="b9834-183">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b9834-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="b9834-184">Para publicar cambios de configuración en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b9834-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="b9834-185">En **Generador de topologías**, seleccione el nodo en primera posición **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b9834-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="b9834-186">En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="b9834-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="b9834-187">Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b9834-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b9834-188">Es posible que aparezca el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9834-188">You may see the following message:</span></span><BR><span data-ttu-id="b9834-189"><STRONG>Advertencia: la topología contiene más de un servidor perimetral federado. Esta situación se puede producir durante la migración a una versión superior del producto. En ese caso, solo se usará activamente un servidor perimetral para la federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (no en un escenario de migración), asegúrese de que todos los socios federados usan Office Communications Server 2007 R2 o Lync Server, y compruebe que en el registro SRV de DNS externo se enumeran todos los servidores perimetrales habilitados para federación.</STRONG></span><span class="sxs-lookup"><span data-stu-id="b9834-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="b9834-190">Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.</span><span class="sxs-lookup"><span data-stu-id="b9834-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="b9834-191">Para comprobar la federación y el acceso remoto de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="b9834-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="b9834-192">En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9834-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="b9834-193">Para verificar el estado de federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9834-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="b9834-194">Para habilitar la federación y el acceso remoto, desde la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9834-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="b9834-195">Para obtener más información sobre estos cmdlets, consulte los siguientes temas: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) y [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="b9834-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="b9834-196">Espere hasta que se haya completado la replicación antes de poner en línea los servidores perimetrales de Lync Server 2013 y pruebe la Federación y el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="b9834-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="b9834-197">Para configurar el servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9834-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="b9834-198">Conecte todos los servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9834-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="b9834-199">Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="b9834-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b9834-p109">Si no tiene un equilibrador de cargas del hardware, tendrá que actualizar el registro A de DNS para que la federación resuelva el nuevo servidor perimetral de acceso Lync Server. Para realizar esta tarea con las mínimas molestias, reduzca el valor TTL del FQDN del servidor perimetral de acceso a Lync Server externo, de modo que cuando se actualice el DNS para apuntar al nuevo servidor perimetral de acceso a Lync Server, la federación y el acceso remoto se actualicen rápidamente.</span><span class="sxs-lookup"><span data-stu-id="b9834-p109">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="b9834-202">A continuación, detenga el **servidor perimetral de acceso de Lync Server** en cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b9834-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="b9834-203">Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="b9834-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="b9834-204">En la lista de servicios, busque **Servidor perimetral de acceso del servidor de Office Communications**.</span><span class="sxs-lookup"><span data-stu-id="b9834-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="b9834-205">Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="b9834-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="b9834-206">Establezca el Tipo de inicio en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b9834-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="b9834-207">Haga clic en **Aceptar** para cerrar la ventana **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b9834-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="b9834-208">Para comprobar la conectividad de los usuarios externos y el acceso externo</span><span class="sxs-lookup"><span data-stu-id="b9834-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="b9834-209">Usuarios de al menos un dominio federado, un usuario interno en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b9834-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="b9834-210">Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="b9834-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="b9834-211">Usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para los que se haya completado el aprovisionamiento) que se comuniquen con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b9834-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="b9834-212">Compruebe que los usuarios anónimos se pueden unir a las conferencias.</span><span class="sxs-lookup"><span data-stu-id="b9834-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="b9834-213">Un usuario hospedado en Office Communications Server 2007 R2 con acceso de usuarios remotos (inicio de sesión en Office Communications Server 2007 R2 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b9834-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="b9834-214">Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="b9834-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="b9834-215">Un usuario hospedado en Lync Server 2013 con acceso de usuarios remotos (iniciando sesión en Lync Server 2013 desde fuera de la intranet pero sin VPN) con un usuario en Lync Server 2013 y un usuario en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b9834-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="b9834-216">Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="b9834-216">Test IM, presence, A/V, and desktop sharing.</span></span>

