---
title: Microsoft Teams Actualizar | Evaluación del entorno, preguntas de detección
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Use esta guía para obtener información sobre los requisitos para evaluar correctamente su entorno actual para actualizar a Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3d1349cf32e652cc308bb85c187db90303aa959
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808960"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>Cuestionario de detección: evaluar el entorno

El siguiente conjunto de tablas enumera preguntas que le ayudarán a evaluar [su entorno antes de actualizar a Teams:](upgrade-plan-journey-evaluate-environment.md)

- [Microsoft 365 o Office 365 de la organización](#microsoft-365-or-office-365-organization-details)
- [Resumen de la plataforma de colaboración existente](#existing-collaboration-platform-summary)
- [Detalles de implementación de la plataforma de colaboración](#collaboration-platform-deployment-details)
- [Redes y acceso a Microsoft 365 o Office 365 servicios](#networking-and-access-to-microsoft-365-or-office-365-services)
- [Puntos de conexión](#endpoints)
- [Operaciones](#operations)
- [Adopción y preparación](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 o Office 365 de la organización

Le recomendamos que tenga una organización Microsoft 365 o Office 365 mientras trabaja con el cuestionario. Si aún no ha activado o configurado una Microsoft 365 o Office 365 organización, vea Planear la configuración de [Microsoft 365 para empresas.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

Use la tabla siguiente para capturar información sobre la Microsoft 365 o Office 365 organización.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Tenga en cuenta la Microsoft 365 producción o Office 365 organización <br>nombre e id. en la columna Respuesta <br/>Si tiene más de un inquilino <br>asociado a su organización, <br>tenga en cuenta todos los IDs. | Nombre del inquilino: <br/>Id. de inquilino:| |
> | ¿En qué regiones están implementados los inquilinos?| | |
> | ¿Son estos inquilinos Microsoft 365 o Office 365 Multitenant o <br>¿Dedicado? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dedicado | |
> | ¿Qué productos de Microsoft Online se están usando? <br/>Tenga en cuenta el número de usuarios habilitados para cada <br>en la columna Comentarios. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype Empresarial <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint En línea <br/> <input type="checkbox">OneDrive para la Empresa <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> Otros| |
> | ¿Qué nivel de licencia está habilitado para Skype para <br>¿Usuarios de Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> Independiente | El número de usuarios <br>para cada SKU: |
> | ¿Cuál es el bosque actual de Active Directory? <br>nivel funcional en el entorno? <br/>Si hay más de un bosque, anote los detalles <br>en la columna Comentarios. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ¿Qué está usando para el directorio? <br>¿Sincronización hoy? |<input type="checkbox"> Sin sincronización (solo en la nube) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp; Conectar <br/> <input type="checkbox"> Otros (Especificar en el <br>&nbsp;&nbsp; &nbsp; Columna Comentarios).| |
> | ¿La identidad federada está implementada en este momento? <br/>(Servicios de federación de Active Directory o <br>terceros) | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Si usa la identidad federada, ¿cuál es la <br>¿Infraestructura de federación? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> Federación de terceros <br>&nbsp;&nbsp; &nbsp; puerta de enlace <br>&nbsp;&nbsp; &nbsp; (Anote los detalles en el <br>&nbsp;&nbsp; &nbsp; Columna Comentarios). | |
> | Si actualmente mantiene una cuenta Microsoft 365 o Office 365 <br>inquilino, es el dominio SMTP/SIP de su <br>¿Usuarios dirigidos asociados con el inquilino? | <input type="checkbox">N/A: sin Microsoft 365 o Office 365 <br>&nbsp;&nbsp; &nbsp; inquilino en su lugar <br/> <input type="checkbox"> No, SMTP/SIP de los usuarios <br>&nbsp;&nbsp; &nbsp; dominio no está asociado <br>&nbsp;&nbsp; &nbsp; con todos los inquilinos en <br>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365 <br/> <input type="checkbox"> Sí, SMTP/SIP de los usuarios <br>&nbsp;&nbsp; &nbsp; dominio está asociado <br>&nbsp;&nbsp; &nbsp; con un inquilino existente <br>&nbsp;&nbsp; &nbsp; en Microsoft 365 o Office 365 | |
> | ¿Coinciden los UPN de usuario con su dirección SMTP principal? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No <br/> <input type="checkbox"> Incoherente | |

## <a name="existing-collaboration-platform-summary"></a>Resumen de la plataforma de colaboración existente

Use la tabla siguiente para capturar información sobre la implementación de la plataforma de colaboración existente.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Microsoft Teams está implementado? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Skype Empresarial está implementado? <br/>Para implementaciones locales e híbridas, asegúrese de que <br>nota la versión y la actualización acumulativa (CU) <br>detalles en la columna Comentarios. | <input type="checkbox">Sí, Microsoft 365 o Office 365 <br/> <input type="checkbox">Sí, híbrido (con Microsoft 365 o Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sí, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> Sí, hospedado, compartido (de terceros) <br/> <input type="checkbox"> No, otros | |
> | ¿Exchange está implementado? <br/>Para implementaciones locales e híbridas, asegúrese de que <br>nota la versión y los detalles de CU en comentarios <br>columna. | <input type="checkbox">Sí, Microsoft 365 o Office 365 <br/> <input type="checkbox">Sí, híbrido (con Microsoft 365 o Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sí, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> Sí, hospedado, compartido <br>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> No, otros | |
> | ¿SharePoint está implementado? <br/>Para implementaciones locales e híbridas, asegúrese de que <br>nota la versión y los detalles de CU en comentarios <br>columna. | <input type="checkbox">Sí, Microsoft 365 o Office 365 <br/> <input type="checkbox">Sí, híbrido (con Microsoft 365 o Office 365) <br/> <input type="checkbox"> Sí, local <br/> <input type="checkbox"> Sí, en línea, dedicado <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sí, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> Sí, hospedado, compartido <br>&nbsp;&nbsp; &nbsp; (terceros) <br/> <input type="checkbox"> No, otros | |
> | ¿Microsoft 365 o Office 365 OneDrive para la Empresa implementado? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Tiene implementadas otras plataformas de terceros? <br>y en uso hoy en día? Si es así, anote el número de usuarios de <br>estas plataformas y los detalles de uso en comentarios <br>columna. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> Otros (Especificar en los comentarios <br>&nbsp;&nbsp; &nbsp; columna). | Número de usuarios: <br/>Detalles:|
> | ¿Está planeando mover usuarios de estos terceros? <br>plataformas para Teams? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Cuál es la solución de telefonía y conferencias actual? <br>de los usuarios que están en el ámbito de esta iniciativa? | | |
> | ¿Tiene [SBC que admiten enrutamiento](direct-routing-plan.md#supported-session-border-controllers-sbcs) directo implementado para sus oficinas que están en el ámbito de esta iniciativa? <br>Si es así, anote los detalles en la columna Comentarios.| <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||

## <a name="collaboration-platform-deployment-details"></a>Detalles de implementación de la plataforma de colaboración

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (si corresponde)

Si procede, capture los detalles de su Teams mediante la tabla de ejemplo siguiente. Si no ha implementado Teams, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Teams? | <input type="checkbox"> Todos los usuarios de la organización <br/> <input type="checkbox"> Usuarios o grupos de usuarios específicos <br>&nbsp;&nbsp; &nbsp; (Especifique en la columna Comentarios) ||
> | ¿Teams características y modalidades están en uso? | <input type="checkbox"> Conversaciones basadas en canales <br/> <input type="checkbox"> Chat privado <br/> <input type="checkbox"> Acceso de invitado <br/> <input type="checkbox"> Reuniones de canal <br/> <input type="checkbox"> Reuniones privadas <br/> <input type="checkbox"> Llamadas privadas <br/> <input type="checkbox"> Reunión del canal ad hoc <br/> <input type="checkbox"> Vídeos en reuniones <br/> <input type="checkbox"> Uso compartido de pantalla en reuniones <br/> <input type="checkbox"> Audioconferencia <br/><input type="checkbox"> Aplicaciones (aplicaciones)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Pestañas<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conectores<br><input type="checkbox"> Integración de almacenamiento en la nube personalizada <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google Drive, Egnyte <br/> <input type="checkbox"> Integración de correo electrónico de canal <br/> <input type="checkbox"> Otros (Especifique en la columna Comentarios). | |
> | ¿Qué aplicaciones ha implementado para Teams? | | |
> | ¿Ha bloqueado específicamente alguna funcionalidad de Teams? <br/>Si es así, anote los detalles en la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||
> | ¿Qué clientes de Teams se están usando? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Móvil | |
> | ¿Quién tiene permiso para crear equipos? | <input type="checkbox"> Todos los miembros de la organización <br>&nbsp;&nbsp; &nbsp; (Esta es la configuración predeterminada) <br/> <input type="checkbox"> Personas específicas <br>&nbsp;&nbsp; &nbsp; (Especifique en la columna Comentarios). | |
> | ¿Está usando características de seguridad y cumplimiento en Teams? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Empresarial Online (si corresponde)

Si procede, capture los detalles de su Skype Empresarial en línea con la tabla de ejemplo siguiente. Si no ha implementado Skype Empresarial implementación en línea, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué tipos de usuarios están habilitados para Skype <br>¿Para Empresas Online? | <input type="checkbox"> Todos los usuarios de la organización <br/> <input type="checkbox"> Usuarios o grupos de usuarios específicos <br>&nbsp;&nbsp; &nbsp; (Especifique en la columna Comentarios) | |
> | ¿Qué modalidades y características son actualmente? <br>en uso hoy en día? | <input type="checkbox"> Mensajería instantánea y presencia (MI/P)<br/> <input type="checkbox"> Reuniones <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Grabación de reuniones <br/> <input type="checkbox"> Audioconferencia de Microsoft <br/> <input type="checkbox"> Audioconferencia de terceros <br>&nbsp;&nbsp; &nbsp; (Observe los detalles de la columna Comentarios). <br/> <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox"> Operadores automáticos de la organización <br/> <input type="checkbox"> Colas de llamadas | |
> | ¿Has bloqueado específicamente cualquier Skype para <br>¿Funcionalidades de Business Online? <br>Si es así, anote los detalles en la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Qué método usa o tiene previsto usar? <br>conectar Sistema telefónico (anteriormente PBX en la nube) a <br>¿la RTC? <br/>Seleccione todas las que se apliquen. | <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) <br/> <input type="checkbox"> Conectividad RTC local (aprovechando la conectividad RTC existente) <br>&nbsp;&nbsp; &nbsp; Skype Empresarial 2015 o Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; implementación) <br/> <input type="checkbox"> Conectividad RTC local (con Conector en la nube) | |
> | ¿Ha transferido algún número de teléfono a Microsoft? <br/>Esto es aplicable a planes de llamadas y audio <br>Características de conferencia. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype Empresarial local (si corresponde)

Si procede, capture los detalles de su Skype Empresarial mediante la tabla de ejemplo siguiente. Si no ha implementado Skype Empresarial local, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Qué versiones de Lync o Skype Empresarial actualmente <br>se implementan localmente? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Empresarial Server 2015 <br/> <input type="checkbox">Skype Empresarial Server 2019 <br/> <input type="checkbox">Skype for Business Edición de conector de nube | |
> | ¿Está configurado el modo híbrido con Skype Empresarial Online? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Este entorno está hospedado y administrado por un tercero? <br/>Si es así, anote los detalles en la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Qué modalidades y características están en uso actualmente <br>¿Hoy? | <input type="checkbox"> Mensajería instantánea y presencia (MI/P) <br/> <input type="checkbox"> Reuniones <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Grabación de reuniones <br/> <input type="checkbox"> Chat persistente / chat grupal <br/> <input type="checkbox"> Audioconferencia de Microsoft <br>&nbsp;&nbsp; &nbsp; (anteriormente Conferencias de acceso telefónico local) en su <br>&nbsp;&nbsp; &nbsp; Lync Server local o <br>&nbsp;&nbsp; &nbsp; Skype Empresarial implementación <br/> <input type="checkbox"> Audioconferencia de terceros <br>&nbsp;&nbsp; &nbsp; (Tenga en cuenta los detalles de la columna Comentarios) <br/> <input type="checkbox">Telefonía IP empresarial uso de RTC local <br>&nbsp;&nbsp; &nbsp; conectividad <br/> <input type="checkbox"> Planes de llamadas (anteriormente llamadas RTC) a través de <br>&nbsp;&nbsp; &nbsp; Híbrido con Skype Empresarial Online | |
> | ¿Qué versiones del servidor perimetral ha implementado? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Empresarial Server 2015 <br/> <input type="checkbox">Skype Empresarial Server 2019 | |
> | ¿Tiene Lync o Skype Empresarial Edge implementados <br>en más de un centro de datos? <br/>Si es así, anote los detalles en la columna Comentarios. | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Seleccione los servicios que su rol de Edge proporciona hoy. | <input type="checkbox"> Acceso de usuario externo (usuarios corporativos) <br/> <input type="checkbox"> Acceso de usuario remoto (externo anónimo) <br>&nbsp;&nbsp; &nbsp; participantes de la reunión) <br/> <input type="checkbox"> Federación <br/> <input type="checkbox"> Retransmisión multimedia | |
> | ¿Cuál de las siguientes características de llamadas de voz le permite <br>actualmente tiene dependencias en? <br/>Tenga en cuenta las dependencias adicionales en los comentarios <br>columna. | <input type="checkbox"> Opciones de disponibilidad <br/> <input type="checkbox"> Parque de llamadas <br/> <input type="checkbox"> Recogida de llamadas o recogida de llamadas grupales <br/> <input type="checkbox"> Teléfonos de área común o "hot desking" <br/> <input type="checkbox"> Grupos de respuesta o grupos de búsqueda <br/> <input type="checkbox"> Apariencia de línea compartida <br/> <input type="checkbox"> Línea privada <br/> <input type="checkbox"> Correo de voz <br/> <input type="checkbox"> Llamar a través del trabajo <br/> <input type="checkbox"> Números de emergencia o de información <br>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Marcación de extensión <br/> <input type="checkbox"> Operador automático <br/> <input type="checkbox"> Acceso de suscriptor <br/> <input type="checkbox"> Dispositivos analógicos <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Identificador de llamada que enmascara o modifica <br/> <input type="checkbox"> Enrutamiento basado en ubicación <br/> <input type="checkbox"> Enrutamiento de menor coste <br/> <input type="checkbox"> Teléfonos con ascensor | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Redes y acceso a Microsoft 365 o Office 365 servicios

Use la tabla siguiente para capturar los detalles de red de su organización y cómo los usuarios están (o estarán) conectados a Microsoft 365 o Office 365 servicios.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | Cómo hacerlo (o cómo lo hará) los usuarios en el ámbito de la migración <br>acceso Teams cuando están en la oficina? <br/>Seleccione todas las que se apliquen. | <input type="checkbox"> Conexión NAT enrutada <br/> <input type="checkbox"> Servidor proxy <br/> <input type="checkbox"> Información Wi-Fi <br/> <input type="checkbox"> Administración (no pública) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (emparejamiento de Microsoft) ||
> | Si el acceso a Microsoft 365 o Office 365 es a través de un servidor proxy, hay <br>¿Alguna forma de omitir el proxy? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿ExpressRoute se está usando? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No <br/> <input type="checkbox"> No, pero se está planeando | |
> | ¿Ha realizado una evaluación de preparación de red? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Es necesario que los usuarios usen una VPN al conectarse a <br>¿Recursos corporativos de forma remota? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Si se usa una VPN, puede Teams el tráfico de <br>la VPN para obtener acceso Microsoft 365 o Office 365 servicios directamente? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Su red admite QoS? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Puede priorizar Teams tráfico de audio y vídeo? <br>para impulsar una experiencia de alta calidad? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | Hacer que todas las ubicaciones de una región tengan salida de Internet, <br>o está centralizada la salida de Internet para toda la región? | <input type="checkbox"> Acceso regional a Internet <br/> <input type="checkbox"> Acceso centralizado a Internet | |

## <a name="endpoints"></a>Puntos de conexión

Use la tabla siguiente para capturar los detalles de los clientes y puntos de conexión en uso.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Qué sistema operativo de escritorio usan los usuarios? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Especifique la versión en la columna Comentarios). <br/> <input type="checkbox"> Linux (Especifique la distribución en la columna Comentarios). <br/> <input type="checkbox"> Otros (Tenga en cuenta los detalles de la columna Comentarios). | |
> | ¿Qué versión de Microsoft Office se implementa? <br>a estos dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox"> Otros (Tenga en cuenta los detalles de la columna Comentarios). | |
> | Qué Office de implementación está en uso <br>en su organización? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Hacer clic y ejecutar | |
> | ¿Cuáles son los dispositivos móviles permitidos y compatibles? <br>plataformas en uso? <br/>Seleccione todas las que se apliquen. | <input type="checkbox">Windows <br/> <input type="checkbox"> Móvil <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Otros (Tenga en cuenta los detalles de la columna Comentarios). | |
> | ¿Cómo se proporcionan los dispositivos móviles? <br/>Seleccione todas las que se apliquen. | <input type="checkbox"> Dispositivos corporativos <br/> <input type="checkbox"> Traer su propio dispositivo | |
> | ¿Qué dispositivos usan actualmente los usuarios para obtener acceso? <br>servicios de voz y conferencias <br>(auriculares, auriculares, teléfonos, vídeo)? | | |

## <a name="operations"></a>Operaciones

Use la tabla siguiente para capturar los detalles de los aspectos operativos de su entorno.

> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es el modelo de operaciones de Lync Server? <br>Skype Empresarial Server, Microsoft 365 o Office 365 implementación <br>¿Hoy? | | |
> | ¿Puede esquematear la disposición de soporte técnico actual para <br>¿Lync Server, Skype Empresarial Server, Microsoft 365 o Office 365? | | |
> | Si va a implementar en varios países o regiones, <br>¿Cada país o región tiene su propia IT/telefonía? <br>personal con el que trabajar o se administrará de forma centralizada? | <input type="checkbox"> Soporte técnico y operaciones regionales <br/> <input type="checkbox"> Operaciones y soporte técnico centralizados | |
> | ¿Sigue la Metodología [de calidad de llamadas?](quality-of-experience-review-guide.md) | <input type="checkbox"> Sí <br/> <input type="checkbox"> No | |
> | ¿Has asignado una persona o un equipo a la <br>Rol de Campeón de calidad para la plataforma de colaboración <br>¿Está en uso? | <input type="checkbox"> Sí <br/> <input type="checkbox"> No ||
> | ¿Cómo supervisa su Lync Server, Skype para <br>¿Business Server, Microsoft 365 o Office 365 implementación? | | |
> | ¿Experimenta problemas de calidad de llamadas? | <input type="checkbox"> Sí<br/> <input type="checkbox"> No | |
> | ¿Cómo y cuándo proporcionas formación a tu <br>departamento de soporte técnico sobre nuevos servicios y capacidades? | | |

## <a name="adoption-and-readiness"></a>Adopción y preparación

Use la tabla siguiente y capture el estado actual de adopción y preparación de su organización.

>
> | Pregunta | Respuesta | Comentarios |
> |---|---|---|
> | ¿Cuál es el uso activo actual de <br>Skype Empresarial? | **__** % total de usuarios activos frente a usuarios habilitados | |
> | Cómo usa su organización <br>Skype Empresarial? | Conversaciones 1:1 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Mensajería instantánea <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamadas <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Uso compartido<br> Reuniones <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferencias<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Uso compartido<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Llamadas | |
> | ¿Su organización tiene una adopción de usuarios? <br>¿y el equipo de administración de cambios? | <input type="checkbox"> Sí<br/> <input type="checkbox"> No | |
> | ¿Cómo se mide actualmente el éxito de la tecnología? <br>rollouts like Skype Empresarial? | | |
> | ¿Qué porcentaje de la base de usuarios diría que tiene? <br>adoptado Skype Empresarial? | | |
> | ¿Qué opinión tiene el usuario sobre Skype Empresarial? | <input type="checkbox"> Bueno <br/> <input type="checkbox"> Neutral <br/> <input type="checkbox"> Malo | |
> | Cuál de las siguientes describe mejor la implementación <br>estrategia usada para su Skype Empresarial <br>implementación? | <input type="checkbox"> Alcance general: Campaña de correo electrónico con <br>&nbsp;&nbsp; &nbsp; vínculos al aprendizaje <br/> <input type="checkbox"> Expandido: Alcance amplio más una variedad <br>&nbsp;&nbsp; &nbsp; campañas de concienciación (pósteres, <br>&nbsp;&nbsp; &nbsp; eventos, campeones) y aprendizaje <br>&nbsp;&nbsp; &nbsp; (vídeos, guías de usuario, en persona) <br/> <input type="checkbox"> Personalizado: Expandido, más dirigido <br>&nbsp;&nbsp; &nbsp; mensajería y aprendizaje por persona <br/> <input type="checkbox"> Otros <br>&nbsp;&nbsp; &nbsp; (Observe los detalles de la columna Comentarios). | |


