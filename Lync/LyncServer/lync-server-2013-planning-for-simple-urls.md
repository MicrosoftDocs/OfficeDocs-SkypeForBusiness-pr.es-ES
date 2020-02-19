---
title: 'Lync Server 2013: Planeación de direcciones URL sencillas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85b01956d901d5c4060dc1cf14f9991fdfce261c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="c62f7-102">Planeación de direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c62f7-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c62f7-103">_**Última modificación del tema:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="c62f7-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="c62f7-104">Las direcciones URL sencillas facilitan la Unión de reuniones a los usuarios y facilitan la obtención de herramientas administrativas de Lync Server para los administradores.</span><span class="sxs-lookup"><span data-stu-id="c62f7-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="c62f7-105">Lync Server admite tres direcciones URL sencillas:</span><span class="sxs-lookup"><span data-stu-id="c62f7-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="c62f7-106">**Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización.</span><span class="sxs-lookup"><span data-stu-id="c62f7-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="c62f7-107">Un ejemplo de una dirección URL sencilla de https://meet.contoso.comreunión es.</span><span class="sxs-lookup"><span data-stu-id="c62f7-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="c62f7-108">Una dirección URL de una reunión concreta podría https://meet.contoso.com/ser *nombre de usuario*/7322994.</span><span class="sxs-lookup"><span data-stu-id="c62f7-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="c62f7-109">Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir.</span><span class="sxs-lookup"><span data-stu-id="c62f7-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="c62f7-110">**Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c62f7-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="c62f7-111">Esta página muestra los números de acceso telefónico de conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no necesitan programarse) y los controles de DTMF en conferencia, y admite la administración del número de identificación personal ( PIN) y la información de conferencia asignada.</span><span class="sxs-lookup"><span data-stu-id="c62f7-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="c62f7-112">La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios.</span><span class="sxs-lookup"><span data-stu-id="c62f7-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="c62f7-113">Un ejemplo de la dirección URL sencilla de acceso telefónico https://dialin.contoso.comes.</span><span class="sxs-lookup"><span data-stu-id="c62f7-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="c62f7-114">El **Administrador** habilita el acceso rápido al panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c62f7-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="c62f7-115">Desde cualquier equipo de los firewalls de su organización, un administrador puede abrir el panel de control de Lync Server escribiendo la dirección URL sencilla de administración en un explorador.</span><span class="sxs-lookup"><span data-stu-id="c62f7-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="c62f7-116">La dirección URL simple de administración es de uso interno para la organización.</span><span class="sxs-lookup"><span data-stu-id="c62f7-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="c62f7-117">Un ejemplo de la dirección URL sencilla de administración eshttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62f7-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="c62f7-118">Ámbito de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="c62f7-118">Simple URL Scope</span></span>

<span data-ttu-id="c62f7-119">Las direcciones URL sencillas se pueden configurar para que tengan un ámbito global, o bien se puede especificar una distinta por cada sitio central de la organización.</span><span class="sxs-lookup"><span data-stu-id="c62f7-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="c62f7-120">Si se especifican una dirección URL sencilla de ámbito global y una dirección URL sencilla de ámbito de sitio, la dirección URL sencilla de ámbito del sitio tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="c62f7-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="c62f7-p105">La mayor parte de las veces es recomendable definir direcciones URL sencillas únicamente en el nivel global, ya que así la dirección URL sencilla de reunión de un usuario no cambiará si se traslada de un sitio a otro. Una excepción a esto serían aquellas organizaciones que necesitan usar números de teléfono distintos para los usuarios de acceso telefónicos localizados en sitios distintos. Tenga en cuenta que, si una dirección URL sencilla (como, por ejemplo, de acceso telefónico) se establece en un sitio como dirección URL sencilla de nivel de sitio, también deberá definir el resto de direcciones URL sencillas como de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="c62f7-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c62f7-124">Si decide usar direcciones URL sencillas con ámbito de sitio, los usuarios no podrán moverse entre los grupos de servidores front-end de sitios diferentes sin que los usuarios vuelvan a programar todas sus reuniones programadas, ya que las direcciones URL sencillas de reunión son diferentes entre los sitios.</span><span class="sxs-lookup"><span data-stu-id="c62f7-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="c62f7-125">Esto incluye escenarios de conmutación por error en los que los grupos de servidores de las relaciones de copia de seguridad se encuentran en sitios independientes.</span><span class="sxs-lookup"><span data-stu-id="c62f7-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="c62f7-126">Cuando necesite conmutar por error entre sitios en los que se implementen direcciones URL sencillas en el ámbito del sitio, los usuarios no podrán unirse a sus reuniones debido al ámbito de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c62f7-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="c62f7-127">Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="c62f7-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="c62f7-128">Puede establecer direcciones URL simples globales en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c62f7-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="c62f7-129">Para establecer una dirección URL sencilla en el nivel de sitio, debe usar el cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c62f7-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="c62f7-130">Nomenclatura de las direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="c62f7-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="c62f7-p108">Son tres las opciones recomendadas de nomenclatura de las direcciones URL sencillas. Aquella que elija conllevará una serie de implicaciones a la hora de configurar los registros A de DNS y certificados que admiten direcciones URL sencillas. Con cada opción deberá configurar una dirección URL sencilla de reunión por cada dominio SIP existente en la organización. Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya.</span><span class="sxs-lookup"><span data-stu-id="c62f7-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="c62f7-134">Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya.</span><span class="sxs-lookup"><span data-stu-id="c62f7-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="c62f7-135">Para obtener más información sobre los certificados y registros A de DNS necesarios, consulte [requisitos de DNS para direcciones URL sencillas en Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) y [requisitos de certificado para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c62f7-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="c62f7-136">Con la opción 1, se crea un nombre de dominio SIP nuevo por cada dirección URL sencilla.</span><span class="sxs-lookup"><span data-stu-id="c62f7-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="c62f7-137">Si se decanta por esta opción, necesitará un registro A de DNS por cada dirección URL sencilla y en los certificados deberá aparecer el nombre de todas las direcciones URL sencillas de reunión.</span><span class="sxs-lookup"><span data-stu-id="c62f7-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="c62f7-138">Opción 1 de nomenclatura de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="c62f7-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c62f7-139"><strong>Direcciones URL sencillas</strong></span><span class="sxs-lookup"><span data-stu-id="c62f7-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c62f7-140"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="c62f7-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62f7-141">Cumplir</span><span class="sxs-lookup"><span data-stu-id="c62f7-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="c62f7-142">https://meet.contoso.com, https://meet.fabrikam.comy así sucesivamente (uno para cada dominio SIP de la organización)</span><span class="sxs-lookup"><span data-stu-id="c62f7-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c62f7-143">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c62f7-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62f7-144">Administración</span><span class="sxs-lookup"><span data-stu-id="c62f7-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c62f7-p109">Con la opción 2, las direcciones URL sencillas se basan en el nombre de dominio lync.contoso.com, de modo que solo es necesario un registro A de DNS que permita los tres tipos de dirección URL sencilla. Este registro A de DNS hace referencia a lync.contoso.com. También necesitará registros A de DNS para otros dominios SIP de la organización.</span><span class="sxs-lookup"><span data-stu-id="c62f7-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="c62f7-149">Opción 2 de nomenclatura de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="c62f7-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c62f7-150"><strong>Direcciones URL sencillas</strong></span><span class="sxs-lookup"><span data-stu-id="c62f7-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c62f7-151"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="c62f7-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62f7-152">Cumplir</span><span class="sxs-lookup"><span data-stu-id="c62f7-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="c62f7-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meety así sucesivamente (uno para cada dominio SIP de la organización)</span><span class="sxs-lookup"><span data-stu-id="c62f7-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c62f7-154">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c62f7-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62f7-155">Administración</span><span class="sxs-lookup"><span data-stu-id="c62f7-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c62f7-156">La opción 3 es la más práctica si existen muchos dominios SIP y quiere que cada uno de ellos tenga una dirección URL sencilla de reunión pero, al mismo tiempo, desea reducir al mínimo los requisitos de registros DNS y certificados para dichas direcciones.</span><span class="sxs-lookup"><span data-stu-id="c62f7-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="c62f7-157">Opción 3 de nomenclatura de dirección URL sencilla</span><span class="sxs-lookup"><span data-stu-id="c62f7-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c62f7-158"><strong>Direcciones URL sencillas</strong></span><span class="sxs-lookup"><span data-stu-id="c62f7-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c62f7-159"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="c62f7-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62f7-160">Cumplir</span><span class="sxs-lookup"><span data-stu-id="c62f7-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c62f7-161">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c62f7-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62f7-162">Administración</span><span class="sxs-lookup"><span data-stu-id="c62f7-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="c62f7-163">Nomenclatura de direcciones URL sencillas y reglas de validación</span><span class="sxs-lookup"><span data-stu-id="c62f7-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="c62f7-164">El generador de topologías y los cmdlets del shell de administración de Lync Server exigen varias reglas de validación para las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="c62f7-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="c62f7-165">Las direcciones URL sencillas para reunión y acceso telefónico deben definirse obligatoriamente, si bien esto es opcional en el caso de las direcciones URL de administración.</span><span class="sxs-lookup"><span data-stu-id="c62f7-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="c62f7-166">Cada dominio SIP debe tener una dirección URL sencilla de reunión particular, mientras que solo es preciso tener una dirección URL sencilla de acceso telefónico y de administración para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="c62f7-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="c62f7-167">Cada dirección URL sencilla de la organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL sencilla (por ejemplo, no es posible definir lync.contoso.com/Meet como dirección URL sencilla de reunión y lync.contoso.com/Meet/Dialin como dirección URL sencilla de acceso telefónico).</span><span class="sxs-lookup"><span data-stu-id="c62f7-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="c62f7-168">Los nombres de dirección URL simple no pueden contener el FQDN de ninguno de sus grupos o cualquier información de puerto https://FQDN:88/meet (por ejemplo, no está permitido).</span><span class="sxs-lookup"><span data-stu-id="c62f7-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="c62f7-169">Todas las direcciones URL sencillas deben empezar por el prefijo https://.</span><span class="sxs-lookup"><span data-stu-id="c62f7-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="c62f7-p112">Las direcciones URL sencillas solo pueden contener caracteres alfanuméricos, esto es, a-z, A-Z, 0-9 y el signo de punto (.); si usa otros caracteres, podrían no funcionar del modo previsto.</span><span class="sxs-lookup"><span data-stu-id="c62f7-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="c62f7-172">Cambiar las direcciones URL sencillas tras la implementación</span><span class="sxs-lookup"><span data-stu-id="c62f7-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="c62f7-173">Si modifica una dirección URL sencilla tras la implementación inicial, deberá tener presentes los cambios que podrían afectar a los registros DNS y certificados de dichas direcciones.</span><span class="sxs-lookup"><span data-stu-id="c62f7-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="c62f7-174">Si el cambio afecta a la base de una dirección URL sencilla, deberá modificar también los certificados y registros DNS.</span><span class="sxs-lookup"><span data-stu-id="c62f7-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="c62f7-175">Por ejemplo, si se https://lync.contoso.com/Meet cambia https://meet.contoso.com de para cambia la dirección URL base de Lync.contoso.com a meet.contoso.com, es necesario cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c62f7-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="c62f7-176">Si ha cambiado la dirección URL sencilla https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingsa, la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario ningún cambio de certificado o DNS.</span><span class="sxs-lookup"><span data-stu-id="c62f7-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="c62f7-177">Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar **enable-CsComputer** en cada director y en el servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="c62f7-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c62f7-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="c62f7-178">See Also</span></span>


[<span data-ttu-id="c62f7-179">Requisitos de DNS para direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c62f7-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

