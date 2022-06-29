---
title: 'Compatibilidad medioambiental: Microsoft Teams'
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Cómo realizar un descubrimiento detallado del entorno a medida que planea su viaje de Skype Empresarial a Microsoft Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 22495b5266cddfd5fd7de4a106e1a55d15767995
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529742"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Detección del entorno para una implementación de Microsoft Teams

El descubrimiento es uno de los primeros pasos clave que debe seguir al planear su viaje a Microsoft Teams.

Realice un descubrimiento detallado de su entorno para comprender mejor su estado actual y revelar cualquier dificultad o, aún más, posibles bloqueadores para la ejecución de su implementación de Teams.

## <a name="discovery-questionnaire"></a>Cuestionario de detección

El cuestionario de ejemplo siguiente le guiará a través de un conjunto de preguntas para confirmar que su organización está lista para la implementación correcta de Audioconferencia y Sistema telefónico con funciones de planes de llamada en Teams.

Todos los asuntos relacionados con su infraestructura de colaboración existente y Microsoft 365 o Office 365 organización, redes, puntos de conexión, operaciones y adopción y preparación se incluyen como parte del cuestionario de detección ambiental.

El cuestionario se divide en varias secciones para confirmar la disponibilidad de su organización para la implementación de Teams en varias áreas principales. Trabaje con su equipo de proyecto para proporcionar la información solicitada con tantos detalles como sea posible para facilitar sus actividades de planificación.

> [!TIP]
> Para empezar, copie el cuestionario en un documento de Microsoft Word. Intenta responder a todas las preguntas y capturar todos los detalles mientras te desplazas.

### <a name="project-team"></a>Equipo de proyecto

Capture información detallada sobre las principales partes interesadas de su proyecto de implementación de Teams. Tenga en cuenta que una persona puede desempeñar varios roles en todo el proyecto.

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

## <a name="microsoft-365-or-office-365-organization-details"></a>Detalles de Microsoft 365 o Office 365 organización

Es muy recomendable que tenga una organización activa de Microsoft 365 o Office 365 mientras trabaja con este cuestionario. Si aún no ha activado o configurado una organización de Microsoft 365 o Office 365, consulte [Planear la configuración de Microsoft 365 para empresas](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use la tabla siguiente para capturar información sobre Microsoft 365 u Office 365 organización.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Tenga en cuenta la producción de Microsoft 365<br/>o Office 365 id. y nombre de la organización<br/>en la columna Respuesta. Si tienes más<br/>más de un espacio empresarial asociado con<br/>tu organización, anota todos los identificadores. | Nombre del inquilino: <br/>Id. de espacio empresarial:| |
> | ¿En qué regiones se implementan los inquilinos?| | |
> | Ten en cuenta el tipo de estas opciones de Microsoft 365 o <br/>Office 365 inquilinos. ¿Son multiempresa <br/>o dedicado? | <input type="checkbox"> Multiempresa<br/> <input type="checkbox"> Dedicado | |
> | ¿Qué productos de Microsoft Online se están usando? <br/>Tenga en cuenta el número de usuarios habilitados para cada <br/>en la columna Comentarios. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">Skype Empresarial <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">OneDrive para la Empresa <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Otro| |
> | Qué nivel de licencia está habilitado para Skype <br/>¿Usuarios de Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | El número de usuarios <br/>para cada SKU: |
> | ¿Cuál es el actual bosque de Active Directory? <br/>nivel funcional en el entorno? <br/>Si hay más de un bosque, anota los detalles <br/>en la columna Comentarios. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ¿Qué usa para el directorio? <br/>sincronización hoy? |<input type="checkbox"> Sin sincronización (solo en la nube) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Conectar <br/> <input type="checkbox"> Otro (especifique en el cuadro <br/>&nbsp;&nbsp; &nbsp; Columna Comentarios).| |
> | ¿La identidad federada está implementada en este momento? <br/>(Servicios de federación de Active Directory (AD FS) o <br/>terceros) | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Si usa la identidad federada, ¿cuál es el <br/>infraestructura de federación? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Federación de terceros <br/>&nbsp;&nbsp; &nbsp;puerta de enlace (tenga en cuenta los detalles <br/>&nbsp;&nbsp; &nbsp;en la columna Comentarios). | |
> | Si actualmente mantiene una cuenta activa de Microsoft 365<br/>o Office 365 espacio empresarial, es el dominio SMTP/SIP de <br/>los usuarios objetivo asociados con el inquilino? | <input type="checkbox"> N/D: sin Microsoft 365 o<br/>&nbsp;&nbsp; &nbsp;Office 365 inquilino local <br/> <input type="checkbox"> No, SMTP/SIP de los usuarios <br/>&nbsp;&nbsp; &nbsp;dominio no está asociado <br/>&nbsp;&nbsp; &nbsp;con cualquier inquilino en <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365<br/> <input type="checkbox"> Sí, SMTP/SIP de los usuarios <br/>&nbsp;&nbsp; &nbsp;dominio está asociado <br/>&nbsp;&nbsp; &nbsp;con un inquilino existente en <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365 | |
> | ¿Coinciden los UPN de usuario con su dirección SMTP principal? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No <br/> <input type="checkbox"> Inconsistente | |

## <a name="existing-collaboration-platform-summary"></a>Resumen de la plataforma de colaboración existente

Use la tabla siguiente para capturar información sobre la implementación de la plataforma de colaboración existente.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Microsoft Teams está implementado? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Skype Empresarial está implementado? <br/>Para implementaciones locales e híbridas, asegúrese de que <br/>tenga en cuenta la versión y la actualización acumulativa (CU) <br/>detalles en la columna Comentarios. | <input type="checkbox"> Sí, Microsoft 365 o <br/>&nbsp; &nbsp; &nbsp;Creación de inquilino <br/> <input type="checkbox"> Sí, híbrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sí, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox"> Sí, hospedado, compartido <br/>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox"> No, otros | |
> | ¿Exchange está implementado? <br/>Para implementaciones locales e híbridas, asegúrese de que <br/>anotas los detalles de la versión y cu en los Comentarios <br/>Columna. | <input type="checkbox"> Sí, Microsoft 365 <br/> <input type="checkbox"> Sí, híbrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sí, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox"> Sí, hospedado, compartido <br/>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox"> No, otros | |
> | ¿SharePoint está implementado? <br/>Para implementaciones locales e híbridas, asegúrese de que <br/>anotas los detalles de la versión y cu en los Comentarios <br/>Columna. | <input type="checkbox"> Sí, Microsoft 365 <br/> <input type="checkbox"> Sí, híbrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sí, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox"> Sí, hospedado, compartido <br/>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox"> No, otros | |
> | ¿OneDrive para la Empresa implementa? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Tiene otras plataformas de terceros implementadas? <br/>y en uso hoy? Si es así, anote el número de usuarios de <br/>estas plataformas y los detalles de uso de la <br/>Columna Comentarios. | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> Flojos <br/> <input type="checkbox"> Otro (especifique en el cuadro <br/>&nbsp;&nbsp; &nbsp; Columna Comentarios). | Número de usuarios: <br/>Detalles:|
> | ¿Está pensando en mover usuarios de estos terceros? <br/>plataformas para Teams? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Cuál es la solución de telefonía y conferencias actual? <br/>de los usuarios que están dentro del ámbito de esta iniciativa? | | |
> | ¿Tiene [SBC que admiten enrutamiento directo](./direct-routing-plan.md#supported-session-border-controllers-sbcs) implementado? <br/>para sus oficinas que están dentro del ámbito de esta iniciativa? Si es Así,<br/>anote los detalles de la columna Comentarios.| <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||

## <a name="collaboration-platform-deployment-details"></a>Detalles de la implementación de la plataforma de colaboración

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (si corresponde)

Si procede, capture los detalles de la implementación de Teams con la tabla de ejemplo siguiente. Si no ha implementado Teams, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Teams? | <input type="checkbox"> Todos los usuarios de la organización <br/> <input type="checkbox"> Usuarios o grupos de usuarios específicos <br/>&nbsp;&nbsp; &nbsp;(Especifique en la columna Comentarios). ||
> | ¿Qué características y modalidades de Teams están en uso? | <input type="checkbox"> Conversaciones basadas en canales <br/> <input type="checkbox"> Chat privado <br/> <input type="checkbox"> Acceso de invitado <br/> <input type="checkbox"> Reuniones de canal <br/> <input type="checkbox"> Reuniones privadas <br/> <input type="checkbox"> Llamadas privadas <br/> <input type="checkbox"> Meetup de canal ad hoc <br/> <input type="checkbox"> Vídeos en reuniones <br/> <input type="checkbox"> Uso compartido de la pantalla en reuniones <br/> <input type="checkbox"> Audioconferencia <br/><input type="checkbox"> Aplicaciones (aplicaciones)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Pestañas<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conectores<br/><input type="checkbox"> Integración personalizada de almacenamiento en la nube <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Integración del correo electrónico del canal <br/> <input type="checkbox"> Otro (especificar en la columna Comentarios). | |
> | ¿Qué aplicaciones ha implementado en Teams? | | |
> | ¿Ha bloqueado específicamente alguna funcionalidad de Teams? <br/>Si es Así, anote los detalles de la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||
> | ¿Qué clientes de Teams se están usando? | <input type="checkbox"> Web <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | ¿Quién tiene permiso para crear equipos? | <input type="checkbox"> Todos los miembros de la organización <br/>&nbsp;&nbsp; &nbsp;(Esta es la configuración predeterminada) <br/> <input type="checkbox"> Personas específicas <br/>&nbsp;&nbsp; &nbsp;(Especifique en la columna Comentarios). | |
> | ¿Está usando características de seguridad y cumplimiento en Teams? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Empresarial Online (si corresponde)

Si procede, capture los detalles de la implementación de Skype Empresarial Online con la tabla de ejemplo siguiente. Si no ha implementado Skype Empresarial implementación en línea, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Qué tipos de usuarios están habilitados para Skype <br/>para empresas en línea? | <input type="checkbox"> Todos los usuarios de la organización <br/> <input type="checkbox"> Usuarios o grupos de usuarios específicos <br/>&nbsp;&nbsp; &nbsp;(Especifique en la columna Comentarios). | |
> | Qué modalidades y características existen actualmente <br/>en uso hoy? | <input type="checkbox"> Mensajería instantánea y presencia (MI/P)<br/> <input type="checkbox"> Conferencias <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Grabación de la reunión <br/> <input type="checkbox"> Audioconferencia de Microsoft <br/> <input type="checkbox"> Audioconferencia de terceros (nota)<br/>&nbsp;&nbsp; &nbsp;los detalles de la columna Comentarios). <br/> <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox"> Operadores automáticos de la organización <br/> <input type="checkbox"> Colas de llamadas | |
> | ¿Has bloqueado específicamente cualquier <br/>¿Capacidades de Business Online? <br/>Si es Así, anote los detalles de la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Qué método está usando o planea usar para <br/>conectar el sistema telefónico (anteriormente PBX en la nube) a <br/>la RTC? <br/>Selecciona todas las que correspondan. | <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox"> Conectividad con RTC local <br/>&nbsp;&nbsp; &nbsp;(aprovechando skype existente para <br/>&nbsp;&nbsp; &nbsp; Empresa 2015 o Lync Server <br/>&nbsp;&nbsp; &nbsp;Implementación de 2013) <br/> <input type="checkbox"> Conectividad con RTC local <br/>&nbsp;&nbsp; &nbsp;(con Cloud Connector) | |
> | ¿Ha transferido algún número de teléfono a Microsoft? <br/>Esto es aplicable a los planes de llamadas y el audio <br/>Características de conferencia. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype Empresarial local (si procede)

Si procede, capture los detalles de la implementación de Skype Empresarial usando la tabla de ejemplo siguiente. Si no ha implementado Skype Empresarial local, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué versiones de Lync o Skype Empresarial <br/> actualmente se implementan de forma local? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Empresarial Server 2015 <br/> <input type="checkbox">Skype Empresarial Server 2019 <br/><input type="checkbox">Skype Empresarial Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edición | |
> | ¿Está configurado el modo híbrido con Skype Empresarial Online? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Este entorno está hospedado y administrado por un tercero? <br/>¿Partido? Si es Así, anota los detalles de la <br/>Columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Qué modalidades y características se están usando actualmente <br/>¿Hoy? | <input type="checkbox"> Mensajería instantánea y presencia (MI/P) <br/> <input type="checkbox"> Conferencias <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Grabación de la reunión <br/> <input type="checkbox"> Chat persistente o chat grupal <br/> <input type="checkbox"> Audioconferencia de Microsoft <br/>&nbsp;&nbsp; &nbsp;(anteriormente, Conferencia de acceso telefónico local) en su <br/>&nbsp;&nbsp; &nbsp;lync Server local o <br/>&nbsp;&nbsp; &nbsp;Implementación de Skype Empresarial <br/> <input type="checkbox"> Audioconferencia de terceros <br/>&nbsp;&nbsp; &nbsp;(Tenga en cuenta los detalles de los Comentarios <br/>&nbsp;&nbsp; &nbsp;columna). <br/> <input type="checkbox">Telefonía IP empresarial usar localmente <br/>&nbsp; &nbsp; &nbsp;Conectividad con RTC <br/> <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) a través de <br/>&nbsp;&nbsp; &nbsp; Implementación híbrida con Skype Empresarial Online | |
> | ¿Qué versiones del servidor perimetral ha implementado? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Empresarial Server 2015 <br/> <input type="checkbox">Skype Empresarial Server 2019| |
> | ¿Tiene Lync o Skype Empresarial Edge? <br/>implementado en más de un centro de datos? <br/>Si es Así, anote los detalles de la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Selecciona los servicios que tu rol de Edge proporciona hoy. | <input type="checkbox"> Acceso de usuarios externos (usuarios corporativos) <br/> <input type="checkbox"> Acceso de usuario remoto (anónimo) <br/>&nbsp;&nbsp; &nbsp;participantes de reuniones externas) <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Retransmisión multimedia | |
> | ¿Cuál de las siguientes características de llamada de voz le permite <br/>actualmente tienes dependencias en? <br/>Anote las dependencias adicionales en los Comentarios <br/>Columna. | <input type="checkbox"> Opciones de ocupado <br/> <input type="checkbox"> Parque de llamadas <br/> <input type="checkbox"> Recogida de llamadas o llamada grupal <br/> <input type="checkbox"> Teléfonos de área común o "escritorio caliente" <br/> <input type="checkbox"> Grupos de respuesta o grupos de búsqueda <br/> <input type="checkbox"> Apariencia de línea compartida <br/> <input type="checkbox"> Línea privada <br/> <input type="checkbox"> Mensaje de voz <br/> <input type="checkbox"> Llamar a través del trabajo <br/> <input type="checkbox"> Números de información o de emergencia <br/>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> Marcado de extensión <br/> <input type="checkbox"> Operador automático <br/> <input type="checkbox"> Acceso de suscriptor <br/> <input type="checkbox"> Dispositivos analógicos <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Enmascaramiento o modificación del identificador de llamada <br/> <input type="checkbox"> Enrutamiento basado en ubicación <br/> <input type="checkbox"> Enrutamiento de menor costo <br/> <input type="checkbox"> Teléfonos elevadores | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Redes y acceso a servicios de Microsoft 365 y Office 365

Use la tabla siguiente para capturar los detalles de red de su organización y cómo los usuarios están (o se conectarán) a los servicios de Microsoft 365 y Office 365.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Cómo (o cómo) los usuarios en el ámbito de la migración <br/>acceder a Teams cuando están en la oficina? <br/>Selecciona todas las que correspondan. | <input type="checkbox"> Conexión NAT enrutada <br/> <input type="checkbox"> Servidor proxy <br/> <input type="checkbox"> Wi-Fi pública <br/> <input type="checkbox"> Wi-Fi administrados (no públicos) <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp;(Emparejamiento de Microsoft) ||
> | Si el acceso a Microsoft 365 o Office 365 es a través de un<br/>servidor proxy, ¿hay alguna manera de omitir el proxy? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿ExpressRoute se está usando? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No <br/> <input type="checkbox"> No, pero se está planeando | |
> | ¿Ha realizado una evaluación de Network Readiness? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Se requiere a los usuarios que usen una VPN al conectarse a <br/>recursos corporativos de forma remota? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Si se usa una VPN, se puede excluir el tráfico de Teams <br/>la VPN para acceder directamente a Los Servicios de Microsoft 365 y Office 365? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Su red admite QoS? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Puede dar prioridad al tráfico de audio y vídeo de Teams? <br/>para impulsar una experiencia de alta calidad? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Todas las ubicaciones de una región tienen salida de Internet, <br/>o ¿está centralizada la salida de Internet para toda la región? | <input type="checkbox"> Acceso regional a Internet <br/> <input type="checkbox"> Acceso centralizado a la <br/>&nbsp;&nbsp; &nbsp;Internet | |

## <a name="endpoints"></a>Puntos de conexión

Use la tabla siguiente para capturar los detalles de los clientes y puntos de conexión en uso.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué sistema operativo de escritorio usan los usuarios? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Especifique la versión en la columna Comentarios). <br/> <input type="checkbox"> Linux (Especifique la distribución en la columna Comentarios). <br/><input type="checkbox"> Otros (Tenga en cuenta los detalles de la columna Comentarios). | |
> | Qué versión de Microsoft Office está implementada <br/>a estos dispositivos? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox"> Otros (Tenga en cuenta los detalles de la columna Comentarios). | |
> | Qué tecnología de implementación de Office está en uso <br/>en su organización? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Hacer clic y ejecutar | |
> | ¿Cuáles son los dispositivos móviles permitidos y admitidos? <br/>plataformas en uso? <br/>Selecciona todas las que correspondan. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Móvil <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Otros (Tenga en cuenta los detalles de la columna Comentarios). | |
> | ¿Cómo se proporcionan los dispositivos móviles? <br/>Selecciona todas las que correspondan. | <input type="checkbox"> Dispositivos corporativos <br/> <input type="checkbox"> Traer tu propio dispositivo | |
> | Qué dispositivos usan actualmente los usuarios para acceder <br/>servicios de voz y conferencia <br/>(auriculares, auriculares, teléfonos, vídeo)? | | |

## <a name="operations"></a>Operaciones

Utilice la tabla siguiente para capturar los detalles de los aspectos operativos de su entorno.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es su modelo de operaciones para Lync Server? <br/>Skype Empresarial Server, implementación de Microsoft 365, <br/>o Office 365 implementación hoy? | | |
> | ¿Puedes indicar la disposición de soporte técnico actual para <br/>Lync Server, Skype Empresarial Server, Microsoft 365, <br/>o Office 365? | | |
> | Si vas a realizar la implementación en varios países o regiones, <br/>cada país o región tiene su propia ti/telefonía <br/>personal para trabajar con o se gestionará de forma centralizada? | <input type="checkbox"> Operaciones regionales y soporte técnico <br/> <input type="checkbox"> Operaciones centralizadas y soporte técnico | |
> | ¿Está siguiendo la metodología de calidad de llamadas? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Ha asignado un individuo o equipo a la <br/>Rol de experto en calidad para la plataforma de colaboración <br/>en uso? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||
> | ¿Cómo se supervisa el servidor de Lync, Skype para <br/>Business Server, implementación de Microsoft 365 o <br/>Office 365 implementación? | | |
> | ¿Experimenta problemas con la calidad de las llamadas? | <input type="checkbox"> Sí<br/> <input type="checkbox"> No | |
> | Cómo y cuándo proporciona formación a su <br/>departamento de soporte técnico sobre nuevos servicios y capacidades? | | |

## <a name="adoption-and-readiness"></a>Adopción y preparación

Use la tabla siguiente y capture el estado actual de adopción y preparación de su organización.

>
> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es tu uso activo actual de <br/>Skype Empresarial? | **__** % total de usuarios activos frente a usuarios habilitados | |
> | ¿Cómo usa su organización? <br/>Skype Empresarial? | Conversaciones individuales <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamando <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartir<br/> Reuniones <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferencias<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartir<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamando | |
> | ¿Su organización tiene una adopción de usuario? <br/>y el equipo de administración de cambios? | <input type="checkbox"> Sí<br/> <input type="checkbox"> No | |
> | ¿Cómo se mide actualmente el éxito de la tecnología? <br/>lanzamientos como Skype Empresarial? | | |
> | ¿Qué porcentaje de su base de usuarios diría que tiene? <br/>adoptado Skype Empresarial? | | |
> | ¿Qué es la opinión de los usuarios sobre Skype Empresarial? | <input type="checkbox"> Bien <br/> <input type="checkbox"> Neutral <br/> <input type="checkbox"> Malo | |
> | Cuál de las siguientes frases describe mejor la implementación <br/>estrategia que se usa para tu Skype Empresarial <br/>¿despliegue? | <input type="checkbox"> Amplio alcance: campaña de correo electrónico con <br/>&nbsp;&nbsp; &nbsp;vínculos a aprendizaje <br/> <input type="checkbox"> Expandido: alcance amplio más una variedad <br/>&nbsp;&nbsp; &nbsp;de campañas de concienciación (pósteres, <br/>&nbsp;&nbsp; &nbsp;eventos, expertos) y formación <br/>&nbsp;&nbsp; &nbsp;(vídeos, guías de usuario, en persona) <br/> <input type="checkbox"> Personalizado: expandido, más dirigido <br/>&nbsp;&nbsp; &nbsp;mensajería y aprendizaje por persona <br/> <input type="checkbox"> Otro <br/>&nbsp;&nbsp; &nbsp;(Tenga en cuenta los detalles de la columna Comentarios). | |
