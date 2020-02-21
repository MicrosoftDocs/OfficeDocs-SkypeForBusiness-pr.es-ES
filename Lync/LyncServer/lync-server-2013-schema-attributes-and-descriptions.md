---
title: 'Lync Server 2013: atributos de esquema y descripciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1c8259312e3ba4e939bd784e189f5aae495605d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Atributos y descripciones de esquema en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En esta sección se describen todos los atributos de esquema que usa Lync Server 2013. Para las clases asociadas a los atributos, consulte [atributos de esquema por clase en Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Para obtener una lista de las clases y atributos que son nuevos en Lync Server 2013, vea [cambios en el esquema en Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Los atributos que son pares vinculados se especifican como vínculos hacia delante o hacia atrás. Un atributo que hace referencia a otro objeto es un vínculo hacia delante; el atributo del otro objeto que hace referencia al primer objeto es un vínculo hacia atrás. Los vínculos hacia delante se pueden actualizar, mientras que los vínculos hacia atrás son de solo lectura.

Algunos atributos tienen un valor de máscara de bits. Para estos atributos, cada configuración se representa por un bit, y el valor decimal mostrado representa la posición del bit. Las posiciones de bit comienzan con el bit 0. Por ejemplo, 1 (binario) es el bit 0 definido y 10000 (binario) es el bit 4 definido. Cada bit representa una propiedad. A continuación, se muestran algunos ejemplos:

  - 10000 (binario) tiene un valor decimal de 16 (es decir, se establece el bit 4).

  - 100000000 (binario) tiene un valor decimal de 256 (es decir, se establece el bit 8).

  - 1100 (binario) tienen un valor decimal de 12 (es decir, se establecen los bits 2 y 3; se habilitan las propiedades representadas por ambos bits).

  - 1111000001 (binario) tiene un valor decimal de 961 (es decir, se establecen los bits 0, 6, 7, 8 y 9; se habilitan las propiedades de cada uno de estos bits).

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Atributos de esquema para Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descripción</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Un atributo existente en los servicios de dominio de Active Directory que ahora está asociado con las clases <strong>msRTCSIP-Pool</strong> y <strong>msRTCSIP-MonitoringServer</strong> . Este atributo especifica el nombre de dominio completo (FQDN) de un grupo o servidor de supervisión.</p>
<p>Un valor válido para cada segmento es 63 caracteres; un valor válido para el FQDN completo es 255 caracteres.</p></td>
<td><p>Nuevo en Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Este atributo contiene la representación de cadena del nombre distintivo (DN) del objeto en otro bosque que se corresponde con este objeto. Se usa para la expansión de grupos de distribución y la asistencia automática. Este atributo se define en el esquema predeterminado de Active Directory para Windows Server 2003 R2.</p>
<p>Para que no sea necesaria una actualización de AD DS a Windows 2003 R2, la preparación del esquema de Active Directory extiende el esquema de Windows Server 2003 con esta definición de atributos.</p></td>
<td><p>Nuevo en Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Este atributo de varios valores contiene la configuración del correo de voz. Este atributo se comparte con mensajería unificada de Exchange (UM).</p></td>
<td><p>Nuevo en Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario. Las directivas de retención conservan los elementos del buzón del usuario durante toda la retención. Este atributo se comparte con Exchange 2013.</p></td>
<td><p>Nuevo en Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Este atributo almacena información sobre el proveedor de servicios de audioconferencia de un usuario.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Este atributo apunta a la entrada de servicio de confianza del contacto de la aplicación.</p></td>
<td><p>Novedad en Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>Este atributo contiene una lista de aplicaciones hospedadas en el servidor de aplicaciones.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Este atributo especifica las opciones del contacto de la aplicación.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Este atributo contiene el idioma principal del contacto de la aplicación.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Este atributo de varios valores contiene los idiomas secundarios del contacto de la aplicación.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Este atributo contiene una lista de los servidores de aplicaciones que pertenecen a este grupo de servidores. El vínculo hacia delante correspondiente a este atributo de vínculo hacia atrás es <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Este atributo apunta al grupo al que pertenece este servidor de aplicaciones. Es el vínculo hacia delante. El vínculo hacia atrás correspondiente es <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (obsoleto)</p></td>
<td><p>Este atributo especifica el valor predeterminado global dentro del límite del bosque para archivar todas las comunicaciones del usuario. Lo aplica la capa del agente de archivado. El intervalo de valores de este atributo es el siguiente:</p>
<ul>
<li><p><strong>TRUE</strong>: se archivan todos los usuarios</p></li>
<li><p><strong>FALSE</strong>: no se archivan todos los usuarios</p></li>
</ul>
<p>Este atributo controla, dentro del límite del bosque y de manera global, cómo se archivan las comunicaciones de los usuarios en una red interna.</p>
<p><strong>Comportamiento de Live Communications Server 2005 (ahora retirado)</strong></p>
<p>El intervalo de valores de este atributo es el siguiente:</p>
<ul>
<li><p>0: se archiva el cuerpo del mensaje [bit 0]</p></li>
<li><p>1: no se archiva el cuerpo del mensaje [bit 0]</p></li>
</ul>
<p><strong>Comportamiento de Office Communications Server 2007</strong></p>
<p>El intervalo de valores de este atributo es el siguiente:</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (retirado)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Este atributo es un entero que se usa como un campo de bits para controlar si se archivan las comunicaciones de un usuario. Este control lo aplica la capa del agente de archivado. Se marca para la replicación del catálogo global.</p>
<p>El ámbito de este atributo es específico de un único usuario o contacto. Los valores válidos (y las posiciones de bits asociadas) en Lync Server son los siguientes:</p>
<ul>
<li><p>0: No archivar (ningún bit establecido)</p></li>
<li><p>1: Retirado (posición de bit 0)</p></li>
<li><p>2: Retirado (posición de bit 1)</p></li>
<li><p>4: Archivar comunicaciones internas (posición de bit 2)</p></li>
<li><p>8: Archivar comunicaciones federadas (posición de bit 3)</p></li>
</ul>
<p>Los valores válidos anteriormente en Live Communications Server 2005 son los siguientes:</p>
<ul>
<li><p>0: Usar el valor predeterminado definido por <strong>msRTCSIP-ArchiveDefault</strong> y <strong>msRTCSIP-ArchiveFederation</strong>, por este orden de prioridad.</p>
<ul>
<li><p>1: Archivar</p></li>
<li><p>2: No archivar</p></li>
<li><p>3: Archivar sin el cuerpo del mensaje</p></li>
</ul></li>
</ul></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (obsoleto)</p></td>
<td><p>Este atributo define la versión del servicio de archivado. Este atributo es un tipo entero que se incrementa con cada versión del producto oficial. Los valores válidos posibles son:</p>
<ul>
<li><p>Sin definir: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Este atributo especifica el FQDN del servidor back-end del grupo de servidores. Como solamente puede haber un servidor back-end por cada grupo de servidores, este atributo tiene un solo valor.</p>
<p>El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Este atributo contiene el identificador del grupo de servidores que hospeda el directorio de conferencia.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Este atributo contiene el identificador de un directorio de conferencia.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Este atributo contiene el identificador del grupo de servidores al que se va a mover el directorio de conferencia.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-default</p></td>
<td><p>Este atributo booleano define si el uso del teléfono es un uso predeterminado. Si este atributo está establecido en <strong>TRUE</strong>, el uso del teléfono es un uso predeterminado y el administrador no puede eliminarlo. Si este atributo está establecido en <strong>FALSE</strong>, el uso se puede eliminar.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están fuera de la organización.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están dentro de la organización.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsoleto)</p></td>
<td><p>Este atributo de un solo valor contiene el nombre distintivo (DN) de un objeto de clase de perfil de ubicación asignado a él.</p>
<p>Vínculo hacia delante: <strong>identificador de vínculo 11036</strong></p>
<p>El vínculo hacia atrás correspondiente es <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsoleto)</p></td>
<td><p>Este atributo booleano especifica si la directiva es una directiva predeterminada. La directiva es una directiva predeterminada cuando está establecida en <strong>TRUE</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</p></td>
<td><p>Este atributo especifica el FQDN del servidor perimetral que ejecuta el servicio perimetral de acceso, si se puede tener acceso a él directamente o del equilibrador de carga de hardware para un grupo de servidores que ejecutan el servicio perimetral de acceso. Si a los servidores que ejecutan el servicio perimetral de acceso solo se puede obtener acceso a través de uno o varios directores, este atributo especifica el FQDN y, opcionalmente, el número de puerto del director o del equilibrador de carga de hardware que atiende a un grupo de directores.</p>
<p>El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</p></td>
<td><p>Este atributo representa el número de puerto que se debe usar para conectar con el servidor que ejecuta el servicio perimetral de acceso.</p>
<p>El valor válido es un entero que especifica el puerto que se debe usar. El valor predeterminado es 5061.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de suscripción de presencia predeterminado.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de registro predeterminado.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de suscripción de datos móviles predeterminado.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Este atributo se usa en una topología de dominio dividido y contiene un nombre de dominio completo (FQDN).</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (obsoleto)</p></td>
<td><p>Este atributo de cadena UNICODE de un solo valor contiene una descripción sencilla de esta ruta de teléfono o regla de normalización.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Este atributo representa un dominio configurado para el registrador.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Este atributo especifica el FQDN del servidor que ejecuta el servicio perimetral de acceso.</p>
<p>El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsoleto)</p></td>
<td><p>Este atributo controla si un servidor genera una solicitud Best Effort NOTIFY (BENOTIFY), o NOTIFY de "mejor esfuerzo", en lugar de una solicitud NOTIFY, en respuesta a una solicitud SUBSCRIBE de un cliente. BENOTIFY es una extensión que mejora el rendimiento para el protocolo de enlace de notificaciones de suscripción mediante la cual el servidor genera solicitudes BENOTIFY en lugar de las solicitudes NOTIFY normales. La ventaja desde el punto de vista del rendimiento consiste en que una solicitud BENOTIFY no requiere una respuesta 200 OK del cliente, a diferencia de la solicitud NOTIFY.</p>
<p>Los valores válidos son <strong>TRUE</strong> o <strong>FALSE</strong>.</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 no admite solicitudes BENOTIFY. Para interactuar con las aplicaciones de servidor escritas con la API de servidor de Live Communications Server 2003 que se ejecuta en servidores de Live Communications Server 2005 y de terceros, las solicitudes BENOTIFY se pueden deshabilitar estableciendo su valor en <STRONG>false</STRONG>. Actualmente, BENOTIFY no forma parte del proceso de normalización del SIP del Grupo de trabajo de ingeniería de Internet (IETF).


</div></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsoleto)</p></td>
<td><p>Este atributo es un modificador global que los administradores de TI usan para configurar si los usuarios pueden comunicarse con usuarios de otras organizaciones. Permite al administrador invalidar el atributo <strong>FederationEnabled</strong> de un usuario concreto. Este atributo puede ser útil para ayudar a proteger la red interna de ataques procedentes de Internet producidos por gusanos o virus, o ataques concretos dirigidos a la compañía.</p>
<p>Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</p>
<ul>
<li><p>1: Habilitado para la conectividad de mensajería instantánea pública (posición de bit 0)</p></li>
<li><p>2: Reservado (posición de bit 1)</p></li>
<li><p>4: Reservado (posición de bit 2)</p></li>
<li><p>8: Reservado (posición de bit 3)</p></li>
<li><p>16: Habilitado para el control remoto de llamadas [Telefonía] (posición de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (posición de bit 6)</p></li>
<li><p>128: UCEnabled (habilitar a los usuarios para las comunicaciones unificadas) (posición de bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar a los usuarios para la conectividad de mensajería instantánea pública) (posición de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posición de bit 9)</p></li>
</ul></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Este atributo indica si los Enterprise Services se cargan en el servidor determinado.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Este atributo contiene el código de marcado para el acceso externo.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Este atributo controla si un usuario está habilitado para la federación. Lo aplica la capa de los Enterprise Services. Se marca para la replicación del catálogo global.</p>
<p>Los valores válidos son <strong>true</strong> o <strong>false</strong>.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Este atributo es una lista de varios valores que contiene los nombres de dominio de todos los servidores Enterprise Edition asociados a un grupo de servidores.</p>
<p>Vínculo hacia atrás: <strong>identificador de vínculo 11023</strong></p>
<p>El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (obsoleto)</p></td>
<td><p>Este atributo de cadena de varios valores contiene una lista de puertas de enlace y puertos (por puerta de enlace).</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsoleto)</p></td>
<td><p>Este atributo almacena los pares de nombre:valor. El par nombre:valor ya definido corresponde al valor para <strong>permitir la consulta de la información de presencia</strong>.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Este atributo es un identificador único de un grupo que se usa para agrupar entradas de la libreta de direcciones.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2003 (no usado).</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2003.</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2003 (no usado).</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Este atributo controla si un usuario está habilitado para el acceso de usuarios externos. Lo aplica la capa de los Enterprise Services. Se marca para la replicación del catálogo global.</p>
<p>Los valores válidos son <strong>TRUE</strong> o <strong>FALSE</strong>.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2003</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-line</p></td>
<td><p>Este atributo de un solo valor contiene el identificador del dispositivo (el URI del SIP o el URI de TEL? o del teléfono que el usuario controla) que usa Lync para la telefonía. Este atributo se marca para la replicación del catálogo global y se indiza. Si un usuario se habilita para Telefonía IP empresarial, este atributo almacena la versión normalizada E.164 del número de teléfono del usuario.</p></td>
<td><p>Novedad en Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Este atributo de un solo valor contiene el URI del SIP del servidor de puerta de enlace CSTA-SIP. Este atributo se marca para la replicación del catálogo global, pero no se indiza.</p></td>
<td><p>Novedad en Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (obsoleto)</p></td>
<td><p>Este atributo de varios valores contiene una lista de nombres distintivos (DN) de normalización local asociados a este perfil de ubicación. El tipo de este atributo es un binario DN. Existe una relación uno a varios entre el perfil de ubicación y las reglas de normalización locales. El orden de la lista de DN de normalización local se debe mantener en el orden que especifica el administrador. La conservación del orden la mantiene la parte binaria del DN binario, que especifica el índice de orden.</p>
<p>Vínculo hacia delante: <strong>identificador de vínculo 11034</strong></p>
<p>El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Este atributo contiene una lista de opciones para la regla de normalización.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (obsoleto)</p></td>
<td><p>Este atributo de un solo valor contiene un nombre descriptivo para el perfil de ubicación que indica la ubicación que representa este perfil. Dado que puede haber varios perfiles de ubicación, el administrador necesita una forma de distinguir los diferentes perfiles.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsoleto)</p></td>
<td><p>Este atributo de varios valores contiene una lista de nombres distintivos de perfil de ubicación. Este atributo especifica el vínculo hacia atrás a uno o más perfiles de ubicación.</p>
<p>Vínculo hacia atrás: <strong>identificador de vínculo 11035</strong></p>
<p>Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Este atributo contiene las opciones del perfil de ubicación.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Este atributo de varios valores contiene una lista de contactos de aplicación.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Este atributo de varios valores contiene una lista de perfiles de ubicación.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</p></td>
<td><p>Este atributo representa el número máximo de solicitudes de búsqueda pendientes por servidor.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</p></td>
<td><p>El atributo representa el número máximo de suscripciones por usuario.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de suscripción máximo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de registros máximo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de suscripciones de datos móviles máximo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Este atributo es un atributo de punto de control de servicio en la clase de equipo que especifica un vínculo hacia atrás a la fábrica de MCU a la que pertenece. Este punto de control de servicio y el atributo se crean para cada MCU de Microsoft. Cada MCU de Microsoft debe buscar el servidor back-end del grupo de servidores al que pertenece para recuperar la configuración en el nivel de grupo de servidores.</p>
<p>El valor de este atributo es el nombre distintivo (DN) de la fábrica de MCU. Este es un atributo de un solo valor y está marcado para la replicación del catálogo global.</p>
<p>Vínculo hacia delante: <strong>identificador de vínculo 11026</strong></p>
<p>El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Este es un atributo reservado de varias cadenas. La configuración almacenada en este atributo se representa como pares nombre=valor. Los pares nombre=valor actualmente definidos son:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Este es un atributo de un solo valor que contiene el nombre distintivo (DN) de una sola fábrica de MCU asociada a un grupo de servidores.</p>
<p>Vínculo hacia delante: <strong>identificador de vínculo 11024</strong></p>
<p>El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Este atributo es una cadena de un solo valor que especifica el GUID del proveedor de la fábrica de MCU. En función del valor de GUID, el proceso de la fábrica de MCU determina si se presta servicio a este tipo de MCU. Si el valor de GUID es <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, el proceso de factoría de MCU (disponible de forma predeterminada en Lync Server) lo procesará. Para cualquier otro valor de GUID, el proceso de la fábrica de MCU no prestará servicio al tipo de MCU.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Este atributo es una lista de varios valores que contiene nombres distintivos (DN). Este atributo contiene una lista de todos los servidores de MCU del mismo tipo y proveedor asociados a esta fábrica de MCU. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</p>
<p>Vínculo hacia atrás: identificador de vínculo 11027</p>
<p>El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Este atributo es una cadena de un solo valor que especifica el medio que la MCU puede administrar.</p>
<p>Los tipos válidos compatibles son:</p>
<ul>
<li><p>misma</p></li>
<li><p>audio y vídeo</p></li>
<li><p>chat</p></li>
<li><p>conf de teléfono</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Este atributo es una cadena de un solo valor que especifica el nombre de un proveedor de MCU. Todas las MCU de Microsoft especificarán que este atributo sea <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsoleto)</p></td>
<td><p>Este atributo define opciones de reunión diferentes que están habilitadas globalmente para todos los objetos de usuarios o de contacto. Este atributo es un valor de máscara de bits de tipo entero.</p>
<p>Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</p>
<ul>
<li><p>0: el valor de AllowOrganizeMeetingWithAnonymousParticipants es None (no permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (no se establece ningún bit)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants es todos (permitir a todos los usuarios invitar a usuarios anónimos a las reuniones) (posición de bit 2)</p></li>
<li><p>8: el valor de AllowOrganizeMeetingWithAnonymousParticipants es UsePerUserSetting (permitir a los usuarios que inviten a usuarios anónimos a las reuniones según la configuración de cada usuario) (posición de bit 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (la directiva de reunión se define por usuario) (posición de bit 4)</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsoleto)</p></td>
<td><p>Este atributo especifica el nombre distintivo (DN) de la directiva que el administrador ha asignado a este usuario como un atributo de un solo valor.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de suscripción de presencia mínimo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de registro mínimo.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera de la suscripción de datos móviles mínimo.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</p></td>
<td><p>Nuevo en Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Este atributo contiene opciones y marcadores que definen la configuración de movilidad.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Este atributo contiene el DN de un objeto de directiva de movilidad.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsoleto)</p></td>
<td><p>Este atributo representa el número permitido de dispositivos en los que un usuario se puede registrar para las comunicaciones SIP y suscribirse a presencia.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Este atributo especifica las opciones que están habilitadas para el objeto User o Contact. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit. Este atributo se marca para la replicación del catálogo global.</p>
<p>Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</p>
<ul>
<li><p>1: Habilitado para la conectividad de la mensajería instantánea pública (posición de bit 0)</p></li>
<li><p>2: Reservado (posición de bit 1)</p></li>
<li><p>4: Reservado (posición de bit 2)</p></li>
<li><p>8: Reservado (posición de bit 3)</p></li>
<li><p>16: Habilitado para el control remoto de llamadas [Telefonía] (posición de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (posición de bit 6)</p></li>
<li><p>128: UCEnabled (habilitar a los usuarios para las UC) (posición de bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar a los usuarios para la conectividad de mensajería instantánea pública) (posición de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posición de bit 9)</p></li>
</ul></td>
<td><p>Nuevo en Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Este atributo se usa en topologías de bosque de recursos y bosque central para habilitar el inicio de sesión único cuando el objeto ObjectSID de un usuario de la cuenta de entidad de seguridad de Windows NT Server se copia en este atributo del objeto User o Contact correspondiente en el bosque de recursos o bosque central. Communicator Web Access busca un usuario en AD DS con este atributo o con el ObjectSID del usuario. Este atributo se marca para la replicación del catálogo global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Este atributo es el Nombre de recursos uniforme (URN) del propietario para un contacto de la aplicación.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (obsoleto)</p></td>
<td><p>Este atributo de cadena de un solo valor contiene un modelo que se usa para comparar los números marcados con el formato E.164. Si el número marcado coincide con este modelo, se aplica la traducción al número marcado.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsoleto)</p></td>
<td><p>Este atributo de varios valores contiene una lista de nombres distintivos (DN) de ruta de teléfono. Este atributo especifica el vínculo hacia atrás a una o más rutas de teléfono.</p>
<p>Vínculo hacia atrás: <strong>identificador de vínculo 11033</strong></p>
<p>Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (obsoleto)</p></td>
<td><p>Este atributo de cadena UNICODE de un solo valor especifica el nombre descriptivo de la ruta de teléfono, de forma que un administrador pueda hacer fácilmente referencia a ella.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (obsoleto)</p></td>
<td><p>Este atributo es una cadena Unicode de un solo valor. Este atributo de cadena contiene la definición de la directiva en formato XML. La definición del esquema XML es común en todos los diferentes tipos de directiva, solo la configuración es diferente para cada tipo de directiva.</p>
<p>Esta es la definición del esquema XML (XSD):</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (obsoleto)</p></td>
<td><p>Este atributo de cadena Unicode de un solo valor contiene el tipo de directiva. Los tipos de directiva válidos son los siguientes:</p>
<ul>
<li><p>misma</p></li>
<li><p>telefonía</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Este atributo especifica un vínculo hacia atrás al grupo de servidores al que pertenece un equipo. Este atributo se establece independientemente de si el equipo ejecuta la versión Standard Edition o Enterprise Edition de Lync Server. Este atributo se marca para la replicación del catálogo global.</p>
<p>El valor válido es el nombre de dominio del grupo de servidores.</p>
<p>Vínculo hacia delante: <strong>identificador de vínculo 11022</strong></p>
<p>El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Este es un atributo de varios valores que contiene una lista de los nombres distintivos (DN) de los grupos de servidores a los que está asociada la fábrica de MCU.</p>
<p>Vínculo hacia atrás: <strong>identificador de vínculo 11025</strong></p>
<p>El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Este atributo especifica un nombre arbitrario de un grupo de servidores que se muestra en la consola de administración. El administrador puede cambiar este nombre.</p>
<p>El valor válido es una cadena que representa el nombre de un grupo de servidores.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Este atributo es un valor de cadena de un solo valor. El valor de este atributo, cuando está presente, representa el FQDN del dominio del grupo de servidores si el administrador desea crear un grupo de servidores front-end con un FQDN que no sigue la estructura de dominios de Active Directory en la que se crea el grupo de servidores front-end [por ejemplo, un espacio de nombres SIP separado del espacio de nombres del sistema de nombres de dominio (DNS)].</p>
<p>Se recomienda asignar el FQDN del dominio del grupo de servidores front-end a la parte del nombre de dominio como el dominio de Active Directory en el que reside el grupo de servidores. Por consiguiente, cuando no haya ningún valor en este atributo, el FQDN del grupo de servidores front-end se establecerá de forma predeterminada en la estructura de nombres de dominio de Active Directory, tal y como indica el atributo <strong>dnsHostName</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Una lista de varios valores de los nombres de dominio de todos los servidores de Lync Server, Enterprise Edition asociados a un grupo de servidores. Este atributo de tipo entero define si el grupo de servidores puede usar las características de mensajería instantánea, presencia y reuniones.</p>
<p>Los tipos de valores válidos posibles son:</p>
<ul>
<li><p>No definido: mensajería instantánea y presencia (Live Communications Server 2005 y 2003)</p></li>
<li><p>1: mensajería instantánea y servicio de presencia (Lync Server)</p></li>
<li><p>2: mensajería instantánea y presencia y servicio de reuniones (Lync Server)</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Este atributo especifica si un grupo de servidores ejecuta el servidor Standard Edition o Enterprise Edition. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit.</p>
<p>Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</p>
<ul>
<li><p>1: servidor Standard Edition, hospeda usuarios (posición de bit 0)</p></li>
<li><p>2: servidor Enterprise Edition, hospeda usuarios (posición de bit 1)</p></li>
<li><p>4: servidor Standard Edition, hospeda aplicaciones (posición de bit 2)</p></li>
<li><p>8: servidor Enterprise Edition, hospeda aplicaciones (posición de bit 3)</p></li>
</ul>
<p>Dado que Lync Server no admite grupos que hospeden solo aplicaciones, los únicos valores válidos son los siguientes:</p>
<ul>
<li><p>5: servidor Standard Edition, hospeda usuarios y aplicaciones (posiciones de bit 0 y 2)</p></li>
<li><p>10: servidor Enterprise Edition, hospeda usuarios y aplicaciones (posiciones de bit 1 y 3)</p></li>
</ul></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Este atributo define la versión del grupo de servidores. Es un tipo entero que se incrementa con cada versión de producto principal.</p>
<p>Los tipos de valores válidos posibles son:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Este atributo contiene opciones y marcadores que definen la configuración de presencia.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Este atributo contiene el DN de un objeto de directiva de presencia.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Este atributo habilita un usuario o contacto para la mensajería SIP. Se ha agregado a la clase de contacto porque, en la topología de bosque central, los objetos de contacto son los que están habilitados para SIP en lugar de los objetos de usuario.</p>
<p>El valor válido es el DN del servidor Standard Edition o grupo de servidores front-end Enterprise Edition donde se hospeda un usuario.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Este atributo contiene la dirección SIP de un usuario determinado.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Este atributo contiene el identificador de dispositivo del dispositivo de línea privada.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-enrutable</p></td>
<td><p>Este atributo es un atributo booleano que se usa para determinar si Lync Server está autorizado a enrutar a este servicio mediante su dirección GRUU. Si este valor se establece en <strong>true</strong>, Lync Server tiene autorización para enrutar a este servicio. Si este valor se establece en <strong>false</strong>, Lync Server no tiene autorización para enrutar a este servicio.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsoleto)</p></td>
<td><p>Este atributo de cadena UNICODE de un solo valor define un atributo que certifica el uso de una ruta de teléfono. La selección de una ruta de teléfono se determina en función de dos elementos: el atributo de uso asignado a la ruta de teléfono y los atributos de uso de directiva permitidos del autor de la llamada. Se selecciona la primera ruta de teléfono con un atributo de uso que coincide con el uso permitido del autor de la llamada.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsoleto)</p></td>
<td><p>Este atributo de nombre distintivo (DN) de varios valores contiene una lista de nombres distintivos de uso de ruta.</p>
<p>Vínculo hacia delante: <strong>identificador de vínculo 11032</strong></p>
<p>Este atributo es un vínculo hacia delante que se corresponde con el vínculo hacia atrás <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Este atributo contiene el DN que apunta al grupo de servidores por el que debe pasar todo el tráfico SIP enviado a este MCU o servicio de confianza.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsoleto)</p></td>
<td><p>Este atributo de cadena UNICODE de un solo valor especifica el nombre descriptivo de la regla de normalización, de forma que un administrador puede hacer fácilmente referencia a ella.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Este atributo representa la versión de esquema implementada actualmente en la organización.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsoleto)</p></td>
<td><p>Este atributo limita el número de resultados de búsqueda que se devolverán desde una búsqueda de directorio cuando un usuario busca un contacto mediante Communicator. Este atributo invalidará el valor proporcionado por el cliente.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsoleto)</p></td>
<td><p>Este atributo limita el número de solicitudes de búsqueda devueltas.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Este atributo de varios valores es un vínculo hacia atrás que contiene una lista de nombres distintivos (DN). Estos DN apuntan a un grupo de servidores u objeto <strong>TrustedService</strong>.</p>
<p>Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Serverprotección</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsoleto)</p></td>
<td><p>Este atributo de varios valores contiene una lista de nombres distintivos. Estos nombres distintivos son vínculos hacia atrás que hacen referencia a otros objetos de servidor que pueden estar asignados a un perfil de ubicación predeterminado.</p>
<p>Vínculo hacia atrás: <strong>identificador de vínculo 11037</strong></p>
<p>El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Este atributo de vínculo hacia atrás hace únicamente referencia a los grupos de servidores y a los servidores de mediación.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Este atributo define la información de versión del servidor. Este número de versión se aplica a todos los roles del servidor. Es un entero que se incrementa con cada versión del producto oficial.</p>
<p>Los valores válidos posibles son:</p>
<ul>
<li><p>Sin definir: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Este atributo de un solo valor de tipo entero especifica el tipo de objeto al que apunta <strong>msDS-SourceObjectDN</strong>, de la siguiente manera.</p>
<ul>
<li><p>null | 0x00000001: representa un objeto de usuario de entidad de seguridad de Windows NT Server de un bosque diferente.</p></li>
<li><p>Los siguientes atributos representan un tipo de grupo de un bosque diferente para la expansión del grupo de distribución:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: representa un objeto de acceso de suscriptor o de operador automático del mismo bosque o de un bosque diferente.</p></li>
</ul></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2003.</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Este atributo permite mover un usuario o un objeto de contacto de un grupo de servidores de Lync Server a otro. Este atributo se ha agregado a la clase de contacto porque, en la topología de bosque central, los objetos de contacto son los que están habilitados para SIP, y no los objetos de usuario.</p>
<p>El valor válido es el DN del servidor Standard Edition o del grupo de servidores front-end de destino al que se va a mover un usuario.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsoleto)</p></td>
<td><p>Este atributo de cadena de un solo valor contiene un modelo o intervalo de números de teléfono para el enrutamiento a las puertas de enlace especificadas en <strong>msRTCSIP-Gateways</strong>.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Este atributo almacena pares de nombre-valor para directivas de destino para los usuarios de Lync Server.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>Este atributo almacena el identificador único para un arrendatario.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (obsoleto)</p></td>
<td><p>Este atributo se usa en la característica de voz de Lync Server y contiene la cadena de traducción que se va a aplicar en el número marcado si se encuentra una coincidencia.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Este atributo es un valor de cadena que contiene el FQDN de la MCU. Es un atributo de un solo valor. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Este atributo es un valor de cadena que contiene el FQDN del servidor que ejecuta el servidor proxy. Este atributo es de un solo valor. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Este atributo es un atributo de un solo valor que representa el FQDN de un servidor de confianza.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Este atributo especifica el número de versión de un servidor de la lista de servidores de confianza.</p>
<p>Los valores válidos posibles son:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Nuevo en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Este atributo define las opciones que están habilitadas para el servicio de confianza.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Este atributo de varios valores contiene una lista de nombres distintivos (DN) que hacen referencia a un objeto de servicio de confianza, como un servicio de autenticación relé multimedia. Un servicio de autenticación de retransmisión multimedia (que se ubica físicamente en el servidor perimetral que ejecuta el servicio de conferencia A/V) debe asociarse con un grupo para admitir escenarios de audio para usuarios remotos.</p>
<p>El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Este atributo es un entero que define el número de puerto que se usa para conectarse con este servicio GRUU.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Este atributo es un valor de cadena que define el tipo de servicio GRUU que representa.</p>
<p>Los tipos de servicios GRUU válidos son los siguientes:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Puerta de enlace</p></li>
<li><p>Servicio de autenticación relé multimedia (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Este atributo es un valor de cadena que contiene el FQDN del IIS que ejecuta los servicios Web de Lync Server. Es un atributo de un solo valor. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsoleto)</p></td>
<td><p>Este atributo define diferentes opciones de UC que están habilitadas globalmente para todos los objetos de usuario o de contacto. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por la presencia de un bit.</p>
<p>El posible valor válido (y la posición de bit asociada) es el siguiente:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (posición de bit 2)</p></li>
</ul>
<p>Cuando se establece este bit, la directiva de UC se define por usuario.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsoleto)</p></td>
<td><p>Este atributo de un solo valor contiene el nombre distintivo (DN) de la directiva de UC que el administrador ha asignado a este usuario.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (obsoleto)</p></td>
<td><p>Este atributo proporciona una lista de todos los dominios de un bosque que hospedan usuarios habilitados para SIP. De manera predeterminada se ofrece una lista vacía, lo que indica que todos los dominios del bosque están habilitados para SIP.</p>
<p>Como valor válido, se admiten cadenas que representen los nombres de dominio de cada dominio.</p></td>
<td><p>Nuevo en Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Este atributo determina si el usuario está actualmente habilitado para Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Este atributo de varios valores contiene una lista de pares nombre-valor en el formato de &quot;name = value. &quot; Este atributo se marca para la replicación del catálogo global.</p></td>
<td><p>Nuevo en Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Este atributo contiene el nombre distintivo (DN) que apunta a un objeto de perfil de ubicación.</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Este atributo almacena los pares de nombre-valor para directivas de usuario.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Este es un atributo de varios valores que contiene una lista de nombres distintivos (DN) con binario (DN_WITH_BINARY) que apunta a las directivas de usuario global de tipos diferentes. La parte binaria indica el tipo de directiva a la que apunta la parte de DN.</p>
<p>Los tipos de valores binarios válidos son:</p>
<ul>
<li><p>0x00000001: Directiva de reunión</p></li>
<li><p>0x00000002: Directiva de UC</p></li>
<li><p>0x00000005: Directiva de presencia</p></li>
</ul></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Este es el identificador del grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</p></td>
<td><p>Nuevo en Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Este es un atributo de varios valores. Este atributo se reserva para usarlo en el futuro.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Este atributo de un solo valor apunta al grupo de servidores o al servidor Standard Edition al que pertenecen los componentes web.</p>
<p>Vínculo hacia delante: <strong>identificador de vínculo 11028</strong></p>
<p>El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Este atributo es una lista de varios valores que contiene nombres distintivos. Contiene una lista de todos los servidores web asociados a este grupo de servidores.</p>
<p>Vínculo hacia atrás: <strong>identificador de vínculo 11029</strong></p>
<p>El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuevo en Live Communications Server 2003.</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>El atributo existente de Active Directory lo usa la telefonía para especificar la lista de direcciones TCP/IP alternativas para teléfonos.</p></td>
<td><p>Nuevo en el sistema operativo Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Los componentes de voz de Lync Server usan este atributo existente de Active Directory, solo para objetos de contacto, con el fin de enrutar llamadas al operador automático de mensajería unificada y a los números de acceso de suscriptor. La dirección de transferencia de llamadas incondicional se almacena en este atributo de varios valores. Esta cuenta se crea para el propósito concreto de acceso de suscriptor y operador automático. Los administradores no deben modificar los atributos de esta cuenta.</p></td>
<td><p>Nuevo en el sistema operativo Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Este atributo de varios valores existente de Active Directory forma parte del esquema base de Active Directory introducido en Windows 2000. Este atributo contiene las diferentes direcciones X400, X500 y SMTP del correo electrónico del usuario. En Live Communications Server 2003 y versiones posteriores, el URI del SIP del usuario se agrega a esta lista mediante &quot;la etiqueta&quot; SIP:.</p>
<p>Las siguientes aplicaciones buscan el URI del SIP del usuario en este atributo:</p>
<ul>
<li><p>Cliente de mensajería y colaboración de Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Nuevo en el sistema operativo Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Este atributo existente de Active Directory contiene el número de teléfono del usuario.</p></td>
<td><p>Nuevo en el sistema operativo Windows 2000.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

