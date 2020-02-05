---
title: 'Lync Server 2013: Configuración de federación de Lync'
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
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="01f4e-102">Configuración de federación de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f4e-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f4e-103">_**Última modificación del tema:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="01f4e-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="01f4e-104">Si ya ha implementado el servidor o servidores perimetrales, agregue las características de escenarios federados hacia delante.</span><span class="sxs-lookup"><span data-stu-id="01f4e-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="01f4e-105">Si no ha configurado servidores perimetrales, debe hacerlo primero.</span><span class="sxs-lookup"><span data-stu-id="01f4e-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="01f4e-106">Para obtener más información, vea: [planificación para el acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación e [implementación de acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="01f4e-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01f4e-107">Si pretende configurar cualquier combinación de Federación de XMPP, Federación de Lync o conectividad de mensajería instantánea pública, puede implementarla de forma simultánea o una por vez.</span><span class="sxs-lookup"><span data-stu-id="01f4e-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="01f4e-108">Si configura las opciones mediante el generador de topología y el shell de administración de Lync Server, ejecute el Asistente de implementación en el servidor perimetral después de configurar las opciones para uno, dos o tres tipos de Federación, puede reducir el número de pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="01f4e-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="01f4e-109">Configurar la Federación de Lync en el generador de topología y el Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="01f4e-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="01f4e-110">En un servidor front-end, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="01f4e-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="01f4e-111">Expanda agrupaciones perimetrales y haga clic con el botón derecho en el servidor perimetral o en el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="01f4e-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="01f4e-112">Seleccione Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="01f4e-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="01f4e-113">En propiedades de edición, en general, seleccione Habilitar Federación para este grupo perimetral (puerto 5061).</span><span class="sxs-lookup"><span data-stu-id="01f4e-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="01f4e-114">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="01f4e-114">Click OK.</span></span>

3.  <span data-ttu-id="01f4e-115">Haga clic en acción, seleccione topología, seleccione publicar.</span><span class="sxs-lookup"><span data-stu-id="01f4e-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="01f4e-116">Cuando se le solicite al publicar la topología, haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="01f4e-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="01f4e-117">Una vez finalizada la publicación, haga clic en finalizar.</span><span class="sxs-lookup"><span data-stu-id="01f4e-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="01f4e-118">En el servidor perimetral, abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01f4e-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="01f4e-119">Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01f4e-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="01f4e-120">Vuelva a hacer clic en ejecutar.</span><span class="sxs-lookup"><span data-stu-id="01f4e-120">Click Run Again.</span></span>

5.  <span data-ttu-id="01f4e-121">En instalación de los componentes de Lync Server, haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="01f4e-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="01f4e-122">La pantalla resumen mostrará las acciones a medida que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="01f4e-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="01f4e-123">Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="01f4e-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="01f4e-124">Haga clic en finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="01f4e-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="01f4e-125">Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación.</span><span class="sxs-lookup"><span data-stu-id="01f4e-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="01f4e-126">Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único.</span><span class="sxs-lookup"><span data-stu-id="01f4e-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="01f4e-127">Por ejemplo, si la implementación incluye un grupo perimetral o un solo servidor perimetral implementado en Nueva York y uno implementado en Londres y habilita la compatibilidad con la Federación en el grupo de servidores perimetrales de Nueva York o en el único servidor de borde, la señal de tráfico para usuarios federados pasará por la Nueva York. Grupo Edge o servidor perimetral único.</span><span class="sxs-lookup"><span data-stu-id="01f4e-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="01f4e-128">Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.</span><span class="sxs-lookup"><span data-stu-id="01f4e-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="01f4e-129">Configurar la Federación con socios</span><span class="sxs-lookup"><span data-stu-id="01f4e-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="01f4e-130">Para configurar una Federación correcta con otro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 u Office Communicator 2007, seleccione el tipo de Federación de la tabla siguiente y defina los registros SRV de DNS, el host DNS (A o AAAA para IPv6) y configurar directivas aplicables al tipo de Federación:</span><span class="sxs-lookup"><span data-stu-id="01f4e-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="01f4e-131">Tipo de Federación</span><span class="sxs-lookup"><span data-stu-id="01f4e-131">Federation type</span></span></th>
    <th><span data-ttu-id="01f4e-132">Registros DNS</span><span class="sxs-lookup"><span data-stu-id="01f4e-132">DNS Records</span></span></th>
    <th><span data-ttu-id="01f4e-133">Definición de Directiva</span><span class="sxs-lookup"><span data-stu-id="01f4e-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="01f4e-134">Notas</span><span class="sxs-lookup"><span data-stu-id="01f4e-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="01f4e-135">Dominio de socio descubierto</span><span class="sxs-lookup"><span data-stu-id="01f4e-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="01f4e-136">Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor del puerto para el registro SRV es TCP 5061 y el <strong>hospedador que ofrece este servicio</strong> se define como SIP.</span><span class="sxs-lookup"><span data-stu-id="01f4e-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="01f4e-137">&lt;nombre&gt; de dominio externo: el FQDN de su servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="01f4e-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="01f4e-138">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</span><span class="sxs-lookup"><span data-stu-id="01f4e-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="01f4e-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="01f4e-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="01f4e-141">Las versiones anteriores hacían referencia a este tipo de Federación como <strong>Federación mejorada abierta</strong>.</span><span class="sxs-lookup"><span data-stu-id="01f4e-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="01f4e-142">La creación del registro SRV es necesaria para este tipo de Federación y es permitir que otros socios descubran su Federación.</span><span class="sxs-lookup"><span data-stu-id="01f4e-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="01f4e-143">Dominio asociado permitido</span><span class="sxs-lookup"><span data-stu-id="01f4e-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="01f4e-144">Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor del puerto para el registro SRV es TCP 5061 y el <strong>hospedador que ofrece este servicio</strong> se define como SIP.</span><span class="sxs-lookup"><span data-stu-id="01f4e-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="01f4e-145">&lt;nombre&gt; de dominio externo: el FQDN de su servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="01f4e-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="01f4e-146">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</span><span class="sxs-lookup"><span data-stu-id="01f4e-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="01f4e-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="01f4e-148">Las versiones anteriores hacían referencia a este tipo de Federación como <strong>Federación mejorada</strong>.</span><span class="sxs-lookup"><span data-stu-id="01f4e-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="01f4e-149">La creación del registro SRV es opcional para este tipo de Federación y es permitir que otros socios descubran su Federación.</span><span class="sxs-lookup"><span data-stu-id="01f4e-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="01f4e-150">Por supuesto, esta es una <strong>Federación mejorada abierta</strong>o un <strong>dominio de socio descubierto</strong></span><span class="sxs-lookup"><span data-stu-id="01f4e-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="01f4e-151">Servidor asociado permitido</span><span class="sxs-lookup"><span data-stu-id="01f4e-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="01f4e-152">Configurar el nombre de dominio SIP y el FQDN del servidor perimetral asociado como un asociado de Federación en las directivas</span><span class="sxs-lookup"><span data-stu-id="01f4e-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="01f4e-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="01f4e-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="01f4e-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="01f4e-156">Este tipo de Federación es la definición de una relación de uno a uno y no permite la detección de otros socios de Federación.</span><span class="sxs-lookup"><span data-stu-id="01f4e-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="01f4e-157">Cada socio de Federación está configurado de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="01f4e-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="01f4e-158">En versiones anteriores, esto se conocía como <strong>Federación directa</strong></span><span class="sxs-lookup"><span data-stu-id="01f4e-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="01f4e-159">Proveedor de hospedaje y proveedor de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="01f4e-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="01f4e-160">No se han definido requisitos DNS específicos para este tipo de Federación</span><span class="sxs-lookup"><span data-stu-id="01f4e-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="01f4e-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="01f4e-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="01f4e-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Crear o editar proveedores federados de SIP hospedados en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="01f4e-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="01f4e-164">Este tipo de Federación define los servicios y proveedores de hospedaje que desea configurar para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="01f4e-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="01f4e-165">Los usos típicos incluyen la configuración de proveedores de mensajería instantánea pública, como Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="01f4e-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="01f4e-166">y AOL, así como los proveedores de hospedaje, como Lync Online y Office 365</span><span class="sxs-lookup"><span data-stu-id="01f4e-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="01f4e-167">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="01f4e-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="01f4e-168">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="01f4e-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="01f4e-169">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="01f4e-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="01f4e-170">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="01f4e-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="01f4e-171">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="01f4e-171">has been announced.</span></span> <span data-ttu-id="01f4e-172">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="01f4e-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="01f4e-173">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="01f4e-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="01f4e-174">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="01f4e-174">Messenger.</span></span> <span data-ttu-id="01f4e-175">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="01f4e-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="01f4e-176">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="01f4e-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="01f4e-177">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="01f4e-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="01f4e-178">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="01f4e-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="01f4e-179">Definir y configurar los registros DNS (A o AAAA para IPv6) necesarios y los registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="01f4e-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="01f4e-180">Defina y configure las directivas mediante el panel de control de Lync Server o mediante el shell de administración de Lync Server y los cmdlets apropiados.</span><span class="sxs-lookup"><span data-stu-id="01f4e-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="01f4e-181">Para obtener más información sobre los cmdlets del shell de administración de Lync Server, consulte [cmdlets de Federación y de acceso externo en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="01f4e-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="01f4e-182">Lync Room System (LRS) no muestra el botón unirse a las reuniones enviadas por los organizadores en socios federados de Lync.</span><span class="sxs-lookup"><span data-stu-id="01f4e-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="01f4e-183">Para que un vínculo de unirse a una reunión aparezca en LRS, la organización remitente debe habilitar TNEF con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="01f4e-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="01f4e-184">Ten en cuenta que esto no es específico de LRS.</span><span class="sxs-lookup"><span data-stu-id="01f4e-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="01f4e-185">Outlook y Lync tampoco mostrarán vínculos de combinación en este caso, ya que las propiedades de MAPI no se transportan, pero en el caso de Outlook, el usuario puede abrir la invitación a la reunión y hacer clic en la dirección URL de la reunión.</span><span class="sxs-lookup"><span data-stu-id="01f4e-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="01f4e-186">Cuando TNEFEnabled se establece en true, Exchange 2013 no elimina las propiedades de MAPI, incluidas OnlineMeetingExternalLink y el botón unirse en el aviso.</span><span class="sxs-lookup"><span data-stu-id="01f4e-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01f4e-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="01f4e-187">See Also</span></span>


[<span data-ttu-id="01f4e-188">Planificación de SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f4e-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="01f4e-189">Administración de la federación y el acceso externo a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f4e-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

