---
title: Introducción a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Conozca Microsoft Teams, su infraestructura y cómo funciona con Office 365.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbbd2cad0b84ccdcc887d5bcdf272c1556c9c546
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
<a name="overview-of-microsoft-teams"></a>Introducción a Microsoft Teams
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


Microsoft Teams une todas las características de Office 365 para brindar un verdadero centro basado en chats para el trabajo en equipo y darles a los clientes la oportunidad de crear un entorno más abierto, fluido y digital. Microsoft Teams está construido a partir de tecnologías de Microsoft existentes que se entrelazan en Grupos de Office 365. 

De forma predeterminada, Microsoft Teams aprovecha las identidades almacenadas en Azure Active Directory (Azure AD) y se integra con otros servicios de Office 365 para crear un sitio de SharePoint Online y una casilla de correo grupal de Exchange Online para cada equipo creado.

Cualquier persona con una cuenta de correo electrónico empresariales o de clientes, como Outlook, Gmail u otros, puede participar como invitado en los equipos. Todos los invitados en equipos están cubiertos por la misma conformidad y auditoría protección que el resto de Office 365 y los invitados pueden administrarse de forma segura dentro de Azure AD. Administradores pueden centralmente administrar cómo participan invitados dentro de su entorno de Office 365 y fácilmente ver, agregar o revocar el acceso de invitado a los inquilinos de host.

Teams proporciona una función de chat persistente, llamadas y reuniones, fácil acceso a otros componentes de Office 365 y una sólida historia de extensibilidad.  Todo ello crea un centro ideal para trabajar en equipo que se adecúa tanto a grandes empresas como pequeñas organizaciones y todos los que estén en medio.  

Para ampliar las funcionalidades de Microsoft Teams, use conectores, fichas y bots (disponibles en forma de [aplicaciones](https://go.microsoft.com/fwlink/?linkid=854629)) para traer desde fuera información, contenido e interacciones de bots inteligentes a Microsoft Teams.  

<a name="microsoft-teams-infrastructure"></a>Infraestructura de Microsoft Teams
------------------------------

Microsoft Teams está construido a partir de tecnologías de Microsoft existentes, que se entrelazan en Grupos de Office 365. Gracias a su tecnología de la nube de Microsoft, las organizaciones pueden esperar un excelente rendimiento y confiabilidad al aprovechar Microsoft Teams como parte de su historia de colaboración.

De manera predeterminada, un equipo creado en Microsoft Teams creará un grupo de Office 365, un sitio de SharePoint Online (completo con una biblioteca de documentos) y un buzón de Exchange Online para el grupo, que Microsoft Teams utilizará para almacenar información, como invitaciones a reuniones. Un equipo puede crearse a partir de grupos de Office 365 existentes, lo que permite que la pertenencia a grupos existente y el contenido almacenado en SharePoint Online y Exchange Online se traslade a Microsoft Teams.

Para complementar la funcionalidad de Microsoft Teams como panel de chat persistente donde se llevan a cabo conversaciones informales en tiempo real, Microsoft Teams también brinda una experiencia de reunión integrada en la infraestructura de próxima generación basada en la nube que también utilizan Skype y Skype Empresarial. Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad.

Los grupos de Office 365 aprovechan las identidades almacenadas en Azure Active Directory (Azure AD) y, de esta manera, todas las funcionalidades de autenticación y autorización en Azure AD, como admisión de autenticación multifactor (MFA), están disponibles para su uso en Microsoft Teams.

Microsoft Teams también brinda una experiencia de llamadas y reuniones integrada en la infraestructura de próxima generación basada en la nube, que también usan Skype y Skype Empresarial. Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad.

> [!NOTE]
> En función de los comentarios de los clientes, nuevos grupos de 365 de Office genera como resultado de la creación de un equipo de Microsoft Teams no volverán a aparecer en Outlook de forma predeterminada. Los clientes que desea continuar con el comportamiento existente de mostrar estos grupos en Outlook, se proporcionará un cmdlet de PowerShell en línea de Exchange que puede habilitar el grupo para la experiencia de Outlook. Grupos creados a través de Outlook y se habilitó posteriormente para equipos continuará mostrando en Outlook y equipos. Esta actualización se aumentará progresivamente roll out a través de Outlook y los equipos en los próximos meses.


<a name="microsoft-teams-and-office-365"></a>Microsoft Teams y Office 365
------------------------------

Los diferentes grupos tienen distintas necesidades en base a su función y estilo de trabajo. Office 365 está diseñado para el estilo de trabajo único de cada grupo e incluye aplicaciones integradas creadas para cada finalidad, como:

-   Outlook para correos electrónicos empresariales, ahora con funcionalidad de grupos.

-   SharePoint para sitios y portales, servicios de contenido inteligente, automatización de procesos de negocio y Enterprise Search.

-   Yammer para impulsar las conexiones dentro de toda la empresa.

-   Skype Empresarial como la columna vertebral del audio y el vídeo de la empresa.

-   Y ahora, Microsoft Teams, el nuevo espacio de trabajo basado en chats de Office 365.

He aquí los casos de uso comunes para cada aplicación en Office 365. Para obtener instrucciones de uso detalladas, visite la [biblioteca de productividad de FastTrack](https://go.microsoft.com/fwlink/?linkid=854630)

![Icono de Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   Aprovechado por usuarios y equipos que desean colaborar en tiempo real con el mismo grupo de personas.

-   Ayuda a los equipos a iterar rápidamente en un proyecto, a la vez que comparten archivos y colaboran en entregas compartidas.

-   Permite a los usuarios conectarse a una amplia gama de herramientas en su área de trabajo (como planificador, alimentación BI, GitHub, etcetera).

![Icono de Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   Aprovechado por usuarios que prefieren colaborar en el entorno familiar del correo electrónico o de un modo más formal y estructurado.

-   Brinda procesos de negocio específicos que requieren el uso del correo electrónico para transmitir documentos e información dentro o fuera de los límites corporativos.

-   Se comunica y conecta con usuarios que se encuentran fuera de los grupos de trabajo u organizaciones inmediatos.

![Icono de Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   Aprovechado para ayudar a conectar a los usuarios de toda la empresa, para que se organicen en comunidades de práctica y compartan procedimientos recomendados.

-   Mejora los flujos de trabajo multidisciplinarios a través de una plataforma basada en fuentes, abierta y transparente.

-   Fomenta la relación entre ejecutivos y empleados con las conversaciones bidireccionales entre los líderes y la base más amplia de empleados.

-   Motiva a la fuerza de trabajo de primera línea a compartir y recibir conocimientos y experiencia.

![Icono de Skype Empresarial.](media/Overview_of_Microsoft_Teams_image4.png)

-   Aprovechado para comunicación y colaboración en tiempo real, tanto de manera interna como externa con clientes/socios.

-   Permite realizar reuniones con audio, vídeo y contenido con pequeños o grandes grupos (incluidos foros con hasta 10 000 participantes).

-   Ofrece funcionalidad de telefonía empresarial.


![Icono de Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   Aprovechado para sitios y portales (por ejemplo, anuncios y novedades de la empresa, búsquedas y colaboración en documentos).

-   Implementa automatización de procesos de negocio en bibliotecas de documentos y listas de información mediante la integración de Microsoft Flow y PowerApps.

-   Sitio de equipo de SharePoint con todo el poder, aprovisionado automáticamente para cada equipo de Microsoft para almacenamiento de archivos, novedades del equipo, páginas, listas y mucho más.

-   Vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md)

## <a name="teams-known-issuesknown-issuesmd"></a>[Problemas conocidos de Microsoft Teams](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[Notas de la versión del cliente de Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a>¿Qué ha pasado con las preguntas frecuentes del administrador de Microsoft Teams?

Aunque las preguntas frecuentes del administrador de Microsoft Teams eran muy útiles cuando se publicó por primera vez Microsoft Teams, rápidamente se convirtieron en un "cajón desastre" donde era muy difícil encontrar algo. Por ese motivo hemos decidido deshacernos de las preguntas frecuentes y hemos incorporado la información más relevante en la documentación de Microsoft Teams que está leyendo en este momento. Aquí encontrará toda la información que estaba en las preguntas frecuentes, en su contexto correcto.

Si buscas algo que no puede encontrar aquí, por favor Díganos acerca de él en la sección **comentarios** a continuación. Intentaremos responder a sus comentarios dentro de 24 horas.

Por cierto, **sí que** hay una sección de preguntas frecuentes en el [recorrido desde Skype Empresarial a Microsoft Teams](FAQ-journey.md). 
