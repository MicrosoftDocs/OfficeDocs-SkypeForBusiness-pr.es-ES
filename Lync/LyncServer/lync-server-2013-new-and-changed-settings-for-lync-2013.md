---
title: 'Lync Server 2013: configuración nueva y modificada para Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de4a1a82dbefb5a7f55a4c5872a6702933af08c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="2ab16-102">Configuración nueva y modificada para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2ab16-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ab16-103">_**Última modificación del tema:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="2ab16-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="2ab16-104">En este tema se tratan los cambios en los cmdlets del shell de administración de Lync Server que se relacionan directamente con la administración de clientes.</span><span class="sxs-lookup"><span data-stu-id="2ab16-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="2ab16-105">Lync Server 2013 presenta varios parámetros nuevos y deja en desuso los parámetros de las características que se pueden configurar a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="2ab16-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="2ab16-106">Nuevos parámetros de administración de cliente</span><span class="sxs-lookup"><span data-stu-id="2ab16-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ab16-107">New</span><span class="sxs-lookup"><span data-stu-id="2ab16-107">New</span></span></th>
<th><span data-ttu-id="2ab16-108">Cmdlet de Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="2ab16-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="2ab16-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ab16-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="2ab16-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="2ab16-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-112">Cuando se establece en true, el seguimiento de software se habilita en Lync; Si se establece en false, el seguimiento de software se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="2ab16-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="2ab16-113">El seguimiento de software implica mantener un registro detallado de todo lo que hace un programa (incluso el seguimiento de llamadas API).</span><span class="sxs-lookup"><span data-stu-id="2ab16-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="2ab16-114">El seguimiento es más útil para los programadores y el personal de soporte técnico de aplicaciones. Esta configuración es equivalente a la opción &quot;de directiva de grupo de Communications Server 2007 R2 para activar el seguimiento de Communicator. &quot; La configuración es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ab16-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ab16-115">Off = El seguimiento está deshabilitado y el usuario no puede cambiar este valor.</span><span class="sxs-lookup"><span data-stu-id="2ab16-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="2ab16-116">Light = Se realiza el seguimiento mínimo y el usuario no puede cambiar este valor.</span><span class="sxs-lookup"><span data-stu-id="2ab16-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="2ab16-117">On = Se realiza el seguimiento detallado y el usuario no puede cambiar este valor.</span><span class="sxs-lookup"><span data-stu-id="2ab16-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="2ab16-p103">De forma predeterminada, TracingLevel se establece en un valor nulo. Esto significa que se realiza el seguimiento mínimo y que el usuario puede habilitarlo o deshabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="2ab16-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="2ab16-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="2ab16-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-p104">Si se establece en True ($True), permite que las secuencias de audio y vídeo se separen del tráfico de red restante. A su vez, esto permite a los dispositivos cliente codificar y descodificar audio y vídeo de forma local. Por lo general, el redireccionamiento de los medios da como resultado un uso menor del ancho de banda, una mayor escalabilidad del servidor y una experiencia de usuario óptima en comparación con técnicas similares, como la comunicación remota de dispositivos o la compresión de códecs.</span><span class="sxs-lookup"><span data-stu-id="2ab16-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="2ab16-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="2ab16-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="2ab16-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="2ab16-126">Cuando se establece en true, todas las reuniones de Lync &quot;se tratan como reuniones grandes. &quot; Con una reunión grande, las restricciones se colocan en el número de notificaciones que se envían a los participantes, además del tamaño de la lista de la reunión que se transmite de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2ab16-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="2ab16-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="2ab16-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="2ab16-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="2ab16-p105">Si se establece en True ($True), los usuarios no pueden agregar anotaciones a las diapositivas de PowerPoint que se usan en una conferencia. Sin embargo (dependiendo del valor de la propiedad AllowAnnotations), los usuarios mantienen el acceso a otras características de la pizarra electrónica. El valor predeterminado es False, lo que significa que se permiten las anotaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="2ab16-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="2ab16-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="2ab16-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="2ab16-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="2ab16-134">Si se establece en True (valor predeterminado), todos los blocs de notas de OneNote abiertos y vinculados con la conferencia se actualizan automáticamente con información como, por ejemplo, los participantes de la conferencia e información detallada sobre el contenido que se ha compartido durante la misma.</span><span class="sxs-lookup"><span data-stu-id="2ab16-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="2ab16-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="2ab16-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ab16-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="2ab16-137">Se usa junto con los otros parámetros de CsMeetingConfiguration para personalizar las invitaciones a reuniones generadas por el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="2ab16-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="2ab16-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ab16-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="2ab16-140">Agrega el logotipo de la organización a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="2ab16-141">El usuario especifica la dirección URL de una imagen GIF o JPG.</span><span class="sxs-lookup"><span data-stu-id="2ab16-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="2ab16-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="2ab16-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ab16-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="2ab16-144">Agrega la dirección URL de ayuda o soporte técnico de la organización a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="2ab16-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="2ab16-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ab16-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="2ab16-147">Agrega texto legal o texto de declinación de responsabilidades a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="2ab16-148">El usuario especifica la dirección URL para la ubicación del texto.</span><span class="sxs-lookup"><span data-stu-id="2ab16-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="2ab16-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="2ab16-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ab16-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="2ab16-151">Agrega un pie de página personalizado a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="2ab16-152">El usuario especifica la dirección URL para la ubicación del texto del pie de página personalizado.</span><span class="sxs-lookup"><span data-stu-id="2ab16-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="2ab16-153">Parámetros de administración de clientes desusados</span><span class="sxs-lookup"><span data-stu-id="2ab16-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ab16-154">Parámetro</span><span class="sxs-lookup"><span data-stu-id="2ab16-154">Parameter</span></span></th>
<th><span data-ttu-id="2ab16-155">Cmdlet de Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="2ab16-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="2ab16-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ab16-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="2ab16-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="2ab16-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-159">Este parámetro ha quedado obsoleto para su uso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="2ab16-160">Cuando se usa en combinación con EnableEnterpriseCustomizedHelp, este parámetro habilitaba una organización para especificar una dirección URL de modo que, cuando los usuarios hace clic en el menú ayuda en Lync, se mostrara la ayuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="2ab16-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="2ab16-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="2ab16-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-163">Este parámetro ha quedado obsoleto para su uso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="2ab16-164">Cuando se usa en combinación con CustomizedHelpUrl, este parámetro permitió a las organizaciones Mostrar la ayuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="2ab16-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="2ab16-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="2ab16-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-167">El parámetro EnableSQMData del cmdlet Set-CSClientPolicy se ha eliminado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="2ab16-168">En su lugar, puede usar el valor compartido de directiva de grupo para los datos de la administración de calidad de software (SQM), para determinar la interfaz de usuario para la opción de mejora de la experiencia del usuario en la página de opciones generales del cliente de Lync:</span><span class="sxs-lookup"><span data-stu-id="2ab16-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="2ab16-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="2ab16-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="2ab16-170">Valor</span><span class="sxs-lookup"><span data-stu-id="2ab16-170">Values:</span></span></p>
<p><span data-ttu-id="2ab16-171">1 = Mostrar y activar la casilla (el usuario puede desactivarla).</span><span class="sxs-lookup"><span data-stu-id="2ab16-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="2ab16-172">0 = Desactivar y deshabilitar la casilla (el usuario no puede invalidarlo).</span><span class="sxs-lookup"><span data-stu-id="2ab16-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="2ab16-173">Null = El valor lo determina la configuración de Office y se muestra la casilla para que el usuario la configure según estime conveniente.</span><span class="sxs-lookup"><span data-stu-id="2ab16-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="2ab16-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="2ab16-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-176">Este parámetro se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="2ab16-176">This parameter has been removed.</span></span> <span data-ttu-id="2ab16-177">En su lugar, al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2ab16-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="2ab16-178">Esto significa que todos los contactos de un usuario se conservan en Exchange y se encuentran disponibles en Lync, Outlook y Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="2ab16-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="2ab16-179">Puede usar el cmdlet Set-CsUserServicesPolicy para personalizar qué usuarios disponen de este almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="2ab16-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="2ab16-180">También puede habilitar a los usuarios de forma global, por sitio, inquilino, individuo o grupo de individuos.</span><span class="sxs-lookup"><span data-stu-id="2ab16-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="2ab16-181">Para obtener más información, consulte <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Habilitar usuarios para el almacén de contactos unificados en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2ab16-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab16-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="2ab16-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="2ab16-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-184">Este parámetro no se usa en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="2ab16-185">En versiones anteriores, este parámetro especificaba la frecuencia con la que el cliente recuperaba datos de MAPI de las carpetas públicas de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2ab16-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab16-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="2ab16-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="2ab16-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2ab16-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="2ab16-188">Este parámetro quedó en desuso en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab16-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

