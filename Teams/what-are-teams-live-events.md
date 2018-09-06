---
title: ¿Cuáles son los equipos de eventos en directo?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviwer: tonysmit
description: Obtenga información sobre cómo Live eventos permiten a los usuarios difundir vídeo y contenido a grandes audiencias en línea en Microsoft Teams, Yammer y Microsoft Stream.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 21f524d6156e13f5c27fe12da97dd287c9f2f3bc
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23846624"
---
# <a name="what-are-teams-live-events"></a>¿Cuáles son los equipos de eventos en directo?
> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview"></a>Información general
Eventos en directo en 365 de Microsoft permiten a los usuarios a difundir vídeo y contenido a grandes audiencias en línea. Eventos en directo Microsoft 365 traer la transmisión por secuencias a un nuevo nivel, fomentar la conexión a lo largo del ciclo de vida de compromiso completo con los asistentes antes, durante y después de eventos en directo de vídeo en directo. Puede crear un evento en directo donde reside la audiencia, equipo o la Comunidad, utilizando Microsoft Stream, Microsoft Teams, o Yammer.  

Microsoft Teams ofrece una colaboración basada en chat, llamada, las reuniones y con eventos en directo, por lo que puede ampliar el público de sus reuniones. Eventos en directo Teams Microsoft es una extensión de las reuniones de los equipos, permitir a los usuarios difundir contenido de reuniones y vídeo a una audiencia en línea de gran tamaño. Estos están diseñados para las comunicaciones de uno a varios donde el host del evento es líder las interacciones y la participación de la audiencia es principalmente ver el contenido compartido por host. Los asistentes pueden verla el evento grabado o en vivo en Yammer, los equipos o Microsoft Stream y pueden interactuar con los moderadores uso moderado Q & o una conversación de Yammer. 

Eventos en directo se consideran la próxima versión de Difundir presentación de reunión de Skype y finalmente a los equipos de reemplazan las funciones proporcionadas en Difundir presentación de reunión de Skype. Durante la versión public preview de eventos en los equipos directo, seguiremos admitir la difusión de reunión de Skype, sin interrupciones en el servicio de eventos nuevo o futuros. Sin embargo, se anima a los usuarios a probar los equipos de eventos en directo para poder aprovechar todas las características nuevas y apasionantes incluida pantalla de uso compartido, el recuento de attendee y compatibilidad con codificadores de hardware y software externos. 

Por lo tanto, vamos a empezar. En primer lugar, eche un vistazo en el siguiente diagrama que muestra los componentes de nivel alto necesarios para Microsoft 365 eventos en directo y cómo se conectan. 

![Eventos de los equipos en directo](media/teams-live-events.png)

## <a name="key-components"></a>Componentes clave
Por lo tanto, se puede ver en la imagen anterior, hay cuatro componentes principales que se usan con eventos en directo en Microsoft Teams.

### <a name="scheduling"></a>Programación
Los equipos proporciona la capacidad para los organizadores crear un evento con el asistente apropiado de permisos, designar los integrantes del grupo de eventos, seleccione el método de producción e invitar a los asistentes. Si se creó el evento en directo desde dentro de un grupo de Yammer, los asistentes de evento live podrán usar Yammer conversación para interactuar con otras personas en el evento. 

### <a name="production"></a>Producción
Los eventos live en Microsoft 365 admite una gran variedad de escenarios de producción, incluir un evento de inicio rápido con cámaras web o un evento de codificador externos mediante equipamiento de calidad studio. La entrada de vídeo es la base de los eventos en directo y puede variar de una cámara Web único a una producción de vídeo profesional de varias cámara. Puede elegir estas opciones según sus requisitos de proyecto y el presupuesto. Hay dos formas para producir eventos:

- **Producción de inicio rápido**: el método de producción de inicio rápido permite a los usuarios producir sus eventos en directo con reuniones de los equipos. Esta opción es mejor y más rápida opción si desea usar los dispositivos de audio y vídeos conectado a su PC o invita a los moderadores remotos por participar en el evento. Esta opción permite a los usuarios usar sus cámaras web fácilmente y compartir su pantalla como entrada en el evento. 


- **Producción de codificador externo**: codificadores externos permiten a los usuarios producir sus eventos en directo directamente desde un codificador basada en software con la [Secuencia de Microsoft](https://stream.microsoft.com)o un hardware externo. Esta opción es mejor si ya dispone de equipamiento de calidad studio (por ejemplo, mezcladores de medios) qué compatibilidad con transmisión por secuencias a un servicio de protocolo de mensajería en tiempo real (RTMP). Este tipo de producción se utiliza normalmente en los eventos de gran escala, como salas de ciudad ejecutivos – donde la difusión de una única secuencia de un mezclador de medios a la audiencia. 

### <a name="streaming-platform"></a>Plataforma de transmisión por secuencias
La plataforma de transmisión por secuencias del evento en directo se compone de los cuatro elementos siguientes:

- **Servicios de medios de Azure** [Servicios de medios de Azure](https://docs.microsoft.com/azure/media-services/previous/) proporciona servicios de transmisión por secuencias vídeo de calidad de difusión para llegar a más grandes audiencias en dispositivos móviles más populares de hoy.   Servicios de medios mejora la accesibilidad, la distribución y la escalabilidad y de manera fácil y rentable para transmitir contenido a su público local o en todo el mundo, al mismo tiempo que protege su contenido.
- **Red de Azure entrega de contenido (CDN)**  Una vez que entre la secuencia, se entrega a través de la [Red de entrega de contenido (CDN) de Azure](https://docs.microsoft.com/azure/cdn/). Servicios de medios Azure proporciona CDN integrada para transmitir los extremos. Esto permite que las secuencias para que se vean en todo el mundo con ningún almacenamiento en búfer.
- **Red de entrega de contenido empresarial (eCDN)**  El objetivo de la red eCDN es tomar el contenido de vídeo de internet y distribuir el contenido en toda la empresa sin afectar el rendimiento de la red. Puede usar uno de estos partners de eCDN para optimizar la red para eventos en directo mantenidos dentro de la organización:
    - Subárbol
    - Kollective
    - Pendiente
- **Experiencia de ATTENDEE**  La experiencia del asistente es el aspecto más importante de eventos en directo y es muy importante que los asistentes pueden participar en el evento en directo sin necesidad de los problemas. La experiencia del asistente usa el Reproductor multimedia de Azure y funciona a través de escritorio, explorador y mobile (iOS, Android). Office 365 proporciona Yammer y los equipos como dos concentradores de colaboración y el Asistente live experiencia se integra en estas herramientas de colaboración. También se pueden tener acceso a los eventos de live codificador externo basado por los asistentes de las [Herramientas administrativas](#administrative-tools).

## <a name="planning-for-live-events"></a>Planeación de eventos en directo
Al planear los equipos eventos en directo para incluir grandes reuniones de su organizaiton, hay varios factores que debe tener en cuenta antes de empezar a establecerla Subir todo. 

### <a name="who-can-create-and-schedule-live-events"></a>¿Quién puede crear y programar eventos en directo? 
Los siguientes requisitos previos son necesarios para el usuario programar un evento en directo los equipos.

Estas son las licencias que se deben asignar:  
- Una licencia de Office 365 Enterprise E3 o E5. 
- Un Microsoft Teams, Skype para la empresa y la licencia de Microsoft Stream.

Es importante saber que se requiere una licencia de Office 365 para participar en un evento en directo como un usuario autenticado, pero esto depende del método de producción usado:

- **Producción de inicio para rápido**  El usuario debe estar asignado a una licencia de Microsoft Teams.
- **Producción de codificador para externo** El usuario debe estar asignado a una licencia de Microsoft Stream.

Para obtener más información acerca de las licencias, vea [Skype para profesionales y los equipos de Microsoft complemento licencias](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).

El usuario debe tener:
- Programación de reunión privada en los equipos habilitados (*AllowPrivateMeetingScheduling - TeamsMeetingPolicy el parámetro = True*).
- Live programación de eventos en los equipos habilitados (*AllowBroadcastScheduling - TeamsMeetingBroadcastPolicy el parámetro = True*).
- Permisos para crear eventos en directo en Microsoft Stream (para [producción codificador externo](#production)).

> [!IMPORTANT]
> Invitados de Office 365, los usuarios federados y anónimos no pueden ser invitados como productores o moderadores en los equipos eventos en directo. No obstante, invitado y los usuarios federados pueden unirse a como asistentes de evento Live anónimo. 
 
### <a name="who-can-watch-live-events"></a>¿Quién puede ver los eventos en directo?

|**Visibilidad de ATTENDEE**           |**Guía de inicio rápido** |**Codificador externo**  |
|------------------------------|-------------|------------------|
|Público (usuarios anónimos)      |  Sí        |  No              |
|Usuarios invitados                   |  No         |  No              |
|Todos los usuarios de empresa federada |  No         |  No              |
|Todos los usuarios de empresa           |  Sí        |  Sí             |
|Específicos de grupos o de personas      |  Sí        |  Sí             |
 
### <a name="teams-live-events-and-skype-meeting-broadcast"></a>Los equipos de live Meeting Difundir presentación de Skype y eventos
En la siguiente tabla resalta las principales características y funciones ofrecidas en eventos en directo y cómo se diferencian de Difundir presentación de reunión de Skype. 

|**Capacidad**   |**Difusión de reunión de Skype** |**Los equipos live eventos (Guía de inicio rápido)** |**Eventos de los equipos en directo (codificador externo)** |
|---------|---------|---------|---------|
|Tamaño máximo de la audiencia |asistentes de 10.000 |10.000 asistentes * |10.000 asistentes * |
|Creación de Live (evento) |   Portal de difusión de la reunión de Skype |Los equipos, Yammer a través de los equipos | Los equipos, Yammer a través de los equipos, secuencia |
|Compromiso de audiencia – Yammer |& #x 2714; |& #x 2714; (experiencia integrada) |& #x 2714; (experiencia integrada) |
|Compromiso de audiencia – moderan preguntas y respuestas |& #x 2714;  |& #x 2714; |& #x 2714; |
|Cliente de productor en Windows |& #x 2714; (Skype para la empresa) |& #x 2714; (Equipos) |& #x 2714; (Secuencia, los equipos a través de secuencia incrustar) |
|Cliente de productor en Mac |X  | & #x 2714; (Equipos) |& #x 2714; (Secuencia, los equipos a través de secuencia incrustar) |
|Recuento de ATTENDEE de la interfaz de usuario de productor |X  |& #x 2714; (Equipos) |& #x 2714; (Secuencia, los equipos a través de secuencia incrustar) |
|Permite que varios moderadores |& #x 2714; (Skype para la empresa) |& #x 2714; (Equipos) |N/D  |
Invitar a un moderador durante la reunión |& #x 2714; (Skype para la empresa) |X |N/D |
|Combinación de moderador en Web y Mobile |& #x 2714; (Skype para la empresa)  |X |N/D |
|Moderador: acceso de RTC |X |& #x 2714; (Equipos) |N/D |
|Presentar una pantalla |X |& #x 2714; (Equipos) |N/D |
|Presentar un archivo de PowerPoint (uso compartido de PPT) |& #x 2714; |X (mitigado mediante el uso compartido de la pantalla) |N/D |
|Grabación de la reunión en función de la nube |& #x 2714; |& #x 2714; |& #x 2714; |
|Publicación automática de grabación en secuencia de Microsoft |X |X |& #x 2714; |
|Traducción y títulos de tiempo Real |& #x 2714; |& #x 2714; (próximamente) |X |
|Títulos en grabaciones de live (evento) |& #x 2714; |& #x 2714; (próximamente) |& #x 2714; |
|Controles DVR ATTENDEE (pausa, retroceso) |& #x 2714; |& #x 2714; |& #x 2714; |
|Socio eCDN soporte técnico |& #x 2714; (Subárbol, Kollective, mejorar) |& #x 2714; (Subárbol, Kollective) |& #x 2714; (Subárbol, Kollective, mejorar) |
|Informe de asistencia posteriores a la difusión de productores |& #x 2714; |& #x 2714; (versión de la característica) |X |
|Análisis de la opinión de los clientes de audiencia – Live de votación & sondeos |& #x 2714; (Impulsos de Microsoft) |X |X |

> [!IMPORTANT]
> Es posible que se puede cambiar los límites que se han establecido.

### <a name="regional-availability"></a>Disponibilidad regional
Puede usar los eventos de los equipos live en varias regiones en todo el mundo. La información siguiente muestra la disponibilidad de los asistentes y los miembros del equipo (evento). 

> [!IMPORTANT]
> La región para el evento se selecciona automáticamente según el organizador y la organización de Office 365.

**Disponible en estas áreas**
- América
- Europa y África
- Asia Pacífico
- Vaya a Canadá Local

**Exclusiones y consideraciones**
- **Vaya variables locales:** Unitied Unido (Reino Unido), India y otras variables locales vaya de los equipos de Microsoft no son compatibles actualmente.
- **China:** Los asistentes y los miembros del equipo de evento no podrá usar los eventos de live de los equipos debido a que no es accesible en China CDN de Azure. Una solución alternativa consiste en usar una conexión VPN, que obtiene el cliente conectado a CDN a través de la red corporativa del cliente de empresa.

## <a name="setting-up-for-live-events"></a>Configuración para eventos en directo
Cuando se configura para eventos en directo, hay varios pasos que debe seguir:

### <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Paso 1: Configurar la red para eventos en directo en Microsoft Teams
Los eventos de live de inicio rápido requieren para [Preparar la red de su organización para que los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

### <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
Asegúrese de que tiene asignaciones de licencia correcta para [quién puede crear y programar eventos en directo?](#who-can-create-and-schedule-live-events) y [quién puede ver los eventos en directo?](#who-can-watch-live-events).

### <a name="step-3-enable-live-event-scheduling-for-users"></a>Paso 3: Habilitar el evento en directo de programación para los usuarios
Programación de evento en directo está habilitada de forma predeterminada para los usuarios de los equipos, pero si desea que los usuarios programar eventos externos codificador existen pasos adicionales que debe realizar.

#### <a name="for-quick-start-events"></a>Para los eventos de inicio rápido
Use la opción *AllowBroadcastScheduling* en **TeamsMeetingBroadcastPolicy** en los equipos de PowerShell para controlar si el usuario puede crear eventos en directo en los equipos o no. Encontrará más información acerca de cómo administrar TeamsMeetingBroadcastPolicy [aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Si no ha asignado una directiva personalizada asignada a los usuarios, los usuarios obtendrá la directiva *Global* , que tiene la grabación habilitado de forma predeterminada.

Compruebe que el parámetro *AllowBroadcastScheduling* se establece en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
A continuación, asigne al usuario a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

##### <a name="user-scenarios"></a>Escenarios de usuario
**Desea que todos los usuarios de su compañía para poder crear eventos en directo.**

Si los usuarios tienen asignados la directiva *global* , ejecute y compruebe que *AllowBroadcastScheduling* * está establecida en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si los usuarios se les asigna una directiva que no sea la directiva *Global* , ejecute lo siguiente y comprobación *- AllowBroadcastScheduling* se establece en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Desea que el evento en directo programación se va a 100% deshabilitado en toda la organización.**

Deshabilitar la programación de difusión, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Asignar a todos los usuarios de la organización a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Desea un gran número de usuarios que puedan crear eventos en directo, pero desea evitar que un conjunto de usuarios desde su creación.**

Asigne la directiva *Global* mediante la **Concesión CsTeamsMeetingBroadcastPolicy** para algunos de los usuarios (que desea que se estén activados) pero primero ejecute lo siguiente y compruebe que *AllowBroadcastScheduling* está establecido en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
A continuación, asignar un usuario o a los usuarios a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crear y asignar una directiva para deshabilitar la programación mediante el cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** a los demás usuarios (que desee deshabilitado). 

Crear la nueva directiva con él deshabilitado, ejecute:
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Deshabilitar la programación, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
A continuación, asignar a usuarios a esta directiva, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Desea eventos en directo que se deshabilite para un gran número de los usuarios, pero desea permitir que un conjunto de usuarios para crearlos.**

Deshabilitar la programación de difusión, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
A continuación, asignar a los usuarios a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crear y asignar una directiva para habilitar la programación, ejecute:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilitar la programación, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
A continuación, asignar a usuarios a esta directiva, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

#### <a name="for-external-encoder-events"></a>Para los eventos de codificador externo
Debe hacer lo siguiente para habilitar la programación de evento en directo para esos usuarios.

##### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Paso 1: Habilitar Microsoft Stream para los usuarios de su organización **
Microsoft Stream está disponible como parte de suscripciones a Office 365 optan o como un servicio independiente. Para obtener más información, vea [información general sobre licencias de secuencia](https://docs.microsoft.com/stream/license-overview) .

> ! [Nota] Microsoft Stream no se incluye en los planes de negocio Essentials o Business Premium.  

Obtenga más información acerca de cómo se pueden [asignar licencias a los usuarios de Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios pueden tener acceso a Microsoft Stream. Asegúrese de que no se bloquea Microsoft Stream para los usuarios tal como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).

##### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Paso 2: Asegúrese de los usuarios tienen permiso de creación de evento en directo en la secuencia de Microsoft **
De forma predeterminada, los administradores pueden crear codificador externo eventos en directo. Administrador de Microsoft Stream puede [Permitir que los usuarios adicionales para la creación de evento en directo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) en secuencia.  

##### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Paso 3: Asegúrese de evento en directo han dado su consentimiento los organizadores de la directiva de empresa establecida por secuencia admin **
Si un administrador de Microsoft Stream tiene que [Configurar una directiva de instrucciones de la compañía](https://docs.microsoft.com/stream/company-policy-and-consent) y requiere que los empleados Aceptar esta directiva antes de guardar el contenido, a continuación, los usuarios deben hacerlo antes de crear un evento en directo (con producción codificador externo) en Microsoft Teams. Antes de la implantación la característica de eventos en directo en la organización, asegúrese de que los usuarios que vayan a crear estos eventos en directo han dado su consentimiento a la directiva. 

### <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Paso 4: Configurar proveedor eCDN para eventos en directo en Microsoft Teams 
Reproducción de vídeos de evento en directo usa adaptable velocidad de bits de transmisión por secuencias (ABR) pero es una secuencia de unidifusión, lo que significa que cada visor obtiene su propia secuencia de vídeo de internet. Para eventos en directo o los vídeos que se envía al gran parte de su organización, podría ser una cantidad considerable de ancho de banda de internet que consume los visores. Para las organizaciones que desean reducir este tráfico de internet para eventos en directo, eventos en directo soluciones se integran con de Microsoft de confianza definen de socios de entrega de vídeo que ofrecen software redes (SDNs) o redes de entrega de contenido empresarial (eCDNs). Estos SDN eCDN plataformas permiten a las organizaciones a optimizar el ancho de banda de red sin sacrificar usuario final experiencias de visualización. Nuestros socios pueden ayudar a permitir una distribución de vídeo más escalable y eficaz a través de la red de la empresa.

**Compra & el programa de instalación la solución fuera de Microsoft Teams** Obtenga ayuda de expertos con ajuste de escala entrega vídeo mediante el aprovechamiento de los socios de entrega de vídeo de confianza de Microsoft. Para poder habilitar un proveedor de entrega de vídeo para su uso con Microsoft Teams debe adquirir y configurar la solución SDN/eCDN externa e independiente de Microsoft Teams.

Las siguientes soluciones SDN/eCDN están integradas en previamente y pueden ser el programa de instalación para usarse con Microsoft Stream.

- **Subárbol de transmisión por secuencias** proporciona una solución sencilla y eficaz para la distribución de vídeo en directo y a petición enterprise. Subárbol es una solución basada en software que no requiere ningún hardware adicional o el ancho de banda y proporciona un modo seguro para habilitar miles de visores de vídeo simultáneos sin afectar a la red. Para clientes que desean para comprender el vídeo de impacto que tiene en su red antes de adquirir una solución de SDN/eCDN, también subárbol de transmisión por secuencias proporciona una solución de análisis basada en explorador para los clientes de Microsoft. [Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective** es una basada en la nube, smart interconexión distribución plataforma que aprovecha la infraestructura de red existente para entregar contenido, en muchas formas, (live transmisiones de vídeo, vídeo y a petición, las actualizaciones de software, las revisiones de seguridad, etc.) con mayor rapidez, confiable y con menos ancho de banda. Nuestra plataforma segura es de confianza por las instituciones financieras más grandes del mundo y sin hardware adicional y, a continuación, el programa de instalación y mantenimiento son fáciles. [Más información](http://www.kollective.com)
 
- **Mejorar OmniCache** proporciona la distribución de red de próxima generación y garantiza la entrega perfecta de contenido de vídeo a través de WAN global, ayudar a los productores de evento optimizar el ancho de banda de red y admitir las difusiones de evento correcta en directo y a petición transmisión por secuencias. La compatibilidad para mejorar OmniCache para eventos en directo inicio rápido estará disponible próximamente.  [Más información](http://www.ramp.com) 
 
> [!NOTE] 
> La solución elegida eCDN está sujeto a la seleccionado **términos 3ª del proveedor de servicio y política de privacidad**, donde se regula el uso de la solución del proveedor eCDN. El uso de la solución del proveedor eCDN no estará sujeto a los términos de licencia por volumen de Microsoft o los términos de servicios en línea. Si no acepta los **términos de 3ª del proveedor**, a continuación, no habilite la solución eCDN en Microsoft Teams. 

**Configurar una red eCDN para "Inicio rápido" eventos en directo** Puede configurar proveedor eCDN para eventos en directo en Teams Microsoft con PowerShell. 

> [!NOTE] 
> Un proveedor único eCDN puede configurarse para su organización. 

***Subárbol*** Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN. En primer lugar, obtener la dirección URL licencia API y el identificador de plantilla desde su contacto subárbol, a continuación, ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN. En primer lugar obtener el token de API y la dirección URL de plantilla de API de su contacto Kollective, a continuación, ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Configurar una red eCDN para eventos en directo "Codificador externo"** 

Si va a crear eventos en directo que usar codificadores externos, necesita [configurar su proveedor eCDN con la secuencia de Microsoft](https://docs.microsoft.com/stream/network-caching) así como. 

## <a name="configure-live-events"></a>Configuración de eventos en directo

### <a name="set-up-event-support-link"></a>Configurar el vínculo de soporte técnico (evento)
Esto es el vínculo que se mostrará a los asistentes de evento en directo. 

En Windows PowerShell, ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>Configurar las opciones de visibilidad de attendee
Esto permite que los organizadores de evento live crear eventos con visibilidad de attendee adecuado.

|**Valores**  |**Comportamiento**  |
|---------|---------|
|Todos     |El usuario tiene una opción para crear eventos en directo con la visibilidad de attendee siguientes: Public, todos los usuarios de la compañía y personas específicas. |
|EveryoneInCompany     |El usuario tiene una opción para crear eventos en directo con la visibilidad de attendee siguientes: todas las personas de la compañía y personas específicas. El usuario no puede crear eventos en directo que pueden ser atendidos por los usuarios anónimos.|
|InvitedUsers |El usuario sólo puede crear eventos en directo que se limitan a personas específicas, tal como se especificó por el organizador del evento. El usuario no puede crear eventos en directo con público y todas las personas de la autenticación de la compañía. |

Use la opción BroadcastAttendeeVisibility en TeamsMeetingBroadcastPolicy en PowerShell para controlar si los usuarios pueden programar la difusión de presentaciones eventos que se pueden ver los asistentes anónimo. 

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene un valor predeterminado establecido en EveryoneInCompany. 
 
En Windows PowerShell, ejecute lo siguiente para permitir a los usuarios crear eventos anónimos en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Configurar las opciones de grabación
> [!NOTE]
> Esta opción es aplicable a los eventos que usan solo el método de producción de inicio rápido.

Esto permite a los administradores para controlar si siempre se registran los eventos en directo, nunca se registró, o si el organizador del evento puede optar por registrar el evento o no.  

|**Valores**  |**Comportamiento**  |
|---------|---------|
|Siempre están habilitadas |Siempre se registran los eventos live organizados por este usuario. El usuario no tiene una opción para invalidar. Si se registra el evento en directo, los miembros del equipo de evento pueden descargar la grabación después del evento, y los asistentes pueden verla el evento después de que el evento es a través de. |
|AlwaysDisabled |Nunca se registran los eventos live organizados por este usuario. El usuario no tiene una opción para invalidar. Si se registra el evento en directo, no se crea ninguna grabación para los miembros del equipo (evento), y los asistentes no pueden inspeccionar el evento después de que se encuentra sobre. |
|UserOverride |Usuario puede decidir si se registra el evento en directo para que se puede crear un archivo de grabación para los miembros del equipo (evento), y los asistentes pueden verla el evento después de que el evento es a través de. |

Use la opción *BroadcastRecordingMode* en **TeamsMeetingBroadcastPolicy** en PowerShell para controlar las opciones de los eventos de live creados por el organizador del evento live de grabación.

En Windows PowerShell, ejecute el siguiente cmdlet para actualizar el modo de grabación en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurar la transcripción en tiempo real y traducción en eventos en los equipos directo (próximamente)
> [!NOTE]
> Esta opción es aplicable a los eventos que usan solo el método de producción de inicio rápido.

Esto permite que los organizadores de evento en directo activar la traducción de los asistentes del evento en directo y títulos en tiempo real. 

Use la opción *AllowBroadcastTranscription* en **TeamsMeetingBroadcastPolicy** en PowerShell para controlar si los asistentes del evento en directo podrá vea transcripción y traducción. Encontrará más información acerca de cómo administrar **TeamsMeetingBroadcastPolicy** con Office 365 PowerShell aquí.  

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene la transcripción y traducción deshabilitado de forma predeterminada.

En Windows PowerShell, ejecute el siguiente cmdlet para activar la transcripción y traducción en para los asistentes de eventos en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="administrative-tools"></a>Herramientas administrativas 
Aunque Microsoft directamente controla todos los centros de datos en línea de Office 365 y es responsable de rendimiento general del sistema, puede controlar sólo una parte de los elementos que se combinan para proporcionar la experiencia de total para los usuarios de Office 365. Las organizaciones a sí mismos son responsables de las conexiones de red en los centros de datos, la red del cliente área extensa (WAN), y redes de área local del cliente (LAN). Además, están a cargo de los dispositivos de usuario y su configuración.También son responsables del mantenimiento de la licencia necesaria por usuario para cualquier característica que desee, incluidos, pero sin limitarse a, la capacidad para administrar estas características, para siempre y cuando el usuario necesita tener acceso a la característica.

Los clientes pueden usar las siguientes herramientas para administrar una variedad de tareas relacionadas de eventos en directo de los equipos.
- [Centro de administración de Microsoft Office 365](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams y Skype para el centro de administración de negocio en línea](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Centro de administración de Microsoft Stream](https://stream.microsoft.com)
- [Windows PowerShell remoto](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?
Cuando se trata de Windows PowerShell, que toda la información sobre administración de usuarios y qué usuarios pueden o no pueden para hacer. Con Windows PowerShell, puede administrar Office 365 y Skype para profesionales Online mediante un único punto de administración que puede simplificar su trabajo diario cuando haya varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:
 - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
 - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>Temas relacionados: 
- [Eventos en directo a través de Microsoft 365 en Yammer, Microsoft Teams y Stream de Microsoft](https://docs.microsoft.com/stream/live-event-m365)
- [Eventos en directo en Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos en directo de Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos en directo en Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)
