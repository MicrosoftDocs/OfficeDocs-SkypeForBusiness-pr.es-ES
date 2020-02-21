---
title: 'Lync Server 2013: configuración de la Federación de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea596f571064a3b72ecbb3b0c2b56c2179aa315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="21de2-102">Configuración de la Federación de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21de2-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21de2-103">_**Última modificación del tema:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="21de2-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="21de2-104">Si ya ha implementado los servidores perimetrales, la adición de las características de los escenarios federados será sencilla.</span><span class="sxs-lookup"><span data-stu-id="21de2-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="21de2-105">Si no ha configurado los servidores perimetrales, debe hacerlo primero.</span><span class="sxs-lookup"><span data-stu-id="21de2-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="21de2-106">Para obtener más información, consulte: [planeación del acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación e [implementación de acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="21de2-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21de2-p102">Si va a configurar cualquier combinación de federación XMPP, federación de Lync o conectividad de mensajería instantánea pública, puede implementarlas simultáneamente o una cada vez. Si configura las opciones mediante el generador de topologías y el shell de administración de Lync Server, y después ejecuta el asistente para la implementación en el servidor perimetral tras la configuración de las opciones de uno, dos o todos los tipos de federación, puede reducir el número de pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="21de2-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="21de2-109">Configuración de la federación de Lync en el Generador de topologías y en el Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="21de2-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="21de2-p103">En un servidor front-end, abra el Generador de topologías. Expanda los Grupos de servidores perimetrales y, a continuación, haga clic con el botón secundario en Servidor perimetral o Grupo de servidores perimetrales. Seleccione Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="21de2-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="21de2-p104">En Editar propiedades en General, seleccione Habilitar federación para este grupo de servidores perimetrales (Puerto 5061). Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="21de2-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="21de2-p105">Haga clic en Acción, seleccione Topología y, finalmente, Publicar. Cuando se le solicite en Publicar la topología, seleccione Siguiente. Una vez completado el proceso de publicación, haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="21de2-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="21de2-p106">En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en Instalar o en Actualizar Lync Server System y, a continuación, en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar nuevamente.</span><span class="sxs-lookup"><span data-stu-id="21de2-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="21de2-p107">En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="21de2-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="21de2-p108">Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="21de2-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="21de2-129">Configuración de la federación con socios</span><span class="sxs-lookup"><span data-stu-id="21de2-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="21de2-130">Para configurar correctamente una federación con otro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 u Office Communicator 2007, seleccione el tipo de Federación de la tabla siguiente y defina los registros DNS SRV, el host DNS (A o AAAA para IPv6) y configure las directivas aplicables al tipo de Federación:</span><span class="sxs-lookup"><span data-stu-id="21de2-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="21de2-131">Tipo de federación</span><span class="sxs-lookup"><span data-stu-id="21de2-131">Federation type</span></span></th>
    <th><span data-ttu-id="21de2-132">Registros DNS</span><span class="sxs-lookup"><span data-stu-id="21de2-132">DNS Records</span></span></th>
    <th><span data-ttu-id="21de2-133">Definición de directiva</span><span class="sxs-lookup"><span data-stu-id="21de2-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="21de2-134">Notas</span><span class="sxs-lookup"><span data-stu-id="21de2-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="21de2-135">Dominio de socio detectado</span><span class="sxs-lookup"><span data-stu-id="21de2-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="21de2-136">Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor de puerto para el registro SRV es TCP 5061 y el <strong>host que ofrece este servicio</strong> se define como SIP.</span><span class="sxs-lookup"><span data-stu-id="21de2-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="21de2-137">&lt;nombre&gt; de dominio externo: el FQDN del servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="21de2-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="21de2-138">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</span><span class="sxs-lookup"><span data-stu-id="21de2-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="21de2-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="21de2-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="21de2-p110">En las versiones anteriores, este tipo de federación se conocía como <strong>Federación abierta mejorada</strong>. La creación del registro SRV es obligatoria para este tipo de federación y permite que otros socios puedan detectar su federación.</span><span class="sxs-lookup"><span data-stu-id="21de2-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="21de2-143">Dominio de socio permitido</span><span class="sxs-lookup"><span data-stu-id="21de2-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="21de2-144">Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor de puerto para el registro SRV es TCP 5061 y el <strong>host que ofrece este servicio</strong> se define como SIP.</span><span class="sxs-lookup"><span data-stu-id="21de2-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="21de2-145">&lt;nombre&gt; de dominio externo: el FQDN del servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="21de2-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="21de2-146">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</span><span class="sxs-lookup"><span data-stu-id="21de2-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="21de2-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="21de2-148">Las versiones anteriores hacían referencia a este tipo de Federación como <strong>Federación mejorada</strong>.</span><span class="sxs-lookup"><span data-stu-id="21de2-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="21de2-149">La creación del registro SRV es opcional para este tipo de federación y permite que otros socios puedan detectar su federación.</span><span class="sxs-lookup"><span data-stu-id="21de2-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="21de2-150">Por ello, se trata de una <strong>Federación abierta mejorada</strong> o de un <strong>Dominio de socio detectado</strong>.</span><span class="sxs-lookup"><span data-stu-id="21de2-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="21de2-151">Servidor de socio permitido</span><span class="sxs-lookup"><span data-stu-id="21de2-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="21de2-152">Configure el nombre de dominio SIP y el FQDN del servidor perimetral de asociados como asociado de Federación en las directivas</span><span class="sxs-lookup"><span data-stu-id="21de2-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="21de2-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="21de2-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="21de2-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="21de2-p113">Este tipo de federación es la definición de una relación unilateral y no permite la detección de otros socios de federación. Cada socio de federación está configurado específicamente. En versiones anteriores, esto se conocía como <strong>Federación directa</strong>.</span><span class="sxs-lookup"><span data-stu-id="21de2-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="21de2-159">Proveedor de hospedaje y proveedor de MI pública</span><span class="sxs-lookup"><span data-stu-id="21de2-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="21de2-160">No son necesarios requisitos de DNS específicos para este tipo de federación.</span><span class="sxs-lookup"><span data-stu-id="21de2-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="21de2-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="21de2-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="21de2-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creación o edición de proveedores federados de SIP hospedados Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="21de2-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="21de2-164">Este tipo de federación define los servicios y proveedores de hospedaje que desea configurar para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="21de2-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="21de2-165">Suele usarse para la configuración de proveedores de MI pública como, por ejemplo, Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="21de2-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="21de2-166">y AOL, así como a los proveedores de hospedaje, como Lync Online y Office 365</span><span class="sxs-lookup"><span data-stu-id="21de2-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="21de2-167">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="21de2-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="21de2-168">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="21de2-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="21de2-169">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="21de2-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="21de2-170">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="21de2-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="21de2-171">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="21de2-171">has been announced.</span></span> <span data-ttu-id="21de2-172">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21de2-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="21de2-173">La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="21de2-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="21de2-174">Service.</span><span class="sxs-lookup"><span data-stu-id="21de2-174">Messenger.</span></span> <span data-ttu-id="21de2-175">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</span><span class="sxs-lookup"><span data-stu-id="21de2-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="21de2-176">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="21de2-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="21de2-177">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="21de2-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="21de2-178">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="21de2-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="21de2-179">Defina y configure los hosts DNS necesarios (A o AAAA para IPv6) así como los registros DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="21de2-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="21de2-180">Definir y configurar las directivas mediante el panel de control de Lync Server o mediante el shell de administración de Lync Server y los cmdlets adecuados.</span><span class="sxs-lookup"><span data-stu-id="21de2-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="21de2-181">Para obtener más información sobre los cmdlets del shell de administración de Lync Server, consulte [cmdlets de Federación y de acceso externo en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="21de2-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21de2-182">Lync Room System (LRS) no muestra el botón de Unión para las reuniones enviadas por los organizadores en socios federados de Lync.</span><span class="sxs-lookup"><span data-stu-id="21de2-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="21de2-183">Para que un vínculo para unirse a una reunión aparezca en LRS, la organización de envío debe habilitar la TNEF mediante el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="21de2-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="21de2-184">Tenga en cuenta que esto no es específico de LRS.</span><span class="sxs-lookup"><span data-stu-id="21de2-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="21de2-185">Outlook y Lync tampoco mostrarán vínculos de combinación en este caso, ya que las propiedades MAPI no se transportan, pero en el caso de Outlook, el usuario puede abrir la invitación a la reunión y hacer clic en la dirección URL de la reunión.</span><span class="sxs-lookup"><span data-stu-id="21de2-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="21de2-186">Cuando TNEFEnabled se establece en true, Exchange 2013 no quita las propiedades MAPI, incluidas OnlineMeetingExternalLink, y el botón unirse se muestra en el aviso.</span><span class="sxs-lookup"><span data-stu-id="21de2-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21de2-187">Consulta también</span><span class="sxs-lookup"><span data-stu-id="21de2-187">See Also</span></span>


[<span data-ttu-id="21de2-188">Planeación de SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21de2-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="21de2-189">Administración de la Federación y el acceso externo a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21de2-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

