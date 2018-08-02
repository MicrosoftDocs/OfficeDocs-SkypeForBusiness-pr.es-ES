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
ms.openlocfilehash: 4017e059f202a89451b9aad419fd007bb4758765
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2018
ms.locfileid: "21711073"
---
# <a name="what-are-teams-live-events"></a>¿Cuáles son los equipos de eventos en directo?
> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Obtenga información sobre cómo live eventos permiten a los usuarios difundir vídeo y contenido a grandes audiencias en línea en Microsoft Teams, Yammer y Microsoft Stream.  

## <a name="overview"></a>Información general
Eventos en directo en 365 de Microsoft permiten a los usuarios a difundir vídeo y contenido a grandes audiencias en línea.  Eventos en directo Microsoft 365 traer la transmisión por secuencias a un nuevo nivel, fomentar la conexión a lo largo del ciclo de vida de compromiso completo con los asistentes antes, durante y después de eventos en directo de vídeo en directo. Puede crear un evento en directo donde reside la audiencia, equipo o la Comunidad, mediante Microsoft Stream, Microsoft Teams o Yammer.  

Microsoft Teams ofrece colaboración basada en chat, al llamar a las reuniones y con eventos en directo, puede ampliar el público de las reuniones. Eventos en directo Teams Microsoft es una extensión de las reuniones de los equipos, permitir a los usuarios difundir contenido de reuniones y vídeo a una audiencia en línea de gran tamaño. Estos están diseñados para las comunicaciones de uno a varios donde el host del evento es líder las interacciones y la participación de la audiencia es principalmente ver el contenido compartido por host. Los asistentes pueden verla el evento grabado o en vivo en Yammer, los equipos o Microsoft Stream y puede interactuar con los moderadores a través de moderado preguntas y respuestas o conversación de Yammer. 

Eventos en directo se considera la próxima versión de Difundir presentación de reunión de Skype y finalmente a los equipos de reemplazan las funciones proporcionadas en Difundir presentación de reunión de Skype. Para la versión preliminar pública de eventos en directo, Microsoft seguirá admitir la difusión de reunión de Skype, sin interrupciones en el servicio de eventos nuevo o futuros. Le recomendamos que pruebe la eventos en directo en los equipos a aprovechar las nuevas características incluidas en pantalla de uso compartido, el recuento de attendee y compatibilidad con codificadores de hardware y software externos. 

## <a name="key-components"></a>Componentes clave
En el siguiente diagrama muestra los componentes de nivel alto necesarios para Microsoft 365 eventos en directo. 

![Eventos de los equipos en directo](media/teams-live-events.png)

### <a name="scheduling"></a>Programación
Los equipos proporciona la capacidad para los organizadores crear un evento con el asistente apropiado permisos, designar los integrantes del grupo de eventos, seleccione producción método invitar a los asistentes. Si se creó el evento en directo desde dentro de un grupo de Yammer, los asistentes de evento live podrán usar Yammer conversación para interactuar con el equipo del evento. 

### <a name="production"></a>Producción
Los eventos live en Microsoft 365 admite una gran variedad de escenarios de producción, incluir un evento de inicio rápido con cámaras web o un evento de codificador externos mediante equipamiento de calidad studio. La entrada de vídeo es la base de los eventos en directo y puede variar de una cámara Web único a una producción de vídeo profesional de varias cámara. Los clientes pueden elegir estas opciones según sus requisitos de proyecto y el presupuesto. 
- **Guía de inicio rápido**: el método de inicio rápido permite a los usuarios producir sus eventos en directo con reuniones de los equipos. Esta opción es mejor si desea usar el audio y los dispositivos de vídeo conectada a su PC o invita a los moderadores remotos / panelistas por participar en el evento. Esta opción permite a los usuarios usar sus cámaras web fácilmente y compartir su pantalla como entrada en la difusión. 
- **Codificador externo**: codificadores externos permiten a los usuarios producir sus eventos en directo directamente desde un hardware externo o codificador basada en software con Microsoft Stream. Esta opción es mejor si ya dispone de equipamiento de calidad studio (por ejemplo, mezcladores de medios) qué compatibilidad con transmisión por secuencias a un servicio RTMP. Esta opción normalmente se usa en los eventos de gran escala, como salas de ciudad ejecutivos – donde una única secuencia de un mezclador de medios se difunde a la audiencia. 

### <a name="streaming-platform"></a>Plataforma de transmisión por secuencias
Se compone de las siguientes partes:

#### <a name="azure-media-services"></a>Servicios de multimedia de Azure
[Servicios de medios de Azure](https://docs.microsoft.com/en-us/azure/media-services/previous/) proporciona servicios de transmisión por secuencias vídeo de calidad de difusión para llegar a más grandes audiencias en dispositivos móviles más populares de hoy. Servicios de medios mejora la accesibilidad, la distribución y la escalabilidad y de manera fácil y rentable para transmitir contenido a sus locales y en todo el mundo de las audiencias, al mismo tiempo que protege su contenido.

#### <a name="azure-content-delivery-network-cdn"></a>Red de Azure entrega de contenido (CDN)
Una vez que entre la secuencia, se entrega a través de la [Red de entrega de contenido (CDN) de Azure](https://docs.microsoft.com/en-us/azure/cdn/). Servicios de medios Azure proporciona CDN integrada para extremos de transmisión por secuencias. Esto permite sus secuencias puedan verse en todo el mundo con ningún almacenamiento en búfer. 

### <a name="enterprise-content-delivery-network-ecdn"></a>Red de entrega de contenido empresarial (eCDN) 
El objetivo de la red eCDN es tomar el contenido de vídeo de internet y distribuir el contenido en toda la empresa sin afectar el rendimiento de la red. Puede usar los siguientes asociados de negocios certificados para optimizar la red para eventos en directo: 
- Subárbol
- Kollective
- Pendiente (próximamente a Inicio rápido)

### <a name="attendee-experience"></a>Experiencia del Asistente
La experiencia del asistente es el aspecto más importante de eventos en directo y es muy importante que los asistentes pueden participar en el evento live sin problemas. La experiencia del asistente usa el Reproductor multimedia de Azure y funciona a través de escritorio, explorador y mobile (iOS, Android). Office 365 proporciona Yammer y los equipos como dos concentradores de colaboración y el Asistente live experiencia se integra en estas herramientas de colaboración. También se pueden tener acceso a los eventos de live codificador externo basado por los asistentes en el portal de Microsoft Stream.

## <a name="prerequisites"></a>Requisitos previos

### <a name="who-can-create-live-events"></a>Quién puede crear eventos en directo
Los siguientes requisitos previos son necesarios para el usuario programar un evento en directo en el período de tiempo de vista previa:  
- El usuario tiene una licencia de Office 365 Enterprise E3 o E5. 
- Usuario está habilitado para Microsoft Teams, Skype para profesionales en línea y Microsoft Stream.
- Usuario está habilitado para programar una reunión privada en los equipos (TeamsMeetingPolicy AllowPrivateMeetingScheduling está establecido en True).
- Usuario está habilitado para la programación de evento en directo en los equipos (TeamsMeetingBroadcastPolicy AllowBroadcastScheduling está establecido en True).
- El usuario tiene permisos para crear eventos en directo en Microsoft Stream (para producción de codificador externo).

> [!NOTE]
> Invitados de Office 365, los usuarios federados y anónimos no pueden ser invitados como productores o moderadores en los equipos eventos en directo. 
 
### <a name="who-can-watch-live-event"></a>Quién puede ver live (evento)
Revise la tabla siguiente para ver quién puede participar en un evento en directo. 

|**Visibilidad de ATTENDEE**           |**Guía de inicio rápido** |**Codificador externo**  |
|------------------------------|-------------|------------------|
|Público (usuarios anónimos)      |  Sí        |  No              |
|Los usuarios de invitado *                   |  No         |  No              |
|Todos los usuarios de empresa federada * |  No         |  No              |
|Todos los usuarios de empresa           |  Sí        |  Sí             |
|Específicos de grupos o de personas      |  Sí        |  Sí             |
* Pueden unirse los usuarios federados e invitados como asistentes de evento live anónimo.

Para participar en un evento en directo como un usuario autenticado, según el método de producción, se necesita una licencia de Office 365.

- **Producción de inicio para rápido**: el usuario debe ser un usuario de los equipos.
- **Producción de codificador para externo**: el usuario debe ser un usuario de la secuencia.
 
## <a name="capabilities"></a>Capacidades
En la siguiente tabla resalta las funcionalidades principales que ofrece en eventos en directo y cómo se diferencian de Difundir presentación de reunión de Skype. 

|Capacidad   |Difusión de reunión de Skype |Los equipos live eventos (Guía de inicio rápido) |Eventos de los equipos en directo (codificador externo) |
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
|Socio eCDN soporte técnico |& #x 2714; (Subárbol, Kollective, mejorar) |& #x 2714; (próximamente) |& #x 2714; (Subárbol, Kollective, mejorar) |
|Informe de asistencia posteriores a la difusión de productores |& #x 2714; |& #x 2714; (próximamente) |X |
|Análisis de la opinión de los clientes de audiencia – Live de votación & sondeos |& #x 2714; (Impulsos de Microsoft) |X |X |

* Los límites son durante la vista preliminar y está sujeta a cambios 

## <a name="planning--setup"></a>Guía de planeación & del programa de instalación
En este artículo se explica cómo puede configurar los usuarios con equipos eventos en directo en su organización.

1. Comprobar la [disponibilidad regional para los equipos de eventos en directo](#configure-live-events) para comprender las regiones que están actualmente disponibles en eventos en directo.
2. Si aún no lo ha hecho, configure [Skype para empresarial en línea](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e) para su organización.
3. Si dispone de los asistentes que se unen a desde dentro de la red corporativa, considere la posibilidad de incorporación y [configurar un proveedor de red eCDN Microsoft recomendadas](#set-up-ecdn-provider-for-teams-live-events) para optimizar el ancho de banda de red. 
4. Asegúrese de que tiene asignaciones de licencia correcta para [quién puede crear eventos en directo](#who-can-create-live-events) y [quién puede ver los eventos en directo](#who-can-watch-live-event). 
5. [Habilitar la programación de evento en directo](#enable-live-event-scheduling-for-the-user) para los usuarios que debe ser capaz de crear eventos en directo en su compañía. Esto es necesario para el inicio rápido & eventos externos codificador. 
6. Para los eventos externos codificador, [permiten a los usuarios para la creación de eventos en directo en el Portal de administración de secuencia de Microsoft](#enable-microsoft-stream-for-users-in-the-organization).  

### <a name="regional-availability-for-teams-live-events"></a>Disponibilidad regional para eventos de los equipos en directo
Puede usar los eventos de los equipos live en varias regiones. La información siguiente muestra la disponibilidad de los asistentes y los miembros del equipo (evento). La región para el evento se selecciona automáticamente según el organizador y el inquilino de Office 365.

#### <a name="regions-available"></a>Regiones disponibles
- América
- Europa y África
- Asia Pacífico

#### <a name="exclusions"></a>Exclusiones de
- Vaya a variables locales
  - Reino Unido, India y otras variables locales vaya de los equipos de Microsoft no son compatibles actualmente.
- Vaya a Local - Canadá 
  - En la vista previa, los clientes pueden crear eventos pero sus datos se ubicarán en la región de América del Norte.
- China
  - Los asistentes y los miembros del equipo de evento no podrá usar los eventos de live de los equipos debido a que no es accesible en China CDN de Azure. Una solución alternativa consiste en usar una conexión VPN, que obtiene el cliente conectado a CDN a través de la red corporativa del cliente de empresa.

### <a name="set-up-your-network-for-live-events-in-microsoft-teams"></a>Configurar la red para eventos en directo en Microsoft Teams
Los eventos de live de inicio rápido requieren para [Preparar la red de su organización para que los equipos de Microsoft](https://docs.microsoft.com/en-us/microsoftteams/prepare-network).  

Eventos en directo para la Guía de inicio rápido y codificador externo, vaya a [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) para obtener una lista detallada y actualizada de la direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para los equipos y la secuencia. Microsoft está mejorando continuamente el servicio Office 365 y agregar la nueva funcionalidad, lo que significa que los puertos requeridos, las direcciones URL, y pueden cambiar las direcciones IP a través del tiempo. Se recomienda que se suscriba a través de RSS para recibir notificaciones cuando esta información se actualiza o se ha cambiado.

### <a name="set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Configurar el proveedor eCDN para eventos en directo en Microsoft Teams 
Reproducción de vídeos de evento en directo usa adaptable velocidad de bits de transmisión por secuencias (ABR) pero es una secuencia de unidifusión, lo que significa que cada visor obtiene su propia secuencia de vídeo de internet. Para eventos en directo o los vídeos que se envía al gran parte de su organización, podría ser una cantidad considerable de ancho de banda de internet que consume los visores.  Para las organizaciones que desean reducir este tráfico de internet para eventos en directo, eventos en directo soluciones se integran con de Microsoft de confianza definen de socios de entrega de vídeo que ofrecen software redes (SDNs) o redes de entrega de contenido empresarial (eCDNs). Estos SDN eCDN plataformas permiten a las organizaciones a optimizar el ancho de banda de red sin sacrificar usuario final experiencias de visualización. Nuestros socios pueden ayudar a permitir una distribución de vídeo más escalable y eficaz a través de la red de la empresa.

#### <a name="purchase--setup-your-solution-outside-of-microsoft-teams"></a>Compra & del programa de instalación la solución fuera de Microsoft Teams
Obtenga ayuda de expertos con ajuste de escala entrega vídeo mediante el aprovechamiento de los socios de entrega de vídeo de confianza de Microsoft.  Para poder habilitar un proveedor de entrega de vídeo para su uso con Microsoft Teams debe adquirir y configurar la solución SDN/eCDN externa e independiente de Microsoft Teams.

Las siguientes soluciones SDN/eCDN están integradas en previamente y pueden ser el programa de instalación para usarse con Microsoft Stream. Ver información de los proveedores que aparece a continuación:

Transmisión por secuencias del subárbol proporciona una solución simple y eficaz para distribución de vídeo en directo y a petición enterprise. Subárbol es una solución basada en software que no requiere ningún hardware adicional o el ancho de banda y proporciona un modo seguro para habilitar miles de visores de vídeo simultáneos sin afectar a la red. Para clientes que desean para comprender el vídeo de impacto que tiene en su red antes de adquirir una solución de SDN/eCDN, también subárbol de transmisión por secuencias proporciona una solución de análisis basada en explorador para los clientes de Microsoft. [Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
Basados en la nube, smart interconexión distribución plataforma del Kollective aprovecha la infraestructura de red existente para entregar contenido, en muchas formas, (live transmisiones de vídeo, vídeo y a petición, las actualizaciones de software, las revisiones de seguridad, etc.) con mayor rapidez, más confiable y menos ancho de banda. Nuestra plataforma segura es de confianza por las instituciones financieras más grandes del mundo y sin hardware adicional y, a continuación, el programa de instalación y mantenimiento son fáciles. [Más información](http://www.kollective.com)
 
Mejorar OmniCache proporciona la distribución de red de próxima generación y garantiza la entrega perfecta de contenido de vídeo a través de WAN global, ayudar a los productores de evento optimizar el ancho de banda de red y admitir las difusiones de eventos live correcta y transmisión por secuencias a petición. La compatibilidad para mejorar OmniCache para eventos en directo inicio rápido estará disponible próximamente.  [Más información](http://www.ramp.com) 
 
[!NOTE] La solución elegida eCDN está sujeto a la seleccionado [términos 3ª del proveedor de servicio y política de privacidad](), que se regirá el uso de la solución del proveedor eCDN. El uso de la solución del proveedor eCDN no estará sujeto a los términos de licencia por volumen de Microsoft o los términos de servicios en línea. Si no acepta los [términos de 3ª del proveedor](), a continuación, no habilite la solución eCDN en Microsoft Teams. 

#### <a name="configure-ecdn-for-quick-start-live-events"></a>Configurar eCDN para eventos en directo "Inicio rápido" 
Puede configurar proveedor eCDN para eventos en directo en Teams Microsoft a través de PowerShell. Nota: sólo un proveedor único eCDN puede configurarse para el inquilino en cualquier momento dado. 

**Configurar el proveedor de red eCDN subárbol** 

Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN. 
1. Obtener licencia API y el identificador de plantilla dirección URL de su contacto de subárbol. 
2. Ejecute el siguiente cmdlet de PowerShell
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```

**Configurar el proveedor de red eCDN Kollective** 

Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN. 
1. Obtener el token de API y la dirección URL de la plantilla de API de su contacto Kollective. 
2. Ejecute el siguiente cmdlet de PowerShell
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```

**Configurar el proveedor de red eCDN pendiente**

#### <a name="configure-ecdn-for-external-encoder-live-events"></a>Configurar eCDN para eventos en directo "Codificador externo" 
Si va a crear eventos en directo que usar codificadores externos, necesita [configurar su proveedor eCDN con la secuencia de Microsoft](https://docs.microsoft.com/stream/network-caching) así como. Si va a crear "Inicio rápido" eventos en directo a través de Microsoft Teams o Yammer necesita configurar su proveedor SDN/eCDN que se integra con Microsoft Teams así como.

### <a name="enable-live-event-scheduling-for-the-user"></a>Habilitar la programación de evento en directo para el usuario
La programación de evento en directo está habilitada de forma predeterminada para un usuario de los equipos.  

Use la opción AllowBroadcastScheduling en TeamsMeetingBroadcastPolicy en los equipos de PowerShell para controlar si el usuario puede crear eventos en directo en los equipos o no. Encontrará más información acerca de cómo administrar TeamsMeetingBroadcastPolicy con Office 365 PowerShell [aquí](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene la grabación habilitado de forma predeterminada. 

 Para que un usuario reserva para la directiva Global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Para cambiar el valor de AllowBroadcastScheduling en la directiva Global, use el siguiente cmdlet:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="scenarios"></a>Scenarios
**Deseo que todos los usuarios de mi compañía para poder crear eventos en directo.**
1. Confirmar CsTeamsMeetingBroadcastPolicy Global tiene AllowBroadcastScheduling = True.
2. Confirme que todos los usuarios tengan el Global OR CsTeamsMeetingBroadcastPolicy una de las directivas de CsTeamsMeetingBroadcastPolicy con AllowBroadcastScheduling = True.

**Deseo que la mayoría de Mis usuarios puedan crear eventos en directo, pero deseo deshabilitar a usuarios específicos que no se les permite selectivamente.**
1. Confirmar CsTeamsMeetingBroadcastPolicy Global tiene AllowBroadcastScheduling = True.
2. Confirmar la mayoría de los usuarios tienen la Global OR CsTeamsMeetingBroadcastPolicy una de las directivas de CsTeamsMeetingBroadcastPolicy con AllowBroadcastScheduling = True.
3. Confirme que se han concedido todos los demás usuarios una de las directivas de CsTeamsMeetingBroadcastPolicy con AllowBroadcastScheduling = False.

**Deseo evento live programación se va a 100% deshabilitado.**
1. Confirmar CsTeamsMeetingBroadcastPolicy Global tiene AllowBroadcastScheduling = False.
2. Confirme que todos los usuarios se han concedido OR CsTeamsMeetingBroadcastPolicy Global una de las directivas de CsTeamsMeetingBroadcastPolicy con AllowBroadcastScheduling = False.

**La opción I want eventos en directo a deshabilitarse para la mayoría de los usuarios, pero habilitar de forma selectiva usuarios específicos para eventos en directo.** 
1. Confirmar CsTeamsMeetingBroadcastPolicy Global tiene AllowBroadcastScheduling = False.
2. Confirme que la mayoría de los usuarios se han concedido OR CsTeamsMeetingBroadcastPolicy Global una de las directivas de CsTeamsMeetingBroadcastPolicy con AllowBroadcastScheduling = False.
3. Confirme que se han concedido todos los demás usuarios una de las directivas de CsTeamsMeetingBroadcastPolicy con AllowBroadcastScheduling = True.

### <a name="enable-creation-of-external-encoder-based-live-events-for-users"></a>Habilitar la creación de eventos live externos basados en codificador para los usuarios

#### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Habilitar Microsoft Stream para los usuarios de la organización
Microsoft Stream está disponible como parte de suscripciones a Office 365 optan o como un servicio independiente. Para obtener más información, vea [información general sobre licencias de secuencia](https://docs.microsoft.com/en-us/stream/license-overview) . Tenga en cuenta Microsoft Stream no se incluye en Business Essentials o planes de Business Premium.  

Obtenga más información acerca de cómo se pueden [asignar licencias a los usuarios de Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios pueden tener acceso a Microsoft Stream. Asegúrese de que no se bloquea Microsoft Stream para los usuarios tal como se define en [este artículo](https://docs.microsoft.com/en-us/stream/disable-user-organization).

#### <a name="ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Asegúrese de que los usuarios tienen permiso de creación de evento en directo en Microsoft Stream
De forma predeterminada, todas las personas de la empresa pueden crear contenido en secuencia, una vez que la secuencia está habilitada y se asigna una licencia para el usuario. Administrador de Microsoft Stream puede [restringir los empleados para la creación de contenido](https://docs.microsoft.com/en-us/stream/restrict-uploaders) en la secuencia. Los usuarios que se encuentran en esta lista restringida no podrá grabar las reuniones.

#### <a name="ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Asegúrese de evento en directo han dado su consentimiento los organizadores de la directiva de empresa establecida por el Administrador de secuencia
Si un administrador de Microsoft Stream tiene que [Configurar una directiva de instrucciones de la compañía](https://docs.microsoft.com/en-us/stream/company-policy-and-consent) y requiere que los empleados Aceptar esta directiva antes de guardar el contenido, a continuación, los usuarios deben hacerlo antes de crear un evento en directo (con producción codificador externo) en Microsoft Teams. Antes de la implantación la característica de eventos en directo en la organización, asegúrese de que los usuarios que vayan a crear estos eventos en directo han dado su consentimiento a la directiva. 

## <a name="configure-live-events"></a>Configuración de eventos en directo

### <a name="set-up-event-support-link-coming-soon"></a>Configurar el vínculo de soporte técnico de evento (próximamente)
Esto es el vínculo que se mostrará a los asistentes de evento en directo. 

PowerShell

En Windows PowerShell, ejecute el siguiente cmdlet:
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

PowerShell

Use la opción BroadcastAttendeeVisibility en TeamsMeetingBroadcastPolicy en PowerShell para controlar si los usuarios pueden programar la difusión de presentaciones eventos que se pueden ver los asistentes anónimo. Encontrará más información acerca de cómo administrar TeamsMeetingBroadcastPolicy con Office 365 PowerShell aquí.  

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene un valor predeterminado establecido en EveryoneInCompany. 
 
En Windows PowerShell, ejecute el siguiente cmdlet para permitir a los usuarios crear eventos anónimos en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Configurar las opciones de grabación
> [!NOTE]
> Esta opción es aplicable a los eventos que usan solo método de producción de inicio rápido.

Esto permite a los administradores para controlar si siempre se registran los eventos en directo, nunca se registró o si el organizador del evento puede optar por registrar el evento o no.  

|**Valores**  |**Comportamiento**  |
|---------|---------|
|Siempre están habilitadas |Siempre se registran los eventos live organizados por este usuario. Usuario no tiene una opción para invalidar. Si se registra el evento en directo, los miembros del equipo (evento) pueden descargar la grabación después del evento y los asistentes pueden verla el evento después de que el evento es a través de. |
|AlwaysDisabled |Nunca se registran los eventos live organizados por este usuario. Usuario no tiene una opción para invalidar. Si se registra el evento en directo, no se crea ninguna grabación para los miembros del equipo (evento) y los asistentes no pueden inspeccionar el evento después de que se encuentra sobre. |
|UserOverride |Usuario puede decidir si se registra el evento en directo para que se puede crear un archivo de grabación para los miembros del equipo (evento) y los asistentes pueden verla el evento después de que el evento es a través de. |

PowerShell

Use la opción BroadcastRecordingMode en TeamsMeetingBroadcastPolicy en PowerShell para controlar las opciones de los eventos de live creados por el organizador del evento live de grabación.

En Windows PowerShell, ejecute el siguiente cmdlet para actualizar el modo de grabación en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurar la transcripción en tiempo real y traducción en eventos en los equipos directo (próximamente)
> [!NOTE]
> Esta opción es aplicable a los eventos que usan solo método de producción de inicio rápido.

Esto permite que los organizadores de evento en directo activar la traducción de los asistentes del evento en directo y títulos en tiempo real. 

PowerShell

Use la opción AllowBroadcastTranscription en TeamsMeetingBroadcastPolicy en PowerShell para controlar si los asistentes del evento en directo podrá vea transcripción y traducción. Encontrará más información acerca de cómo administrar TeamsMeetingBroadcastPolicy con Office 365 PowerShell aquí.  

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene transcripción & traducción deshabilitado de forma predeterminada.

En Windows PowerShell, ejecute el siguiente cmdlet para activar la transcripción y traducción en para los asistentes de eventos en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="self-service-administration-tools"></a>Herramientas de administración de autoservicio 
Aunque Microsoft directamente controla todos los centros de datos en línea de Office 365 y es responsable de rendimiento general del sistema, puede controlar sólo una parte de los elementos que se combinan para proporcionar la experiencia de total para los usuarios de Office 365. Las organizaciones a sí mismos son responsables de las conexiones de red en los centros de datos, la red del cliente área extensa (WAN), y redes de área local del cliente (LAN). Además, están a cargo de los dispositivos de usuario y su configuración.También son responsables del mantenimiento de la licencia necesaria por usuario para cualquier característica que desee, incluidos, pero sin limitarse a, la capacidad para administrar estas características, para siempre y cuando el usuario necesita tener acceso a la característica.

Los clientes pueden usar las siguientes herramientas para administrar una variedad de tareas relacionadas de eventos en directo de los equipos.
- [Centro de administración de Microsoft Office 365](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams y Skype para el centro de administración de negocio en línea](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Centro de administración de Microsoft Stream
- [Windows PowerShell remoto](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?
- Cuando se trata de Windows PowerShell, que toda la información sobre administración de usuarios y qué usuarios pueden o no pueden para hacer. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)


### <a name="related-topics"></a>Temas relacionados: 

- [Eventos en directo a través de Microsoft 365 en Yammer, Microsoft Teams y Stream de Microsoft](https://docs.microsoft.com/stream/live-event-m365)
- [Eventos en directo en Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos en directo de Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos en directo en Microsoft Stream](https://review.docs.microsoft.com/stream/live-event-overview)