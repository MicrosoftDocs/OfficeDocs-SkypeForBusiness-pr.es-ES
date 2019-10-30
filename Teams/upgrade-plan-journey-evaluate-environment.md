---
title: Actualización de Microsoft Teams | Evaluación del entorno, preguntas sobre descubrimiento
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Use esta guía para obtener información sobre los requisitos para evaluar correctamente su entorno actual para actualizar a teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4716eac44880ca149fb757d2f16ebfe80ccab65
ms.sourcegitcommit: 8db50c46992dccf54c1d4be58d8a0d21ec64ddd0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772324"
---
![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")

Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario. Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:

- [Inventar a los participantes del proyecto](upgrade-enlist-stakeholders.md)
- [Definió el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [La coexistencia y la interoperabilidad de Skype para empresas y equipos](https://aka.ms/SkypeToTeams-Coexist)
- [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>Evaluar el entorno antes de actualizar a teams

Este artículo proporciona una descripción general de los requisitos para evaluar correctamente su entorno actual para equipos operativos. Al evaluar su entorno, usted identifica los riesgos y los requisitos que influirán en la implementación general. Al identificar estos elementos previamente, puede ajustar la planificación para que funcione correctamente.

## <a name="introduction-to-the-discovery-questionnaire"></a>Introducción al cuestionario de detección

Para lograr los resultados clave objetivo (OKRs), ya has tomado decisiones clave sobre el servicio. El siguiente paso es realizar el descubrimiento medioambiental para evaluar todos los aspectos relacionados con la infraestructura de ti, las redes y las operaciones para confirmar que su organización está lista para implementar la solución. El descubrimiento es uno de los primeros pasos clave que debe tomar al planear su viaje a teams. El descubrimiento medioambiental debe incluir una evaluación de la disponibilidad de red para asegurarse de que su red pueda admitir la actualización a teams. Puede realizar un descubrimiento detallado de su entorno para comprender mejor su estado actual y revelar cualquier dificultad o, aún más importante, los posibles bloqueadores para la ejecución de la implementación de su equipo.

Identifique los riesgos técnicos como parte de una evaluación del medio ambiente y de la evaluación de la preparación de la adopción, y desarrolle un plan de mitigación por cada riesgo identificado. Debes incorporar esta información en el registro de riesgos.

Todos los temas relacionados con su infraestructura de colaboración y el inquilino de Office 365, la red, los puntos de conexión, las operaciones, la adopción y la preparación están incluidos en el cuestionario de descubrimiento ambiental. El cuestionario se divide en varias secciones para confirmar la preparación de su organización para la implementación de equipos en varias áreas principales. Trabaje con su equipo de proyecto para proporcionar la información solicitada con la mayor cantidad de detalles posible para facilitar sus actividades de planificación.

> [!TIP]
> Puede empezar copiando el cuestionario en un documento de Microsoft Word. Intenta contestar todas las preguntas y captura todos los detalles a medida que te desplazas.

## <a name="project-team"></a>Equipo del proyecto

Asegúrese de que ha contratado a las personas adecuadas para el equipo de su proyecto. Comprobar los pasos completados en [dar de alta el proyecto stakekholders](upgrade-enlist-stakeholders.md).

## <a name="office-365-tenant-details"></a>Detalles del inquilino de Office 365

Le recomendamos encarecidamente tener un inquilino activo de Office 365 mientras trabaja con este cuestionario. Si aún no ha activado ni configurado un inquilino de Office 365, consulte [planear la configuración de office 365 para empresas](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use la tabla siguiente para capturar información sobre el inquilino de Office 365.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Nota el inquilino de Office 365 de producción <br>nombre e identificador en la columna respuesta <br/>Si tiene más de un inquilino <br>asociado a su organización, <br>Anote todos los identificadores. | Nombre del inquilino: <br/>IDENTIFICADOR de inquilino:| |
> | ¿En qué regiones se han implementado los inquilinos?| | |
> | Estos son los inquilinos de Office 365 multiinquilino o <br>Dique? | <input type="checkbox">Multiinquilino<br/> <input type="checkbox">Dique | |
> | ¿Qué productos de Microsoft Online se están usando? <br/>Anote el número de usuarios habilitados para cada uno <br>servicio en la columna Comentarios. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype empresarial <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive para la empresa <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Otros| |
> | ¿Qué nivel de licencia está habilitado para Skype? <br>¿Los usuarios de empresas online? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">Independiente | El número de usuarios <br>para cada SKU: |
> | ¿Qué es el bosque de Active Directory actual? <br>nivel funcional del entorno? <br/>Si hay más de un bosque, anote los detalles <br>en la columna Comentarios. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ¿Qué usa para el directorio? <br>¿sincronizar hoy? |<input type="checkbox">Sin sincronización (solo en la nube) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Conectar <br/> <input type="checkbox">Other (especificar en el <br>&nbsp;&nbsp; &nbsp;| |
> | ¿La identidad federada está implementada en este momento? <br/>(Servicios de Federación de Active Directory o <br>tercero) | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Si está usando la identidad federada, ¿cuál es el <br>infraestructura de Federación? | <input type="checkbox">AD FS de Windows 2008 R2 <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">AD FS de Windows 2012 R2 <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federación de terceros <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; (Tenga en cuenta los detalles &nbsp;de la <br>&nbsp;&nbsp; &nbsp; | |
> | Si actualmente mantiene un 365 activo de Office <br>inquilino, es el dominio SMTP/SIP de su <br>¿los usuarios de destino están asociados con el inquilino? | <input type="checkbox">N/A: sin 365 de Office <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">No, el usuario no es SMTP/SIP <br>&nbsp;&nbsp; &nbsp;está asociado <br>&nbsp;&nbsp; &nbsp; <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Sí, el SIP/SIP de los usuarios <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; | |
> | ¿Los UPN de usuario coinciden con su dirección SMTP principal? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No <br/> <input type="checkbox">Impredecible | |

## <a name="existing-collaboration-platform-summary"></a>Resumen de la plataforma de colaboración existente

Use la tabla siguiente para capturar información sobre la implementación de la plataforma de colaboración existente.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Microsoft Teams está implementado? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Skype Empresarial está implementado? <br/>Para las implementaciones híbridas y locales, asegúrese de que <br>Nota la versión y la actualización acumulativa (CU) <br>detalles en la columna Comentarios. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrida (con Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicado <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sí, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sí, hospedado, compartido (tercero) <br/> <input type="checkbox">No, otros | |
> | ¿Exchange está implementado? <br/>Para las implementaciones híbridas y locales, asegúrese de que <br>Anote los detalles de versión y de CU en los comentarios <br>DataColumn. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrida (con Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicado <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sí, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sí, hospedado, compartido <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">No, otros | |
> | ¿SharePoint está implementado? <br/>Para las implementaciones híbridas y locales, asegúrese de que <br>Anote los detalles de versión y de CU en los comentarios <br>DataColumn. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrida (con Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicado <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sí, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sí, hospedado, compartido <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">No, otros | |
> | ¿Se ha implementado Office 365 OneDrive para la empresa? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Tiene implementadas otras plataformas de terceros? <br>¿y en uso hoy? Si es así, anote el número de usuarios de <br>Estas plataformas y los detalles de uso en los comentarios <br>DataColumn. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Parafina <br/> <input type="checkbox">Otros (especificar en los comentarios <br>&nbsp;&nbsp; &nbsp; | Número de usuarios: <br/>Sobre|
> | ¿Está pensando en mover usuarios de estos <br>¿Cuáles son las plataformas de Teams? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Qué es la solución de telefonía y Conferencia actual? <br>¿de los usuarios que están dentro del ámbito de esta iniciativa? | | |
> | ¿Tiene [SBCS que admite el enrutamiento directo](direct-routing-plan.md#supported-session-border-controllers-sbcs) implementado para sus oficinas en el ámbito de esta iniciativa? <br>En caso afirmativo, anote los detalles de la columna Comentarios.| <input type="checkbox">Afirmativa <br/> <input type="checkbox">No ||

## <a name="collaboration-platform-deployment-details"></a>Detalles de implementación de la plataforma de colaboración

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (si corresponde)

Si procede, Capture los detalles de la implementación de Teams mediante la tabla de ejemplo siguiente. Si no ha implementado Teams, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Teams? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Usuarios o grupos de usuarios específicos <br>&nbsp;&nbsp; (Especifique en la columna &nbsp;comentarios) ||
> | ¿Qué características y modalidades de Teams se usan? | <input type="checkbox">Conversaciones basadas en canales <br/> <input type="checkbox">Chat privado <br/> <input type="checkbox">Acceso de invitados <br/> <input type="checkbox">Reuniones de canal <br/> <input type="checkbox">Reuniones privadas <br/> <input type="checkbox">Llamadas privadas <br/> <input type="checkbox">Meetup de canal ad hoc <br/> <input type="checkbox">Vídeos en reuniones <br/> <input type="checkbox">Pantalla compartida en reuniones <br/> <input type="checkbox">Audioconferencia <br/><input type="checkbox">Aplicaciones (aplicaciones)<br> &nbsp;&nbsp; &nbsp; Pestañas <input type="checkbox"><br>&nbsp;&nbsp; Bots &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; Conectores &nbsp; <input type="checkbox"><br><input type="checkbox">Integración de almacenamiento en nube personalizada <br>&nbsp;&nbsp; (Box, Dropbox, ShareFile, Google &nbsp; Drive) <br/> <input type="checkbox">Integración del correo electrónico del canal <br/> <input type="checkbox">Otro (especifique en la columna comentarios). | |
> | ¿Qué aplicaciones ha implementado en Teams? | | |
> | ¿Ha bloqueado específicamente alguna funcionalidad de Teams? <br/>En caso afirmativo, anote los detalles de la columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No ||
> | ¿Qué clientes de Teams se están usando? | <input type="checkbox">Web <br/> <input type="checkbox">Ventana <br/> <input type="checkbox">Mac <br/> <input type="checkbox">i <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | ¿Quién tiene permiso para crear equipos? | <input type="checkbox">Todas las personas de la organización <br>&nbsp;&nbsp; (Esta es la configuración &nbsp;predeterminada) <br/> <input type="checkbox">Personas específicas <br>&nbsp;&nbsp; (Especifique en la columna comentarios &nbsp;). | |
> | ¿Está usando características de seguridad y cumplimiento en Teams? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Empresarial Online (si corresponde)

Si procede, Capture los detalles de su implementación de Skype empresarial online con la tabla de ejemplo siguiente. Si no ha implementado la implementación de Skype empresarial online, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Skype? <br>para empresas online? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Usuarios o grupos de usuarios específicos <br>&nbsp;&nbsp; (Especifique en la columna &nbsp;comentarios) | |
> | Qué modalidades y características están actualmente <br>¿está en uso hoy? | <input type="checkbox">Mensajería instantánea y presencia (mi/P)<br/> <input type="checkbox">Dichas <br/> <input type="checkbox">Unifica <br/> <input type="checkbox">Grabación de reuniones <br/> <input type="checkbox">Conferencias de audio de Microsoft <br/> <input type="checkbox">Conferencias de audio de terceros <br>&nbsp;&nbsp; (Tenga en cuenta los detalles de la columna comentarios &nbsp;). <br/> <input type="checkbox">Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox">Operadores automáticos de la organización <br/> <input type="checkbox">Colas de llamadas | |
> | ¿Has bloqueado específicamente cualquier Skype para <br>¿Capacidades de empresa online? <br>En caso afirmativo, anote los detalles de la columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Qué método utilizas o planeas usar para <br>conectar el sistema telefónico (anteriormente PBX en la nube) a <br>la RTC? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox">Conectividad RTC local (aprovechamiento de las existentes) <br>&nbsp;&nbsp; Skype empresarial 2015 o Lync &nbsp;Server 2013 <br>&nbsp;&nbsp; &nbsp;implementación) <br/> <input type="checkbox">Conectividad RTC local (con el conector de nube) | |
> | ¿Ha transferido algún número de teléfono a Microsoft? <br/>Esto es aplicable a los planes de llamadas y el audio <br>Características de conferencia. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype empresarial local (si corresponde)

Si procede, Capture los detalles de la implementación de Skype empresarial con la tabla de ejemplo siguiente. Si no ha implementado Skype empresarial en local, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué versiones de Lync o Skype empresarial existen actualmente? <br>¿se han implementado de forma local? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype empresarial Server 2015 <br/> <input type="checkbox">Skype empresarial Server 2019 <br/> <input type="checkbox">Skype empresarial Cloud Connector Edition | |
> | ¿Está configurado el modo híbrido con Skype Empresarial Online? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Está hospedado y administrado por un tercero? <br/>En caso afirmativo, anote los detalles de la columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Qué modalidades y características se usan actualmente <br>hoy? | <input type="checkbox">Mensajería instantánea y presencia (mi/P) <br/> <input type="checkbox">Dichas <br/> <input type="checkbox">Unifica <br/> <input type="checkbox">Grabación de reuniones <br/> <input type="checkbox">Chat persistente/chat grupal <br/> <input type="checkbox">Conferencias de audio de Microsoft <br>&nbsp;&nbsp; (antes marcar Conferencia) &nbsp;en el <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Conferencias de audio de terceros <br>&nbsp;&nbsp; (Tenga en cuenta los detalles de la columna &nbsp;comentarios) <br/> <input type="checkbox">Telefonía IP empresarial con RTC local <br>&nbsp;&nbsp; &nbsp;conectividad <br/> <input type="checkbox">Planes de llamadas (anteriormente llamadas RTC) a través de <br>&nbsp;&nbsp; Entorno híbrido con Skype &nbsp;empresarial online | |
> | ¿Qué versiones del servidor perimetral ha implementado? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype empresarial Server 2015 <br/> <input type="checkbox">Skype empresarial Server 2019 | |
> | ¿Tiene implementado el Edge de Lync o Skype empresarial? <br>¿en más de un centro de información? <br/>En caso afirmativo, anote los detalles de la columna Comentarios. | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Selecciona los servicios que tu rol de Edge proporciona hoy. | <input type="checkbox">Acceso de usuarios externos (usuarios corporativos) <br/> <input type="checkbox">Acceso remoto de usuarios (anónimos) <br>&nbsp;&nbsp; &nbsp;reunión) <br/> <input type="checkbox">Unifica <br/> <input type="checkbox">Relé multimedia | |
> | ¿Cuáles de las siguientes características de las llamadas de voz <br>¿tiene actualmente dependencias? <br/>Anote las dependencias adicionales de los comentarios <br>DataColumn. | <input type="checkbox">Opciones de ocupado <br/> <input type="checkbox">Parque de llamadas <br/> <input type="checkbox">Recogida de llamadas o recogida de llamadas grupales <br/> <input type="checkbox">Teléfonos de área común o "entradas de lápiz en caliente" <br/> <input type="checkbox">Grupos de respuesta o grupos de captura <br/> <input type="checkbox">Apariencia de línea compartida <br/> <input type="checkbox">Línea privada <br/> <input type="checkbox">Telefónica <br/> <input type="checkbox">Llamar por el trabajo <br/> <input type="checkbox">Números de emergencia o de información <br>&nbsp;&nbsp; (911, 811, &nbsp;411) <br/> <input type="checkbox">Marcado de extensión <br/> <input type="checkbox">Operador automático <br/> <input type="checkbox">Acceso de suscriptor <br/> <input type="checkbox">Dispositivos analógicos <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Máscara o modificación de identificación de llamadas <br/> <input type="checkbox">Enrutamiento basado en la ubicación <br/> <input type="checkbox">Enrutamiento de menor costo <br/> <input type="checkbox">Teléfonos elevados | |

## <a name="networking-and-access-to-office-365-services"></a>Redes y acceso a servicios de Office 365

Use la tabla siguiente para capturar los detalles de red de su organización y cómo están (o estarán) conectados los usuarios a los servicios de Office 365.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Cómo (o cómo) los usuarios en el ámbito de la migración <br>¿tiene acceso a teams cuando están en la oficina? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Conexión NAT enrutada <br/> <input type="checkbox">Servidor proxy <br/> <input type="checkbox">Wi-Fi pública <br/> <input type="checkbox">Wi-Fi administrada (no pública) <br/> <input type="checkbox">ExpressRoute (emparejamiento de Microsoft) ||
> | Si el acceso a Office 365 se realiza a través de un servidor proxy, está <br>¿alguna manera de eludir el proxy? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿ExpressRoute se está usando? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No <br/> <input type="checkbox">No, pero se está planificando | |
> | ¿Ha realizado una evaluación de la disponibilidad de red? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Los usuarios deben usar una VPN al conectarse a <br>¿los recursos corporativos de forma remota? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Si se usa una red privada virtual, se puede excluir el tráfico de los equipos de <br>¿VPN para obtener acceso directo a servicios de Office 365? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Su red admite QoS? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Puede priorizar el tráfico de audio y vídeo de los equipos <br>para impulsar una experiencia de alta calidad? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | ¿Todas las ubicaciones de una región tienen salida a través de Internet? <br>¿o se está centralizando la salida de Internet para toda la región? | <input type="checkbox">Acceso regional a Internet <br/> <input type="checkbox">Acceso centralizado a Internet | |

## <a name="endpoints"></a>Puntos de conexión

Use la siguiente tabla para capturar los detalles de los clientes y puntos de conexión en uso.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué sistema operativo de escritorio usan los usuarios? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (especifique la versión en la columna comentarios). <br/> <input type="checkbox">Linux (especifique la distribución en la columna comentarios). <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | Qué versión de Microsoft Office está implementada <br>a estos dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | Qué tecnología de implementación de Office está en uso <br>en su organización? | <input type="checkbox">MS <br/> <input type="checkbox">Hacer clic y ejecutar | |
> | ¿Qué son los móviles permitidos y admitidos? <br>¿se están usando las plataformas? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Ventana <br/> <input type="checkbox">Vil <br/> <input type="checkbox">i <br/> <input type="checkbox">Android <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | ¿Cómo se proporcionan los dispositivos móviles? <br/>Seleccione todos los que correspondan. | <input type="checkbox">Dispositivos empresariales <br/> <input type="checkbox">Traiga su propio dispositivo | |
> | Qué dispositivos usan actualmente los usuarios para acceder a <br>servicios de voz y Conferencia <br>(teléfonos, auriculares con micrófono, teléfonos y video) | | |

## <a name="operations"></a>Operations

Use la tabla siguiente para capturar los detalles de los aspectos operativos de su entorno.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es el modelo de operaciones para su Lync Server? <br>Skype empresarial Server u Office 365 Deployment <br>hoy? | | |
> | ¿Puede esbozar la organización de soporte técnico actual para <br>¿Lync Server, Skype empresarial Server u Office 365? | | |
> | Si va a realizar la implementación en varios países o regiones, <br>¿cada país o región tienen su propia telefonía/telefonía? <br>¿el personal debe trabajar con él o se administrará de forma centralizada? | <input type="checkbox">Operaciones y asistencia regional <br/> <input type="checkbox">Soporte técnico y operaciones centralizadas | |
> | ¿Estás siguiendo la [metodología de calidad](quality-of-experience-review-guide.md)de las llamadas? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No | |
> | Ha asignado una persona o un equipo a la <br>Función de calidad de experto para la plataforma de colaboración <br>¿está en uso? | <input type="checkbox">Afirmativa <br/> <input type="checkbox">No ||
> | ¿Cómo se supervisa su Lync Server, Skype para <br>Business Server u Office 365 Deployment? | | |
> | ¿Experimenta problemas de calidad de las llamadas? | <input type="checkbox">Afirmativa<br/> <input type="checkbox">No | |
> | Cómo y cuándo proporcionas formación a tu <br>¿tiene soporte técnico sobre nuevos servicios y capacidades? | | |

## <a name="adoption-and-readiness"></a>Adopción y preparación

Use la siguiente tabla para capturar el estado actual de adopción y preparación de su organización.

>
> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es el uso activo actual de <br>¿Skype empresarial? | **_ _** % total de usuarios activos frente a usuarios habilitados | |
> | ¿Cómo está usando su organización <br>¿Skype empresarial? | conversaciones de 1:1 <br>&nbsp;&nbsp; &nbsp; Mensaje <input type="checkbox"> instantáneo <br>&nbsp;&nbsp; Llamadas &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; &nbsp; Uso <input type="checkbox"> compartido<br> Reuniones <br>&nbsp;&nbsp; Conferencias &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; &nbsp; Uso <input type="checkbox"> compartido<br>&nbsp;&nbsp; Llamadas &nbsp; <input type="checkbox"> | |
> | ¿Tiene su organización una adopción de usuario? <br>y el equipo de administración de cambios? | <input type="checkbox">Afirmativa<br/> <input type="checkbox">No | |
> | ¿Cómo medimos el éxito de la tecnología? <br>implementaciones como Skype empresarial | | |
> | ¿Qué porcentaje de la base de usuarios dice que tiene <br>¿ha adoptado Skype empresarial? | | |
> | ¿Qué es la opinión del usuario en relación con Skype empresarial? | <input type="checkbox">Bueno <br/> <input type="checkbox">Neutral <br/> <input type="checkbox">Malo | |
> | ¿Cuál de las siguientes opciones describe mejor el despliegue? <br>estrategia usada para Skype empresarial <br>implementación? | <input type="checkbox">Amplio alcance: campaña de correo electrónico con <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ampliado: amplio alcance más una variedad <br>&nbsp;&nbsp; de campañas de conciencia (pósteres &nbsp;, <br>&nbsp;&nbsp; eventos, campeones) &nbsp;y formación <br>&nbsp;&nbsp; (vídeos, guías para usuarios, &nbsp;personal) <br/> <input type="checkbox">Personalizado: ampliado, además de destino <br>&nbsp;&nbsp; &nbsp;por persona <br/> <input type="checkbox">Otros <br>&nbsp;&nbsp; (Tenga en cuenta los detalles de la columna comentarios &nbsp;). | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será el responsable de completar una evaluación del entorno?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Paso siguiente</td><td><ul><li>Documente los resultados de la evaluación del entorno.</li></ul></td></tr>
</table>

Después de evaluar su entorno, continúe con el siguiente paso: [preparar la red](upgrade-prepare-environment-prepare-network.md).
