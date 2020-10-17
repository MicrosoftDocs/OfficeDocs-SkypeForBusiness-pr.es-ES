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
ms.openlocfilehash: 5aa98f8935a692f06b78db523e4e109e8cba9ddf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505437"
---
# <a name="new-and-changed-settings-for-lync-2013"></a>Configuración nueva y modificada para Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-05_

En este tema se tratan los cambios en los cmdlets del shell de administración de Lync Server que se relacionan directamente con la administración de clientes. Lync Server 2013 presenta varios parámetros nuevos y deja en desuso los parámetros de las características que se pueden configurar a través de otros medios.

<div>

## <a name="new-client-management-parameters"></a>Nuevos parámetros de administración de cliente


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nuevo</th>
<th>Cmdlet de Shell de administración de Lync Server</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Cuando se establece en true, el seguimiento de software se habilita en Lync; Si se establece en false, el seguimiento de software se deshabilitará. El seguimiento de software implica mantener un registro detallado de todo lo que hace un programa (incluso el seguimiento de llamadas API). El seguimiento es más útil para los programadores y el personal de soporte técnico de aplicaciones. Esta configuración es equivalente a la opción de directiva de grupo de Communications Server 2007 R2 para &quot; activar el seguimiento de Communicator. &quot; La configuración es la siguiente:</p>
<ul>
<li><p>Off = El seguimiento está deshabilitado y el usuario no puede cambiar este valor.</p></li>
<li><p>Light = Se realiza el seguimiento mínimo y el usuario no puede cambiar este valor.</p></li>
<li><p>On = Se realiza el seguimiento detallado y el usuario no puede cambiar este valor.</p></li>
</ul>
<p>De forma predeterminada, TracingLevel se establece en un valor nulo. Esto significa que se realiza el seguimiento mínimo y que el usuario puede habilitarlo o deshabilitarlo.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Si se establece en True ($True), permite que las secuencias de audio y vídeo se separen del tráfico de red restante. A su vez, esto permite a los dispositivos cliente codificar y descodificar audio y vídeo de forma local. Por lo general, el redireccionamiento de los medios da como resultado un uso menor del ancho de banda, una mayor escalabilidad del servidor y una experiencia de usuario óptima en comparación con técnicas similares, como la comunicación remota de dispositivos o la compresión de códecs.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Cuando se establece en true, todas las reuniones de Lync se tratan como &quot; reuniones grandes. &quot; Con una reunión grande, las restricciones se colocan en el número de notificaciones que se envían a los participantes, además del tamaño de la lista de la reunión que se transmite de forma predeterminada.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Si se establece en True ($True), los usuarios no pueden agregar anotaciones a las diapositivas de PowerPoint que se usan en una conferencia. Sin embargo (dependiendo del valor de la propiedad AllowAnnotations), los usuarios mantienen el acceso a otras características de la pizarra electrónica. El valor predeterminado es False, lo que significa que se permiten las anotaciones de PowerPoint.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Si se establece en True (valor predeterminado), todos los blocs de notas de OneNote abiertos y vinculados con la conferencia se actualizan automáticamente con información como, por ejemplo, los participantes de la conferencia e información detallada sobre el contenido que se ha compartido durante la misma.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Se usa junto con los otros parámetros de CsMeetingConfiguration para personalizar las invitaciones a reuniones generadas por el complemento de reunión en línea para Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega el logotipo de la organización a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013. El usuario especifica la dirección URL de una imagen GIF o JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega la dirección URL de ayuda o soporte técnico de la organización a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega texto legal o texto de declinación de responsabilidades a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013. El usuario especifica la dirección URL para la ubicación del texto.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega un pie de página personalizado a todas las invitaciones generadas por el complemento de reunión en línea para Lync 2013. El usuario especifica la dirección URL para la ubicación del texto del pie de página personalizado.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>Parámetros de administración de clientes desusados


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Parámetro</th>
<th>Cmdlet de Shell de administración de Lync Server</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parámetro ha quedado obsoleto para su uso con Lync Server 2013. Cuando se usa en combinación con EnableEnterpriseCustomizedHelp, este parámetro habilitaba una organización para especificar una dirección URL de modo que, cuando los usuarios hace clic en el menú ayuda en Lync, se mostrara la ayuda personalizada.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parámetro ha quedado obsoleto para su uso con Lync Server 2013. Cuando se usa en combinación con CustomizedHelpUrl, este parámetro permitió a las organizaciones Mostrar la ayuda personalizada.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>El parámetro EnableSQMData del cmdlet Set-CSClientPolicy se ha quitado en Lync Server 2013. En su lugar, puede usar el valor compartido de directiva de grupo para los datos de la administración de calidad de software (SQM), para determinar la interfaz de usuario para la opción de mejora de la experiencia del usuario en la página de opciones generales del cliente de Lync:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Valor</p>
<p>1 = Mostrar y activar la casilla (el usuario puede desactivarla).</p>
<p>0 = Desactivar y deshabilitar la casilla (el usuario no puede invalidarlo).</p>
<p>Null = El valor lo determina la configuración de Office y se muestra la casilla para que el usuario la configure según estime conveniente.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parámetro se ha quitado. En su lugar, al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada. Esto significa que todos los contactos de un usuario se conservan en Exchange y se encuentran disponibles en Lync, Outlook y Outlook Web Access. Puede usar el cmdlet Set-CsUserServicesPolicy para personalizar qué usuarios disponen de este almacén de contactos unificado. También puede habilitar a los usuarios de forma global, por sitio, inquilino, individuo o grupo de individuos. Para obtener más información, consulte <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Habilitar usuarios para el almacén de contactos unificados en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parámetro no se usa en Lync 2013. En versiones anteriores, este parámetro especificaba la frecuencia con la que el cliente recuperaba datos de MAPI de las carpetas públicas de Exchange.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parámetro quedó en desuso en Lync 2013.</p></td>
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

