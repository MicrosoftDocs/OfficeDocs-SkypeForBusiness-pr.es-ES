---
title: Nueva configuración y configuración modificada para Lync 2013
TOCTitle: Nueva configuración y configuración modificada para Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48276505
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nueva configuración y configuración modificada para Lync 2013

 

_**Última modificación del tema:** 2015-03-09_

Este tema analiza los cambios que se han realizado en los cmdlets de Shell de administración de Lync Server, directamente relacionados con la administración de cliente. Lync Server 2013 introduce varios parámetros nuevos y deja de usar parámetros de características que se pueden configurar a través de otros medios.

## Nuevos parámetros de administración de cliente


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
<td><p>Si se establece en True, se habilita el seguimiento de software en Lync y, si se establece en False, se deshabilita. El seguimiento de software implica mantener un registro detallado de todas las acciones de un programa (incluido el seguimiento de las llamadas API). El seguimiento resulta útil fundamentalmente para los desarrolladores y para el personal de soporte de aplicaciones. Este valor es equivalente al valor &quot;Activar el seguimiento para Communicator&quot; de directiva de grupo de Communications Server 2007 R2. Los posibles valores son los siguientes:</p>
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
<td><p>Si se establece en True, todas las reuniones de Lync se consideran &quot;reuniones grandes&quot;, donde se restringe la cantidad de notificaciones que se envían a los participantes y el tamaño de la lista de reuniones que se transmite de forma predeterminada.</p></td>
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
<td><p>Se usa junto con los demás parámetros nuevos de tipo CsMeetingConfiguration para personalizar las invitaciones a reuniones que genera Complemento para conferencia en línea para Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega el logotipo de la organización a todas las invitaciones que genera Complemento para conferencia en línea para Lync 2013. El usuario especifica la dirección URL de una imagen GIF o JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega la dirección URL de ayuda o soporte de la organización a todas las invitaciones que genera Complemento para conferencia en línea para Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega el texto legal o de declinación de responsabilidades a todas las invitaciones que genera Complemento para conferencia en línea para Lync 2013. El usuario especifica la dirección URL para la ubicación del texto.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Agrega un pie de página personalizado a todas las invitaciones que genera Complemento para conferencia en línea para Lync 2013. El usuario especifica la dirección URL para la ubicación del texto del pie de página personalizado.</p></td>
</tr>
<tr class="odd">
<td><p>IsPublicDisclosureAllowed</p></td>
<td><p>CsWebServiceConfiguration</p></td>
<td><p>Habilita la nueva versión de 2013 de Lync Web App. La nueva versión de Lync Web App no está habilitada de manera predeterminada y debe habilitarla el administrador.</p></td>
</tr>
</tbody>
</table>


## Parámetros de administración de clientes desusados


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
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>El parámetro EnableSQMData del cmdlet Set-CSClientPolicy se ha quitado de Lync Server 2013. En su lugar, puede usar el valor compartido de directiva de grupo para los datos de la administración de calidad de software (SQM), para determinar la interfaz de usuario para la opción de mejora de la experiencia del usuario en la página de opciones generales del cliente de Lync:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Valores:</p>
<p>1 = Mostrar y activar la casilla (el usuario puede desactivarla).</p>
<p>0 = Desactivar y deshabilitar la casilla (el usuario no puede invalidarlo).</p>
<p>Null = El valor lo determina la configuración de Office y se muestra la casilla para que el usuario la configure según estime conveniente.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parámetro se ha quitado. En su lugar, al implementar Lync Server 2013 y publicar la topología, se habilita de forma predeterminada el almacén de contactos unificado para todos los usuarios. Esto significa que todos los contactos de un usuario se conservan en Exchange y se encuentran disponibles en Lync, Outlook y Outlook Web Access. Puede usar el cmdlet Set-CsUserServicesPolicy para personalizar qué usuarios disponen de este almacén de contactos unificado. También puede habilitar a los usuarios de forma global, por sitio, inquilino, individuo o grupo de individuos. Para más información, consulte <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Habilitar usuarios para el almacenamiento de contactos unificado en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lync 2013 no usa este parámetro. En versiones anteriores, este parámetro especificaba la frecuencia con la que el cliente recuperaba datos de MAPI de las carpetas públicas de Exchange.</p></td>
</tr>
</tbody>
</table>

