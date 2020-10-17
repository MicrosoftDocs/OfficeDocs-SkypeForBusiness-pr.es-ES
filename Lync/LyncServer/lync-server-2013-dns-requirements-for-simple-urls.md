---
title: 'Lync Server 2013: requisitos de DNS para direcciones URL sencillas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501377"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="a3df0-102">Requisitos de DNS para direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3df0-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3df0-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a3df0-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a3df0-104">Lync Server 2013 admite direcciones URL sencillas que facilitan la combinación de reuniones con los usuarios y facilitan a los administradores las herramientas administrativas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3df0-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="a3df0-105">Para obtener más información sobre las direcciones URL sencillas, consulte [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="a3df0-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="a3df0-106">Lync Server admite las siguientes tres direcciones URL sencillas: reunirse, acceso telefónico y administrador. Es necesario configurar direcciones URL sencillas para la reunión y el acceso telefónico, y la dirección URL sencilla de administración es opcional.</span><span class="sxs-lookup"><span data-stu-id="a3df0-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="a3df0-107">Los registros del sistema de nombres de dominio (DNS) necesarios para admitir direcciones URL sencillas varían en función de la forma en que se hayan definido dichas direcciones URL sencillas y de si desea admitir la recuperación ante desastres para las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="a3df0-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="a3df0-108">Opción 1 de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="a3df0-108">Simple URL Option 1</span></span>

<span data-ttu-id="a3df0-109">En la opción 1, se crea una nueva dirección URL base para cada dirección URL sencilla.</span><span class="sxs-lookup"><span data-stu-id="a3df0-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="a3df0-p103">Cuando un usuario hace clic en un vínculo de reunión de dirección URL sencilla, el servidor en el que se resuelve el registro DNS A determina el software cliente correcto para iniciarlo. Una vez iniciado, el software cliente se comunica automáticamente con el grupo de servidores en el que se hospeda la conferencia. De este modo, los usuarios se dirigen al servidor adecuado para contenido de reunión, con independencia del servidor o grupo de servidores en el que se resuelvan los registros DNS A de la dirección URL sencilla.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="a3df0-113">Opción 1 de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="a3df0-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3df0-114"><strong>Direcciones URL sencillas</strong></span><span class="sxs-lookup"><span data-stu-id="a3df0-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="a3df0-115"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="a3df0-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3df0-116">Cumplir</span><span class="sxs-lookup"><span data-stu-id="a3df0-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="a3df0-117">https://meet.contoso.com, https://meet.fabrikam.com y así sucesivamente (uno para cada dominio SIP de la organización)</span><span class="sxs-lookup"><span data-stu-id="a3df0-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3df0-118">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a3df0-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3df0-119">Admin</span><span class="sxs-lookup"><span data-stu-id="a3df0-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3df0-120">Si usa la opción 1, debe definir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3df0-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="a3df0-p104">Para cada URL sencilla de reunión, necesita un registro DNS A que resuelva la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, debe resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="a3df0-124">Si dispone de más de un dominio SIP en la organización y usa esta opción, debe crear direcciones URL sencillas de reunión para cada dominio SIP y se necesita un registro DNS A para cada dirección URL sencilla de reunión.</span><span class="sxs-lookup"><span data-stu-id="a3df0-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="a3df0-125">Por ejemplo, si tiene tanto contoso.com como fabrikam.com, se crearán registros A de DNS para https://meet.contoso.com y https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="a3df0-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="a3df0-126">Asimismo, si tiene varios dominios SIP y desea reducir al máximo los requisitos de registro DNS y de certificado de estas direcciones URL sencillas, use la opción 3 que se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a3df0-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="a3df0-p106">Para la dirección URL de acceso telefónico local, necesita un registro DNS A que resuelva la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, debe resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="a3df0-p107">La dirección URL sencilla de administrador es solo de uso interno. Necesita un registro DNS A que resuelva la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, debe resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="a3df0-134">Opción 2 de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="a3df0-134">Simple URL Option 2</span></span>

<span data-ttu-id="a3df0-p108">Con la opción 2, todas las direcciones URL sencillas de reunión, acceso telefónico local y administrador tienen una dirección URL base, como lync.contoso.com. Por consiguiente, únicamente necesita un registro DNS A para estas direcciones URL sencillas, que resuelve lync.contoso.com en la dirección IP de un grupo de servidores director o un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="a3df0-138">Tenga en cuenta que si dispone de más de un dominio SIP en la organización y usa esta opción, debe crear direcciones URL sencillas de reunión para cada dominio SIP y se necesita un registro DNS A para cada dirección URL sencilla de reunión.</span><span class="sxs-lookup"><span data-stu-id="a3df0-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="a3df0-139">En este ejemplo, aunque las tres direcciones URL sencillas se basan en lync.contoso.com, se configura una dirección URL sencilla de reunión adicional para fabrikam.com con una dirección URL base distinta.</span><span class="sxs-lookup"><span data-stu-id="a3df0-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="a3df0-140">En este ejemplo, debe crear registros A de DNS para https://lync.contoso.com y https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="a3df0-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="a3df0-141">La opción 3 de dirección URL sencilla muestra otra forma de administrar registros DNS A y de nomenclatura si tiene varios dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="a3df0-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="a3df0-142">Opción 2 de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="a3df0-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3df0-143"><strong>Direcciones URL sencillas</strong></span><span class="sxs-lookup"><span data-stu-id="a3df0-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="a3df0-144"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="a3df0-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3df0-145">Cumplir</span><span class="sxs-lookup"><span data-stu-id="a3df0-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="a3df0-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet y así sucesivamente (uno para cada dominio SIP de la organización)</span><span class="sxs-lookup"><span data-stu-id="a3df0-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3df0-147">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a3df0-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3df0-148">Admin</span><span class="sxs-lookup"><span data-stu-id="a3df0-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="a3df0-149">Opción 3 de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="a3df0-149">Simple URL Option 3</span></span>

<span data-ttu-id="a3df0-p110">La opción 3 resulta más útil si se tienen varios dominios SIP y se desea que tengan direcciones URL sencillas independientes y al mismo tiempo reducir al máximo los requisitos de registro DNS y de certificado de estas direcciones URL sencillas. En este ejemplo, solo se necesita un solo registro DNS A, que resuelve lync.contoso.com en la dirección IP de un grupo de servidores director o un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="a3df0-152">Opción 3 de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="a3df0-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3df0-153"><strong>Direcciones URL sencillas</strong></span><span class="sxs-lookup"><span data-stu-id="a3df0-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="a3df0-154"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="a3df0-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3df0-155">Cumplir</span><span class="sxs-lookup"><span data-stu-id="a3df0-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3df0-156">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a3df0-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3df0-157">Admin</span><span class="sxs-lookup"><span data-stu-id="a3df0-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="a3df0-158">Opción de recuperación ante desastres para direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="a3df0-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="a3df0-159">Si tiene varios sitios que contienen grupos de servidores front-end y el proveedor de DNS admite GeoDNS, puede configurar los registros DNS para que las direcciones URL sencillas admitan la recuperación ante desastres, de modo que la funcionalidad de dirección URL sencilla continúe incluso si se produce un grupo de servidores front-end completo.</span><span class="sxs-lookup"><span data-stu-id="a3df0-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="a3df0-160">Esta función de recuperación ante desastres admite las direcciones URL sencillas de Acceso telefónico y Reunión.</span><span class="sxs-lookup"><span data-stu-id="a3df0-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="a3df0-p112">Para configurar esto, cree dos direcciones de GeoDNS. Cada dirección tiene dos registros DNS A o CNAME que resultan en dos grupos de servidores que funcionan juntos con fines de recuperación ante desastres. Una dirección de GeoDNS se utiliza para el acceso interno y se resuelve en el FQDN web interno o la dirección IP del equilibrador de carga para dos grupos de servidores. La otra dirección de GeoDNS se utiliza para el acceso externo y se resuelve en el FQDN web externo o la dirección IP del equilibrador de carga para dos grupos de servidores. Lo siguiente es un ejemplo de dirección URL sencilla de Reunión, que utiliza los FQDN para los grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="a3df0-166">Luego cree registros CNAME que se resuelven su dirección URL sencilla de Reunión (como meet.contoso.com) en las dos direcciones de GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="a3df0-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="a3df0-167">Si su red utiliza <EM>vinculaciones</EM> (enrutamiento de todo su tráfico de direcciones URL sencillas a través del enlace externo, incluido el tráfico que proviene desde su organización), entonces puede simplemente configurar la dirección de GeoDNS externa y resolver su dirección URL sencilla de Reunión en solo esa dirección externa.</span><span class="sxs-lookup"><span data-stu-id="a3df0-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="a3df0-168">Al utilizar este método, puede configurar cada dirección de GeoDNS para que utilice un método de operación por turnos para distribuir solicitudes en los dos grupos de servidores, o bien para que se conecte a un grupo de servidores (como el grupo de servidores más cercano) y utilizar el otro grupo solo en caso de que no se pueda establecer la conexión.</span><span class="sxs-lookup"><span data-stu-id="a3df0-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="a3df0-169">Puede configurar los mismos parámetros para la dirección URL sencilla de Acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a3df0-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="a3df0-170">Para ello, cree registros adicionales como los del ejemplo anterior, sustituyendo `dialin` por `meet` en los registros DNS.</span><span class="sxs-lookup"><span data-stu-id="a3df0-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="a3df0-171">Para la dirección URL sencilla de Administrador, utilice una de las tres opciones que se mencionaron antes en esta sección.</span><span class="sxs-lookup"><span data-stu-id="a3df0-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="a3df0-172">Una vez que esta configuración esté definida, debe utilizar una aplicación de supervisión para configurar la supervisión HTTP para que esté alerta de los fallos.</span><span class="sxs-lookup"><span data-stu-id="a3df0-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="a3df0-173">Para el acceso externo, supervise para asegurarse de que las solicitudes HTTPS GET AutoDiscovery para el FQDN de Web externo o la dirección IP del equilibrador de carga para los dos grupos de servidores sean correctas.</span><span class="sxs-lookup"><span data-stu-id="a3df0-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="a3df0-174">Por ejemplo, las siguientes solicitudes no deben contener ningún encabezado **ACCEPT** y deben devolver **200 OK**.</span><span class="sxs-lookup"><span data-stu-id="a3df0-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="a3df0-p115">Para el acceso interno, debe supervisar el puerto 5061 en el FQDN web interno o la dirección IP del equilibrador de carga para los dos grupos de servidores. Si se detecta cualquier problema de conectividad, la VIP de estos grupos de servidores deben cerrar los puertos 80, 443 y 444.</span><span class="sxs-lookup"><span data-stu-id="a3df0-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

