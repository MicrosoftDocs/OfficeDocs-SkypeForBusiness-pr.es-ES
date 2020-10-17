---
title: Lync Server 2013 soporte para conectividad de mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ad9f5083d336fdf90e415d627fe448d02e4db29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519427"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="465e3-102">Compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465e3-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="465e3-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="465e3-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="465e3-104">Compatibilidad con la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="465e3-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="465e3-105">En este artículo se proporciona información acerca de la compatibilidad con la conectividad de mensajería instantánea pública (PIC).</span><span class="sxs-lookup"><span data-stu-id="465e3-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="465e3-106">PIC es una característica de Microsoft Lync que permite a las organizaciones habilitar a sus usuarios de Lync para que se conecten con los usuarios de determinados servicios de mensajería instantánea (mi) pública a través de sus clientes e identidades de Lync.</span><span class="sxs-lookup"><span data-stu-id="465e3-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="465e3-107">Los usuarios finales se benefician de poder conectar con los clientes, socios y proveedores en sus términos.</span><span class="sxs-lookup"><span data-stu-id="465e3-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="465e3-108">Se beneficia de la compatibilidad de un solo cliente de comunicaciones en tiempo real a la vez que se mantienen las características de control, cumplimiento y archivado de Lync.</span><span class="sxs-lookup"><span data-stu-id="465e3-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="465e3-109">Lync-Skype conectividad, [disponible públicamente en mayo de 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), se basa en el heredado de que Lync/Office Communications Server (OCS)/Live Communications Server (LCS) se estableció por primera vez con PIC en la conexión a MSN/Windows Live, AOL y Yahoo.</span><span class="sxs-lookup"><span data-stu-id="465e3-109">Lync-Skype connectivity, [publicly available in May 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="465e3-110">Para obtener más información acerca de la conectividad de Lync-Skype, consulte [Lync-Skype Connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="465e3-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="465e3-111">La Federación con Windows Live, AOL y Yahoo se encuentran en una ruta hacia el final de la vida.</span><span class="sxs-lookup"><span data-stu-id="465e3-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="465e3-112">Esta página documenta el estado de cada servicio.</span><span class="sxs-lookup"><span data-stu-id="465e3-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="465e3-113">Para usar PIC, los clientes deben activar el servicio para cada proveedor de servicios de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="465e3-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="465e3-114">Los requisitos y los detalles para hacerlo dependen del proveedor de servicios de mensajería instantánea y del programa de licencias subyacente del cliente.</span><span class="sxs-lookup"><span data-stu-id="465e3-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="465e3-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="465e3-115">Windows Live Messenger</span></span>

<span data-ttu-id="465e3-116">Microsoft puso a trabajar en Windows Live Messenger y Skype.</span><span class="sxs-lookup"><span data-stu-id="465e3-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="465e3-117">En abril de 2013, los usuarios de Messenger se migraron a Skype al iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="465e3-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="465e3-118">Los clientes de Lync que confían en la Federación con Messenger seguirán pudiendo comunicarse con sus contactos de Messenger, incluso después de que esos contactos se actualicen a Skype.</span><span class="sxs-lookup"><span data-stu-id="465e3-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="465e3-119">No hay nada que los administradores de Lync o los usuarios finales de Lync deban hacer para mantener la continuidad del servicio, y la administración de esta funcionalidad dentro de Lync sigue siendo la misma que para la comunicación con Messenger.</span><span class="sxs-lookup"><span data-stu-id="465e3-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="465e3-120">Cuando los usuarios de Messenger inician sesión en Skype usando sus cuentas de Microsoft (es decir, las mismas credenciales usadas para Messenger), todos sus contactos de Messenger, incluidos los contactos federados de Lync, las siguen en Skype.</span><span class="sxs-lookup"><span data-stu-id="465e3-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="465e3-121">El uso compartido de presencia y la mensajería instantánea entre Skype y Lync para estos contactos está disponible.</span><span class="sxs-lookup"><span data-stu-id="465e3-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="465e3-122">Lync-Skype conectividad: la adición de contactos, el uso compartido de presencia, la mensajería instantánea y las llamadas de audio entre los usuarios de Lync y Skype, también está disponible para todos los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="465e3-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="465e3-123">Toolbar\!</span><span class="sxs-lookup"><span data-stu-id="465e3-123">Yahoo\!</span></span> <span data-ttu-id="465e3-124">y AOL Instant Messenger</span><span class="sxs-lookup"><span data-stu-id="465e3-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="465e3-125">Federación con Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="465e3-125">Federation with Yahoo\!</span></span> <span data-ttu-id="465e3-126">y AOL se encuentran en una ruta hacia el final del ciclo de vida para los clientes de Lync (y Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="465e3-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="465e3-127">La capacidad de Microsoft para proporcionar cada uno de estos servicios se ha supeditado al soporte de Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="465e3-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="465e3-128">y AOL, y los acuerdos subyacentes de estos se liquidan.</span><span class="sxs-lookup"><span data-stu-id="465e3-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="465e3-129">Para Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="465e3-129">For both Yahoo\!</span></span> <span data-ttu-id="465e3-130">y AOL, el servicio continuará hasta el 2014 de junio.</span><span class="sxs-lookup"><span data-stu-id="465e3-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="465e3-131">**Yahoo** -Service seguirá hasta el 2014 de junio y los clientes seguirán teniendo licencia con la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL").</span><span class="sxs-lookup"><span data-stu-id="465e3-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="465e3-132">A partir del 1 de septiembre de 2012, la capa USL de PIC ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="465e3-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="465e3-133">Los clientes con licencias adquiridas antes de esta fecha podrán seguir federando a Yahoo.\!</span><span class="sxs-lookup"><span data-stu-id="465e3-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="465e3-134">hasta la fecha de cierre del servicio o la expiración de la licencia.</span><span class="sxs-lookup"><span data-stu-id="465e3-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="465e3-135">Lea [el anuncio](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) en el blog del equipo de Lync.</span><span class="sxs-lookup"><span data-stu-id="465e3-135"> Read [the announcement](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="465e3-136">Los clientes que tienen licencias PIC en contratos que se extienden más allá del 30 de junio de 2014 recibirán un crédito en proporción a la cantidad de pagos que cubren el período de tiempo posterior al 30 de junio de 2014.</span><span class="sxs-lookup"><span data-stu-id="465e3-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="465e3-137">**AOL** : el 30 de junio de 2014, el servicio de conectividad de mensajería instantánea ("PIC") de Lync dejará de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="465e3-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="465e3-138">A fin de limitar la interrupción del cliente cuando el servicio finaliza, hemos dejado de realizar el aprovisionamiento de dominios de cliente adicionales.</span><span class="sxs-lookup"><span data-stu-id="465e3-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="465e3-139">Hasta el 30 de junio de 2014, los clientes no tienen que hacer nada para seguir admitiendo comunicaciones federadas con AIM.</span><span class="sxs-lookup"><span data-stu-id="465e3-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="465e3-140">Más allá de esta fecha (o para los clientes que, al mismo modo, desea aprovisionar dominios adicionales), hay disponible un servicio sustituto directamente desde AOL.</span><span class="sxs-lookup"><span data-stu-id="465e3-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="465e3-141">Para obtener más información sobre el nuevo servicio de AOL, consulte [establecer la Federación directa con AIM](http://aimenterprise.aol.com/pic.php)    (abre una página nueva en AOL.com).</span><span class="sxs-lookup"><span data-stu-id="465e3-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="465e3-142">Resumen de proveedor de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="465e3-142">Public IM Provider Summary</span></span>

<span data-ttu-id="465e3-143">En la siguiente tabla se proporciona un resumen de los proveedores de servicios públicos de mensajería instantánea, las capacidades de Federación con Lync y los requisitos de licencia.</span><span class="sxs-lookup"><span data-stu-id="465e3-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="465e3-144">Proveedor de servicios de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="465e3-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="465e3-145">Capacidades federadas</span><span class="sxs-lookup"><span data-stu-id="465e3-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="465e3-146">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="465e3-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="465e3-147">Skype</span><span class="sxs-lookup"><span data-stu-id="465e3-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="465e3-148">MI, presencia, audio</span><span class="sxs-lookup"><span data-stu-id="465e3-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="465e3-149">Licencias de acceso de cliente de Lync Server, plan 1/2/3 de Lync Online</span><span class="sxs-lookup"><span data-stu-id="465e3-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="465e3-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="465e3-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="465e3-151">MI, presencia, audio/vídeo</span><span class="sxs-lookup"><span data-stu-id="465e3-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="465e3-152">Licencias de acceso de cliente de Lync Server (admitidas siempre que WLM esté en el mercado)</span><span class="sxs-lookup"><span data-stu-id="465e3-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="465e3-153">TOTALMENTE</span><span class="sxs-lookup"><span data-stu-id="465e3-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="465e3-154">MI, presencia</span><span class="sxs-lookup"><span data-stu-id="465e3-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="465e3-155">Licencias de acceso de cliente de Lync Server; admitido hasta el 2014 de junio para los clientes existentes.</span><span class="sxs-lookup"><span data-stu-id="465e3-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="465e3-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="465e3-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="465e3-157">MI, presencia</span><span class="sxs-lookup"><span data-stu-id="465e3-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="465e3-158">Requiere una licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync adicional ("PIC USL"), además de las licencias de acceso de cliente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="465e3-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="465e3-159">A partir de la lista de precios de septiembre de 2012, la capa de PIC ya no está disponible para la compra.</span><span class="sxs-lookup"><span data-stu-id="465e3-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="465e3-160">Los clientes con licencias activas pueden seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="465e3-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="465e3-161">Messenger hasta que se cierre el servicio la fecha del 30 de junio de 2014.</span><span class="sxs-lookup"><span data-stu-id="465e3-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

