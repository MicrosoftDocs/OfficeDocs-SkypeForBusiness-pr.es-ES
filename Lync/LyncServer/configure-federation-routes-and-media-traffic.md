---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="e7852-102">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="e7852-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7852-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="e7852-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="e7852-104">La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red.</span><span class="sxs-lookup"><span data-stu-id="e7852-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="e7852-105">Después de migrar a su grupo piloto de Lync Server 2013, tendrá que realizar una transición de la ruta de Federación de sus servidores perimetrales de Lync Server 2010 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7852-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="e7852-106">Use los procedimientos siguientes para realizar la transición de la ruta de Federación y la ruta de tráfico multimedia desde el servidor perimetral de Lync Server 2010 y el director a su servidor perimetral de Lync Server 2013, para una implementación de un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="e7852-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7852-107">Cambiar la ruta de Federación y la ruta del tráfico multimedia requiere que programe el tiempo de mantenimiento de los servidores perimetrales de Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e7852-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="e7852-108">Todo este proceso de transición también significa que el acceso federado no estará disponible durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="e7852-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="e7852-109">Debe programar el tiempo de inactividad para una hora en la que espera una actividad mínima de usuario.</span><span class="sxs-lookup"><span data-stu-id="e7852-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="e7852-110">También debe proporcionar una notificación suficiente a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="e7852-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="e7852-111">Planee en consecuencia para esta interrupción y establezca las expectativas apropiadas dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="e7852-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7852-112">Si su servidor perimetral antiguo de Lync Server 2010 está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral a/V, no se admiten los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="e7852-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="e7852-113">Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Lync Server 2010 a Lync Server 2013 y, después, retirar el servidor perimetral de Lync Server 2010 antes de habilitar la Federación en el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7852-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7852-114">Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Lync Server 2010 no podrán comunicarse con el socio federado del XMPP hasta que todos los usuarios hayan pasado a Lync Server 2013, las directivas XMPP y los certificados se han configurado, el socio de XMPP federado se ha configurado en Lync Server 2013 y, por último, se han actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="e7852-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="e7852-115">Para quitar la Asociación de Federación heredada de sitios de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7852-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="e7852-116">En el servidor front-end de Lync Server 2013, abra la topología existente en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="e7852-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="e7852-117">En el panel de la izquierda, vaya al nodo del sitio, que se encuentra directamente debajo de **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7852-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="e7852-118">Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7852-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="e7852-119">En el panel de la izquierda, seleccione **ruta de Federación**.</span><span class="sxs-lookup"><span data-stu-id="e7852-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="e7852-120">En **asignación de ruta de Federación de sitios**, desactive la casilla de verificación **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e7852-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="e7852-121">![Cuadro de diálogo Editar propiedades, página Ruta de Federación](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="e7852-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="e7852-122">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="e7852-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="e7852-123">En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7852-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="e7852-124">En el menú **acción** , haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="e7852-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="e7852-125">Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando se haya completado el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="e7852-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="e7852-126">Para configurar el servidor perimetral heredado como servidor perimetral de no Federación</span><span class="sxs-lookup"><span data-stu-id="e7852-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="e7852-127">En el panel de la izquierda, vaya al nodo de **2010 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="e7852-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="e7852-128">Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7852-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e7852-129">Seleccione **General** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="e7852-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="e7852-130">Desactive la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="e7852-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="e7852-131">![Editar propiedades, general, habilitar la Federación](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propiedades, general, habilitar la Federación")</span><span class="sxs-lookup"><span data-stu-id="e7852-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="e7852-132">En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7852-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e7852-133">Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e7852-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="e7852-134">Comprobar que la Federación del servidor perimetral heredado está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e7852-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="e7852-135">![Generador de topología, grupo Edge, Federación deshabilitada](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generador de topología, grupo Edge, Federación deshabilitada")</span><span class="sxs-lookup"><span data-stu-id="e7852-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="e7852-136">Para configurar certificados en el servidor perimetral de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e7852-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="e7852-137">Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e7852-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="e7852-138">En el servidor perimetral de Lync Server 2013, importe el certificado externo del proxy de acceso del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="e7852-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="e7852-139">Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e7852-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="e7852-140">Debe solicitarse el certificado de interfaz interno del servidor perimetral de Lync Server 2013 de una entidad de certificación de confianza y se asignará.</span><span class="sxs-lookup"><span data-stu-id="e7852-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="e7852-141">Para cambiar la ruta de Federación de Lync Server 2010 para usar Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="e7852-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e7852-142">Desde el generador de topologías, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="e7852-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="e7852-143">Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7852-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e7852-144">Seleccione **General** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="e7852-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="e7852-145">Seleccione la entrada de la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="e7852-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="e7852-146">![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")</span><span class="sxs-lookup"><span data-stu-id="e7852-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="e7852-147">En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7852-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e7852-148">Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e7852-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="e7852-149">Comprobar la **Federación (el puerto 5061)** está **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="e7852-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="e7852-150">![Generador de topología, grupo Edge, Federación habilitada](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generador de topología, grupo Edge, Federación habilitada")</span><span class="sxs-lookup"><span data-stu-id="e7852-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="e7852-151">Para actualizar el próximo salto de la Federación de Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="e7852-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="e7852-152">Desde el generador de topologías, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="e7852-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="e7852-153">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7852-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e7852-154">En la página **General** , en **selección del próximo salto**, seleccione de la lista desplegable el grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e7852-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="e7852-155">![Cuadro de diálogo Editar propiedades, página de salto siguiente](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página de salto siguiente")</span><span class="sxs-lookup"><span data-stu-id="e7852-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="e7852-156">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="e7852-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="e7852-157">En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="e7852-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="e7852-158">En el menú **acción** , haga clic en **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="e7852-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="e7852-159">Para configurar la ruta multimedia de salida de Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="e7852-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="e7852-160">Desde el generador de topología, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, a los grupos de servidores de aplicaciones de usuario de la parte inferior **Standard Edition** o a los **grupos front-end de Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="e7852-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="e7852-161">Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7852-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e7852-162">En la sección **asociaciones** , active la casilla **asociar grupo perimetral (para componentes multimedia)** .</span><span class="sxs-lookup"><span data-stu-id="e7852-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="e7852-163">![Editar propiedades, general, asociar grupo Edge](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propiedades, general, asociar grupo Edge")</span><span class="sxs-lookup"><span data-stu-id="e7852-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="e7852-164">En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7852-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="e7852-165">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="e7852-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="e7852-166">Para activar la Federación de Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="e7852-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="e7852-167">Desde el generador de topologías, en el panel de la izquierda, vaya al nodo de **2013 de Lync Server** y, a continuación, al nodo de las **agrupaciones perimetrales** .</span><span class="sxs-lookup"><span data-stu-id="e7852-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="e7852-168">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7852-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7852-169">La Federación solo se puede habilitar para un único grupo de borde.</span><span class="sxs-lookup"><span data-stu-id="e7852-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="e7852-170">Si tiene varios grupos de límites, seleccione uno para usarlo como el grupo de servidores perimetrales de Federación.</span><span class="sxs-lookup"><span data-stu-id="e7852-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="e7852-171">En la página **General** , compruebe que la opción **Habilitar Federación para este grupo perimetral (puerto 5061)** esté activada.</span><span class="sxs-lookup"><span data-stu-id="e7852-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="e7852-172">![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")</span><span class="sxs-lookup"><span data-stu-id="e7852-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="e7852-173">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="e7852-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="e7852-174">A continuación, vaya al nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="e7852-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="e7852-175">Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7852-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="e7852-176">En el panel de la izquierda, haga clic en **ruta de Federación**.</span><span class="sxs-lookup"><span data-stu-id="e7852-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="e7852-177">En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, en la lista, seleccione el servidor perimetral 2013 de Lync Server en la lista.</span><span class="sxs-lookup"><span data-stu-id="e7852-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="e7852-178">![Editar propiedades, página de ruta de Federación](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propiedades, página de ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="e7852-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="e7852-179">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="e7852-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="e7852-180">Para implementaciones de varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="e7852-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="e7852-181">Para publicar cambios en la configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e7852-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="e7852-182">En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="e7852-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="e7852-183">En el menú **acción** , seleccione **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="e7852-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="e7852-184">Espere a que se produzca la replicación de Active Directory en todos los grupos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="e7852-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7852-185">Es posible que vea el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="e7852-185">You may see the following message:</span></span><BR><span data-ttu-id="e7852-186"><STRONG>ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la Federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de forma simultánea (es decir, no un escenario de migración), compruebe que todos los socios federados usen Lync Server. Compruebe que el registro SRV de DNS externo muestra todos los servidores perimetrales habilitados para la Federación.</STRONG></span><span class="sxs-lookup"><span data-stu-id="e7852-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="e7852-187">Esta advertencia es esperada y puede ignorarse de forma segura.</span><span class="sxs-lookup"><span data-stu-id="e7852-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="e7852-188">Para configurar el servidor perimetral 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7852-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e7852-189">Conecte todos los servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7852-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="e7852-190">Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar el tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="e7852-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7852-191">Si no tiene un equilibrador de carga de hardware, tendrá que actualizar el registro a de DNS para que la Federación se resuelva en el nuevo servidor perimetral de acceso de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7852-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="e7852-192">Para lograr esto con el mínimo de interrupciones, reduzca el valor de TLL del FQDN del perímetro externo de acceso de Lync Server para que cuando se actualice DNS para que apunte al nuevo perimetral de acceso de Lync Server, la Federación y el acceso remoto se actualizarán rápidamente.</span><span class="sxs-lookup"><span data-stu-id="e7852-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="e7852-193">Después, detenga la aplicación **perimetral de acceso de Lync Server** desde cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e7852-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="e7852-194">Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="e7852-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="e7852-195">En la lista servicios, busque **Lync Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="e7852-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="e7852-196">Haga clic con el botón secundario en el nombre de servicios y, a continuación, seleccione **detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="e7852-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="e7852-197">Establezca el tipo de inicio en **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="e7852-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="e7852-198">Haga clic en **Aceptar** para cerrar la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="e7852-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

