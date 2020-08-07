---
title: Compatibilidad ambiental-Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Cómo realizar un descubrimiento medioambiental detallado mientras planea su viaje de Skype empresarial a Microsoft Teams.
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
ms.openlocfilehash: 43fc4728ab634efe78a0e0e129b2979096a57d60
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581121"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Descubrimiento ambiental para una implementación de Microsoft Teams
===================================================

El descubrimiento es uno de los primeros pasos clave que debe realizar al planificar el viaje a Microsoft Teams.

Puede realizar un descubrimiento detallado de su entorno para comprender mejor su estado actual y revelar cualquier dificultad o, incluso más aún más,: posibles bloqueos para la ejecución de la implementación de su equipo.

## <a name="discovery-questionnaire"></a>Cuestionario de la detección

El siguiente cuestionario de ejemplo le guiará a través de un conjunto de preguntas para confirmar que su organización está lista para el lanzamiento satisfactorio de audioconferencias y sistemas telefónicos con las funciones de planes de llamadas de Teams.

Todos los temas relacionados con su infraestructura de colaboración existente y Microsoft 365 u Office 365 organización, redes, puntos de conexión, operaciones, adopción y preparación se incluyen como parte del cuestionario de descubrimiento ambiental.

El cuestionario se divide en varias secciones para confirmar la preparación de su organización para la implementación de equipos en varias áreas principales. Trabaje con su equipo de proyecto para proporcionar la información solicitada con la mayor cantidad de detalles posible para facilitar sus actividades de planificación.

> [!TIP]
> Puede empezar copiando el cuestionario en un documento de Microsoft Word. Intenta contestar todas las preguntas y captura todos los detalles a medida que te desplazas.

<a name="project-team"></a>Equipo del proyecto
---

Obtener información detallada sobre los participantes clave del proyecto de lanzamiento de Teams. Tenga en cuenta que una persona puede desempeñar varias funciones en todo el proyecto.

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
> | Leads de unidades de negocio | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Detalles de la organización de Microsoft 365 u Office 365
---

Le recomendamos encarecidamente que tenga una organización activa de Microsoft 365 u Office 365 mientras trabaja con este cuestionario. Si aún no ha activado ni configurado una organización de Microsoft 365 u Office 365, consulte [planear la configuración de microsoft 365 para empresas](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use la tabla siguiente para capturar información sobre la organización de Microsoft 365 u Office 365.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Nota la producción de Microsoft 365<br/>o nombre e identificador de la organización de Office 365<br/>en la columna respuesta. Si tienes más<br/>de un inquilino asociado con<br/>su organización, anote todos los IDs. | Nombre del inquilino: <br/>IDENTIFICADOR de inquilino:| |
> | ¿En qué regiones se han implementado los inquilinos?| | |
> | Anote el tipo de estos de Microsoft 365 o <br/>Inquilinos de Office 365. Son de multiinquilino <br/>¿o dedicado? | <input type="checkbox">Multiinquilino<br/> <input type="checkbox">Dique | |
> | ¿Qué productos de Microsoft Online se están usando? <br/>Anote el número de usuarios habilitados para cada uno <br/>servicio en la columna Comentarios. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype empresarial <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive para la empresa <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Otros| |
> | ¿Qué nivel de licencia está habilitado para Skype? <br/>¿Los usuarios de empresas online? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 | El número de usuarios <br/>para cada SKU: |
> | ¿Qué es el bosque de Active Directory actual? <br/>nivel funcional del entorno? <br/>Si hay más de un bosque, anote los detalles <br/>en la columna Comentarios. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ¿Qué usa para el directorio? <br/>¿sincronizar hoy? |<input type="checkbox">Sin sincronización (solo en la nube) <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Vuelve <br/> <input type="checkbox">Other (especificar en el <br/>&nbsp;&nbsp; &nbsp; Columna comentarios).| |
> | ¿La identidad federada está implementada en este momento? <br/>(Servicios de Federación de Active Directory o <br/>tercero) | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Si está usando la identidad federada, ¿cuál es el <br/>infraestructura de Federación? | <input type="checkbox">AD FS de Windows 2008 R2 <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">AD FS de Windows 2012 R2 <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federación de terceros <br/>&nbsp;&nbsp; &nbsp; puerta de enlace (tenga en cuenta los detalles <br/>&nbsp;&nbsp; &nbsp; en la columna comentarios). | |
> | Si actualmente mantiene un Microsoft 365 activo<br/>u Office 365 tenant es el dominio SMTP/SIP de <br/>¿los usuarios de destino están asociados con el inquilino? | <input type="checkbox">N/A: sin Microsoft 365 ni<br/>&nbsp;&nbsp; &nbsp; Inquilino de Office 365 en su lugar <br/> <input type="checkbox">No, el usuario no es SMTP/SIP <br/>&nbsp;el &nbsp; &nbsp; dominio no está asociado <br/>&nbsp;&nbsp; &nbsp; con cualquier inquilino de <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 u Office 365<br/> <input type="checkbox">Sí, el SIP/SIP de los usuarios <br/>&nbsp;el &nbsp; &nbsp; dominio está asociado <br/>&nbsp;&nbsp; &nbsp; con un inquilino existente en <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 u Office 365 | |
> | ¿Los UPN de usuario coinciden con su dirección SMTP principal? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No <br/> <input type="checkbox">Impredecible | |

<a name="existing-collaboration-platform-summary"></a>Resumen de la plataforma de colaboración existente
---

Use la tabla siguiente para capturar información sobre la implementación de la plataforma de colaboración existente.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Microsoft Teams está implementado? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Skype Empresarial está implementado? <br/>Para las implementaciones híbridas y locales, asegúrese de que <br/>Nota la versión y la actualización acumulativa (CU) <br/>detalles en la columna Comentarios. | <input type="checkbox">Sí, Microsoft 365 o <br/>&nbsp; &nbsp; &nbsp;Creación de inquilino <br/> <input type="checkbox">Sí, híbrida (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp; (tercero) <br/> <input type="checkbox">Sí, hospedado, compartido <br/>&nbsp;&nbsp; &nbsp; (tercero) <br/> <input type="checkbox">No, otros | |
> | ¿Exchange está implementado? <br/>Para las implementaciones híbridas y locales, asegúrese de que <br/>Anote los detalles de versión y de CU en los comentarios <br/>DataColumn. | <input type="checkbox">Sí, Microsoft 365 <br/> <input type="checkbox">Sí, híbrida (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp; (tercero) <br/> <input type="checkbox">Sí, hospedado, compartido <br/>&nbsp;&nbsp; &nbsp; (tercero) <br/> <input type="checkbox">No, otros | |
> | ¿SharePoint está implementado? <br/>Para las implementaciones híbridas y locales, asegúrese de que <br/>Anote los detalles de versión y de CU en los comentarios <br/>DataColumn. | <input type="checkbox">Sí, Microsoft 365 <br/> <input type="checkbox">Sí, híbrida (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicado <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp; (tercero) <br/> <input type="checkbox">Sí, hospedado, compartido <br/>&nbsp;&nbsp; &nbsp; (tercero) <br/> <input type="checkbox">No, otros | |
> | ¿Se ha implementado OneDrive para la empresa? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Tiene implementadas otras plataformas de terceros? <br/>¿y en uso hoy? Si es así, anote el número de usuarios de <br/>Estas plataformas y los detalles de uso en la <br/>Columna Comentarios. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Parafina <br/> <input type="checkbox">Other (especificar en el <br/>&nbsp;&nbsp; &nbsp; Columna comentarios). | Número de usuarios: <br/>Sobre|
> | ¿Está pensando en mover usuarios de estos <br/>¿Cuáles son las plataformas de Teams? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Qué es la solución de telefonía y Conferencia actual? <br/>¿de los usuarios que están dentro del ámbito de esta iniciativa? | | |
> | ¿Tiene [SBC que admita el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) implementado? <br/>¿Cuáles son sus oficinas en el ámbito de esta iniciativa? En caso afirmativo,<br/>Anote los detalles de la columna Comentarios.| <input type="checkbox">Afirmativa <br/> <input type="checkbox">No ||

<a name="collaboration-platform-deployment-details"></a>Detalles de implementación de la plataforma de colaboración
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (si corresponde)

Si procede, Capture los detalles de la implementación de Teams mediante la tabla de ejemplo siguiente. Si no ha implementado Teams, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Teams? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Usuarios o grupos de usuarios específicos <br/>&nbsp;&nbsp; &nbsp; (Especifique en la columna comentarios). ||
> | ¿Qué características y modalidades de Teams se usan? | <input type="checkbox">Conversaciones basadas en canales <br/> <input type="checkbox">Chat privado <br/> <input type="checkbox">Acceso de invitados <br/> <input type="checkbox">Reuniones de canal <br/> <input type="checkbox">Reuniones privadas <br/> <input type="checkbox">Llamadas privadas <br/> <input type="checkbox">Meetup de canal ad hoc <br/> <input type="checkbox">Vídeos en reuniones <br/> <input type="checkbox">Pantalla compartida en reuniones <br/> <input type="checkbox">Audioconferencia <br/><input type="checkbox">Aplicaciones (aplicaciones)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Pestañas<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Los<br/><input type="checkbox">Integración de almacenamiento en nube personalizada <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Unidad, Egnyte (próximamente) <br/> <input type="checkbox">Integración del correo electrónico del canal <br/> <input type="checkbox">Otro (especifique en la columna comentarios). | |
> | ¿Qué aplicaciones ha implementado en Teams? | | |
> | ¿Ha bloqueado específicamente alguna funcionalidad de Teams? <br/>En caso afirmativo, anote los detalles de la columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No ||
> | ¿Qué clientes de Teams se están usando? | <input type="checkbox">Web <br/> <input type="checkbox">Ventana <br/> <input type="checkbox">Mac <br/> <input type="checkbox">Linux <br/>  <input type="checkbox">i <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | ¿Quién tiene permiso para crear equipos? | <input type="checkbox">Todas las personas de la organización <br/>&nbsp;&nbsp; &nbsp; (Esta es la configuración predeterminada) <br/> <input type="checkbox">Personas específicas <br/>&nbsp;&nbsp; &nbsp; (Especifique en la columna comentarios). | |
> | ¿Está usando características de seguridad y cumplimiento en Teams? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Empresarial Online (si corresponde)

Si procede, Capture los detalles de su implementación de Skype empresarial online con la tabla de ejemplo siguiente. Si no ha implementado la implementación de Skype empresarial online, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Skype? <br/>para empresas online? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Usuarios o grupos de usuarios específicos <br/>&nbsp;&nbsp; &nbsp; (Especifique en la columna comentarios). | |
> | Qué modalidades y características están actualmente <br/>¿está en uso hoy? | <input type="checkbox">Mensajería instantánea y presencia (mi/P)<br/> <input type="checkbox">Ferenc <br/> <input type="checkbox">Unifica <br/> <input type="checkbox">Grabación de reuniones <br/> <input type="checkbox">Conferencias de audio de Microsoft <br/> <input type="checkbox">Conferencia de audio de terceros (Nota<br/>&nbsp;&nbsp; &nbsp; detalles en la columna Comentarios.) <br/> <input type="checkbox">Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox">Operadores automáticos de la organización <br/> <input type="checkbox">Colas de llamadas | |
> | ¿Has bloqueado específicamente cualquier Skype para <br/>¿Capacidades de empresa online? <br/>En caso afirmativo, anote los detalles de la columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Qué método utilizas o planeas usar para <br/>conectar el sistema telefónico (anteriormente PBX en la nube) a <br/>la RTC? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox">Conectividad RTC local <br/>&nbsp;&nbsp; &nbsp; (aprovechando Skype existente para <br/>&nbsp;&nbsp; &nbsp; Empresa 2015 o Lync Server <br/>&nbsp;&nbsp; &nbsp; implementación de 2013) <br/> <input type="checkbox">Conectividad RTC local <br/>&nbsp;&nbsp; &nbsp; (mediante el conector de nube) | |
> | ¿Ha transferido algún número de teléfono a Microsoft? <br/>Esto es aplicable a los planes de llamadas y el audio <br/>Características de conferencia. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype empresarial local (si corresponde)

Si procede, Capture los detalles de la implementación de Skype empresarial con la tabla de ejemplo siguiente. Si no ha implementado Skype empresarial en local, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué versiones de Lync o Skype empresarial? <br/> ¿se implementan actualmente en el entorno local? | <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype empresarial Server 2015 <br/> <input type="checkbox">Skype empresarial Server 2019 <br/><input type="checkbox">Conector para la nube de Skype empresarial <br/>&nbsp;&nbsp; &nbsp; Home | |
> | ¿Está configurado el modo híbrido con Skype Empresarial Online? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Este entorno está hospedado y administrado por un tercero <br/>interlocutor? En caso afirmativo, anote los detalles de la <br/>Columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Qué modalidades y características se usan actualmente <br/>hoy? | <input type="checkbox">Mensajería instantánea y presencia (mi/P) <br/> <input type="checkbox">Ferenc <br/> <input type="checkbox">Unifica <br/> <input type="checkbox">Grabación de reuniones <br/> <input type="checkbox">Chat persistente/chat grupal <br/> <input type="checkbox">Conferencias de audio de Microsoft <br/>&nbsp;&nbsp; &nbsp; (antes marcar Conferencia) en el <br/>&nbsp;&nbsp; &nbsp; Lync Server local o <br/>&nbsp;&nbsp; &nbsp; Implementación de Skype empresarial <br/> <input type="checkbox">Conferencias de audio de terceros <br/>&nbsp;&nbsp; &nbsp; (Tenga en cuenta los detalles de los comentarios <br/>&nbsp;&nbsp; &nbsp; columna). <br/> <input type="checkbox">Telefonía IP empresarial con local <br/>&nbsp; &nbsp; &nbsp;Conectividad con RTC <br/> <input type="checkbox">Planes de llamadas (anteriormente llamadas RTC) a través de <br/>&nbsp;&nbsp; &nbsp; Entorno híbrido con Skype empresarial online | |
> | ¿Qué versiones del servidor perimetral ha implementado? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype empresarial Server 2015 <br/> <input type="checkbox">Skype empresarial Server 2019| |
> | ¿Tiene el Edge de Lync o Skype empresarial? <br/>¿se ha implementado en más de un centro de información? <br/>En caso afirmativo, anote los detalles de la columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Selecciona los servicios que tu rol de Edge proporciona hoy. | <input type="checkbox">Acceso de usuarios externos (usuarios corporativos) <br/> <input type="checkbox">Acceso de usuarios remotos (anónimo <br/>&nbsp;participantes de la &nbsp; &nbsp; reunión externa) <br/> <input type="checkbox">Unifica <br/> <input type="checkbox">Relé multimedia | |
> | ¿Cuáles de las siguientes características de las llamadas de voz <br/>¿tiene actualmente dependencias? <br/>Anote las dependencias adicionales de los comentarios <br/>DataColumn. | <input type="checkbox">Opciones de ocupado <br/> <input type="checkbox">Parque de llamadas <br/> <input type="checkbox">Recogida de llamadas o recogida de llamadas grupales <br/> <input type="checkbox">Teléfonos de área común o "entradas de lápiz en caliente" <br/> <input type="checkbox">Grupos de respuesta o grupos de captura <br/> <input type="checkbox">Apariencia de línea compartida <br/> <input type="checkbox">Línea privada <br/> <input type="checkbox">Telefónica <br/> <input type="checkbox">Llamar por el trabajo <br/> <input type="checkbox">Números de emergencia o de información <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox">Marcado de extensión <br/> <input type="checkbox">Operador automático <br/> <input type="checkbox">Acceso de suscriptor <br/> <input type="checkbox">Dispositivos analógicos <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Máscara o modificación de identificación de llamadas <br/> <input type="checkbox">Enrutamiento basado en la ubicación <br/> <input type="checkbox">Enrutamiento de menor costo <br/> <input type="checkbox">Teléfonos elevados | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Redes y acceso a Microsoft 365 y servicios de Office 365
---

Use la siguiente tabla para capturar los detalles de red de su organización y cómo se conectan los usuarios (o estarán) con los servicios de Microsoft 365 y Office 365.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Cómo (o cómo) los usuarios en el ámbito de la migración <br/>¿tiene acceso a teams cuando están en la oficina? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Conexión NAT enrutada <br/> <input type="checkbox">Servidor proxy <br/> <input type="checkbox">Wi-Fi pública <br/> <input type="checkbox">Wi-Fi administrada (no pública) <br/> <input type="checkbox">ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Emparejamiento de Microsoft) ||
> | Si el acceso a Microsoft 365 u Office 365 se realiza a través de un<br/>servidor proxy, ¿hay alguna forma de eludir el proxy? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿ExpressRoute se está usando? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No <br/> <input type="checkbox">No, pero se está planificando | |
> | ¿Ha realizado una evaluación de la disponibilidad de red? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Los usuarios deben usar una VPN al conectarse a <br/>¿los recursos corporativos de forma remota? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Si se usa una red privada virtual, se puede excluir el tráfico de los equipos de <br/>¿VPN para obtener acceso a los servicios de Microsoft 365 y Office 365 directamente? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Su red admite QoS? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Puede priorizar el tráfico de audio y vídeo de los equipos <br/>para impulsar una experiencia de alta calidad? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Todas las ubicaciones de una región tienen salida a través de Internet? <br/>¿o se está centralizando la salida de Internet para toda la región? | <input type="checkbox">Acceso regional a Internet <br/> <input type="checkbox">Acceso centralizado a la <br/>&nbsp;&nbsp; &nbsp; Internet | |

<a name="endpoints"></a>Puntos de conexión
---

Use la siguiente tabla para capturar los detalles de los clientes y puntos de conexión en uso.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué sistema operativo de escritorio usan los usuarios? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (especifique la versión en la columna comentarios). <br/> <input type="checkbox">Linux (especifique la distribución en la columna comentarios). <br/><input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | Qué versión de Microsoft Office está implementada <br/>a estos dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | Qué tecnología de implementación de Office está en uso <br/>en su organización? | <input type="checkbox">MS <br/> <input type="checkbox">Hacer clic y ejecutar | |
> | ¿Qué son los móviles permitidos y admitidos? <br/>¿se están usando las plataformas? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Ventana <br/> <input type="checkbox">Vil <br/> <input type="checkbox">i <br/> <input type="checkbox">Android <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | ¿Cómo se proporcionan los dispositivos móviles? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Dispositivos empresariales <br/> <input type="checkbox">Traiga su propio dispositivo | |
> | Qué dispositivos usan actualmente los usuarios para acceder a <br/>servicios de voz y Conferencia <br/>(teléfonos, auriculares con micrófono, teléfonos y video) | | |

<a name="operations"></a>Operations
---

Use la tabla siguiente para capturar los detalles de los aspectos operativos de su entorno.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es el modelo de operaciones para su Lync Server? <br/>Skype empresarial Server, implantación de Microsoft 365, <br/>¿o la implementación de Office 365 hoy? | | |
> | ¿Puede esbozar la organización de soporte técnico actual para <br/>Lync Server, Skype empresarial Server, Microsoft 365, <br/>u Office 365? | | |
> | Si va a realizar la implementación en varios países o regiones, <br/>¿cada país o región tienen su propia telefonía/telefonía? <br/>¿el personal debe trabajar con él o se administrará de forma centralizada? | <input type="checkbox">Operaciones y asistencia regional <br/> <input type="checkbox">Soporte técnico y operaciones centralizadas | |
> | ¿Estás siguiendo la metodología de calidad de las llamadas? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Ha asignado una persona o un equipo a la <br/>Función de calidad de experto para la plataforma de colaboración <br/>¿está en uso? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No ||
> | ¿Cómo se supervisa su Lync Server, Skype para <br/>Business Server, implementación de Microsoft 365 o <br/>Implementación de Office 365 | | |
> | ¿Experimenta problemas de calidad de las llamadas? | <input type="checkbox">Afirmativa<br/> <input type="checkbox">No | |
> | Cómo y cuándo proporcionas formación a tu <br/>¿tiene soporte técnico sobre nuevos servicios y capacidades? | | |

<a name="adoption-and-readiness"></a>Adopción y preparación
---

Use la siguiente tabla para capturar el estado actual de adopción y preparación de su organización.

>
> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es el uso activo actual de <br/>¿Skype empresarial? | **_ _** % total de usuarios activos frente a usuarios habilitados | |
> | ¿Cómo está usando su organización <br/>¿Skype empresarial? | conversaciones de 1:1 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> MENSAJERÍA <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamadas <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Equilibrio<br/> Reuniones <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Ferenc<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Equilibrio<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamadas | |
> | ¿Tiene su organización una adopción de usuario? <br/>y el equipo de administración de cambios? | <input type="checkbox">Afirmativa<br/> <input type="checkbox">No | |
> | ¿Cómo medimos el éxito de la tecnología? <br/>implementaciones como Skype empresarial | | |
> | ¿Qué porcentaje de la base de usuarios dice que tiene <br/>¿ha adoptado Skype empresarial? | | |
> | ¿Qué es la opinión del usuario en relación con Skype empresarial? | <input type="checkbox">Bueno <br/> <input type="checkbox">Neutral <br/> <input type="checkbox">Malo | |
> | ¿Cuál de las siguientes opciones describe mejor el despliegue? <br/>estrategia usada para Skype empresarial <br/>implementación? | <input type="checkbox">Amplio alcance: campaña de correo electrónico con <br/>&nbsp;&nbsp; &nbsp; vínculos al aprendizaje <br/> <input type="checkbox">Ampliado: amplio alcance más una variedad <br/>&nbsp;&nbsp; &nbsp; de campañas de conciencia (pósteres, <br/>&nbsp;&nbsp; &nbsp; eventos, campeones) y formación <br/>&nbsp;&nbsp; &nbsp; (vídeos, guías para usuarios, personal) <br/> <input type="checkbox">Personalizado: ampliado, además de destino <br/>&nbsp;&nbsp; &nbsp; Mensajería y formación por persona <br/> <input type="checkbox">Otros <br/>&nbsp;&nbsp; &nbsp; (Tenga en cuenta los detalles de la columna comentarios). | |
