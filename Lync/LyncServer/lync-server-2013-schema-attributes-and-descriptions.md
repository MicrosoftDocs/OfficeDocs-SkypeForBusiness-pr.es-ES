---
title: 'Lync Server 2013: descripciones y atributos de esquema'
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
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Atributos y descripciones de esquema en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En esta sección se describen todos los atributos de esquema usados por Lync Server 2013. Para las clases asociadas a los atributos, consulte [atributos de esquema por clase en Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Para obtener una lista de las clases y atributos que son nuevos en Lync Server 2013, consulte [cambios en el esquema de Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Los atributos que están vinculados se especifican como vínculos hacia adelante o vínculos hacia atrás. Un atributo que hace referencia a otro objeto es un vínculo hacia adelante; el atributo del otro objeto que hace referencia al primer objeto es un vínculo hacia atrás. Los vínculos de reenvío son actualizables, mientras que los vínculos posteriores son de solo lectura.

Algunos atributos tienen un valor de máscara de bits. Para estos atributos, cada configuración está representada por un bit y el valor decimal que se muestra representa la posición del bit. Las posiciones de bits comienzan con el bit 0. Por ejemplo, 1 (binario) es el bit 0 establecido y 10000 (binario) es el bit 4 establecido. Cada bit representa una propiedad. A continuación se muestran algunos ejemplos:

  - 10000 (binario) tiene un valor decimal de 16 (es decir, el bit 4 está establecido).

  - 100 millones (binario) tiene un valor decimal de 256 (es decir, el bit 8 está establecido).

  - 1100 (binario) tiene un valor decimal de 12 (es decir, los bits 2 y 3 están establecidos; las propiedades representadas por los dos bits están habilitadas).

  - 1111000001 (binario) tiene un valor decimal de 961 (es decir, están establecidos los bits 0, 6, 7, 8 y 9; las propiedades de cada uno de estos bits están habilitadas).

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
<td><p>servicePrincipalName</p></td>
<td><p>Un atributo existente en servicios de dominio de Active Directory que está ahora asociado a las clases <strong>msRTCSIP-Pool</strong> y <strong>msRTCSIP-MonitoringServer</strong> . Este atributo especifica el nombre de dominio completo (FQDN) de un grupo o servidor de supervisión.</p>
<p>Un valor válido para cada segmento es de 63 caracteres; un valor válido para todo el FQDN es 255 caracteres.</p></td>
<td><p>Novedades de Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Este atributo contiene la representación de cadena del nombre distintivo (DN) del objeto de otro bosque que corresponde a este objeto. Este atributo se usa para la expansión del grupo de distribución y la asistencia automática. Este atributo se define en el esquema predeterminado de Active Directory para Windows Server 2003 R2.</p>
<p>Para evitar tener que actualizar AD DS a Windows Server 2003 R2, la preparación del esquema de Active Directory extiende el esquema de Windows Server 2003 con esta definición de atributo.</p></td>
<td><p>Novedades de Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Este atributo de valor múltiple contiene la configuración del correo de voz. Este atributo se comparte con la mensajería unificada de Exchange (UM).</p></td>
<td><p>Novedades de Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Este atributo de valor múltiple contiene los identificadores para las directivas de retención que se aplican al usuario. Las directivas de retención mantienen los elementos del buzón de correo para el usuario durante el período de espera. Este atributo se comparte con Exchange 2013.</p></td>
<td><p>Novedades de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Este atributo almacena información del proveedor de servicios de audioconferencia para un usuario.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Este atributo señala a la entrada de servicio de confianza del contacto de la aplicación.</p></td>
<td><p>Novedades de Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>Este atributo contiene una lista de aplicaciones hospedadas en el servidor de aplicaciones.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Este atributo especifica las opciones para el contacto de la aplicación.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Este atributo contiene el idioma principal del contacto de la aplicación.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Este atributo de valor múltiple contiene los idiomas secundarios para el contacto de la aplicación.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Este atributo contiene una lista de servidores de aplicaciones que pertenecen a este grupo. El vínculo de reenvío correspondiente a este atributo de vínculo de retroceso es <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Este atributo señala al grupo al que pertenece este servidor de aplicaciones. Este es el vínculo hacia adelante. El correspondiente vínculo de retroceso es <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (obsoleto)</p></td>
<td><p>Este atributo especifica el valor predeterminado global dentro del límite del bosque para archivar todas las comunicaciones de los usuarios. Esto lo aplica la capa del agente de archivado. El intervalo de valores para este atributo es el siguiente:</p>
<ul>
<li><p><strong>True</strong>: archivar todos los usuarios</p></li>
<li><p><strong>False</strong>: no archivar todos los usuarios</p></li>
</ul>
<p>Este atributo controla globalmente, dentro del límite del bosque, cómo se archivan las comunicaciones de los usuarios dentro de una red interna.</p>
<p><strong>Comportamiento de Live Communications Server 2005 (ahora retirado)</strong></p>
<p>El intervalo de valores para este atributo es el siguiente:</p>
<ul>
<li><p>0: archivar el cuerpo del mensaje [bit 0]</p></li>
<li><p>1: no archivar el cuerpo del mensaje [bit 0]</p></li>
</ul>
<p><strong>Comportamiento de Office Communications Server 2007</strong></p>
<p>El intervalo de valores para este atributo es el siguiente:</p>
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
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Este atributo es un entero usado como campo de bits para controlar si se van a archivar las comunicaciones de un solo usuario. Este control lo aplica la capa del agente de archivado. Se marca para la replicación del catálogo global.</p>
<p>El ámbito de este atributo es específico de un solo usuario o contacto. Los valores válidos (y las posiciones de bits asociadas) en Lync Server son los siguientes:</p>
<ul>
<li><p>0: no archivar (sin bit establecido)</p></li>
<li><p>1: retirado (posición de bit 0)</p></li>
<li><p>2: retirado (posición de bit 1)</p></li>
<li><p>4: comunicaciones internas de archivo (posición de bit 2)</p></li>
<li><p>8: archivar comunicaciones federadas (posición de bit 3)</p></li>
</ul>
<p>Los valores anteriores válidos en Live Communications Server 2005 son los siguientes:</p>
<ul>
<li><p>0: Use el valor predeterminado definido por <strong>msRTCSIP-ArchiveDefault</strong> y <strong>msRTCSIP-ArchiveFederation</strong> en este orden de prioridad:</p>
<ul>
<li><p>1: archivo</p></li>
<li><p>2: no archivar</p></li>
<li><p>3: archivar sin el cuerpo del mensaje</p></li>
</ul></li>
</ul></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (obsoleto)</p></td>
<td><p>Este atributo define la versión del servicio de archivado. Este atributo es un tipo entero monotonously que se incrementa con cada lanzamiento oficial de producto. Los valores válidos posibles son:</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Este atributo especifica el nombre de dominio completo (FQDN) del servidor back-end de la agrupación. Puesto que solo puede haber un único servidor de servicios de fondo por grupo, se trata de un atributo de valor único.</p>
<p>El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Este atributo contiene el identificador del grupo de servidores que hospeda el directorio de la Conferencia.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Este atributo contiene el identificador de un directorio de conferencia.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Este atributo contiene el identificador de la agrupación a la que se mueve el directorio de la Conferencia.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-default</p></td>
<td><p>Este atributo booleano define si el uso del teléfono es el predeterminado. Si este atributo se establece en <strong>true</strong>, el uso del teléfono es un uso predeterminado y el administrador no puede eliminarlo. Si este atributo se establece en <strong>false</strong>, el uso se puede eliminar.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están fuera de la organización.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Este atributo identifica la dirección URL de Communicator Web Access para los usuarios de la organización.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsoleto)</p></td>
<td><p>Este atributo de valor único contiene el nombre distintivo (DN) de un objeto de clase de Perfil de ubicación asignado a él.</p>
<p>Vínculo hacia adelante: <strong>identificador de vínculo 11036</strong></p>
<p>El correspondiente vínculo de retroceso es <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsoleto)</p></td>
<td><p>Este atributo Boolean especifica si la Directiva es una directiva predeterminada. La Directiva es una directiva predeterminada cuando se establece en <strong>true</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</p></td>
<td><p>Este atributo especifica el FQDN del servidor perimetral que está ejecutando el servicio perimetral de acceso, si se puede obtener acceso a él directamente, o del equilibrador de carga de hardware para un grupo de servidores que ejecutan el servicio perimetral de acceso. Si solo se puede acceder a los servidores que ejecutan Access Edge a través de uno o más directores, este atributo especifica el FQDN y, opcionalmente, el número de puerto del director o del equilibrador de carga de hardware que atiende un grupo de directores.</p>
<p>El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</p></td>
<td><p>Este atributo representa el número de puerto que debe usarse para conectarse al servidor que ejecuta el servicio perimetral de acceso.</p>
<p>El valor válido es un valor entero que especifica el puerto que se va a usar. El valor predeterminado es 5061.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el período de tiempo de espera predeterminado de la suscripción de presencia.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsoleto)</p></td>
<td><p>Este atributo representa la ventana de tiempo de espera de registro predeterminada.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa la ventana de tiempo de espera predeterminada de la suscripción de datos de itinerancia.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Este atributo se usa en una topología de dominio dividida y contiene un nombre de dominio completo (FQDN).</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (obsoleto)</p></td>
<td><p>Este atributo de cadena Unicode de valor único contiene una descripción detallada de esta ruta de teléfono o regla de normalización.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Este atributo representa un dominio configurado para el registrador.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Este atributo especifica el FQDN del servidor que ejecuta el servicio perimetral de acceso.</p>
<p>El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsoleto)</p></td>
<td><p>Este atributo controla si un servidor genera una solicitud de notificación de mejor esfuerzo (BENOTIFY), en lugar de una solicitud NOTIFY, en respuesta a una solicitud SUBSCRIBE de un cliente. BENOTIFY es una extensión que mejora el rendimiento del Protocolo de enlace para notificaciones en el que el servidor genera solicitudes BENOTIFY, en lugar de solicitudes de notificación ordinarias. La ventaja de rendimiento es que una solicitud BENOTIFY no requiere una respuesta 200 del cliente, ya que la solicitud NOTIFY sí.</p>
<p>Los valores válidos son <strong>true</strong> o <strong>false</strong>.</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 no admite solicitudes BENOTIFY. Para interactuar con aplicaciones de servidor escritas con la API de servidor de Live Communications Server 2003 que se ejecuta en Live Communications Server 2005 y en servidores de terceros, las solicitudes BENOTIFY pueden deshabilitarse estableciendo su valor en <STRONG>false</STRONG>. BENOTIFY no forma parte del proceso de estandarización de SIP (el equipo de tareas de ingeniería de Internet) IETF.


</div></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsoleto)</p></td>
<td><p>Este atributo es un modificador global que los administradores de ti usan para configurar si los usuarios pueden comunicarse con usuarios de otras organizaciones. Permite a un administrador sobrescribir el atributo <strong>FederationEnabled</strong> de un usuario individual. Este atributo puede ser útil para ayudar a proteger la red interna de ataques de Internet que pueden estar causados por gusanos, virus o ataques dirigidos a la compañía.</p>
<p>Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</p>
<ul>
<li><p>1: habilitado para conectividad de mensajería instantánea pública (posición de bit 0)</p></li>
<li><p>2: reservado (posición de bit 1)</p></li>
<li><p>4: reservado (posición de bit 2)</p></li>
<li><p>8: reservado (posición de bit 3)</p></li>
<li><p>16: control remoto de llamadas habilitado [telefonía] (posición de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios invitar a usuarios anónimos a reuniones (bit 6)</p></li>
<li><p>128: UCEnabled (habilitar usuarios para comunicaciones unificadas) (posición de bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar usuario para conectividad de mensajería instantánea pública) (posición de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posición de bit 9)</p></li>
</ul></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Este atributo indica si los servicios empresariales se cargan en el servidor dado.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Este atributo contiene el código de marcado para acceso externo.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Este atributo controla si un solo usuario está habilitado para la Federación. La capa de servicios empresariales la aplica. Se marca para la replicación del catálogo global.</p>
<p>Los valores válidos son <strong>true</strong> o <strong>false</strong>.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Este atributo es una lista con varios valores de los nombres de dominio de todos los servidores Enterprise Edition asociados a un grupo.</p>
<p>Vínculo anterior: <strong>identificador de vínculo 11023</strong></p>
<p>El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-gateways (obsoleto)</p></td>
<td><p>Este atributo de cadena de valor múltiple contiene una lista de puertas de enlace y puertos (por puerta de enlace).</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsoleto)</p></td>
<td><p>Este atributo almacena pares de nombre: valor. El par nombre: valor ya definido es para permitir el <strong>sondeo de la configuración de presencia</strong> .</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Este atributo es un identificador único de un grupo que se usa para agrupar las entradas de la libreta de direcciones.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2003 (no usado).</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2003.</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2003 (no usado).</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Este atributo controla si un solo usuario está habilitado para el acceso de usuarios externos. La capa de servicios empresariales la aplica. Se marca para la replicación del catálogo global.</p>
<p>Los valores válidos son <strong>true</strong> o <strong>false</strong>.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2003</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-line</p></td>
<td><p>Este atributo de valor único contiene el identificador de dispositivo (el URI de SIP o el URI de TEL? del teléfono que usa Lync para telefonía). Este atributo está marcado para la replicación del catálogo global y está indizado. Si un usuario está habilitado para Enterprise Voice, este atributo almacena la versión normalizada E. 164 del número de teléfono del usuario.</p></td>
<td><p>Novedades de Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Este atributo de valor único contiene el URI SIP del servidor de puerta de enlace CSTA-SIP. Este atributo está marcado para la replicación del catálogo global, pero no está indizado.</p></td>
<td><p>Novedades de Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (obsoleto)</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de nombres completos de normalización (DN) de normalización asociados con este perfil de ubicación. El tipo de este atributo es un binario DN. Existe una relación de uno a varios entre el perfil de ubicación y las reglas de normalización locales. El orden de la lista de DNs de normalización local debe mantenerse en el orden especificado por el administrador. La conservación del pedido se mantiene mediante la parte binaria del código binario DN, que especifica el índice del pedido.</p>
<p>Vínculo hacia adelante: <strong>identificador de vínculo 11034</strong></p>
<p>El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Este atributo contiene una lista de opciones para la regla de normalización.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (obsoleto)</p></td>
<td><p>Este atributo de valor único contiene un nombre descriptivo para el perfil de ubicación que indica la ubicación que representa este perfil. Dado que puede haber varios perfiles de ubicación, el administrador necesita una forma de distinguir los distintos perfiles.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsoleto)</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de nombres distintivos del perfil de ubicación. Este atributo especifica el vínculo de retroceso a uno o más perfiles de ubicación.</p>
<p>Vínculo anterior: <strong>identificador de vínculo 11035</strong></p>
<p>Este atributo corresponde al vínculo de reenvío <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Este atributo contiene las opciones para el perfil de ubicación.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de contactos de la aplicación.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de perfiles de ubicación.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
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
<td><p>Este atributo representa la ventana máximo de tiempo de espera de suscripción.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsoleto)</p></td>
<td><p>Este atributo representa el límite máximo de registros de la ventana de tiempo de espera.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa la ventana de tiempo de espera máxima de suscripciones de datos de movilidad.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Este atributo es un atributo del punto de control de servicio en la clase de equipo que especifica un vínculo a la fábrica de la unidad de control multipunto (MCU) a la que pertenece. Este punto de control de servicio y atributo se crea para cada MCU de Microsoft. Cada MCU de Microsoft debe encontrar el servidor back-end del grupo al que pertenece, a fin de recuperar la configuración de nivel de grupo.</p>
<p>El valor de este atributo es el nombre distintivo (DN) del generador MCU. Este es un atributo de valor único y está marcado para replicación de catálogo global.</p>
<p>Vínculo hacia adelante: <strong>identificador de vínculo 11026</strong></p>
<p>El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Este es un atributo reservado de cadena múltiple. La configuración almacenada en este atributo se representa como un par nombre = valor. Los pares de nombre definido actualmente = valor son:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Este es un atributo de valor único que contiene el nombre distintivo (DN) de un solo generador MCU asociado con un grupo.</p>
<p>Vínculo hacia adelante: <strong>identificador de vínculo 11024</strong></p>
<p>El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Este atributo es una cadena de valor único que especifica el GUID del proveedor de factoría MCU. Según el valor de GUID, el proceso de fábrica de MCU determina si se debe atender a este tipo de MCU. Si el valor de GUID es <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, el proceso de fábrica de MCU (disponible de forma predeterminada en Lync Server) lo procesará. Para cualquier otro valor de GUID, el proceso de fábrica de MCU no procesará el tipo de MCU.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Este atributo es una lista con varios valores de nombres completos (DN). Este atributo contiene una lista de todos los servidores MCU del mismo tipo y proveedor asociados a este generador MCU. El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</p>
<p>Vínculo anterior: identificador de vínculo 11027</p>
<p>El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Este atributo es una cadena de valor único que especifica el medio que el MCU puede controlar.</p>
<p>Los tipos válidos compatibles son:</p>
<ul>
<li><p>satisfacción</p></li>
<li><p>audio y vídeo</p></li>
<li><p>Chatea</p></li>
<li><p>conf. teléfono</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Este atributo es una cadena de valor único que especifica el nombre de un proveedor de la MCU. Todos los MCU de Microsoft especificarán que este atributo sea <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsoleto)</p></td>
<td><p>Este atributo define diferentes opciones de reunión que se habilitan globalmente para todos los usuarios o los objetos de contacto. Este atributo es un valor de máscara de bits de tipo entero.</p>
<p>Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants es None (no permite que los usuarios inviten a usuarios anónimos a reuniones) (sin ningún bit)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants es todos (permitir que todos los usuarios inviten a usuarios anónimos a reuniones) (posición de bit 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants es UsePerUserSetting (permitir a los usuarios invitar a usuarios anónimos a reuniones según la configuración por usuario) (posición de bit 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (se define la Directiva de reunión por usuario) (posición de bit 4)</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsoleto)</p></td>
<td><p>Este atributo especifica el nombre completo (DN) de la Directiva que el administrador ha asignado a este usuario como un atributo de valor único.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa la ventana de tiempo de espera de suscripción de presencia mínima.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsoleto)</p></td>
<td><p>Este atributo representa la ventana de tiempo de espera de registro mínimo.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa la ventana de tiempo de espera de la suscripción de datos de itinerancia mínima.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</p></td>
<td><p>Novedades de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Este atributo contiene opciones e indicadores que definen la configuración de movilidad.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Este atributo contiene el DN de un objeto de directiva de movilidad.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsoleto)</p></td>
<td><p>Este atributo representa la cantidad permitida de dispositivos en los que un usuario puede registrarse para comunicaciones SIP y suscribirse a la presencia.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Este atributo especifica las opciones que están habilitadas para el objeto de usuario o contacto. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit. Este atributo se marca para la replicación del catálogo global.</p>
<p>Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</p>
<ul>
<li><p>1: habilitado para conectividad de mensajería instantánea (mi) pública (posición de bit 0)</p></li>
<li><p>2: reservado (posición de bit 1)</p></li>
<li><p>4: reservado (posición de bit 2)</p></li>
<li><p>8: reservado (posición de bit 3)</p></li>
<li><p>16: control remoto de llamadas habilitado [telefonía] (posición de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios invitar a usuarios anónimos a reuniones (bit 6)</p></li>
<li><p>128: UCEnabled (habilitar usuarios para UC) (posición de bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar usuario para conectividad de mensajería instantánea pública) (posición de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posición de bit 9)</p></li>
</ul></td>
<td><p>Novedades de Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Este atributo se usa en las topologías de bosque de recursos y central para habilitar el inicio de sesión único cuando el ObjectSID de un usuario de la cuenta principal de Windows NT Server se copia en este atributo del objeto de usuario o contacto correspondiente del recurso o del bosque central. Communicator Web Access busca un usuario en AD DS con este atributo o el ObjectSID del usuario. Este atributo se marca para la replicación del catálogo global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Este atributo es el nombre de recursos uniforme (URN) del propietario de un contacto de la aplicación.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (obsoleto)</p></td>
<td><p>Este atributo de cadena de valor único contiene un patrón usado para hacer coincidir números de marcado con el formato E. 164. Si el número de marcado coincide con este patrón, la traducción se aplica al número marcado.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsoleto)</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de nombres distintivos de rutas de teléfono (DN). Este atributo especifica el vínculo de retroceso a una o más rutas de teléfono.</p>
<p>Vínculo anterior: <strong>identificador de vínculo 11033</strong></p>
<p>Este atributo corresponde al vínculo de reenvío <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (obsoleto)</p></td>
<td><p>Este atributo de cadena Unicode de valor único especifica el nombre descriptivo de la ruta telefónica, de modo que el administrador puede hacer referencia a ella fácilmente.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (obsoleto)</p></td>
<td><p>Este atributo es una cadena Unicode de valor único. Este atributo de cadena contiene la definición de directiva en formato XML. La definición del esquema XML es común en los distintos tipos de Directiva, solo la configuración es distinta para cada tipo de directiva.</p>
<p>La definición de esquema XML (XSD) se define de la siguiente manera:</p>
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
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (obsoleto)</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (obsoleto)</p></td>
<td><p>Este atributo de cadena Unicode de valor único contiene el tipo de directiva. Los tipos de directiva válidos son los siguientes:</p>
<ul>
<li><p>satisfacción</p></li>
<li><p>telefonía</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Este atributo especifica un vínculo al grupo al que pertenece el equipo. Este atributo se establece independientemente de si el equipo está ejecutando la versión Standard Edition o la versión Enterprise de Lync Server. Este atributo se marca para la replicación del catálogo global.</p>
<p>El valor válido es el nombre de dominio del grupo.</p>
<p>Vínculo hacia adelante: <strong>identificador de vínculo 11022</strong></p>
<p>El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Se trata de un atributo de valor múltiple que contiene una lista de los nombres completos (DN) de los grupos a los que está asociada la fábrica del MCU.</p>
<p>Vínculo anterior: <strong>identificador de vínculo 11025</strong></p>
<p>El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Este atributo especifica un nombre arbitrario para un grupo que se muestra en la consola de administración. El administrador puede cambiar este nombre.</p>
<p>El valor válido es una cadena que representa el nombre de un grupo.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Este atributo es un valor de cadena de valor único. El valor de este atributo, cuando está presente, representa el FQDN de dominio del grupo si el administrador desea crear un grupo front-end con un FQDN que no se ajuste a la estructura de dominios de Active Directory en la que se crea el grupo front-end (por ejemplo, un SIP espacio de nombres separado del espacio de nombres del sistema de nombres de dominio (DNS)).</p>
<p>Le recomendamos que asigne el FQDN del dominio del grupo de servidores front-end a la parte de nombre de dominio como el dominio de Active Directory en el que se encuentra el grupo. Por lo tanto, cuando no hay ningún valor en este atributo, el FQDN del grupo de servidores front-end se establece de forma predeterminada en la estructura de nombres de dominio de Active Directory, como indica el atributo <strong>DnsHostName</strong> .</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Lista con varios valores de los nombres de dominio de todos los servidores de Lync Server, Enterprise Edition asociados a un grupo. Este atributo de tipo entero define si el grupo es capaz de la mensajería instantánea (mi), la presencia y las reuniones.</p>
<p>Los posibles tipos de valor válidos son los siguientes:</p>
<ul>
<li><p>Undefined: mensajería instantánea y servicio de presencia (Live Communications Server 2005 y 2003)</p></li>
<li><p>1: mensajería instantánea y servicio de presencia (Lync Server)</p></li>
<li><p>2: mensajería instantánea y presencia y servicio de reuniones (Lync Server)</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Este atributo especifica si un grupo de servidores ejecuta un servidor Standard Edition o Enterprise Edition. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit.</p>
<p>Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</p>
<ul>
<li><p>1: servidor Standard Edition, usuarios de hosts (posición de bit 0)</p></li>
<li><p>2: servidor Enterprise Edition, usuarios de hosts (posición de bit 1)</p></li>
<li><p>4: servidor Standard Edition, aplicaciones de hosts (posición de bit 2)</p></li>
<li><p>8: servidor Enterprise Edition, aplicaciones para hosts (posición de bit 3)</p></li>
</ul>
<p>Puesto que Lync Server no es compatible con los grupos que hospedan solo aplicaciones, los únicos valores válidos son los siguientes:</p>
<ul>
<li><p>5: servidor Standard Edition, hospeda usuarios y aplicaciones (posiciones de bits 0 y 2)</p></li>
<li><p>10: servidor Enterprise Edition, hospeda usuarios y aplicaciones (posiciones de bits 1 y 3)</p></li>
</ul></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Este atributo define la versión del grupo. Es un tipo entero que se incrementa con cada lanzamiento de producto principal.</p>
<p>Los posibles tipos de valor válidos son los siguientes:</p>
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
<td><p>Este atributo contiene opciones e indicadores que definen la configuración de presencia.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Este atributo contiene el DN de un objeto de directiva de presencia.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Este atributo habilita a un usuario o contacto para mensajería SIP. Se agrega a la clase de contacto porque en la topología del bosque central, los objetos de contacto, no los objetos de usuario, están habilitados para SIP.</p>
<p>El valor válido es el nombre completo del servidor Standard Edition o del grupo front-end de Enterprise Edition en el que se aloja un usuario.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Este atributo contiene la dirección SIP de un usuario determinado.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Este atributo contiene el identificador del dispositivo de línea privada.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-enrutable</p></td>
<td><p>Este atributo es un atributo booleano que se usa para determinar si Lync Server está autorizado a enrutar a este servicio mediante su dirección GRUU. Si este valor se establece en <strong>true</strong>, Lync Server está autorizado para enrutar a este servicio. Si este valor se establece en <strong>false</strong>, Lync Server no está autorizado a enrutar a este servicio.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsoleto)</p></td>
<td><p>Este atributo de cadena Unicode de valor único define un atributo que califica el uso de una ruta de teléfono. La selección de una ruta telefónica se determina en función de dos elementos: el atributo de uso asignado a la ruta telefónica y los atributos de uso de directivas permitidos por la persona que llama. Se selecciona la primera ruta del teléfono con un atributo de uso que coincida con el uso permitido de la persona que llama.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsoleto)</p></td>
<td><p>Este atributo de nombre distintivo (DN) multivalor contiene una lista de nombres completos de uso de ruta.</p>
<p>Vínculo hacia adelante: <strong>identificador de vínculo 11032</strong></p>
<p>Este atributo es un vínculo hacia adelante al vínculo atrás correspondiente <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Este atributo contiene el DN que apunta al grupo al que debe pasar todo el tráfico SIP dirigido a este servicio MCU o de confianza.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsoleto)</p></td>
<td><p>Este atributo de cadena Unicode de valor único especifica el nombre descriptivo de la regla de normalización, de modo que un administrador puede hacer referencia a ella fácilmente.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Este atributo representa la versión del esquema implementada actualmente en la organización.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsoleto)</p></td>
<td><p>Este atributo limita el número de resultados de búsqueda que se devolverán desde una búsqueda de directorio cuando un usuario busca un contacto con Communicator. Este atributo invalidará el valor proporcionado por el cliente.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsoleto)</p></td>
<td><p>Este atributo limita el número de solicitudes de búsqueda devuelto.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Este atributo de valor múltiple es un vínculo hacia atrás que contiene una lista de nombres completos (DN). Este DNs apunta a un grupo o a un objeto <strong>TrustedService</strong> .</p>
<p>Este atributo corresponde al vínculo de reenvío <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsoleto)</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de nombres completos. Estos nombres completos devuelven vínculos que hacen referencia a otros objetos de servidor a los que se puede asignar un perfil de ubicación predeterminado.</p>
<p>Vínculo anterior: <strong>identificador de vínculo 11037</strong></p>
<p>El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Este atributo de vínculo de retroceso solo hace referencia a los grupos y servidores de mediación.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Este atributo define la información de versión del servidor. Este número de versión se aplica a todos los roles de servidor. Es un monotonously que aumenta con cada versión oficial del producto.</p>
<p>Los posibles valores válidos son los siguientes:</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Este atributo de valor único de tipo entero especifica el tipo de objeto al que apunta <strong>MSDS-SourceObjectDN</strong> , de la siguiente manera:</p>
<ul>
<li><p>null | 0x00000001: representa un objeto de usuario principal de Windows NT Server de un bosque diferente</p></li>
<li><p>Los siguientes atributos representan un tipo de grupo de un bosque diferente para la expansión de grupos de distribución:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: representa un objeto de acceso de operador automático o de suscriptor del mismo bosque o de un bosque diferente</p></li>
</ul></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2003.</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Este atributo le permite mover un usuario o un objeto de contacto de un grupo de servidores de Lync a otro. Este atributo se agrega a la clase de contacto, porque en la topología del bosque central, los objetos de contacto, no los objetos de usuario, están habilitados para SIP.</p>
<p>El valor válido es el nombre completo del servidor Standard Edition o del grupo de servidores front end al que se va a mover un usuario.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsoleto)</p></td>
<td><p>Este atributo de cadena de valor único contiene un intervalo o un patrón de números de teléfono para enrutar a las puertas de enlace especificadas definidas en <strong>msRTCSIP-gateways</strong>.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Este atributo almacena pares de nombre y valor para las directivas de destino de los usuarios de Lync Server.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>Este atributo almacena el identificador único para un inquilino.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (obsoleto)</p></td>
<td><p>Este atributo es utilizado por la característica de voz de Lync Server y contiene la cadena de traducción para aplicar en el número marcado, si se encuentra una coincidencia.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Este atributo es un valor de cadena que contiene el FQDN del MCU. Este es un atributo de valor único. El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Este atributo es un valor de cadena que contiene el nombre completo del servidor que ejecuta Proxy Server. Este atributo tiene un único valor. El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Este atributo es un atributo de valor único que representa el FQDN de un servidor de confianza.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Este atributo especifica el número de versión de un servidor en la lista de servidores de confianza.</p>
<p>Los posibles valores válidos son los siguientes:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Novedades de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Este atributo define las opciones que están habilitadas para el servicio de confianza.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de nombres completos (DN) que hacen referencia a un objeto de servicio de confianza, como un servicio de autenticación de retransmisión multimedia. Un servicio de autenticación de retransmisión multimedia (que se encuentra físicamente en el servidor perimetral que ejecuta el servicio de conferencia A/V) debe estar asociado a un grupo para admitir escenarios de audio para usuarios remotos.</p>
<p>El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Este atributo es un entero que define el número de puerto que se usa para conectarse a este servicio de GRUU.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Este atributo es un valor de cadena que define el tipo de servicio GRUU que representa.</p>
<p>Los tipos de servicio GRUU válidos son los siguientes:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Puerta</p></li>
<li><p>Servicio de autenticación de retransmisión de multimedia (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Este atributo es un valor de cadena que contiene el FQDN de los servicios Web de Lync Server de IIS. Este es un atributo de valor único. El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsoleto)</p></td>
<td><p>Este atributo define diferentes opciones de UC que se habilitan globalmente para todos los objetos de usuario o contacto. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por la presencia de un bit.</p>
<p>El posible valor válido (y la posición de bits asociada) son los siguientes:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (posición de bit 2)</p></li>
</ul>
<p>Cuando se establece este bit, se define la Directiva de UC por usuario.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsoleto)</p></td>
<td><p>Este atributo de valor único contiene el nombre completo (DN) de la Directiva UC que el administrador ha asignado para este usuario.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (obsoleto)</p></td>
<td><p>Este atributo proporciona una lista de todos los dominios de un bosque que hospedan usuarios habilitados para SIP. El valor predeterminado es una lista vacía, que indica que todos los dominios del bosque están habilitados para SIP.</p>
<p>Los valores válidos son varias cadenas que representan los nombres de dominio de los dominios individuales.</p></td>
<td><p>Novedades de Live Communications Server 2005.</p>
<p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Este atributo determina si el usuario está actualmente habilitado para Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Este atributo de valor múltiple contiene una lista de pares de nombre y valor en el formato &quot;de name = value. &quot; Este atributo se marca para la replicación del catálogo global.</p></td>
<td><p>Novedades de Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Este atributo contiene el nombre distintivo (DN) que apunta a un objeto de Perfil de ubicación.</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Este atributo almacena pares de nombre y valor para directivas de usuario.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Este es un atributo de valor múltiple que contiene una lista de nombres completos con binario (DN_WITH_BINARY) que apunta a directivas de usuario globales de diferentes tipos. El elemento binario indica el tipo de directiva a la que apunta la parte DN.</p>
<p>Los valores binarios válidos son los siguientes:</p>
<ul>
<li><p>0x00000001: política de reuniones</p></li>
<li><p>0x00000002: Directiva UC</p></li>
<li><p>0x00000005: Directiva de presencia</p></li>
</ul></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Este es el identificador de grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</p></td>
<td><p>Novedades de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Este es un atributo de valor múltiple. Este atributo se reserva para usarse en el futuro.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Este atributo de valor único apunta al grupo de servidores o al servidor Standard Edition al que pertenecen los componentes Web.</p>
<p>Vínculo hacia adelante: <strong>identificador de vínculo 11028</strong></p>
<p>El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Este atributo es una lista con varios valores de nombres completos. Este atributo contiene una lista de todos los servidores web asociados con este grupo.</p>
<p>Vínculo anterior: <strong>identificador de vínculo 11029</strong></p>
<p>El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novedades de Live Communications Server 2003.</p>
<p>Obsoleto en Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Este atributo de Active Directory existente es utilizado por telefonía para especificar la lista de direcciones TCP/IP alternativas para un teléfono.</p></td>
<td><p>Nuevo en el sistema operativo Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Los componentes de voz de Lync Server usan este atributo de Active Directory existente, solo para objetos de contacto, con el fin de enrutar llamadas a los números de acceso de los suscriptores y el operador automático de mensajería unificada. La dirección de desvío de llamadas incondicionales se almacena en este atributo de valor múltiple. Esta cuenta se crea para el propósito específico del acceso de operador automático y suscriptor. Los administradores no deben modificar los atributos de esta cuenta.</p></td>
<td><p>Nuevo en el sistema operativo Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Este atributo de valor múltiple de Active Directory existente forma parte del esquema de Active Directory base introducido en Windows 2000. Este atributo contiene las distintas direcciones de X400, X500 y SMTP del correo electrónico del usuario. En Live Communications Server 2003 y versiones posteriores, el URI del SIP del usuario se agrega a la lista con &quot;la etiqueta&quot; SIP:.</p>
<p>Las siguientes aplicaciones buscan el URI SIP del usuario desde este atributo:</p>
<ul>
<li><p>Cliente de mensajería y colaboración 2003 de Microsoft Office Outlook</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Nuevo en el sistema operativo Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>NúmeroDeTeléfono</p></td>
<td><p>Este atributo de Active Directory existente contiene el número de teléfono para el usuario.</p></td>
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

