---
title: 'Lync Server 2013: configuración nueva y modificada para Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Configuración nueva y modificada para Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-05_

En este tema se tratan los cambios en los cmdlets del shell de administración de Lync Server que se relacionan directamente con la administración de clientes. Lync Server 2013 introduce varios parámetros nuevos y deja obsoletos los parámetros de las características que se pueden configurar por otros medios.

<div>

## <a name="new-client-management-parameters"></a>Nuevos parámetros de administración de clientes


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nuevo</th>
<th>Cmdlet del shell de administración de Lync Server</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>ClientPolicy</p></td>
<td><p>Cuando se establece en true, el seguimiento de software se habilita en Lync; Cuando se establece en false, el seguimiento de software se deshabilitará. El seguimiento de software implica mantener un registro detallado de todo lo que hace un programa (incluido el seguimiento de llamadas API). El seguimiento es principalmente útil para los programadores y el personal de soporte técnico de aplicaciones. Esta configuración es equivalente a la configuración &quot;de directiva de grupo de Communications Server 2007 R2 para activar el seguimiento de Communicator. &quot; La configuración es la siguiente:</p>
<ul>
<li><p>OFF = el seguimiento está deshabilitado y el usuario no puede cambiar esta configuración.</p></li>
<li><p>Light = se realiza un seguimiento mínimo y el usuario no puede cambiar esta configuración.</p></li>
<li><p>On = se realiza el seguimiento detallado y el usuario no puede cambiar esta configuración.</p></li>
</ul>
<p>De forma predeterminada TracingLevel se establece en un valor nulo. Eso significa que se realiza un seguimiento mínimo, pero el usuario puede habilitar o deshabilitar este seguimiento mínimo.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>ClientPolicy</p></td>
<td><p>Cuando se establece en true ($True) permite que las secuencias de audio y vídeo se separen de otro tráfico de red, a su vez, esto permite que los dispositivos cliente realicen la codificación y la descodificación de audio y vídeo de forma local. Normalmente, el redireccionamiento de medios tiene un uso de ancho de banda menor, una mayor escalabilidad del servidor y una experiencia de usuario más óptima en comparación con técnicas similares, como el acceso remoto del dispositivo o la compresión de códec.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Cuando se establece en true, todas las reuniones de Lync &quot;se tratan como reuniones grandes. &quot; En una reunión grande, se colocan restricciones en el número de notificaciones que se envían a los participantes, además del tamaño de la lista de la reunión que se transmite de forma predeterminada.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Cuando se establece en true ($True), los usuarios no podrán agregar anotaciones a las diapositivas de PowerPoint usadas en una conferencia. Sin embargo (según el valor de la propiedad AllowAnnotations), los usuarios seguirán teniendo acceso a otras características de pizarra. El valor predeterminado es false, lo que significa que se permiten las anotaciones de PowerPoint.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Cuando se establece en true (valor predeterminado), cualquier Bloc de notas de OneNote abierto vinculado a la Conferencia se actualizará automáticamente con información como los participantes de la Conferencia, así como detalles sobre el contenido compartido durante la Conferencia.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Se usa junto con los otros parámetros de CsMeetingConfiguration para personalizar las invitaciones a reuniones generadas por el complemento de reunión en línea para Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega el logotipo de su organización a todas las invitaciones generadas por el complemento de reuniones en línea para Lync 2013. Especifique la dirección URL de una imagen GIF o JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega la dirección URL de ayuda o soporte técnico de la organización a todas las invitaciones generadas por el complemento de reuniones en línea para Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega texto legal o texto de renuncia a todas las invitaciones generadas por el complemento de reuniones en línea para Lync 2013. Especifique la dirección URL de la ubicación del texto.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega un pie de página personalizado a todas las invitaciones generadas por el complemento de reuniones en línea para Lync 2013. Especifique la dirección URL de la ubicación del texto del pie de página personalizado.</p></td>
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
<th>Cmdlet del shell de administración de Lync Server</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>ClientPolicy</p></td>
<td><p>Este parámetro ha quedado obsoleto para usarse con Lync Server 2013. Cuando se usa conjuntamente con EnableEnterpriseCustomizedHelp, este parámetro permitió a una organización especificar una dirección URL para que cuando los usuarios hagan clic en el menú ayuda en Lync, se muestre una ayuda personalizada.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>ClientPolicy</p></td>
<td><p>Este parámetro ha quedado obsoleto para usarse con Lync Server 2013. Cuando se usa conjuntamente con CustomizedHelpUrl, este parámetro permitió que las organizaciones mostraran ayuda personalizada.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>ClientPolicy</p></td>
<td><p>El parámetro EnableSQMData del cmdlet Set-ClientPolicy se ha eliminado en Lync Server 2013. En su lugar, puede usar la configuración de directiva de grupo compartida para datos de administración de calidad de software (SQM) para determinar la interfaz de usuario para la opción de mejora de la experiencia del cliente en la página Opciones generales del cliente de Lync:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Los</p>
<p>1 = Mostrar y seleccionar la casilla (el usuario puede desactivar la casilla de verificación)</p>
<p>0 = desactivar y deshabilitar la casilla (el usuario no puede reemplazar)</p>
<p>Null = el valor está determinado por el programa de instalación de Office y se muestra la casilla de verificación para que los usuarios establezcan lo que elijan.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>ClientPolicy</p></td>
<td><p>Este parámetro se ha eliminado. En su lugar, al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada. Esto significa que todos los contactos de un usuario se guardan en Exchange y que están disponibles en Lync, Outlook y Outlook Web Access. Puede usar el cmdlet Set-CsUserServicesPolicy para personalizar qué usuarios tienen disponible el almacén de contactos unificado. Puede habilitar usuarios de forma global, por sitio, por inquilino o por individuos o grupos de personas. Para obtener más información, vea <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Habilitar usuarios para el almacenamiento de contactos unificado en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>ClientPolicy</p></td>
<td><p>Este parámetro no se usa en Lync 2013. En versiones anteriores, este parámetro especificaba la frecuencia con la que el cliente recuperó datos MAPI de las carpetas públicas de Exchange.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>ClientPolicy</p></td>
<td><p>Este parámetro quedó obsoleto en Lync 2013.</p></td>
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

