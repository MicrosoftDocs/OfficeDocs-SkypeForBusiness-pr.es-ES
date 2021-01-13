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
description: Información general sobre el centro de contactos integrado como solución de servicio (CCaaS) para Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: e48cac3e556c6bb99e29ad07f3d875362ad42489
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821000"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Integraciones del Centro de contactos para Microsoft Teams

La integración de soluciones populares de centros de contactos con Microsoft Teams es una necesidad común de los clientes al implementar las capacidades de llamadas de Teams.  Este artículo proporciona información general sobre cómo se pueden integrar las soluciones del centro de contactos con Microsoft Teams y la información adicional sobre las soluciones de asociados que participan en el programa de certificación del Centro de contactos conectado de Microsoft Teams.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>¿Qué es la integración de un centro de contactos con Microsoft Teams?

Los centros de contacto de hoy en día proporcionan mucho más que soporte técnico: actúan como uno de los principales vehículos para interactuar y comentarios sin filtrar sobre la experiencia de un cliente con una marca. Debido a la amplia cantidad de canales que los clientes de hoy en día prefieren interactuar por teléfono, correo electrónico, texto, redes sociales y el gran volumen de puntos de contacto asociados con los procesos de compra actuales, muchas organizaciones han realizado dos realidades adicionales:

1. Todos los miembros de la organización tienen el potencial de participar en la participación directa de un cliente y, por lo tanto, necesitan estar equipados con las herramientas adecuadas.

2. Este ámbito ampliado de las interacciones con los clientes requiere herramientas que puedan ayudarle a impulsar la coherencia, la mejora constante y la escala.

Microsoft Teams admite las transmisiones de trabajo por interacción del cliente actuando como el concentrador para la conexión de clientes internos y externos en sus modos de comunicación, incluidos el chat, las reuniones de vídeo y las llamadas. Para algunas compañías, las capacidades [](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) de voz en la nube de Microsoft [Teams,](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)incluidos los operadores [automáticos](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)y las colas de llamadas, proporcionan las características y la configuración para satisfacer sus necesidades.

Para otros usuarios que desean soluciones integradas con herramientas empresariales y flujos de trabajo para dirigir el viaje del cliente, Microsoft Teams también se integra con algunos de los proveedores de soluciones líderes del sector centro de contactos como servicio (CCaaS).

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Centro de contactos conectado para el programa de certificación de Microsoft Teams

Las API permiten a los partners desarrollar e integrar soluciones CCaaS para Teams. Además, hemos desarrollado el programa de certificación Centro de contactos conectados para Microsoft Teams para proporcionar a los clientes la garantía de que la solución de cada partner participante se ha probado y comprobado para proporcionar la calidad, la compatibilidad y la confiabilidad que esperan de las soluciones de Microsoft.

Los siguientes partners están en proceso de certificar su solución para Microsoft Teams y están listos para atraer a los clientes:

|  Partner                                                                                                                               |  Sitio web de la solución                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `8x8` | https://www.8x8.com/products/integrations/8x8-voice-for-microsoft-teams?locale=us |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| `ContactCenter4All` | www.contactcenter4all.com |
| `Content Guru` | https://www.contentguru.com/microsoft-teams-integration/    |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| 'Geomant' | https://www.geomant.com/buzzeasy-contact-centre-for-microsoft-teams                                          |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |


Esta lista se actualizará a medida que más partners se unan y cumplan con los criterios de certificación.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>¿Cómo funcionan las soluciones del centro de contactos en Microsoft Teams?

Microsoft Teams ofrece una variedad de capacidades para apoyar el desarrollo de soluciones de voz de terceros, entre las que se incluyen:

1. [Conectividad de enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [API de comunicación en la nube de Microsoft Graph](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Plataforma y extensibilidad de Teams

4. SDK de Teams

Juntos, estas capacidades permiten tres modelos de integración:

  - **Conectar** (a través de enrutamiento directo)

  - **Conectar y ampliar** (enrutamiento directo, API de Graph y plataforma de aplicaciones de Teams)

  - **Ampliar y ampliar Power** (incrustar LOS SDK de Teams en aplicaciones 3p para interacciones nativas de Teams)

### <a name="connect"></a>Conectar

Este modelo conecta a los asociados de CCaaS con la infraestructura de sistemas telefónicos de Microsoft Teams, lo que permite mejorar el enrutamiento, la configuración y la información del sistema. En este modelo, la solución asociada al centro de contactos también puede proporcionar servicios de telefonía para usuarios y números seleccionados.

Los agentes que usan soluciones creadas en el modelo Connect pueden recopilar información & información y, si es necesario, transferir llamadas a expertos en la materia directamente, usando la presencia de SME en Teams para garantizar su disponibilidad.

Las organizaciones pueden asegurarse de que las llamadas se enrutar al agente óptimo configurando asistentes virtuales automatizados y colas de enrutamiento basadas en aptitudes.

**Aspectos destacados de las características:**

Aunque lo siguiente no es una lista exhaustiva de las capacidades de características para este modelo de integración, las áreas en las que centrarse incluyen:

  - Autenticación de Office 365 para agentes para permitir que los agentes se conecten a su inquilino de Microsoft desde su cliente integrado de CCaaS 

  - Indicación de presencia de los usuarios de Teams 

  - Flujos de llamadas a través de enrutamiento directo (como se indica en los planes de prueba) 

  - Soporte técnico para transferencias y llamadas grupales con usuarios de Teams 

  - API de Teams Graph y API de comunicación en la nube para la integración con Teams 

  - Puede admitir la tronco SIP multiinquilino para admitir varios clientes en SBC del partner.  

  - Partners para implementar el [ <span class="underline">controlador de borde de sesión certificado de Microsoft (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Conectar y extender

Este modelo amplía las experiencias de agente y personal del centro de contactos mediante la integración con el cliente de Teams mediante la plataforma del cliente de [Teams,](https://docs.microsoft.com/microsoftteams/platform/overview)las API de [Teams Graph](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) y la API de comunicaciones en la nube en [Microsoft Graph,](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) y usa el sistema telefónico de Teams para todas las llamadas y experiencias de control de llamadas del centro de contactos. En este modelo, el partner del centro de contactos actúa como operador de telefonía junto con Microsoft 365.

Al usar soluciones basadas en Connect y Extend, los agentes pueden beneficiarse de notas contextuales y dinámicas que correlacionan datos de varios sistemas antes de iniciar una participación y, a continuación, evitar el cambio de contexto costoso si trabajan de forma nativa en Teams para la colaboración interna y las comunicaciones externas.

Las organizaciones pueden diseñar flujos de trabajo y configuraciones avanzadas de enrutamiento de forma individual y medir la calidad de su sistema e interacciones.

**Aspectos destacados de las características:**

Aunque lo siguiente no es una lista completa de las capacidades de características para este modelo de integración, sí resalta las áreas principales:

  - API de Teams Graph y API de comunicación en la nube para la integración con Teams 

  - Aplicación basada en Teams para experiencias de agente 

  - Teams como punto de conexión de llamada principal para los agentes 

  - Llamadas de clientes de Teams para todos los controles de llamada

  - La aplicación de experiencia del agente también debería poder funcionar en la web y en el cliente móvil de Teams.

  - Análisis, administración de flujos de trabajo y experiencias basadas en roles para agentes dentro de la aplicación CCaaS en Teams

  - Experiencias de chat y colaboración integradas con clientes de Teams 

  - Conservar el rendimiento y la calidad de las experiencias de cliente de Teams en todas las aplicaciones  

### <a name="extend-and-power"></a>Extender y encender

Este modelo permite a los partners crear aplicaciones de voz nativas basadas en Azure mediante la infraestructura de llamadas de Teams y la plataforma de clientes para ofrecer soluciones modernas e inteligentes para la conexión colaborativa entre clientes y agentes. El objetivo de Ampliar y Power es fomentar la creatividad de los desarrolladores e impulsar la productividad de los clientes.

Al crear directamente en Azure, los partners pueden implementar y aprovisionar rápidamente su solución en todas las regiones y regiones geográficas de Teams, beneficiándose de nuestra red de comunicaciones global compartida y al mismo tiempo aprovechar el almacenamiento, el cálculo y el análisis de Azure & servicios cognitivas.

Con el modelo de integración de Extend y Power, los partners pueden proporcionar a los agentes del centro de contacto experiencias de comunicación de canal vertical e incorporar inteligencia artificial para personalizar cómo y cuándo los participantes (u otros servicios) participan en una llamada aplicando la API de comunicaciones en la nube en [Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)

**Aspectos destacados de las características:**

Aunque lo siguiente no es una lista exhaustiva de las funcionalidades de características para este modelo de integración, estas áreas resaltadas se sume a las proporcionadas por el modelo Conectar y extender.

  - Experiencias formales del agente habilitadas de forma nativa para la comunicación de canal mediante SDK de Teams 

  - Usar los servicios de colaboración de Teams para la colaboración del agente y las interacciones con los clientes  

  - Aprovisionamiento rápido de servicios en la nube, implementar en cualquier lugar 

  - Control directo de la conversación e interacción con los usuarios durante las conversaciones de Teams 

### <a name="comparing-connected-contact-center-integration-models"></a>Comparación de modelos de integración de centros de contactos conectados

Revise la tabla siguiente para obtener información general sobre los modelos de integración que admite Microsoft Teams.

<table>
<thead>
<tr class="header">
<th></th>
<th>Aplicaciones de voz de Teams</th>
<th>Conectar</th>
<th>Extender</th>
<th>Energía</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modelo de servicio en la nube</td>
<td>Azure</td>
<td>Partner</td>
<td><p>Partner +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>¿Quién funciona con la solución?</td>
<td>Microsoft</td>
<td>Partner</td>
<td>Partner</td>
<td>Partner</td>
</tr>
<tr class="odd">
<td>Inicio de sesión de M365</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr class="even">
<td>¿Usuarios con llamadas de Teams?</td>
<td>Informal, SME</td>
<td>Informal, SME</td>
<td>Informal, SME, Formal</td>
<td>Informal, SME, Formal</td>
</tr>
<tr class="odd">
<td>Experiencia de IW/SME</td>
<td>Teams</td>
<td>Teams</td>
<td><p>Teams +</p>
<p>extensiones</p></td>
<td><p>Teams +</p>
<p>extensiones</p></td>
</tr>
<tr class="even">
<td>Conectividad de servicio</td>
<td>Plataforma<br />
(Planes de llamadas +DR)</td>
<td>Enrutamiento directo</td>
<td>Plataforma<br />
(Planes de llamadas + DR)</td>
<td>Plataforma<br />
(Planes de llamadas + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Pasos siguientes

Si eres un proveedor que solicita unirse al programa de certificación, envía un correo <Teamscategorypartner@microsoft.com> electrónico.
