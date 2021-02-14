---
title: 'Compatibilidad medioambiental: Microsoft Teams'
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Cómo realizar un descubrimiento medioambiental detallado mientras planea el viaje de Skype Empresarial a Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 00173fe35d41241fb35a69f88785fa84b8bdf378
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790402"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Descubrimiento medioambiental de una implementación de Microsoft Teams
===================================================

Descubrir es uno de los primeros pasos clave que debe seguir al planear su viaje a Microsoft Teams.

Realice un descubrimiento detallado del entorno para comprender mejor su estado actual y para revelar cualquier dificultad o, aún más, posibles bloqueadores de la ejecución de la implementación de Teams.

## <a name="discovery-questionnaire"></a>Cuestionario de la detección

El cuestionario de ejemplo siguiente le guiará a través de un conjunto de preguntas para confirmar que su organización está lista para el correcto lanzamiento de Audioconferencia y Sistema telefónico con capacidades de planes de llamadas en Teams.

Todos los aspectos relacionados con su infraestructura de colaboración existente y la organización de Microsoft 365 u Office 365, redes, puntos de conexión, operaciones, adopción y preparación se incluyen como parte del cuestionario de detección medioambiental.

El cuestionario se divide en varias secciones para confirmar la disponibilidad de su organización para la implementación de Teams en varias áreas principales. Trabaje con el equipo del proyecto para proporcionar la información solicitada todos los detalles posibles para facilitar sus actividades de planificación.

> [!TIP]
> Para empezar, copie el cuestionario en un documento de Microsoft Word. Intente responder a todas las preguntas y capturar todos los detalles a medida que se desplaza por ellos.

<a name="project-team"></a>Equipo del proyecto
---

Capture información detallada sobre las principales partes interesadas del proyecto de implementación de Teams. Tenga en cuenta que una persona puede tener varios roles en todo el proyecto.

> | Rol | Nombre, dirección de correo electrónico, número de teléfono | Ubicación, zona horaria | Comentarios |
> |---|---|---|---|
> | Patrocinador ejecutivo | | | |
> | Responsable de proyecto | | | |
> | Arquitecto/responsable de colaboración | | | |
> | Consultor | | | |
> | Jefe de proyecto | | | |
> | Especialista en adopción/administración de cambios | | | |
> | Responsable de redes | | | |
> | Responsable de seguridad | | | |
> | Responsable de telefonía | | | |
> | Responsable de escritorio | | | |
> | Responsable del servicio de asistencia y soporte técnico | | | |
> | Responsable de implementación | | | |
> | Propietario del servicio | | | |
> | Responsable de las instalaciones | | | |
> | Responsable del equipo de vídeo | | | |
> | Clientes potenciales de unidades de negocio | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Detalles de la organización de Microsoft 365 u Office 365
---

Recomendamos encarecidamente que tenga una organización activa de Microsoft 365 u Office 365 mientras trabaja con este cuestionario. Si aún no ha activado o configurado una organización de Microsoft 365 u Office 365, consulte Planear la configuración de [Microsoft 365 para empresas.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

Use la tabla siguiente para capturar información sobre la organización de Microsoft 365 u Office 365.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Observe la versión de producción de Microsoft 365<br/>u Id. y nombre de la organización de Office 365<br/>en la columna Respuesta. Si tienes más<br/>de un inquilino asociado con<br/>de su organización, anote todos los datos. | Nombre del inquilino: <br/>Id. de espacio empresarial:| |
> | ¿En qué regiones se implementan los inquilinos?| | |
> | Anote el tipo de estos microsoft 365 o <br/>Inquilinos de Office 365. ¿Son multitenant? <br/>o Dedicado? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dedicado | |
> | ¿Qué productos de Microsoft Online se están usando? <br/>Tenga en cuenta el número de usuarios habilitados para cada <br/>en la columna Comentarios. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox"> Skype Empresarial <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> OneDrive para la Empresa <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Otros| |
> | Qué nivel de licencia está habilitado para Skype para <br/>¿Usuarios de Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | El número de usuarios <br/>para cada SKU: |
> | ¿Cuál es el bosque actual de Active Directory? <br/>nivel funcional en el entorno? <br/>Si hay más de un bosque, ten en cuenta los detalles <br/>en la columna Comentarios. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | ¿Qué usa para el directorio? <br/>sincronización actual? |<input type="checkbox"> Sin sincronización (solo en la nube) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Conectar <br/> <input type="checkbox"> Otros (especifica en el cuadro <br/>&nbsp;&nbsp; &nbsp; Columna Comentarios).| |
> | ¿La identidad federada está implementada en este momento? <br/>(Servicios de federación de Active Directory o <br/>terceros) | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Si usas la identidad federada, ¿cuál es el <br/>infraestructura de federación? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Federación de terceros <br/>&nbsp;&nbsp; &nbsp; puerta de enlace (tenga en cuenta los detalles) <br/>&nbsp;&nbsp; &nbsp; en la columna Comentarios). | |
> | Si actualmente mantiene una cuenta activa de Microsoft 365<br/>o el espacio empresarial de Office 365, es el dominio SMTP/SIP de <br/>los usuarios de destino asociados con el inquilino? | <input type="checkbox"> N/A: Sin Microsoft 365 o<br/>&nbsp;&nbsp; &nbsp; Espacio empresarial de Office 365 local <br/> <input type="checkbox"> No, el SMTP/SIP de los usuarios <br/>&nbsp;&nbsp; &nbsp; dominio no está asociado <br/>&nbsp;&nbsp; &nbsp; con cualquier inquilino en <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 u Office 365<br/> <input type="checkbox"> Sí, smtp/SIP de los usuarios <br/>&nbsp;&nbsp; &nbsp; dominio está asociado <br/>&nbsp;&nbsp; &nbsp; con un inquilino existente en <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 u Office 365 | |
> | ¿Los UPN de usuario coinciden con su dirección SMTP principal? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No <br/> <input type="checkbox"> Incoherente | |

<a name="existing-collaboration-platform-summary"></a>Resumen de la plataforma de colaboración existente
---

Use la tabla siguiente para capturar información sobre la implementación de la plataforma de colaboración existente.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Microsoft Teams está implementado? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Skype Empresarial está implementado? <br/>Para implementaciones híbridas y locales, asegúrese de que la configuración <br/>tenga en cuenta la versión y la actualización acumulativa (CU) <br/>en la columna Comentarios. | <input type="checkbox"> Sí, Microsoft 365 o <br/>&nbsp; &nbsp; &nbsp;Creación de inquilino <br/> <input type="checkbox"> Sí, híbrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sí, alojado, dedicado <br/>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> Sí, alojado, compartido <br/>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> No, otro | |
> | ¿Exchange está implementado? <br/>Para implementaciones híbridas y locales, asegúrese de que <br/>tome nota de la versión y de los detalles de cu en los comentarios <br/>. | <input type="checkbox"> Sí, Microsoft 365 <br/> <input type="checkbox"> Sí, híbrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sí, alojado, dedicado <br/>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> Sí, alojado, compartido <br/>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> No, otro | |
> | ¿SharePoint está implementado? <br/>Para implementaciones híbridas y locales, asegúrese de que la configuración <br/>tome nota de la versión y de los detalles de cu en los comentarios <br/>. | <input type="checkbox"> Sí, Microsoft 365 <br/> <input type="checkbox"> Sí, híbrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sí, alojado, dedicado <br/>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> Sí, alojado, compartido <br/>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> No, otro | |
> | ¿Está implementado OneDrive para la Empresa? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Tiene implementadas otras plataformas de terceros? <br/>y en uso hoy? Si es así, ten en cuenta el número de usuarios de <br/>estas plataformas y los detalles de uso en el <br/>Columna Comentarios. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Margen de demora <br/> <input type="checkbox"> Otros (especifica en el cuadro <br/>&nbsp;&nbsp; &nbsp; Columna Comentarios). | Número de usuarios: <br/>Detalles:|
> | ¿Está pensando en mover usuarios de estos terceros? <br/>plataformas de Teams? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Cuál es la solución de telefonía y conferencias actual? <br/>de los usuarios que están en el ámbito de esta iniciativa? | | |
> | ¿Tiene [SBC compatibles con Enrutamiento](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) directo implementado? <br/>para las oficinas que están dentro del ámbito de esta iniciativa? Si es así,<br/>tenga en cuenta los detalles de la columna Comentarios.| <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||

<a name="collaboration-platform-deployment-details"></a>Detalles de implementación de la plataforma de colaboración
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (si corresponde)

Si procede, capture los detalles de la implementación de Teams con la tabla de ejemplo siguiente. Si no ha implementado Teams, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Teams? | <input type="checkbox"> Todos los usuarios de la organización <br/> <input type="checkbox"> Usuarios o grupos de usuarios específicos <br/>&nbsp;&nbsp; &nbsp; (Especifique en la columna Comentarios). ||
> | ¿Qué características y modalidades de Teams se utilizan? | <input type="checkbox"> Conversaciones basadas en canal <br/> <input type="checkbox"> Chat privado <br/> <input type="checkbox"> Acceso de invitado <br/> <input type="checkbox"> Reuniones de canal <br/> <input type="checkbox"> Reuniones privadas <br/> <input type="checkbox"> Llamadas privadas <br/> <input type="checkbox"> Reunión de canal ad hoc <br/> <input type="checkbox"> Vídeos en reuniones <br/> <input type="checkbox"> Pantalla compartida en reuniones <br/> <input type="checkbox"> Audioconferencia <br/><input type="checkbox"> Aplicaciones (aplicaciones)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Pestañas<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conectores<br/><input type="checkbox"> Integración personalizada del almacenamiento en la nube <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Integración del correo electrónico del canal <br/> <input type="checkbox"> Otros (especificar en la columna Comentarios). | |
> | ¿Qué aplicaciones ha implementado en Teams? | | |
> | ¿Ha bloqueado específicamente alguna funcionalidad de Teams? <br/>Si es así, anote los detalles de la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||
> | ¿Qué clientes de Teams se están usando? | <input type="checkbox"> Web <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | ¿Quién tiene permiso para crear equipos? | <input type="checkbox"> Todos los usuarios de la organización <br/>&nbsp;&nbsp; &nbsp; (Esta es la configuración predeterminada) <br/> <input type="checkbox"> Personas específicas <br/>&nbsp;&nbsp; &nbsp; (Especifique en la columna Comentarios). | |
> | ¿Está usando características de seguridad y cumplimiento en Teams? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Empresarial Online (si corresponde)

Si procede, capture los detalles de su implementación de Skype Empresarial Online con la tabla de ejemplo siguiente. Si no ha implementado Skype Empresarial Online, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Qué tipos de usuarios están habilitados para Skype <br/>para empresas Online? | <input type="checkbox"> Todos los usuarios de la organización <br/> <input type="checkbox"> Usuarios o grupos de usuarios específicos <br/>&nbsp;&nbsp; &nbsp; (Especifique en la columna Comentarios). | |
> | Qué modalidades y características son actualmente <br/>¿Está en uso hoy? | <input type="checkbox"> Mensajería instantánea y presencia (MI/P)<br/> <input type="checkbox"> Conferencia <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Grabación de la reunión <br/> <input type="checkbox"> Audioconferencia de Microsoft <br/> <input type="checkbox"> Audioconferencia de terceros (nota)<br/>&nbsp;&nbsp; &nbsp; los detalles de la columna Comentarios). <br/> <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox"> Operadores automáticos de la organización <br/> <input type="checkbox"> Colas de llamadas | |
> | ¿Has bloqueado específicamente cualquier skype para <br/>¿Funcionalidades de Business Online? <br/>Si es así, anote los detalles de la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Qué método usa o para qué va a usar? <br/>conectar Sistema telefónico (anteriormente PBX en la nube) a <br/>¿RTC? <br/>Seleccione todas las opciones que se apliquen. | <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox"> Conectividad con RTC local <br/>&nbsp;&nbsp; &nbsp; (aprovechando skype existente para <br/>&nbsp;&nbsp; &nbsp; Business 2015 o Lync Server <br/>&nbsp;&nbsp; &nbsp; Implementación de 2013) <br/> <input type="checkbox"> Conectividad con RTC local <br/>&nbsp;&nbsp; &nbsp; (usando Cloud Connector) | |
> | ¿Ha transferido algún número de teléfono a Microsoft? <br/>Esto es aplicable a los planes de llamadas y audio <br/>Características de conferencia. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype Empresarial local (si procede)

Si procede, capture los detalles de su implementación de Skype Empresarial usando la tabla de ejemplo siguiente. Si no ha implementado Skype Empresarial local, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Qué versiones de Lync o Skype Empresarial <br/> están implementadas actualmente de forma local? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype Empresarial Server 2015 <br/> <input type="checkbox"> Skype Empresarial Server 2019 <br/><input type="checkbox"> Conector de nube de Skype Empresarial <br/>&nbsp;&nbsp; &nbsp; Edición | |
> | ¿Está configurado el modo híbrido con Skype Empresarial Online? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Este entorno está hospedado y administrado por un tercero <br/>fiesta? Si es así, anote los detalles en el cuadro <br/>Columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Qué modalidades y características están en uso actualmente <br/>¿está hoy? | <input type="checkbox"> Mensajería instantánea y presencia (MI/P) <br/> <input type="checkbox"> Conferencia <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Grabación de la reunión <br/> <input type="checkbox"> Chat persistente o chat grupal <br/> <input type="checkbox"> Audioconferencia de Microsoft <br/>&nbsp;&nbsp; &nbsp; (anteriormente Conferencia de acceso telefónico local) en su <br/>&nbsp;&nbsp; &nbsp; Lync Server local o <br/>&nbsp;&nbsp; &nbsp; Implementación de Skype Empresarial <br/> <input type="checkbox"> Audioconferencia de terceros <br/>&nbsp;&nbsp; &nbsp; (Tenga en cuenta los detalles en los comentarios <br/>&nbsp;&nbsp; &nbsp; columna). <br/> <input type="checkbox"> Telefonía IP empresarial uso local <br/>&nbsp; &nbsp; &nbsp;Conectividad con RTC <br/> <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) a través de <br/>&nbsp;&nbsp; &nbsp; Híbrido con Skype Empresarial Online | |
> | ¿Qué versiones del servidor perimetral ha implementado? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype Empresarial Server 2015 <br/> <input type="checkbox"> Skype Empresarial Server 2019| |
> | ¿Tiene Lync o Skype Empresarial Edge? <br/>implementado en más de un centro de datos? <br/>Si es así, anote los detalles de la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Selecciona los servicios que tu rol de Edge proporciona actualmente. | <input type="checkbox"> Acceso de usuarios externos (usuarios corporativos) <br/> <input type="checkbox"> Acceso remoto de usuario (anónimo) <br/>&nbsp;&nbsp; &nbsp; participantes externos a la reunión) <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Retransmisión multimedia | |
> | ¿Cuál de las siguientes características de llamadas de voz te <br/>actualmente tienen dependencias en? <br/>Note las dependencias adicionales en los comentarios <br/>. | <input type="checkbox"> Opciones de disponibilidad <br/> <input type="checkbox"> Parque de llamadas <br/> <input type="checkbox"> Recogida de llamadas o recogida de llamadas grupales <br/> <input type="checkbox"> Teléfonos de área comunes o "hot desking" <br/> <input type="checkbox"> Grupos de respuesta o grupos de búsqueda <br/> <input type="checkbox"> Apariencia de línea compartida <br/> <input type="checkbox"> Línea privada <br/> <input type="checkbox"> Correo de voz <br/> <input type="checkbox"> Llamar a través del trabajo <br/> <input type="checkbox"> Números de información o de emergencia <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Marcación de extensión <br/> <input type="checkbox"> Operador automático <br/> <input type="checkbox"> Acceso de suscriptor <br/> <input type="checkbox"> Dispositivos analógicos <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Enmascaramiento o alteración de la identificación de llamadas <br/> <input type="checkbox"> Enrutamiento basado en la ubicación <br/> <input type="checkbox"> Enrutamiento de menor costo <br/> <input type="checkbox"> Teléfonos de teléfonos móviles de telefonía | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Redes y acceso a servicios de Microsoft 365 y Office 365
---

Use la tabla siguiente para capturar los detalles de red de su organización y la forma en que los usuarios se conectan (o se conectarán) a los servicios de Microsoft 365 y Office 365.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Cómo hacerlo (o cómo) los usuarios en el ámbito de la migración <br/>¿Acceder a Teams cuando están en la oficina? <br/>Seleccione todas las opciones que se apliquen. | <input type="checkbox"> Conexión NAT enrutada <br/> <input type="checkbox"> Servidor proxy <br/> <input type="checkbox"> Información Wi-Fi <br/> <input type="checkbox"> Administración (no pública) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Emparejamiento de Microsoft) ||
> | Si el acceso a Microsoft 365 u Office 365 es a través de un<br/>servidor proxy, ¿existe alguna forma de omitir el proxy? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿ExpressRoute se está usando? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No <br/> <input type="checkbox"> No, pero se está planeando | |
> | ¿Ha realizado una evaluación de disponibilidad de red? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Los usuarios necesitan usar una VPN al conectarse a <br/>recursos corporativos de forma remota? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Si se usa una VPN, puede excluirse el tráfico de Teams de <br/>la VPN para acceder directamente a los Servicios de Microsoft 365 y Office 365? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Su red admite QoS? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Puede priorizar el tráfico de audio y vídeo de Teams? <br/>para impulsar una experiencia de alta calidad? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Hacer que todas las ubicaciones de una región tengan salida de Internet, <br/>¿O está centralizada la salida de Internet para toda la región? | <input type="checkbox"> Acceso regional a Internet <br/> <input type="checkbox"> Acceso centralizado a la <br/>&nbsp;&nbsp; &nbsp; internet | |

<a name="endpoints"></a>Puntos de conexión
---

Use la tabla siguiente para capturar los detalles de los clientes y puntos de conexión en uso.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué sistema operativo de escritorio usan los usuarios? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac (especifique la versión en la columna Comentarios). <br/> <input type="checkbox"> Linux (especifica la distribución en la columna Comentarios). <br/><input type="checkbox"> Otros (tenga en cuenta los detalles de la columna Comentarios). | |
> | Qué versión de Microsoft Office está implementada <br/>a estos dispositivos? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Office para Mac 2011 <br/> <input type="checkbox"> Office para Mac 2016 <br/> <input type="checkbox"> Otros (tenga en cuenta los detalles de la columna Comentarios). | |
> | Qué tecnología de implementación de Office está en uso <br/>de su organización? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Hacer clic y ejecutar | |
> | ¿Cuáles son los dispositivos móviles permitidos y compatibles? <br/>plataformas en uso? <br/>Seleccione todas las opciones que se apliquen. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Móvil <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Otros (tenga en cuenta los detalles de la columna Comentarios). | |
> | ¿Cómo se proporcionan los dispositivos móviles? <br/>Seleccione todas las opciones que se apliquen. | <input type="checkbox"> Dispositivos corporativos <br/> <input type="checkbox"> Lleva tu propio dispositivo | |
> | Qué dispositivos usan actualmente los usuarios para obtener acceso <br/>servicios de voz y conferencia <br/>(auriculares, auriculares, teléfonos, vídeo)? | | |

<a name="operations"></a>Operations
---

Use la tabla siguiente para capturar los detalles de los aspectos operativos de su entorno.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es su modelo de operaciones para Lync Server? <br/>Skype Empresarial Server, implementación de Microsoft 365, <br/>u implementación de Office 365 actualmente? | | |
> | ¿Puede esquematear la disposición de soporte actual para <br/>Lync Server, Skype Empresarial Server, Microsoft 365, <br/>u Office 365? | | |
> | Si va a implementar en varios países o regiones, <br/>cada país o región tiene su propia it/telefonía <br/>el personal docente con el que trabajar, ¿o se administrará de forma centralizada? | <input type="checkbox"> Operaciones regionales y soporte técnico <br/> <input type="checkbox"> Operaciones centralizadas y soporte técnico | |
> | ¿Está siguiendo la metodología de calidad de llamadas? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Has asignado una persona o un equipo a la <br/>Rol de champion de calidad para la plataforma de colaboración <br/>en uso? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||
> | ¿Cómo se supervisa el servidor de Lync, Skype para <br/>Business Server, implementación de Microsoft 365 o <br/>¿Implementación de Office 365? | | |
> | ¿Experimenta problemas de calidad de llamadas? | <input type="checkbox"> Sí<br/> <input type="checkbox"> No | |
> | Cómo y cuándo debe proporcionar aprendizaje a su <br/>departamento de soporte técnico sobre nuevos servicios y capacidades? | | |

<a name="adoption-and-readiness"></a>Adopción y preparación
---

Use la tabla siguiente y capture el estado de adopción y preparación actual de su organización.

>
> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Cuál es su uso activo actual de <br/>¿Skype Empresarial? | **__** % del total de usuarios activos frente a usuarios habilitados | |
> | ¿Cómo usa su organización? <br/>¿Skype Empresarial? | Conversaciones 1:1 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> MENSAJERÍA INSTANTÁNEA <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamadas <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Uso compartido<br/> Reuniones <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferencia<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Uso compartido<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamadas | |
> | ¿Su organización tiene una adopción de usuario? <br/>y el equipo de administración de cambios? | <input type="checkbox"> Sí<br/> <input type="checkbox"> No | |
> | ¿Cómo se mide el éxito de la tecnología actualmente? <br/>implementación como Skype Empresarial? | | |
> | ¿Qué porcentaje de la base de usuarios tendría que decir que tiene? <br/>¿Adoptó Skype Empresarial? | | |
> | ¿Qué opinión tiene el usuario sobre Skype Empresarial? | <input type="checkbox"> Buena <br/> <input type="checkbox"> Neutro <br/> <input type="checkbox"> Malo | |
> | Cuál de las siguientes describe mejor la implementación <br/>estrategia usada para su Skype Empresarial <br/>implementación? | <input type="checkbox"> Amplio alcance: Campaña de correo electrónico con <br/>&nbsp;&nbsp; &nbsp; vínculos a aprendizaje <br/> <input type="checkbox"> Expandido: amplio alcance y una variedad <br/>&nbsp;&nbsp; &nbsp; de campañas de concienciación (pósteres, <br/>&nbsp;&nbsp; &nbsp; eventos, campeones) y formación <br/>&nbsp;&nbsp; &nbsp; (vídeos, guías de usuario, en persona) <br/> <input type="checkbox"> Personalizado: Expandido, más dirigido <br/>&nbsp;&nbsp; &nbsp; mensajería y aprendizaje por rol <br/> <input type="checkbox"> Otros <br/>&nbsp;&nbsp; &nbsp; (Tenga en cuenta los detalles de la columna Comentarios). | |
