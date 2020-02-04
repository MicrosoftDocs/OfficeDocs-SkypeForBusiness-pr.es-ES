---
title: 'Lync Server 2013: Planeación de las direcciones URL simples'
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="3a8fc-102">Planeación de las direcciones URL simples en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a8fc-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a8fc-103">_**Última modificación del tema:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="3a8fc-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="3a8fc-104">Las direcciones URL simples facilitan la Unión a las reuniones para los usuarios y hacen que los administradores faciliten las herramientas administrativas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="3a8fc-105">Lync Server admite tres direcciones URL simples:</span><span class="sxs-lookup"><span data-stu-id="3a8fc-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="3a8fc-106">**Reunirse** se usa como la dirección URL base para todas las conferencias del sitio o la organización.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="3a8fc-107">Un ejemplo de una dirección URL simple de https://meet.contoso.comreunirse es.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="3a8fc-108">Una dirección URL de una reunión determinada puede https://meet.contoso.com/ser *username*/7322994.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="3a8fc-109">Con la dirección URL simple, los vínculos a las reuniones de unirse son fáciles de comprender y se pueden comunicar y distribuir fácilmente.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="3a8fc-110">El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="3a8fc-111">Esta página muestra los números de acceso telefónico de la Conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no es necesario programar) y los controles de DTMF de la Conferencia, y admite la administración del número de identificación personal ( PIN) y la información de conferencia asignada.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="3a8fc-112">La dirección URL de acceso telefónico simple está incluida en todas las invitaciones a reuniones para que los usuarios que deseen llamar a la reunión puedan tener acceso a la información del número de teléfono y del PIN necesarios.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="3a8fc-113">Un ejemplo de la dirección URL simple de acceso telefónico https://dialin.contoso.comes.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="3a8fc-114">El **Administrador** permite acceder rápidamente al panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="3a8fc-115">Desde cualquier equipo de los servidores de seguridad de su organización, un administrador puede abrir el panel de control de Lync Server escribiendo la dirección URL simple de administrador en un explorador.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="3a8fc-116">La dirección URL simple de administración es interna de su organización.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="3a8fc-117">Un ejemplo de la dirección URL simple de administración eshttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8fc-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="3a8fc-118">Ámbito de dirección URL simple</span><span class="sxs-lookup"><span data-stu-id="3a8fc-118">Simple URL Scope</span></span>

<span data-ttu-id="3a8fc-119">Puede configurar las direcciones URL simples para que tengan ámbito global o puede especificar direcciones URL simples diferentes para cada sitio central de su organización.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="3a8fc-120">Si se especifican una dirección URL simple de ámbito global y una dirección URL simple de ámbito de sitio, la dirección URL simple de ámbito del sitio tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="3a8fc-121">En la mayoría de los casos, se recomienda establecer direcciones URL simples solo en el nivel global, de modo que la dirección URL simple de un usuario no cambie si se mueve de un sitio a otro.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="3a8fc-122">La excepción serían organizaciones que necesitan usar números de teléfono diferentes para los usuarios de acceso telefónico local en diferentes sitios.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="3a8fc-123">Tenga en cuenta que si establece una dirección URL simple (como la dirección URL de acceso telefónico simple) en un sitio para que sea una dirección URL simple de nivel de sitio, también debe establecer las otras direcciones URL simples en ese sitio para que también sean del nivel del sitio.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a8fc-124">Si elige usar direcciones URL simples en el ámbito del sitio, los usuarios no podrán pasar de un grupo de servidores front-end a otro diferente sin que esos usuarios reprogramen todas las reuniones programadas porque las direcciones URL simples difieren entre los sitios.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="3a8fc-125">Esto incluye escenarios de conmutación por error en los que los grupos de las relaciones de copia de seguridad están en sitios independientes.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="3a8fc-126">Si necesita conmutación por error entre los sitios donde se implementan direcciones URL simples en el ámbito del sitio, los usuarios no podrán unirse a sus reuniones debido al ámbito de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="3a8fc-127">Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="3a8fc-128">Puede establecer direcciones URL globales simples en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="3a8fc-129">Para establecer una dirección URL simple en el nivel del sitio, debe usar el cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="3a8fc-130">Asignar un nombre a las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="3a8fc-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="3a8fc-131">Hay tres opciones recomendadas para asignar nombres a las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="3a8fc-132">La opción que elija tiene implicaciones en cuanto a la configuración de los registros A de DNS y los certificados que admiten direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="3a8fc-133">En cada opción, debe configurar una dirección URL simple para cada dominio SIP de su organización.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="3a8fc-134">Siempre necesita una única dirección URL en toda la organización para el acceso telefónico y otra para el administrador, independientemente del número de dominios SIP que tenga.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="3a8fc-135">Para obtener más información sobre los certificados y los registros de DNS necesarios, consulte [requisitos de DNS para direcciones URL simples en Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) y [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="3a8fc-136">En la opción 1, puede crear un nuevo nombre de dominio SIP para cada dirección URL simple.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="3a8fc-137">Si usa esta opción, necesita un registro DNS (A) independiente para cada dirección URL simple, y cada reunión dirección URL simple debe tener un nombre en los certificados.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="3a8fc-138">Opción de nomenclatura de URL simple 1</span><span class="sxs-lookup"><span data-stu-id="3a8fc-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a8fc-139"><strong>Dirección URL sencilla</strong></span><span class="sxs-lookup"><span data-stu-id="3a8fc-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8fc-140"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="3a8fc-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8fc-141">Reunión</span><span class="sxs-lookup"><span data-stu-id="3a8fc-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="3a8fc-142">https://meet.contoso.com, https://meet.fabrikam.com, y así sucesivamente (uno para cada dominio SIP de su organización)</span><span class="sxs-lookup"><span data-stu-id="3a8fc-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a8fc-143">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="3a8fc-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8fc-144">Administrador</span><span class="sxs-lookup"><span data-stu-id="3a8fc-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3a8fc-145">Con la opción 2, las direcciones URL simples se basan en el nombre de dominio lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="3a8fc-146">Por lo tanto, solo necesita un registro DNS para habilitar los tres tipos de direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="3a8fc-147">Este registro A DNS hace referencia a lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="3a8fc-148">Además, aún necesitará un registro DNS A para otros dominios SIP de su organización.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="3a8fc-149">Opción de nomenclatura de URL simple 2</span><span class="sxs-lookup"><span data-stu-id="3a8fc-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a8fc-150"><strong>Dirección URL sencilla</strong></span><span class="sxs-lookup"><span data-stu-id="3a8fc-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8fc-151"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="3a8fc-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8fc-152">Reunión</span><span class="sxs-lookup"><span data-stu-id="3a8fc-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="3a8fc-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, y así sucesivamente (uno para cada dominio SIP de su organización)</span><span class="sxs-lookup"><span data-stu-id="3a8fc-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a8fc-154">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="3a8fc-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8fc-155">Administrador</span><span class="sxs-lookup"><span data-stu-id="3a8fc-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3a8fc-156">La opción 3 es más útil si tiene muchos dominios SIP y desea que tengan diferentes direcciones URL simples, pero quiere minimizar los requisitos de certificados y registros DNS para estas direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="3a8fc-157">Opción de nomenclatura de URL simple 3</span><span class="sxs-lookup"><span data-stu-id="3a8fc-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a8fc-158"><strong>Dirección URL sencilla</strong></span><span class="sxs-lookup"><span data-stu-id="3a8fc-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8fc-159"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="3a8fc-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8fc-160">Reunión</span><span class="sxs-lookup"><span data-stu-id="3a8fc-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a8fc-161">Acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="3a8fc-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8fc-162">Administrador</span><span class="sxs-lookup"><span data-stu-id="3a8fc-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="3a8fc-163">Nomenclatura de URL simple y reglas de validación</span><span class="sxs-lookup"><span data-stu-id="3a8fc-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="3a8fc-164">El generador de topología y los cmdlets del shell de administración de Lync Server exigen varias reglas de validación para las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="3a8fc-165">Debe establecer direcciones URL simples para reunirse y llamar, pero establecer una para administrador es opcional.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="3a8fc-166">Cada dominio SIP debe tener una dirección URL simple de reunirse, pero solo se necesita una dirección URL simple de marcación y una dirección URL simple de administración para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="3a8fc-167">Cada dirección URL simple de su organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL simple (por ejemplo, no puede establecer lync.contoso.com/Meet como su dirección URL simple y lync.contoso.com/Meet/Dialin como la dirección URL simple de marcado).</span><span class="sxs-lookup"><span data-stu-id="3a8fc-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="3a8fc-168">Los nombres de direcciones URL simples no pueden contener el FQDN de ninguna de sus agrupaciones ni ninguna información de https://FQDN:88/meet puerto (por ejemplo, no está permitido).</span><span class="sxs-lookup"><span data-stu-id="3a8fc-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="3a8fc-169">Todas las direcciones URL simples deben comenzar con el prefijo https://.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="3a8fc-170">Las direcciones URL simples solo pueden contener caracteres alfanuméricos (es decir, a-z, A-Z, 0-9 y el punto (.).</span><span class="sxs-lookup"><span data-stu-id="3a8fc-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="3a8fc-171">Si usa otros caracteres, es posible que las direcciones URL simples no funcionen de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="3a8fc-172">Cambiar direcciones URL simples después de la implementación</span><span class="sxs-lookup"><span data-stu-id="3a8fc-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="3a8fc-173">Si cambia una dirección URL simple después de la implementación inicial, debe tener en cuenta cómo afecta el cambio a los registros DNS y los certificados para las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="3a8fc-174">Si cambia la base de una dirección URL simple, debe cambiar también los certificados y los registros DNS.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="3a8fc-175">Por ejemplo, si cambia https://lync.contoso.com/Meet de https://meet.contoso.com para cambia la dirección URL base de Lync.contoso.com a meet.contoso.com, tendrá que cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="3a8fc-176">Si cambió la dirección URL simple de https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings, la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario realizar cambios en el certificado o DNS.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="3a8fc-177">Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar **enable-CsComputer** en cada director y en el servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="3a8fc-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a8fc-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a8fc-178">See Also</span></span>


[<span data-ttu-id="3a8fc-179">Requisitos de DNS para direcciones URL simples en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a8fc-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

