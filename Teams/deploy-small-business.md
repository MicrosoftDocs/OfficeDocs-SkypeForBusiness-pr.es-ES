---
title: Configurar Microsoft Teams para empresas pequeñas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Configure Teams para empresas pequeñas para permitirles a sus usuarios colaborar a través del chat y del uso compartido de archivos, configurar y asistir a reuniones de cualquier tamaño, y comunicarse por vídeo y voz.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3afa62cfaca28c0c428c15b44868e7237973955
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045449"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>Configurar Microsoft Teams para empresas pequeñas

Hay muchas formas de personalizar Teams. En las secciones siguientes se muestra cómo configurar cada carga de trabajo de Teams: **chats, equipos y canales**; **reuniones y conferencias**; y **soluciones de voz**. Podrá configurar cada carga de trabajo en el orden que desee. Aunque recomendamos configurar primero la carga de trabajo de los chats, los equipos y los canales, también puede empezar por las reuniones y conferencias o incluso con la voz en la nube. Es su decisión.

> [!NOTE]
> Si aún no lo ha hecho, le sugerimos encarecidamente que comience la implementación de Teams con un piloto. El piloto le permitirá tanto a usted como a los primeros usuarios familiarizarse con Teams y con sus características antes de la planificación y del lanzamiento. Para obtener más información sobre cómo iniciar el piloto, consulte [Introducción a Microsoft Teams](get-started-with-teams-quick-start.md).

Antes de que implemente Teams ampliamente, asegúrese de que su organización está lista revisando los elementos de [Asegúrese de que está listo](get-started-with-teams-quick-start.md#make-sure-youre-ready).

Diríjase a la sección de interés:

- [Cargas de trabajo](#workloads)
  - [Chat, equipos y canales](#chat-teams-and-channels)
  - [Reuniones y conferencias](#meetings-and-conferencing)
  - [Teléfono de Teams con plan de llamadas](#teams-phone-with-calling-plan)
- [Implementación de clientes](#deploy-clients)
- [Aprendizaje](#training)

## <a name="workloads"></a>Cargas de trabajo
### <a name="chat-teams-and-channels"></a>Chat, equipos y canales

El chat, los equipos y los canales son el eje central de Teams. El **chat** permite que uno o más usuarios se comuniquen entre sí, compartan archivos y se reúnan en privado. Los **equipos**, que pueden ser visibles para todos los usuarios de la organización o solo para los miembros de ese equipo, permiten a los usuarios adecuados colaborar en cualquier tipo de tarea u ocasión, desde un proyecto de larga duración hasta la planificación de una fiesta de cumpleaños. Los **canales** dentro de los equipos pueden segmentar temas, proyectos, departamentos o lo que necesite su equipo. Para obtener más información sobre el chat, los equipos y los canales, consulte la [Introducción a los equipos y canales](teams-channels-overview.md).

> [!TIP]
> Complete el módulo de administración de [Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) en Microsoft Learn para descubrir cómo administrar los roles de equipo y gestionar el acceso y las directivas de mensajería.

A medida que implemente los equipos y canales, necesitará decidir quiénes pueden crearlos, si concederá acceso a los invitados fuera de la organización y mucho más. El artículo [Chat, equipos, canales y aplicaciones en Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) contiene toda la información acerca de cómo planificar los chats, los equipos y los canales; sin embargo, hay ciertos puntos clave en el artículo que debe tomar en cuenta. Seleccione una decisión para obtener más información al respecto.

| Decisión | Descripción |
|--|--|
| [¿Quiénes deben ser los administradores de Teams?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | Los roles de administrador se pueden usar para conceder permisos específicos a las personas que usted quiera que administren Teams. Es posible que las empresas pequeñas no necesiten estos roles adicionales, ya que la misma persona puede encargarse de manejar todos los aspectos de Teams. Siempre podrá agregar o quitar administradores en otro momento.<br><br>[Usar roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md) |
| [¿Quiénes serán los propietarios y quiénes serán los miembros del equipo?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Los propietarios del equipo controlan quiénes pueden acceder al equipo y a sus canales. Pueden decidir si un equipo o canal es público (para la organización) o privado y configurar directivas; por ejemplo, si el canal debe moderarse o no. Los miembros pueden acceder al equipo y a sus canales (a menos que el canal se establezca como privado y los miembros no pertenezcan a ese canal), así como también ser designados como moderadores.<br><br>[Asignar miembros y propietarios de equipo en Microsoft Teams](assign-roles-permissions.md) |
| [¿Debe habilitarse el acceso a los invitados?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |El acceso de invitado permite que las personas de su organización inviten a otras personas fuera de la organización para que accedan a los equipos y canales. El acceso de invitado suele usarse para colaborar con personas fuera de la organización que no tengan una relación formal con esta. Por ejemplo, puede invitar temporalmente a un planificador de proyectos para que trabaje en un proyecto.<br>El acceso de invitados es distinto al acceso externo. El acceso de invitado permite a usuarios específicos interactuar con personas de su organización.  <br>El acceso de invitado está **Desactivado** de forma predeterminada. <br><br>[Activar o desactivar el acceso de invitado a Microsoft Teams](set-up-guests.md)  |

No necesita hacer más nada para que sus usuarios comiencen a usar el chat, los equipos y los canales. Sin embargo, existen muchas maneras de controlar la forma en que se utiliza Teams. Puede hacer los cambios ahora o esperar para ver cómo las personas usan Teams. Para obtener más información, revise los siguientes artículos:

- [Administrar las directivas de mensajería en Teams](messaging-policies-in-teams.md)
- [Configuración de Teams](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>Reuniones y conferencias

Las reuniones y conferencias permiten que las personas de la organización se reúnan entre sí y con usuarios ajenos a la organización. Cualquier usuario con un cliente de Teams o de Skype Empresarial puede unirse a las **reuniones** a las que haya sido invitado. Usando el micrófono, la cámara y la pantalla de su dispositivo, los participantes pueden unirse a la conversación sin necesidad de tener un teléfono. También pueden chatear, realizar llamadas de voz y compartir vídeo y aplicaciones con otros participantes a través de un equipo o de un dispositivo móvil.

El asistente de **Audioconferencia** permite a los participantes unirse a las reuniones a través de un teléfono normal al llamar a un número de teléfono de conferencia y especificar el id. de la reunión. Las audioconferencias son útiles cuando uno de los participantes no tiene una buena conexión a Internet, la reunión es solo de voz o hay alguna otra circunstancia que le impida al participante unirse a través del cliente de Teams.

> [!TIP]
> Si desea familiarizarse con las reuniones y los eventos, complete el módulo [Administrar reuniones, conferencias y eventos de Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) en Microsoft Learn.

Las reuniones están habilitadas de forma predeterminada en Teams, sin embargo, usted puede controlar la experiencia de la reunión para los organizadores y participantes. También puede establecer directivas para lo que pueden o no pueden hacer los participantes antes y durante las reuniones. Para obtener más información, revise los siguientes artículos:

- [Inicio rápido de administrador: Reuniones y eventos en directo en Microsoft Teams](quick-start-meetings-live-events.md)
- [Configurar la Audioconferencia para empresas pequeñas y medianas](audio-conferencing-smb.md)

### <a name="teams-phone-with-calling-plan"></a>Teléfono de Teams con plan de llamadas

Teléfono de Teams de Microsoft 365 con plan de llamadas es una excelente solución para empresas con menos de 300 usuarios que ofrece todas las características de un sistema telefónico de oficina. Teams Phone incluye correo de voz, identificador de llamada, menús del sistema telefónico, números gratuitos y mucho más, sin necesidad de administrar un sistema telefónico local complejo y costoso.

Para obtener más información sobre Teams Teléfono plan de llamadas para pequeñas y medianas empresas, vea Teams Teléfono guía para pequeñas [y medianas empresas.](/microsoftteams/business-voice/whats-business-voice)

## <a name="deploy-clients"></a>Implementación de clientes

Cuando esté listo para que los usuarios comiencen a usar Teams, estos podrán instalar el cliente de Teams en sus equipos Windows, Mac o Linux o en sus dispositivos Android o iOS. Los usuarios pueden descargar el cliente de Teams directamente desde <https://teams.microsoft.com/downloads>.

Asegúrese de que quienes vayan a emplear Teams tengan una licencia de Teams. Para obtener más información acerca de cómo asignar una licencia de Teams, consulte [Administrar el acceso del usuario a Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Para obtener recomendaciones sobre cómo planear la implementación del cliente de Teams, complete el módulo [Implementar clientes de Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) en Microsoft Learn.

Si su organización usa Microsoft Endpoint Configuration Manager, alguna directiva de grupo o un mecanismo de distribución de terceros para implementar el software en los equipos de los usuarios, consulte [Instalar Microsoft Teams a través de Microsoft Endpoint Configuration Manager](msi-deployment.md).

Si desea obtener información detallada acerca de la implementación de clientes de Teams, consulte [Obtener clientes para Microsoft Teams](get-clients.md).

## <a name="training"></a>Aprendizaje

Para obtener información sobre cómo entrenar a los usuarios y administradores para que usen Teams, consulte [Aprendizaje de Microsoft Teams](training-microsoft-teams-landing-page.md).