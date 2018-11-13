---
title: Detección del entorno para la implementación de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Cómo se realiza una detección medioambiental detallada al planear su viaje de Skype para la empresa a Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53f8704daf923b54e30d0061669ea1de63eeb02e
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295594"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Detección del entorno para la implementación de Microsoft Teams
===================================================

Detección es uno de los pasos de la primeros, claves que tomar al planear para su viaje a Microsoft Teams.

Realizar un descubrimiento detallado de su entorno para comprender mejor su estado actual y para revelar las dificultades o — aún más — los bloqueadores de elementos posibles para la ejecución de la implantación de los equipos.

<a name="discovery-questionnaire"></a>Cuestionario de la detección
=======================

El cuestionario de ejemplo que aparece a continuación le guiará a través de un conjunto de preguntas para confirmar que la organización está preparada para la correcta implantación de conferencias de Audio y el sistema telefónico con planes de llamar a las capacidades de los equipos.

Todos los asuntos relacionados con su existente infraestructura de colaboración y Office 365 inquilino, redes, extremos, las operaciones y adopción y preparación se incluyen como parte del cuestionario de descubrimiento del entorno.

El cuestionario se divide en varias secciones para confirmar la preparación de su organización para la implementación de los equipos en varias áreas principales. Trabajar con el equipo del proyecto para proporcionar la información solicitada con tantos detalles como sea posible para facilitar las actividades de planeación.

> [!TIP]
> Puede iniciar copiando el cuestionario en un documento de Microsoft Word. Intente responder a todas las preguntas y capturar todos los detalles cuando se desplaza a través de.

<a name="project-team"></a>Equipo del proyecto
------------

Capturar información detallada acerca de las partes interesadas claves de su proyecto de implantación de los equipos. Tenga en cuenta que una persona puede reproducir varias funciones a lo largo del proyecto.

> | Rol                                  | Nombre, dirección de correo electrónico, número de teléfono | Ubicación, zona horaria | Comentarios      |
> |---------------------------------------|-----------------------------------|---------------------|---------------|
> | Patrocinador ejecutivo                     |                                   |                     |               |
> | Responsable de proyecto                          |                                   |                     |               |
> | Arquitecto/responsable de colaboración          |                                   |                     |               |
> | Consultor                            |                                   |                     |               |
> | Jefe de proyecto                       |                                   |                     |               |
> | Especialista en adopción/administración de cambios |                                   |                     |               |
> | Responsable de redes                          |                                   |                     |               |
> | Responsable de seguridad                         |                                   |                     |               |
> | Responsable de telefonía                        |                                   |                     |               |
> | Responsable de escritorio                          |                                   |                     |               |
> | Responsable del servicio de asistencia y soporte técnico                |                                   |                     |               |
> | Responsable de implementación                       |                                   |                     |               |
> | Propietario del servicio                         |                                   |                     |               |
> | Responsable de las instalaciones                       |                                   |                     |               |
> | Responsable del equipo de vídeo                       |                                   |                     |               |
> | Responsables de la unidad de negocio                   |                                   |                     |               |

<a name="office-365-tenant-details"></a>Detalles del inquilino de Office 365
-------------------------

Se recomienda que tengan un inquilino de Office 365 activo mientras se trabaja con este cuestionario. Si no ha activado o configurado aún un inquilino de Office 365, vea [Planear el programa de instalación de Office 365 para la empresa](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use la tabla siguiente para capturar la información sobre el inquilino de Office 365.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Tenga en cuenta al inquilino de producción Office 365 <br>nombre y el identificador de la columna de respuesta <br/>Si tiene más de un inquilino <br>asociado con la organización, <br>Tenga en cuenta todos los identificadores.  | Nombre del inquilino: <br/>Identificador de inquilino:| |
> | ¿En qué áreas se implementan los inquilinos?| | |
> | Son estos los inquilinos de Office 365 Multitenant o <br>¿Dedicado? | <input type="checkbox">Multitenant<br/> <input type="checkbox">Dedicada | |
> | ¿Qué productos de Microsoft Online se están usando? <br/>Tenga en cuenta el número de usuarios habilitados para cada uno <br>servicio en la columna comentarios. | <input type="checkbox">Equipos de Microsoft <br/> <input type="checkbox">Skype para la empresa <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive para la empresa <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Otros|                                   |
> | ¿Qué nivel de licencia está habilitado para Skype para <br>¿Usuarios en línea de negocio? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 | El número de usuarios <br>para cada SKU: |
> | ¿Qué es el bosque de Active Directory actual <br>¿nivel funcional en el entorno? <br/>Si hay más de un bosque, tenga en cuenta los detalles <br>en la columna comentarios. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ¿Qué se está utilizando para Active directory <br>¿sincronización de hoy en día? |<input type="checkbox">No hay sincronización (solo en la nube) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Conectar <br/> <input type="checkbox">Otros (especifique en el <br>&nbsp;&nbsp; &nbsp;Columna comentarios.)| |
> | ¿La identidad federada está implementada en este momento? <br/>(Servicios de federación de active Directory o <br>aplicaciones de terceros) | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Si usa la identidad federada, ¿cuál es el <br>¿infraestructura de federación? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federación de terceros <br>&nbsp;&nbsp; &nbsp;puerta de enlace <br>&nbsp;&nbsp; &nbsp;(Tenga en cuenta los detalles en el <br>&nbsp;&nbsp; &nbsp;Columna comentarios.) | |
> | Si mantiene actualmente un activo Office 365 <br>de inquilinos, es el dominio SMTP o SIP de su <br>¿usuarios de destino asociados con el inquilino? | <input type="checkbox">N/a – sin Office 365 <br>&nbsp;&nbsp; &nbsp;inquilino en contexto <br/> <input type="checkbox">No, SMTP o SIP los usuarios <br>&nbsp;&nbsp; &nbsp;dominio no está asociado <br>&nbsp;&nbsp; &nbsp;con cualquier inquilinos en <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Sí, SMTP o SIP los usuarios <br>&nbsp;&nbsp; &nbsp;dominio está asociado <br>&nbsp;&nbsp; &nbsp;con un inquilino existente <br>&nbsp;&nbsp; &nbsp;en Office 365 | |
> | ¿Usuario UPN coincide con su dirección SMTP principal? | <input type="checkbox">Sí <br/> <input type="checkbox">No <br/> <input type="checkbox">Forma incoherente | |

<a name="existing-collaboration-platform-summary"></a>Resumen de plataforma de colaboración existentes
---------------------------------------

Use la tabla siguiente para capturar la información acerca de la implementación de plataforma de colaboración existente.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Microsoft Teams está implementado? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Skype Empresarial está implementado? <br/>Para local y híbridos de las implementaciones, asegúrese de que <br>Tenga en cuenta la versión y la actualización acumulativa (CU) <br>obtener información detallada en la columna comentarios. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrida (con Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicada <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicada <br>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox">Sí, hospedado, compartida (terceros) <br/> <input type="checkbox">No, otros | |
> | ¿Exchange está implementado? <br/>Para local y híbridos de las implementaciones, asegúrese de que <br>Tenga en cuenta la versión y CU detalles en los comentarios <br>columna. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrida (con Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicada <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicada <br>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox">Sí, hospedado, compartidos <br>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox">No, otros | |
> | ¿SharePoint está implementado? <br/>Para local y híbridos de las implementaciones, asegúrese de que <br>Tenga en cuenta la versión y CU detalles en los comentarios <br>columna. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrida (con Office 365) <br/> <input type="checkbox">Sí, local <br/> <input type="checkbox">Sí, en línea, dedicada <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicada <br>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox">Sí, hospedado, compartidos <br>&nbsp;&nbsp; &nbsp;(terceros) <br/> <input type="checkbox">No, otros | |
> | ¿Es Office 365 OneDrive para la empresa implementa? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Tiene otras plataformas de terceros implementados <br>¿y en uso en la actualidad? Si es así, tenga en cuenta el número de usuarios de <br>estas plataformas y los detalles de uso en los comentarios <br>columna. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Margen de demora <br/> <input type="checkbox">Otros (especifique en los comentarios <br>&nbsp;&nbsp; &nbsp;columna.) | Número de usuarios: <br/>Detalles:|
> | Vaya a mover los usuarios desde estos productos de terceros <br>¿plataformas de los equipos? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Qué es la solución de telefonía y conferencias actual <br>¿de los usuarios que están en el ámbito de esta iniciativa? | | |
> | ¿Dispone de [SBC que admita el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) implementado para las oficinas que están en el ámbito de esta iniciativa? <br>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios.| <input type="checkbox">Sí <br/> <input type="checkbox">No ||

<a name="collaboration-platform-deployment-details"></a>Detalles de implementación de plataforma de colaboración
-----------------------------------------

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (si corresponde)

Si procede, capturar los detalles de la implementación de los equipos mediante el uso de la tabla de ejemplo que aparece a continuación. Si no ha implementado los equipos, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Qué tipos de usuarios están habilitados para Teams? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Grupos de usuarios o usuarios específicos <br>&nbsp;&nbsp; &nbsp;(Especifique en la columna comentarios) ||
> | ¿Qué características de los equipos y las modalidades están en uso? | <input type="checkbox">Conversaciones de canal <br/> <input type="checkbox">Chat privado <br/> <input type="checkbox">Acceso de invitado <br/> <input type="checkbox">Reuniones de canal <br/> <input type="checkbox">Conferencias privadas <br/> <input type="checkbox">Llamada privada <br/> <input type="checkbox">Meetup de canal ad hoc <br/> <input type="checkbox">Vídeos en las reuniones <br/> <input type="checkbox">Pantalla de uso compartido en reuniones <br/> <input type="checkbox">Conferencias de audio <br/><input type="checkbox">Aplicaciones (aplicaciones)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox"> Fichas<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Bots <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conectores<br><input type="checkbox">Integración de almacenamiento de información de nube personalizado <br>&nbsp;&nbsp; &nbsp; (Cuadro de lista desplegable, ShareFile, unidad de Google) <br/> <input type="checkbox">Integración de correo electrónico de canal <br/> <input type="checkbox">Otro (especifique en la columna comentarios). | |
> | ¿Qué aplicaciones han implementado para los equipos? | | |
> | ¿Ha bloqueado específicamente alguna funcionalidad de Teams? <br/>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No ||
> | ¿Qué clientes de Teams se están usando? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | ¿Quién tiene permiso para crear equipos? | <input type="checkbox">Todas las personas de la organización <br>&nbsp;&nbsp; &nbsp;(Es decir, la configuración predeterminada) <br/> <input type="checkbox">Personas específicas <br>&nbsp;&nbsp; &nbsp;(Especifique en la columna comentarios). | |
> | ¿Está usando características de seguridad y cumplimiento en Teams? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Empresarial Online (si corresponde)

Si procede, capturar los detalles de su Skype para la implementación empresarial en línea mediante el uso de la tabla de ejemplo que aparece a continuación. Si no ha implementado Skype para la implementación empresarial en línea, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Qué tipos de usuarios están habilitados para Skype <br>¿para la empresa en línea? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Grupos de usuarios o usuarios específicos <br>&nbsp;&nbsp; &nbsp;(Especifique en la columna comentarios) | |
> | ¿Qué modalidades y características están actualmente <br>¿en uso hoy en día? | <input type="checkbox">Mensajería instantánea y presencia (IM/P)<br/> <input type="checkbox">Conferencia <br/> <input type="checkbox">Federación <br/> <input type="checkbox">Grabación de la reunión <br/> <input type="checkbox">Conferencia de Audio de Microsoft <br/> <input type="checkbox">Conferencia de audio de terceros <br>&nbsp;&nbsp; &nbsp;(Tenga en cuenta los detalles en la columna comentarios). <br/> <input type="checkbox">Planes de llamada (anteriormente RTC de llamada) <br/> <input type="checkbox">Organizativa operadores automáticos <br/> <input type="checkbox">Colas de llamadas | |
> | Han bloqueado específicamente cualquier Skype para <br>¿Capacidades de negocio en línea? <br>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Qué método están usando o plan a usar para <br>conectar el sistema telefónico (anteriormente en la nube PBX) a <br>¿la RTC? <br/>Seleccione todos los que se aplican. | <input type="checkbox">Planes de llamada (anteriormente RTC de llamada) <br/> <input type="checkbox">Conectividad de RTC local (aprovechando los existentes <br>&nbsp;&nbsp; &nbsp;Skype para 2015 empresarial o Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;implementación) <br/> <input type="checkbox">Conectividad de RTC local (mediante el conector de la nube) | |
> | ¿Ha transferido algún número de teléfono a Microsoft? <br/>Esto es aplicable a una llamada a los planes y Audio <br>Características de conferencia. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype para la empresa local (si procede)

Si procede, capturar los detalles de su Skype para la implementación empresarial mediante el uso de la tabla de ejemplo que aparece a continuación. Si no ha implementado Skype para empresarial local, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Qué versiones de Lync o Skype para la empresa actualmente <br>¿están instalados en servidores locales? | <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype para Business Server 2015 <br/> <input type="checkbox">Skype para Business Server 2019 <input type="checkbox"> Skype para Business Edition de conector en la nube | |
> | ¿Está configurado el modo híbrido con Skype Empresarial Online? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Es este entorno hospedado y administrado por un tercero? <br/>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Las modalidades y las características que están actualmente en uso <br>¿hoy? | <input type="checkbox">Mensajería instantánea y presencia (IM/P) <br/> <input type="checkbox">Conferencia <br/> <input type="checkbox">Federación <br/> <input type="checkbox">Grabación de la reunión <br/> <input type="checkbox">Chat en grupo o grupos de Chat <br/> <input type="checkbox">Conferencia de Audio de Microsoft <br>&nbsp;&nbsp; &nbsp;(anteriormente de marcado en la conferencia) en su <br>&nbsp;&nbsp; &nbsp;Lync Server local o <br>&nbsp;&nbsp; &nbsp;Skype para la implementación empresarial <br/> <input type="checkbox">Conferencia de audio de terceros <br>&nbsp;&nbsp; &nbsp;(Tenga en cuenta los detalles en la columna comentarios) <br/> <input type="checkbox">Uso de Enterprise Voice local RTC <br>&nbsp;&nbsp; &nbsp;conectividad <br/> <input type="checkbox">Planes de llamada (anteriormente RTC de llamada) a través de <br>&nbsp;&nbsp; &nbsp;Híbrida con Skype para la empresa en línea | |
> | ¿Qué versiones del servidor perimetral ha implementado? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype para Business Server 2015 <br/> <input type="checkbox">Skype para Business Server 2019| |
> | ¿Tiene Lync o Skype para implementar el servidor perimetral empresarial <br>¿en más de un centro de datos? <br/>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Seleccione los servicios que su función perimetral proporciona hoy en día. | <input type="checkbox">Acceso de usuarios externos (usuarios corporativos) <br/> <input type="checkbox">Acceso de usuarios remotos (anónimo externo <br>&nbsp;&nbsp; &nbsp;los participantes de la reunión) <br/> <input type="checkbox">Federación <br/> <input type="checkbox">Transmisión de medios | |
> | ¿Cuál de la siguiente características de llamada de voz <br>¿actualmente tienen dependencias de? <br/>Tenga en cuenta las dependencias adicionales en los comentarios <br>columna. | <input type="checkbox">Opciones de disponibilidad <br/> <input type="checkbox">Estacionamiento de llamadas <br/> <input type="checkbox">Recogida de llamada o de respuesta de llamadas en grupo <br/> <input type="checkbox">Teléfonos de área común, o "hot desking" <br/> <input type="checkbox">Grupos de respuesta o grupos de extensiones <br/> <input type="checkbox">Apariencia de línea compartida <br/> <input type="checkbox">Línea privada <br/> <input type="checkbox">Correo de voz <br/> <input type="checkbox">Llamar vía trabajo <br/> <input type="checkbox">Números de emergencia o información <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">Marcado de extensión <br/> <input type="checkbox">Operador automático <br/> <input type="checkbox">Acceso de suscriptor <br/> <input type="checkbox">Dispositivos analógicos <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Alterar o máscaras de identificador de autor de la llamada <br/> <input type="checkbox">Enrutamiento basado en la ubicación <br/> <input type="checkbox">Enrutamiento de menor costo <br/> <input type="checkbox">Teléfonos breve | |

<a name="networking-and-access-to-office-365-services"></a>Redes y acceso a servicios de Office 365
--------------------------------------------

Use la tabla siguiente para capturar los detalles de la red de su organización y cómo los usuarios están (o será) conectado a servicios de Office 365.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Cómo (o cómo va a) los usuarios en el ámbito de migración <br>¿obtener acceso a los equipos cuando estén en la oficina? <br/>Seleccione todos los que se aplican. | <input type="checkbox">Conexión de NAT enrutada <br/> <input type="checkbox">Servidor proxy <br/> <input type="checkbox">Wi-Fi pública <br/> <input type="checkbox">Administrada (no pública) Wi-Fi <br/> <input type="checkbox">ExpressRoute (interconexión de Microsoft) ||
> | Si el acceso a Office 365 es a través de un servidor proxy, ¿existe <br>¿cualquier forma de utilizar al servidor proxy? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿ExpressRoute se está usando? | <input type="checkbox">Sí <br/> <input type="checkbox">No <br/> <input type="checkbox">No, pero se ha planeado | |
> | ¿Ha realizado una evaluación de preparación de la red? <br/>Para obtener más información, vea [Evaluación de preparación de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness). | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Son necesarios para usar una red privada virtual cuando se conecta a usuarios <br>¿recursos corporativos forma remota? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Si se utiliza una VPN, el tráfico de los equipos se puede excluir de <br>¿VPN para tener acceso a servicios de Office 365 directamente? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Su red admite QoS? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Puede priorizar el tráfico de audio y vídeo de los equipos <br>¿para una experiencia de calidad de la unidad? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Es necesario de todas las ubicaciones dentro de un área de salida de internet, <br>¿o bien, está centralizada de salida de internet para toda la región? | <input type="checkbox">Regional acceso a internet <br/> <input type="checkbox">Acceso centralizado a internet | |

> [!TIP]
> Para calcular la cantidad de ancho de banda y otros requisitos de red para la voz en la nube implementación, dependiendo de su organización detalles y uso estimado, visite el [Organizador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) en [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).

<a name="endpoints"></a>Puntos de conexión
---------

Use la tabla siguiente para capturar los detalles de los clientes y los extremos en uso.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Qué sistema operativo de escritorio están empleando los usuarios? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">10 de Windows <br/> <input type="checkbox">Mac (especificar la versión en la columna comentarios). <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | ¿Qué versión de Microsoft Office se implementa <br>¿para estos dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | Qué tecnología de implementación de Office está en uso <br>¿en su organización? | <input type="checkbox">MSI <br/> <input type="checkbox">Click-to-Run | |
> | ¿Cuáles son los permitidos y admiten móviles <br>¿plataformas en uso? <br/>Seleccione todos los que se aplican. | <input type="checkbox">Windows <br/> <input type="checkbox"> Móvil <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Otros (tenga en cuenta los detalles en la columna comentarios). | |
> | ¿Cómo se proporcionan los dispositivos móviles <br/>Seleccione todos los que se aplican. | <input type="checkbox">Dispositivos corporativos <br/> <input type="checkbox">Traer su propio dispositivo | |
> | ¿Qué dispositivos lo hacen los usuarios actualmente se usa para tener acceso a <br>Servicios de voz y conferencia <br>¿(los auriculares, auriculares, teléfonos, vídeo)? | | |

<a name="operations"></a>Operaciones
----------

Use la tabla siguiente para capturar los detalles de los aspectos operativos de su entorno.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Cuál es su modelo de operaciones para el servidor de Lync <br>Skype para Business Server o la implementación de Office 365 <br>¿hoy? | | |
> | Puede describir la organización de soporte técnico actual para <br>¿Lync Server, Skype para Business Server o Office 365? | | |
> | Si va a implementar en varios países o regiones, <br>¿cada país o región tiene su propia TI y telefonía <br>para que funcione con el personal o se Esto se administran de forma centralizada? | <input type="checkbox">Soporte técnico y operaciones regionales <br/> <input type="checkbox">Soporte técnico y operaciones centralizadas | |
> | ¿Está siguiendo la metodología de calidad de llamada? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Ha asignado un individuo o equipo a la <br>Rol de campeones de calidad para la plataforma de colaboración <br>¿en uso? | <input type="checkbox">Sí <br/> <input type="checkbox">No ||
> | Cómo supervisar el servidor de Lync, Skype para <br>¿Business Server u Office 365 implementación? | | |
> | ¿Tiene problemas relacionados con la calidad de las llamadas? | <input type="checkbox">Sí<br/> <input type="checkbox">No | |
> | Cómo y cuándo proporcionar recursos de aprendizaje a su <br>¿departamento de soporte técnico en nuevas capacidades y servicios? | | |

<a name="adoption-and-readiness"></a>Preparación y adopción
----------------------

Con la siguiente tabla, capture el estado actual de la adopción y el nivel de preparación de su organización.

> 
> |                                                    Pregunta                                                     |                                                                                                                                                                                                                                                                                      Respuesta                                                                                                                                                                                                                                                                                      | Comentarios |
> |-----------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
> |                          ¿Cuál es su uso activo actual de <br>¿Skype para la empresa?                           |                                                                                                                                                                                                                                                                 usuarios activos de **__** % total frente a usuarios habilitados                                                                                                                                                                                                                                                                 |          |
> |                             Cómo usa la organización <br>¿Skype para la empresa?                              |                                                                                                   Conversaciones uno a uno <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Mensajería instantánea <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De llamada <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De uso compartido<br> Reuniones. <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conferencia<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De uso compartido<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De llamada                                                                                                   |          |
> |                   ¿Su organización tiene una adopción de usuario <br>¿y el equipo de administración de cambios?                   |                                                                                                                                                                                                                                                           <input type="checkbox">Sí<br/> <input type="checkbox">No                                                                                                                                                                                                                                                            |          |
> |            ¿Cómo actualmente medir el éxito de tecnología <br>¿implantaciones como Skype para la empresa?            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |          |
> |               ¿Qué porcentaje de su base de usuarios diría que tiene <br>¿adoptadas Skype para la empresa?               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |          |
> |                                ¿Cuál es la sensación de los usuarios en torno a Skype Empresarial?                                |                                                                                                                                                                                                                                       <input type="checkbox">Buena <br/> <input type="checkbox">Independiente del <br/> <input type="checkbox">Incorrecta                                                                                                                                                                                                                                       |          |
> | Cuál de las siguientes describe mejor la implantación <br>estrategia utilizada para su Skype para la empresa <br>¿implementación? | <input type="checkbox">Mayor alcance: campaña con un correo electrónico <br>&nbsp;&nbsp; &nbsp;vínculos a recursos de aprendizaje <br/> <input type="checkbox">Ampliado: Mayor alcance además una gran variedad <br>&nbsp;&nbsp; &nbsp;de campañas de sensibilización (Pósteres, <br>&nbsp;&nbsp; &nbsp;eventos, Campeones) y recursos de aprendizaje <br>&nbsp;&nbsp; &nbsp;(vídeos, guías de usuario, en persona) <br/> <input type="checkbox">Adaptadas: Expandida, además de destino <br>&nbsp;&nbsp; &nbsp;de mensajería y recursos de aprendizaje por rol <br/> <input type="checkbox">Otros <br>&nbsp;&nbsp; &nbsp;(Tenga en cuenta los detalles en la columna comentarios). |          |
