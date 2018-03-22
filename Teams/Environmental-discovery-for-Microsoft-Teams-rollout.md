---
title: Descubrimientos del entorno para el lanzamiento de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Cómo realizar un descubrimiento detallado ambiental al planear su viaje de Skype para empresas a Teams de Microsoft.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5fde916c4fe9ece9ad80ec63dad1618fa0d1ae5
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Descubrimientos del entorno para el lanzamiento de Microsoft Teams
===================================================

Descubrimiento es uno de los pasos clave, primeros que tomar al planear para su viaje a la Teams de Microsoft.

Realizar un descubrimiento detallado de su entorno para comprender mejor su estado actual y revelar las dificultades o — aún más — posibles obstáculos para la ejecución de la implementación de equipos.

<a name="discovery-questionnaire"></a>Cuestionario de la detección
=======================

El cuestionario de ejemplo siguiente recorre una serie de preguntas para confirmar que su organización está preparada para la ejecución correcta de las conferencias de Audio y sistema de teléfono con planes de llamar a funciones en los equipos.

Todos los asuntos relacionados con su existente infraestructura de colaboración y Office 365 inquilinos, redes, extremos, operaciones y adopción y preparación se incluyen como parte del cuestionario descubrimientos del entorno.

El cuestionario se divide en varias secciones para confirmar la preparación de su organización para la implementación de equipos en diversas áreas importantes. Trabaje con su equipo de proyecto para proporcionar la información solicitada con tantos detalles como sea posible para facilitar las actividades de planificación.

> [!TIP]
> Puede iniciar copiando el cuestionario en un documento de Microsoft Word. Intente responder todas las preguntas y capturar todos los detalles según avanza.

<a name="project-team"></a>Equipo del proyecto
------------

Capturar información detallada sobre los aspectos principales de su proyecto de despliegue de equipos. Tenga en cuenta que una persona puede desempeñar varias funciones durante todo el proyecto.

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
> | Clientes potenciales de la unidad de negocio                   |                                   |                     |               |

<a name="office-365-tenant-details"></a>Detalles de inquilinos de Office 365
-------------------------

Recomendamos tener un arrendatario Office 365 activo mientras trabaja con este cuestionario. Si no ha activado o configurado aún un arrendatario de Office 365, vea [Planear la instalación de Office 365 para el negocio](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Utilice la siguiente tabla para capturar información acerca de los inquilinos de Office 365.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Tenga en cuenta al inquilino producción Office 365 <br>nombre y el identificador de la columna respuesta <br/>Si tiene más de un arrendatario <br>asociado con su organización, <br>Tenga en cuenta todos los identificadores.  | Nombre del inquilino: <br/>Id. de inquilinos:| |
> | ¿En qué regiones se implementan los inquilinos?| | |
> | Son estos los inquilinos Office 365 multiempresa o <br>¿Dedicado? | <input type="checkbox">Multiempresa<br/> <input type="checkbox">Dedicado | |
> | ¿Qué productos de Microsoft Online se están usando? <br/>Anote el número de usuarios habilitados para cada <br>servicio en la columna comentarios. | <input type="checkbox">Equipos de Microsoft <br/> <input type="checkbox">Skype para empresas <br>&nbsp;&nbsp; &nbsp;En línea <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive para el negocio <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Otros|                                   |
> | ¿Qué nivel de licencia está habilitado para Skype para <br>¿Usuarios de negocio en línea? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E5 E4/G4 | El número de usuarios <br>para cada SKU: |
> | ¿Qué es el bosque de Active Directory actual <br>¿nivel funcional en el entorno? <br/>Si hay más de un bosque, tenga en cuenta los detalles <br>en la columna comentarios. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">R2 de Windows Server 2012 <br/> <input type="checkbox">Windows Server 2016| |
> | ¿Qué se está utilizando para directorio <br>¿sincronización de hoy? |<input type="checkbox">No hay sincronización (sólo nube) <br/> <input type="checkbox">Active Directory Azure <br>&nbsp;&nbsp; &nbsp;Conectar <br/> <input type="checkbox">Otros (especifique en el <br>&nbsp;&nbsp; &nbsp;Columna comentarios.)| |
> | ¿La identidad federada está implementada en este momento? <br/>(Servicios de federación de active Directory o <br>aplicaciones de terceros) | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Si utilizas una identidad federada, ¿cuál es el <br>¿infraestructura de federación? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federación de terceros <br>&nbsp;&nbsp; &nbsp;puerta de enlace <br>&nbsp;&nbsp; &nbsp;(Observe los detalles en el <br>&nbsp;&nbsp; &nbsp;Columna comentarios.) | |
> | Si mantiene actualmente una activa Office 365 <br>de inquilinos, es el dominio SMTP/SIP de su <br>¿usuarios de destino asociados con el inquilino? | <input type="checkbox">N/D: no hay Office 365 <br>&nbsp;&nbsp; &nbsp;arrendatario en lugar <br/> <input type="checkbox">No, SMTP/SIP los usuarios <br>&nbsp;&nbsp; &nbsp;dominio no está asociado <br>&nbsp;&nbsp; &nbsp;con los inquilinos en <br>&nbsp;&nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Sí, SMTP/SIP los usuarios <br>&nbsp;&nbsp; &nbsp;dominio está asociado <br>&nbsp;&nbsp; &nbsp;con un arrendatario existente <br>&nbsp;&nbsp; &nbsp;en Office 365 | |
> | ¿Usuario UPN coincide con su dirección SMTP principal? | <input type="checkbox">Sí <br/> <input type="checkbox">No <br/> <input type="checkbox">Forma incoherente | |

<a name="existing-collaboration-platform-summary"></a>Resumen de plataforma de colaboración existente
---------------------------------------

Utilice la siguiente tabla para capturar información acerca de la implementación de plataforma de colaboración existente.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Microsoft Teams está implementado? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Skype Empresarial está implementado? <br/>Para los híbridos y locales de las implementaciones, asegúrese de que <br>Anote la versión y la actualización acumulativa (CU) <br>detalles en la columna comentarios. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrido (con Office 365) <br/> <input type="checkbox">Sí, locales <br/> <input type="checkbox">Sí, en línea, dedicada <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicada <br>&nbsp;&nbsp; &nbsp;(tercera parte) <br/> <input type="checkbox">Sí, alojado, compartida (tercera parte) <br/> <input type="checkbox">No, el otro | |
> | ¿Exchange está implementado? <br/>Para los híbridos y locales de las implementaciones, asegúrese de que <br>Anote la versión y detalles CU en los comentarios <br>columna. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrido (con Office 365) <br/> <input type="checkbox">Sí, locales <br/> <input type="checkbox">Sí, en línea, dedicada <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicada <br>&nbsp;&nbsp; &nbsp;(tercera parte) <br/> <input type="checkbox">Sí, hospedado, compartidos <br>&nbsp;&nbsp; &nbsp;(tercera parte) <br/> <input type="checkbox">No, el otro | |
> | ¿SharePoint está implementado? <br/>Para los híbridos y locales de las implementaciones, asegúrese de que <br>Anote la versión y detalles CU en los comentarios <br>columna. | <input type="checkbox">Sí, Office 365 <br/> <input type="checkbox">Sí, híbrido (con Office 365) <br/> <input type="checkbox">Sí, locales <br/> <input type="checkbox">Sí, en línea, dedicada <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sí, hospedado, dedicada <br>&nbsp;&nbsp; &nbsp;(tercera parte) <br/> <input type="checkbox">Sí, hospedado, compartidos <br>&nbsp;&nbsp; &nbsp;(tercera parte) <br/> <input type="checkbox">No, el otro | |
> | ¿Es OneDrive de Office 365 para el negocio implementar? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Tienes otras plataformas de terceros implementados <br>¿y en uso hoy en día? Si es así, tenga en cuenta el número de usuarios de <br>estas plataformas y los detalles de uso en los comentarios <br>columna. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Margen de demora <br/> <input type="checkbox">Otros (especifique en los comentarios <br>&nbsp;&nbsp; &nbsp;columna.) | Número de usuarios: <br/>Detalles:|
> | Va a mover los usuarios de estos productos de terceros <br>¿plataformas de equipos? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Cuál es la solución actual de telefonía y conferencias <br>¿los usuarios que están en el ámbito de esta iniciativa? | | |

<a name="collaboration-platform-deployment-details"></a>Detalles de implementación de plataforma de colaboración
-----------------------------------------

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (si corresponde)

Si procede, capturar los detalles de la implementación de los equipos mediante la tabla de ejemplo siguiente. Si no ha implementado equipos, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Qué tipos de usuarios están habilitados para Teams? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Grupos de usuarios específicos <br>&nbsp;&nbsp; &nbsp;(Especificar en la columna comentarios) ||
> | ¿Las características de los equipos y las modalidades están en uso? | <input type="checkbox">Conversaciones de canal <br/> <input type="checkbox">Chat privado <br/> <input type="checkbox">Acceso como invitado <br/> <input type="checkbox">Reuniones de canal <br/> <input type="checkbox">Reuniones privadas <br/> <input type="checkbox">Llamada privada <br/> <input type="checkbox">Meetup de canal ad hoc <br/> <input type="checkbox">Vídeos de reuniones <br/> <input type="checkbox">Pantalla compartida en reuniones <br/> <input type="checkbox">Conferencia de audio <br/><input type="checkbox">Aplicaciones (aplicaciones)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox"> Fichas<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Robots <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conectores<br><input type="checkbox">Integración de almacenamiento de nube personalizados <br>&nbsp;&nbsp; &nbsp; (Cuadro, Dropbox, ShareFile, unidad de Google) <br/> <input type="checkbox">Integración de correo electrónico de canal <br/> <input type="checkbox">Otro (especifique en la columna comentarios.) | |
> | ¿Qué aplicaciones han implementado en los equipos? | | |
> | ¿Ha bloqueado específicamente alguna funcionalidad de Teams? <br/>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No ||
> | ¿Qué clientes de Teams se están usando? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | ¿Quién tiene permiso para crear equipos? | <input type="checkbox">Todos los miembros de la organización <br>&nbsp;&nbsp; &nbsp;(Es decir, la configuración predeterminada) <br/> <input type="checkbox">Personas determinadas <br>&nbsp;&nbsp; &nbsp;(Especificar en la columna comentarios.) | |
> | ¿Está usando características de seguridad y cumplimiento en Teams? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Empresarial Online (si corresponde)

Si procede, capturar los detalles de tu Skype para la implementación de los negocios en línea utilizando la siguiente tabla de ejemplo. Si no ha implementado Skype para la implementación de los negocios en línea, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Los tipos de usuarios están habilitados para Skype <br>¿para el negocio en línea? | <input type="checkbox">Todos los usuarios de la organización <br/> <input type="checkbox">Grupos de usuarios específicos <br>&nbsp;&nbsp; &nbsp;(Especificar en la columna comentarios) | |
> | Las modalidades y características son qué actualmente <br>¿en uso hoy en día? | <input type="checkbox">Mensajería instantánea y presencia (IM/P)<br/> <input type="checkbox">Conferencia <br/> <input type="checkbox">Federación <br/> <input type="checkbox">Grabación de la reunión <br/> <input type="checkbox">Conferencia de Audio de Microsoft <br/> <input type="checkbox">Conferencia de audio de terceros <br>&nbsp;&nbsp; &nbsp;(Observe los detalles en la columna comentarios.) <br/> <input type="checkbox">Planes de llamada (PSTN anteriormente llamada) <br/> <input type="checkbox">Operadores automáticos organizativa <br/> <input type="checkbox">Colas de llamada | |
> | Han bloqueado específicamente cualquier Skype para <br>¿Capacidades de negocio en línea? <br>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Qué método están utilizando o planea usar para <br>conectar el sistema de teléfono (anteriormente nube PBX) a <br>¿la RTC? <br/>Seleccione todas las que correspondan. | <input type="checkbox">Planes de llamada (PSTN anteriormente llamada) <br/> <input type="checkbox">Conectividad de RTC local (aprovechando existente <br>&nbsp;&nbsp; &nbsp;Skype para negocios 2015 o 2013 de Lync Server <br>&nbsp;&nbsp; &nbsp;implementación) <br/> <input type="checkbox">Conectividad de RTC local (mediante el conector de nube) | |
> | ¿Ha transferido algún número de teléfono a Microsoft? <br/>Esto es aplicable a los planes de llamada y el Audio <br>Características de las conferencias. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype para empresas locales (si procede)

Si procede, capturar los detalles de tu Skype para la implementación de negocios mediante el uso de la tabla de ejemplo siguiente. Si no ha implementado Skype para negocios locales, omita esta sección.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Qué versiones de Lync o Skype para empresas actualmente <br>¿están implementados en locales? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">2013 de Lync Server <br/> <input type="checkbox">Skype para Business Server 2015 <br/> <input type="checkbox">Skype para conector de nube Business Edition | |
> | ¿Está configurado el modo híbrido con Skype Empresarial Online? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Es este entorno hospedado y administrado por un tercero? <br/>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Qué modalidades y características que están actualmente en uso <br>¿hoy en día? | <input type="checkbox">Mensajería instantánea y presencia (IM/P) <br/> <input type="checkbox">Conferencia <br/> <input type="checkbox">Federación <br/> <input type="checkbox">Grabación de la reunión <br/> <input type="checkbox">Persistente Chat o charla de grupo <br/> <input type="checkbox">Conferencia de Audio de Microsoft <br>&nbsp;&nbsp; &nbsp;(Dial anteriormente en la conferencia) en su <br>&nbsp;&nbsp; &nbsp;Lync Server local o <br>&nbsp;&nbsp; &nbsp;Skype para implementación en la empresa <br/> <input type="checkbox">Conferencia de audio de terceros <br>&nbsp;&nbsp; &nbsp;(Observe los detalles en la columna comentarios) <br/> <input type="checkbox">Uso de la Telefonía IP empresarial local PSTN <br>&nbsp;&nbsp; &nbsp;conectividad <br/> <input type="checkbox">Planes de llamada (anteriormente PSTN llamar) a través de <br>&nbsp;&nbsp; &nbsp;Híbrido con Skype para el negocio en línea | |
> | ¿Qué versiones del servidor perimetral ha implementado? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">2013 de Lync Server <br/> <input type="checkbox">Skype para Business Server 2015 | |
> | ¿Tienes Lync o Skype para borde de negocio implementado <br>¿en más de un centro de datos? <br/>En caso afirmativo, tenga en cuenta los detalles en la columna comentarios. | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Seleccione los servicios que su función perimetral proporciona hoy. | <input type="checkbox">Acceso de usuarios externos (usuarios corporativos) <br/> <input type="checkbox">Acceso de usuarios remotos (anónimo externo <br>&nbsp;&nbsp; &nbsp;participantes de la reunión) <br/> <input type="checkbox">Federación <br/> <input type="checkbox">Transmisión de medios | |
> | ¿Cuál de la siguiente voz llamar a funciones <br>¿actualmente tiene dependencias en? <br/>Tenga en cuenta las dependencias adicionales en los comentarios <br>columna. | <input type="checkbox">Opciones de disponibilidad <br/> <input type="checkbox">Parque de llamada <br/> <input type="checkbox">Llame a la recolección o recogida de llamada de grupo <br/> <input type="checkbox">Teléfonos de área común o "hot desking" <br/> <input type="checkbox">Grupos de respuesta o de grupos de captura <br/> <input type="checkbox">Apariencia de línea compartida <br/> <input type="checkbox">Línea privada <br/> <input type="checkbox">Correo de voz <br/> <input type="checkbox">Llamada mediante el trabajo <br/> <input type="checkbox">Números de emergencia o información <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">Marcado de extensión <br/> <input type="checkbox">Operador automático <br/> <input type="checkbox">Acceso de suscriptor <br/> <input type="checkbox">Dispositivos analógicos <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Enmascaramiento de ID de llamador o alterar <br/> <input type="checkbox">Enrutamiento basado en la ubicación <br/> <input type="checkbox">Enrutamiento de menor costo <br/> <input type="checkbox">Teléfonos de ascensor | |

<a name="networking-and-access-to-office-365-services"></a>Redes y acceso a los servicios de Office 365
--------------------------------------------

Utilice la siguiente tabla para capturar los detalles de la red de su organización y cómo los usuarios (o será) conectada a los servicios de Office 365.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Cómo (o cómo) los usuarios en el ámbito de la migración <br>¿tener acceso a los equipos cuando estén en la oficina? <br/>Seleccione todas las que correspondan. | <input type="checkbox">Conexión enrutada de NAT <br/> <input type="checkbox">Servidor proxy <br/> <input type="checkbox">Wi-Fi pública <br/> <input type="checkbox">Administrado (no pública) Wi-Fi <br/> <input type="checkbox">ExpressRoute (interconexión de Microsoft) ||
> | Si el acceso a Office 365 es a través de un servidor proxy, está allí <br>¿cualquier forma de utilizar al servidor proxy? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿ExpressRoute se está usando? | <input type="checkbox">Sí <br/> <input type="checkbox">No <br/> <input type="checkbox">No, pero se está planeando | |
> | ¿Ha realizado una evaluación de disponibilidad de la red? <br/>Para obtener más información, vea [Evaluación de disponibilidad de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness). | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Son los usuarios deben utilizar una VPN para conectarse a <br>¿recursos corporativos remotamente? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Si se utiliza una VPN, el tráfico de equipos se puede excluir de <br>¿la conexión VPN para tener acceso a los servicios de Office 365 directamente? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Su red admite QoS? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Puede priorizar tráfico de audio y vídeo de equipos <br>¿para una experiencia de calidad de la unidad? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | ¿Todas las ubicaciones dentro de una región tiene salida de internet, <br>¿o se centraliza la salida de internet para toda la región? | <input type="checkbox">Regional acceso a internet <br/> <input type="checkbox">Acceso centralizado a internet | |

> [!TIP]
> Para calcular la cantidad de ancho de banda y otros requisitos de red para su voz de nube implementación, dependiendo de su organización detalles y uso estimado, visite [Planificador de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) en [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).

<a name="endpoints"></a>Puntos de conexión
---------

Utilice la siguiente tabla para capturar los detalles de los clientes y los extremos en uso.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Qué sistema operativo de escritorio están empleando los usuarios? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">10 de Windows <br/> <input type="checkbox">Mac (especificar la versión en la columna comentarios.) <br/> <input type="checkbox">Otros (Observe los detalles en la columna comentarios.) | |
> | ¿Qué versión de Microsoft Office se implementa <br>¿en estos dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Oficina de 2013 <br/> <input type="checkbox">Oficina de 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox">Otros (Observe los detalles en la columna comentarios.) | |
> | La tecnología de implementación de Office está en uso <br>¿en su organización? | <input type="checkbox">MSI <br/> <input type="checkbox">Hacer clic para ejecutar | |
> | ¿Cuáles son los permitidos y admiten móviles <br>¿plataformas en uso? <br/>Seleccione todas las que correspondan. | <input type="checkbox">Windows <br/> <input type="checkbox"> Móvil <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Otros (Observe los detalles en la columna comentarios.) | |
> | ¿Cómo se proporcionan los dispositivos móviles <br/>Seleccione todas las que correspondan. | <input type="checkbox">A la empresa <br/> <input type="checkbox">Traiga su propio dispositivo | |
> | ¿Qué dispositivos lo hacen los usuarios actualmente para acceder a <br>conferencias de voz y servicios <br>¿(teléfonos móviles, auriculares, teléfonos, vídeo)? | | |

<a name="operations"></a>Operaciones
----------

Utilice la siguiente tabla para capturar los detalles de los aspectos operacionales de su entorno.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Cuál es su modelo de operaciones para el servidor de Lync <br>Skype para Business Server o la implementación de Office 365 <br>¿hoy en día? | | |
> | Puede describir la organización de soporte actual para <br>¿Lync Server, Skype para Business Server o Office 365? | | |
> | Si está implementando en varios países o regiones, <br>cada país o región tiene su propia TI / telefonía <br>para trabajar con el personal o se administrará centralmente? | <input type="checkbox">Soporte técnico y operaciones regionales <br/> <input type="checkbox">Soporte y centralizar las operaciones | |
> | ¿Está siguiendo la metodología de calidad de llamada? | <input type="checkbox">Sí <br/> <input type="checkbox">No | |
> | Ha asignado un individuo o grupo a la <br>Función Champion de calidad para la plataforma de colaboración <br>¿en uso? | <input type="checkbox">Sí <br/> <input type="checkbox">No ||
> | Cómo supervisar el servidor de Lync, Skype para <br>¿Business Server o Office 365 implementación? | | |
> | ¿Tiene problemas relacionados con la calidad de las llamadas? | <input type="checkbox">Sí<br/> <input type="checkbox">No | |
> | Cómo y cuándo proporcionar formación a su <br>¿asistencia técnica en nuevas capacidades y servicios? | | |

<a name="adoption-and-readiness"></a>Preparación y aprobación
----------------------

Con la siguiente tabla, capture el estado actual de la adopción y el nivel de preparación de su organización.

> | Pregunta | Respuesta | Comentarios |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | ¿Cuál es su uso actual activado de <br>¿Skype para el negocio? | ___ % total usuarios activos frente a los usuarios habilitados | |
> | Cómo utiliza la organización <br>¿Skype para el negocio? | Conversaciones uno a uno <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Llamar a <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Compartir<br> Reuniones. <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conferencia<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Compartir<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Llamar a| |
> | ¿Su organización tiene una adopción del usuario <br>¿y el equipo de administración de cambios? | <input type="checkbox">Sí<br/> <input type="checkbox">No | |
> | ¿Cómo actualmente medir el éxito de la tecnología <br>¿implementaciones como Skype para el negocio? | | |
> | ¿Qué porcentaje de su base de usuarios diría que tiene <br>¿adoptado Skype para el negocio? | | |
> | ¿Cuál es la sensación de los usuarios en torno a Skype Empresarial? | <input type="checkbox">Buena <br/> <input type="checkbox">Punto muerto <br/> <input type="checkbox">Mala | |
> | Cuál de las siguientes describe mejor la puesta en servicio <br>estrategia utilizada para su Skype para empresas <br>¿implementación? | <input type="checkbox">Mayor alcance: correo electrónico de campaña con <br>&nbsp;&nbsp; &nbsp;enlaces a formación <br/> <input type="checkbox">Expandido: Amplio alcance más una variedad <br>&nbsp;&nbsp; &nbsp;de campañas de sensibilización (pósters, <br>&nbsp;&nbsp; &nbsp;eventos, champions) y formación <br>&nbsp;&nbsp; &nbsp;(vídeos, guías de usuario, en persona) <br/> <input type="checkbox">Adaptados: Expandido, además de destino <br>&nbsp;&nbsp; &nbsp;mensajería y formación por persona <br/> <input type="checkbox">Otros <br>&nbsp;&nbsp; &nbsp;(Observe los detalles en la columna comentarios.) | |