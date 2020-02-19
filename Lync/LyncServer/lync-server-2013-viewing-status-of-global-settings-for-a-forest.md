---
title: 'Lync Server 2013: ver el estado de la configuración global de un bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540ce07a106e583f3ea0d4b523e1cf882677c19b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Ver el estado de la configuración global de un bosque en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-20_

Los administradores deben revisar la configuración global de una implementación de Lync Server 2013 mensualmente. El objetivo sería revisar la configuración implementada con un conjunto de configuraciones conocidas, una configuración de línea base para ayudar a garantizar que la configuración sea válida y para determinar si se debe actualizar la documentación de línea base. Los cambios en la configuración global deben implementarse a través de un proceso de control de cambio que debe incluir la documentación de la nueva configuración.

En las siguientes secciones se describen las opciones globales que deben revisarse:

<div>

## <a name="check-general-settings"></a>Comprobar la configuración general

Compruebe la configuración general, incluidos los dominios admitidos del Protocolo de inicio de sesión (SIP) para Lync Server 2013.

La información del dominio SIP se puede devolver mediante Windows PowerShell y el cmdlet **Get-CsSipDomain** . Para devolver esta información, ejecute el `Get-CsSipDomain` comando de Windows PowerShell.

Get-CsSipDomain devolverá información similar a la siguiente para todos los dominios SIP autorizados:

Nombre de identidad IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com true

na.fabrikam.com na.fabrikam.com false

Si la propiedad IsDefault se establece en true, el dominio correspondiente es su dominio SIP predeterminado. Puede usar el cmdlet Set-CsSipDomain para cambiar el dominio SIP predeterminado de su organización. Sin embargo, no se puede eliminar simplemente el dominio SIP predeterminado, ya que esto le dejaría sin un dominio predeterminado. Si deseara eliminar el dominio fabrikam.com (como se muestra en el ejemplo anterior), primero tendría que configurar na.fabrikam.com para que sea su dominio predeterminado.

</div>

<div>

## <a name="check-meeting-settings"></a>Comprobar la configuración de la reunión

La configuración de reunión incluye definiciones de directivas de reuniones y soporte para la participación de usuarios anónimos en reuniones.

Las opciones de configuración de reuniones se pueden recuperar con Windows PowerShell y el cmdlet **Get-CsMeetingConfiguration** . Por ejemplo, este comando devuelve información sobre las opciones de configuración de reunión global:

Get-CsMeetingConfiguration – Identity "global" las opciones de configuración de reuniones también se pueden configurar en el ámbito del sitio. Por ello, es posible que desee usar el siguiente comando, que devuelve información sobre todas las opciones de configuración de reuniones:

`Get-CsMeetingConfiguration`

El cmdlet **Get-CsMeetingConfiguration** devuelve información similar a la siguiente:

Identidad: global

PstnCallersBypassLobby: true

EnableAssignedConferenceType: true

DesignateAsPresenter: compañía

AssignedConferenceTypeByDefault: true

AdmitAnonymousUsersByDefault: true

De nuevo, el último elemento de la lista, **AdmitAnonymousUsersByDefault**, habilita o deshabilita la posibilidad de que los usuarios anónimos participen en las reuniones.

Al comprobar las opciones de configuración de reuniones, es posible que le resulte útil comparar la configuración actual con los equivalentes predeterminados. Para ver las opciones de configuración de reunión predeterminadas, ejecute el siguiente comando:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

El comando anterior crea una instancia de solo memoria de las opciones de configuración de reunión global, una instancia que usa el valor predeterminado para cada propiedad. No se crea ninguna configuración de reunión real al ejecutar el comando. Sin embargo, todos los valores de propiedad predeterminados se mostrarán en pantalla.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Comprobar los servidores perimetrales y su configuración

La información del servidor perimetral se puede recuperar con Windows PowerShell. Este comando devuelve información sobre todos los servidores perimetrales configurados para su uso en la organización:

`Get-CsService -EdgeServer`

La información devuelta incluye todo el FQDN y la configuración de puerto de cada servidor perimetral:

Identidad: EdgeServer: dc.fabrikam.com

Registrar: registrar: LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 50000

MediaComunicationPortCount: 10000

AccessEdgeExternalFqdn: dc.fabrikam.com

DataEdgeExternalFqdn: dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn: dc.fabrikam.com

DependentServiceList: {registrar: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-SE. fabrikam

com, MediationServer: LYNC-SE.

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: sitio:fabrikam. com

PoolFqdn: dc.fabrikam.com

Versión: 5

Rol: EdgeServer

<div>

## <a name="check-federation-settings"></a>Comprobar la configuración de la Federación

Compruebe la configuración de la Federación, por ejemplo si está configurada y, si la respuesta es "sí", el nombre de dominio completo y el puerto. La Federación se habilita y deshabilita mediante el uso de la colección global de opciones de configuración perimetral de acceso. Entre otras cosas, esto significa que la Federación está configurada en todo o nada: la Federación está habilitada para toda la organización o la Federación está deshabilitada para toda la organización.

Las opciones de configuración perimetral de acceso se pueden devolver mediante Windows PowerShell. Para ello, ejecute el siguiente comando de Windows PowerShell:

`Get-CsAccessEdgeConfiguration`

A su vez, ese comando devolverá datos similares a estos:

Identidad: global

AllowAnonymousUsers: false

AllowFederatedUsers: false

AllowOutsideUsers: false

BeClearingHouse: false

EnablePartnerDiscovery: false

EnableArchivingDisclaimer: false

KeepCrlsUpToDateForPeers: true

MarkSourceVerifiableOnOutgoingMessages: true

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

Si la propiedad **AllowFederatedUsers** está establecida en true, significa que la Federación está habilitada para su organización. (Si se establece **AllowFederatedUsers** en true, también significa que, en un escenario de dominio dividido, los usuarios locales podrán comunicarse sin problemas con los usuarios de la nube).

Para recuperar el FQDN y la configuración del puerto para el servidor perimetral, vea la tarea anterior (servidores perimetrales y su configuración).

Habilitar la Federación solo en el ámbito global significa que los usuarios pueden comunicarse potencialmente con usuarios federados. Para determinar si los usuarios individuales pueden comunicarse realmente con los usuarios federados, es necesario que examine la Directiva de acceso de usuarios externos asignada a ese usuario.

La información de acceso de usuarios externos se puede devolver mediante Windows PowerShell. Por ejemplo, este comando devuelve información de la Directiva de acceso de usuario externo global:

`Get-CsExternalAccessPolicy -Identity "Global"`

Y este comando devuelve información de todas las directivas de acceso de usuarios externos:

`Get-CsExternalAccessPolicy`

La información devuelta será similar a esta:

Identidad: falso

Descriptiva

EnableFederationAccess: false

EnablePublicCloudAccess: false

EnablePublicCloudAccessAudioVideoAccess: false

EnableOutsideAccess: false

Si **EnableFederationAccess** se establece en true, los usuarios administrados por la directiva determinada podrán comunicarse con los usuarios federados.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Comprobar la configuración de archivado

Compruebe la configuración de archivado para las comunicaciones internas y federadas. Antes de comprobar la configuración de la archivación interna y externa, debe comprobar que el archivado esté habilitado.

Las opciones de configuración de archivado se pueden comprobar mediante Windows PowerShell y el cmdlet Get-CsArchivingConfiguration:

`Get-CsArchivingConfiguration -Identity "Global"`

Tenga en cuenta que la configuración de archivado también se puede configurar en el ámbito del sitio. Para devolver información acerca de toda la configuración de archivado, use este comando:

`Get-CsArchivingConfiguration`

El cmdlet Get-CsArchivingConfiguration devuelve datos similares a estos:

Identidad: global

EnableArchiving: false

EnablePurging: false

PurgeExportedArchivesOnly: false

BlockOnArchiveFailure: false

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: true

Cachepurgeinterval: 24

Si la propiedad EnableArchiving está establecida en false, significa que no se archivará ninguna sesión de comunicación. Si sólo desea archivar sesiones de mensajería instantánea, use un comando como el siguiente para habilitar el archivado de sesiones de mensajería instantánea:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Para archivar sesiones de conferencia y sesiones de mensajería instantánea, use este comando:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Si quiere comparar la configuración de archivado actual con la configuración predeterminada, ejecute el siguiente comando de Windows PowerShell:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Ese comando crea una instancia de solo memoria de las opciones de configuración de archivado global. No es una colección real de opciones de configuración que usa Lync Server. Sin embargo, muestra los valores predeterminados de todas las propiedades de configuración de archivado.

También puede usar este comando para devolver el FQDN de los servidores de archivado:

`Get-CsService -ArchivingServer`

Una vez que haya comprobado que el archivado está habilitado, puede ver las directivas de archivado para determinar si las sesiones de comunicación internas y externas se archivan.

La información de la Directiva de archivado se puede recuperar con el cmdlet Get-CsArchivingPolicy. Por ejemplo, este comando devuelve información sobre la Directiva de archivado global:

`Get-CsArchivingPolicy -Identity "Global"`

Como las directivas de archivado también se pueden configurar en el sitio y el ámbito por usuario, es posible que también desee usar este comando, que devuelve información sobre todas las directivas de archivado:

`Get-CsArchivingPolicy`

La información que recibe de Get-CsArchivingPolicy será similar a esta:

Identidad: global

Descriptiva

ArchiveInternal: false

ArchiveExternal: false

Tenga en cuenta que, de forma predeterminada, los archivados internos y externos están deshabilitados en una directiva de archivado.

</div>

<div>

## <a name="check-cdr-settings"></a>Comprobar la configuración de CDR

Compruebe la configuración de registro de detalles de llamadas (CDR) para el registro detallado de llamadas de voz, de conferencia y de punto a punto. Se puede devolver información detallada sobre la configuración de CDR mediante el cmdlet **Get-CsCdrConfiguration** . Por ejemplo, este comando devuelve información sobre la colección global de opciones de configuración de CDR:

`Get-CsCdrConfiguration -Identity "Global"`

Como CDR también se puede configurar en el ámbito de sitio, es posible que también desee ejecutar este comando, que devuelve información sobre todas las opciones de configuración de CDR:

`Get-CsCdrConfiguration`

El cmdlet Get-CsCdrConfiguration devuelve información similar a la siguiente para cada colección de opciones de configuración de CDR:

Identidad: global

EnableCDR: true

EnablePurging: true

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

Se puede devolver información similar para la supervisión de QoE mediante el cmdlet Get-CsQoEConfiguration. Por ejemplo, este comando devuelve información sobre la colección global de opciones de configuración de QoE:

`Get-QoEConfiguration -Identity "Global"`

Esta información será similar a la siguiente:

Identidad: global

ExternalConsumerIssuedCertId :

EnablePurging: true

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: false

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: true

Si desea comparar la configuración actual de CDR con la configuración predeterminada de CDR, puede revisar los valores predeterminados mediante la ejecución de este comando:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

Del mismo modo, los valores predeterminados para la supervisión de QoE se pueden recuperar con este comando:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

También puede devolver el FQDN de los servidores de supervisión mediante la ejecución de este comando:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Comprobar la configuración de voz

La configuración de voz suele ser importante para los administradores en las directivas de voz y rutas de voz: las directivas de voz contienen la configuración que determina las capacidades que se exponen a los usuarios individuales (como la capacidad de desviar o transferir las llamadas), mientras que las rutas de voz determinan cómo se enrutan las llamadas (y si) a través de la RTC.

La información de la Directiva de voz se puede recuperar con Windows PowerShell. Por ejemplo, este comando devuelve información sobre la Directiva de voz global:

`Get-CsVoicePolicy -Identity "Global"`

Y este comando devuelve información sobre todas las directivas de voz configuradas para su uso en la organización:

`Get-CsVoicePolicy`

La información devuelta por el cmdlet Get-CsVoicePolicy es similar a la siguiente:

Identidad: global

PstnUsages{}

Descriptiva

AllowSimulRing: true

AllowCallForwarding: true

AllowPSTNReRouting: true

Nombre: DefaultPolicy

EnableDelegation: true

EnableTeamCall: true

EnableCallTransfer: true

EnableCallPark: false

EnableMaliciousCallTracing: false

EnableBWPolicyOverride: false

PreventPSTNTollBypass: false

También puede crear consultas que devuelvan un subconjunto de las directivas de voz. Por ejemplo, este comando devuelve todas las directivas de voz que permiten el desvío de llamadas:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

Y este comando devuelve todas las directivas de voz que no permiten el desvío de llamadas:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

En Windows PowerShell, use el cmdlet Get-CsVoiceRouting para devolver información sobre las rutas de voz:

`Get-CsVoiceRoute`

Este comando devuelve información como esta para todas las rutas de voz:

Identidad: LocalRoute

Prioridad: 0

Descriptiva

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages{}

PstnGatewayList :{}

Nombre: LocalRoute

SuppressCallerId

AlternateCallerId

Lync Server le permite crear rutas de voz que no tienen un uso de RTC y no especifican una puerta de enlace RTC. Sin embargo, en realidad no puede enrutar las llamadas a través de una ruta de voz que no tenga estos dos valores de propiedad configurados. Por ello, es posible que le resulte útil ejecutar periódicamente este comando, que devuelve la identidad de cualquier ruta de voz que no tenga uso de RTC:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

De forma similar, este comando devuelve la identidad de cualquier ruta de voz que no se haya configurado para tener una puerta de enlace RTC:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Comprobar la configuración del operador de conferencia

Compruebe la configuración del operador de conferencia para las conferencias de acceso telefónico local RTC. La configuración del operador de conferencia solo puede recuperarse con el cmdlet **Get-CsDialInConferencingConfiguration** . Esta configuración no está disponible en el panel de control de Lync Server. Para ver la configuración del operador de conferencia, use un comando de Windows PowerShell similar al siguiente, que devuelve la colección global de opciones de configuración del operador de Conferencia:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Tenga en cuenta que la configuración del operador de conferencia también se puede configurar en el ámbito del sitio. Para obtener información acerca de todas las opciones de configuración del operador de conferencia, use este comando en su lugar:

`Get-CsDialInConferencingConfiguration`

El cmdlet Get-CsDialInConferencingConfiguration devuelve datos similares a estos:

Identidad: global

EntryExitAnnouncementsType: UseNames

EnableNameRecording: true

EntryExitAnnouncementsEnabledByDefault: false

Si EntryExitAnnouncementsEnabledByDefault se establece en false, significa que los anuncios de conferencia están deshabilitados. Para habilitar los anuncios de entrada y salida, ejecute un comando de Windows PowerShell similar al siguiente:

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

