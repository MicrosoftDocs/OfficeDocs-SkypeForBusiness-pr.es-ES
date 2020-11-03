---
title: Centro de contactos de Teams
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: Información general de la solución centro de contacto integrado como servicio (CCaaS) para Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fb65edc260c5a91ee51a32c6c3796e2773ba179
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827744"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Integraciones del centro de contactos para Microsoft Teams

La integración de las soluciones más populares del centro de contactos con Microsoft Teams es una necesidad común para los clientes que implementan las capacidades de llamadas de equipos.  Este artículo proporciona una descripción general de cómo se pueden integrar las soluciones del centro de contactos con Microsoft Teams y información adicional sobre las soluciones de socios que participan en el programa de certificación Connected Contact Center de Microsoft Teams.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>¿Qué es una integración de centro de contactos para Microsoft Teams?

Los centros de contacto de hoy en día proporcionan mucho más que el soporte técnico, actúan como uno de los principales vehículos para la interacción y la retroalimentación no filtrada sobre la experiencia del cliente con una marca. Debido a la amplitud de los canales que los clientes actuales prefieren para comunicarse: por teléfono, correo electrónico, texto, social, y por el volumen ampliado de puntos táctiles relacionados con los procesos de compra del día actual, muchas organizaciones han realizado dos actividades adicionales:

1. Cada miembro de la organización tiene el potencial de involucrarse en la participación de un cliente directamente y, por lo tanto, debe estar equipado con las herramientas apropiadas.

2. Este ámbito ampliado de interacciones con el cliente requiere herramientas que puedan ayudar a impulsar la coherencia, la mejora constante y la escala.

Microsoft Teams es compatible con las secuencias de trabajo de interacción con el cliente actuando como hub para la conexión de clientes internos y externos a través de sus modos de comunicación, como chat, videoconferencias y llamadas. Para algunas empresas, las capacidades de [voz en la nube](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)de Microsoft Teams, incluidos el [operador automático](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) y las [colas de llamadas](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue), proporcionan las características y la configuración para satisfacer sus necesidades.

Para otras personas que deseen soluciones integradas con el flujo de trabajo y las herramientas empresariales para impulsar el camino de los clientes, Microsoft Teams también se integra con algunos de los proveedores líderes de contactos de la industria como proveedores de soluciones de servicio (CCaaS).

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Centro de contacto conectado para el programa de certificación de Microsoft Teams

Las API permiten a los socios desarrollar e integrar soluciones de CCaaS para Teams. Además, hemos desarrollado el centro de contactos conectado para el programa de certificación de Microsoft Teams a fin de ofrecer a los clientes la seguridad de que la solución de cada socio participante ha sido probada y verificada para proporcionar la calidad, la compatibilidad y la confiabilidad que esperan de las soluciones de Microsoft.

Los siguientes socios están en el proceso de certificar su solución para Microsoft Teams y están listos para participar en los clientes:

|  Servidor                                                                                                                               |  Sitio web de soluciones                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Anywhere365 | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| Competella | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| ComputerTalk | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| ContactCenter4All | www.contactcenter4all.com |
| Enghouse interactivo | http://www.enghouseteams.com/                                                       |
| Five9 | https://www.five9.com/products/application-integration/uc-integration                                                   |
| Genes | https://www.genesys.com/microsoft                                                                                   |
| Tecnologías de Landis | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| Luware | https://luware.com/en/solutions/                                                                                       |
| BONITO contacto | https://www.niceincontact.com/microsoft-teams                                                            |
| Novomind | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| Tendfor | https://www.tendfor.com/en/                                                                                     |

Esta lista se actualizará a medida que se unan más socios y cumplan los criterios de certificación.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>¿Cómo funcionan las soluciones de centro de contactos en Microsoft Teams?

Microsoft Teams ofrece una variedad de capacidades para admitir el desarrollo de soluciones de voz de terceros, entre las que se incluyen:

1. [Conectividad de enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [API de comunicación en la nube de Microsoft Graph](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Plataforma y extensibilidad de Teams

4. SDK de Teams

Juntas, estas capacidades permiten tres modelos de integración:

  - **Conectar** (mediante enrutamiento directo)

  - **Conectar y extender** (enrutamiento directo, API de Graph y plataforma de aplicaciones de Teams)

  - **Ampliar y apagar** (incrustar los SDK de Teams en aplicaciones 3P para interacciones de equipos nativos)

### <a name="connect"></a>Vuelve

Este modelo conecta a socios de CCaaS con Microsoft Teams, infraestructura de sistemas telefónicos, lo que permite mejorar el enrutamiento, la configuración y la visión del sistema. En este modelo, la solución de socio del centro de contacto también puede proporcionar servicios de telefonía para números y usuarios seleccionados.

Los agentes que usan soluciones integradas en el modelo de conexión pueden recopilar información & Insights y, si es necesario, transferir llamadas a expertos en el tema directamente, aprovechando la presencia de SME en Teams para garantizar su disponibilidad.

Las organizaciones pueden asegurarse de que las llamadas se dirigen al agente óptimo al configurar ayudantes virtuales automatizadas y colas de enrutamiento basadas en habilidades.

**Características destacadas:**

Aunque la siguiente no es una lista completa de características de la característica para este modelo de integración, las áreas de interés son:

  - Office 365 authn para agentes para que los agentes puedan conectarse a su inquilino de Microsoft desde su cliente de CCaaS integrado 

  - Indicación de presencia de los usuarios de Teams 

  - Flujos de llamadas mediante enrutamiento directo (según se indica en los planes de prueba) 

  - Soporte técnico de transferencias y llamadas grupales con usuarios de Teams 

  - Las API de Graph y las API de comunicación en la nube para la integración con Teams 

  - Capaz de admitir el Troncalización SIP de varios inquilinos para admitir varios clientes en la SBC del socio.  

  - Partners para implementar el [ <span class="underline">controlador de borde de sesión (SBC) Microsoft Certified Session</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Conectar y extender

Este modelo amplía el personal del centro de contacto y las experiencias del agente al integrarse con el cliente de Teams mediante la [plataforma de cliente de Teams](https://docs.microsoft.com/microsoftteams/platform/overview), las API de [Team Graph](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) y la [API de comunicaciones en la nube en Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) , y usa el sistema telefónico de Teams para todas las llamadas del centro de contactos y las experiencias de control En este modelo, el socio del centro de contactos actúa como una portadora de telefonía junto con Microsoft 365.

Al aprovechar las soluciones basadas en Connect y Extend, los agentes pueden beneficiarse de notas contextuales dinámicas que correlacionan datos de varios sistemas antes de iniciar una negociación y, a continuación, evitar el costoso cambio de contexto al trabajar de forma nativa dentro de equipos para la colaboración interna y las comunicaciones externas.

Las organizaciones pueden diseñar flujos de trabajo y configuraciones de enrutamiento avanzadas a la persona y medir la calidad de su sistema e interacciones.

**Características destacadas:**

Aunque la siguiente no es una lista completa de funciones de características para este modelo de integración, resalta las principales áreas de enfoque:

  - Las API de Graph y las API de comunicación en la nube para la integración con Teams 

  - Aplicación basada en equipos para experiencias de agente 

  - Teams como extremo de llamadas primarias para los agentes 

  - Clientes de teams que llaman para todos los controles de llamada

  - La aplicación de experiencia del agente también debería poder trabajar en la web y el cliente móvil de Teams

  - Análisis, administración de flujo de trabajo, experiencias basadas en roles para agentes dentro de la aplicación CCaaS dentro de Teams

  - Experiencias de colaboración y chat integradas con clientes de Teams 

  - Mantener el rendimiento y la calidad de la experiencia del cliente de Teams en todas las aplicaciones  

### <a name="extend-and-power"></a>Ampliar y potenciar

Este modelo permite a los partners crear aplicaciones de voz nativas basadas en Azure, aprovechando la infraestructura de llamadas y la plataforma de cliente de los equipos para ofrecer soluciones inteligentes y modernas para la conexión de clientes y agentes de colaboración. El objetivo de la ampliación y la potencia es Stoke la creatividad de los desarrolladores y impulsar la productividad de los clientes.

Al compilar directamente en Azure, los socios pueden implementar y aprovisionar rápidamente su solución en todas las regiones y geografías de Teams, Benefitting de nuestra red de comunicaciones internacional compartida y aprovechando los servicios de almacenamiento de Azure, análisis, análisis & cognitiva.

Con el modelo de ampliación y de integración de energía, los socios pueden proporcionar a los agentes del centro de contacto las experiencias de comunicación de Omni-canal al mismo tiempo que incorporan inteligencia artificial para personalizar la forma y el momento en que los participantes, u otros servicios, participan en una llamada que aprovecha la [API de las comunicaciones en la nube en Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).

**Características destacadas:**

Aunque la siguiente no es una lista completa de funciones de características para este modelo de integración, estas áreas de resaltado, además de las proporcionadas por el modelo Connect and Extend.

  - Experiencias de agente formal habilitadas nativamente para la comunicación de canal Omni a través del SDK de Teams 

  - Aprovechar los servicios de colaboración de Teams para la colaboración de agentes e interacciones con clientes  

  - Aprovisionamiento rápido de servicios en la nube, implementar en cualquier lugar 

  - Control directo de conversaciones e interacción con los usuarios durante las conversaciones de Teams 

### <a name="comparing-connected-contact-center-integration-models"></a>Comparación de modelos de integración del centro de contacto conectado

Consulte la tabla siguiente para obtener información general sobre los modelos de integración que admite Microsoft Teams.

<table>
<thead>
<tr class="header">
<th></th>
<th>Aplicaciones de voz de Teams</th>
<th>Vuelve</th>
<th>Extendido</th>
<th>Eléctricos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modelo de servicio en la nube</td>
<td>Azure</td>
<td>Servidor</td>
<td><p>Partner +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>¿Quién funciona?</td>
<td>Microsoft</td>
<td>Servidor</td>
<td>Servidor</td>
<td>Servidor</td>
</tr>
<tr class="odd">
<td>Inicio de sesión de M365</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr class="even">
<td>¿Los usuarios con Teams llaman?</td>
<td>Informal, SME</td>
<td>Informal, SME</td>
<td>Informal, SME, formal</td>
<td>Informal, SME, formal</td>
</tr>
<tr class="odd">
<td>Experiencia de IW/SME</td>
<td>Teams</td>
<td>Teams</td>
<td><p>Teams +</p>
<p>prórroga</p></td>
<td><p>Teams +</p>
<p>prórroga</p></td>
</tr>
<tr class="even">
<td>Conectividad de servicio</td>
<td>Plataforma<br />
(Planes de llamadas + DR)</td>
<td>Enrutamiento directo</td>
<td>Plataforma<br />
(Planes de llamadas + DR)</td>
<td>Plataforma<br />
(Planes de llamadas + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Pasos siguientes

Si es un proveedor y quiere unirse al programa de certificación, envíe un mensaje de correo electrónico <Teamscategorypartner@microsoft.com> .
