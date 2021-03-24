---
title: Configurar Microsoft Teams para empresas pequeñas
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Configure Teams para empresas pequeñas para permitirles a sus usuarios colaborar a través del chat y del uso compartido de archivos, configurar y asistir a reuniones de cualquier tamaño, y comunicarse por vídeo y voz.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2fd7865823cffdfd2f2b2932a78744786c59cfd0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101236"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>Configurar Microsoft Teams para empresas pequeñas

Hay muchas formas de personalizar Teams. En las siguientes secciones se muestra cómo configurar cada carga de trabajo de Teams: **chats, equipos y canales**; **conferencias y reuniones** y **voz en la nube**. Puede configurar cada carga de trabajo en el orden que más le convenga. Aunque recomendamos configurar primero la carga de trabajo de los chats, los equipos y los canales, también puede empezar por las reuniones y conferencias o incluso con la voz en la nube. Es su decisión.

> [!NOTE]
> Si aún no lo ha hecho, le recomendamos encarecidamente que empiece la implementación de Teams con un piloto. El piloto le permitirá a usted y a los usuarios pioneros familiarizarse con Teams y con sus características antes de su planificación y lanzamiento. Para obtener más información sobre cómo iniciar el piloto, consulte la [Introducción a Microsoft Teams](get-started-with-teams-quick-start.md).

Antes de implementar Teams ampliamente, asegúrese de que su organización esté lista revisando los elementos de [Asegúrese de estar preparado](get-started-with-teams-quick-start.md#make-sure-youre-ready).

Diríjase a la sección de interés:

- [Cargas de trabajo](#workloads)
  - [Chat, equipos y canales](#chat-teams-and-channels)
  - [Reuniones y conferencias](#meetings-and-conferencing)
  - [Business Voice](#business-voice)
- [Implementación de clientes](#deploy-clients)
- [Aprendizaje](#training)

## <a name="workloads"></a>Cargas de trabajo
### <a name="chat-teams-and-channels"></a>Chat, equipos y canales

El chat, los equipos y los canales son el eje central de Teams. El **chat** permite que uno o más usuarios se comuniquen entre sí, compartan archivos y se reúnan en privado. Los **equipos**, que pueden ser visibles para todos los usuarios de la organización o solo para los miembros de ese equipo, permiten a los usuarios adecuados colaborar en cualquier tipo de tarea u ocasión, desde un proyecto de larga duración hasta la planificación de una fiesta de cumpleaños. Los **canales** dentro de los equipos pueden segmentar temas, proyectos, departamentos o lo que necesite su equipo. Para obtener más información sobre el chat, los equipos y los canales, consulte la [Introducción a los equipos y canales](teams-channels-overview.md).

> [!TIP]
> Descubra cómo administrar los roles del equipo, el acceso y las directivas de mensajería completando el módulo de [Administración de Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) en Microsoft Learn.

A medida que implemente los equipos y canales, necesitará decidir quiénes pueden crearlos, si concederá acceso a los invitados fuera de la organización y mucho más. El artículo [Chat, equipos, canales y aplicaciones en Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) contiene toda la información acerca de cómo planificar los chats, los equipos y los canales; sin embargo, hay ciertos puntos clave en el artículo que debe tomar en cuenta. Seleccione una decisión para obtener más información al respecto.

| Decisión | Descripción |
|--|--|
| [¿Quiénes deben ser los administradores de Teams?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | Los roles de administrador se pueden usar para conceder permisos específicos a las personas que usted quiera que administren Teams. Es posible que las empresas pequeñas no necesiten estos roles adicionales, ya que la misma persona puede encargarse de manejar todos los aspectos de Teams. Siempre podrá agregar o quitar administradores en otro momento.<br><br>[Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md) |
| [¿Quiénes serán los propietarios y quiénes serán los miembros del equipo?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Los propietarios del equipo controlan quiénes pueden acceder al equipo y a sus canales. Pueden decidir si un equipo o canal es público (para la organización) o privado y configurar directivas; por ejemplo, si el canal debe moderarse o no. Los miembros pueden acceder al equipo y a sus canales (a menos que el canal se establezca como privado y los miembros no pertenezcan a ese canal), así como también ser designados como moderadores.<br><br>[Asignar miembros y propietarios de equipo en Microsoft Teams](assign-roles-permissions.md) |
| [¿Debe habilitarse el acceso a los invitados?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |El acceso de invitado permite que las personas de su organización inviten a otras personas fuera de la organización para que accedan a los equipos y canales. El acceso de invitado suele usarse para colaborar con personas fuera de la organización que no tengan una relación formal con esta. Por ejemplo, puede invitar temporalmente a un planificador de proyectos para que trabaje en un proyecto.<br>El acceso de invitados es distinto al acceso externo. El acceso de invitados permite que usuarios específicos interactúen con personas de su organización.  <br>El acceso de invitado está **Desactivado** de forma predeterminada. <br><br>[Activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md)  |

No necesita hacer más nada para que sus usuarios comiencen a usar el chat, los equipos y los canales. Sin embargo, existen muchas maneras de controlar la forma en que se utiliza Teams. Puede hacer los cambios ahora o esperar para ver cómo las personas usan Teams. Para obtener más información, revise los siguientes artículos:

- [Administrar las directivas de mensajería en Teams](messaging-policies-in-teams.md)
- [Configuración de Teams](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>Reuniones y conferencias

Las reuniones y conferencias permiten que las personas de la organización se reúnan entre sí y con usuarios ajenos a la organización. Cualquier usuario con un cliente de Teams o de Skype Empresarial puede unirse a las **reuniones** a las que haya sido invitado. Usando el micrófono, la cámara y la pantalla de su dispositivo, los participantes pueden unirse a la conversación sin necesidad de tener un teléfono. También pueden chatear, realizar llamadas de voz y compartir vídeo y aplicaciones con otros participantes a través de un equipo o de un dispositivo móvil.

El asistente de **Audioconferencia** permite a los participantes unirse a las reuniones a través de un teléfono normal al llamar a un número de teléfono de conferencia y especificar el id. de la reunión. Las audioconferencias son útiles cuando uno de los participantes no tiene una buena conexión a Internet, la reunión es solo de voz o hay alguna otra circunstancia que le impida al participante unirse a través del cliente de Teams.

> [!TIP]
> Si desea familiarizarse con las reuniones y los eventos, complete el módulo [Administrar reuniones, conferencias y eventos con Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) en Microsoft Learn.

Las reuniones están habilitadas de forma predeterminada en Teams, sin embargo, usted puede controlar la experiencia de la reunión para los organizadores y participantes. También puede establecer directivas para lo que pueden o no pueden hacer los participantes antes y durante las reuniones. Para obtener más información, revise los siguientes artículos:

- [Inicio rápido de administrador: Reuniones y eventos en directo en Microsoft Teams](quick-start-meetings-live-events.md)
- [Configurar la Audioconferencia para empresas pequeñas y medianas](audio-conferencing-smb.md)

### <a name="business-voice"></a>Business Voice

[Microsoft 365 Business Voice](business-voice/whats-business-voice.md) es una solución ideal para los negocios con menos de 300 usuarios que le brinda todas las características de un sistema telefónico de oficina. Business Voice incluye correo de voz, identificación de llamadas, menús de sistema telefónico, números gratuitos y mucho más, sin necesidad de tener que recurrir a los costosos y complejos sistemas telefónicos locales.

Basado en el sistema telefónico de Microsoft 365, Business Voice simplifica la incorporación de llamadas a su organización al unir las características del sistema telefónico y los complementos en un solo lugar y proporcionándole un asistente fácil de seguir que le ayudará a configurar su sistema telefónico. Si su organización se encuentra en un [país o región compatible con Business Voice](business-voice/country-region-availability.md), puede transferir sus números telefónicos a Microsoft 365 y permitirnos administrar su sistema telefónico por usted.

Si tiene Microsoft 365 como su sistema telefónico, podrá convertir cualquier dispositivo en un teléfono al instalarle un cliente de Teams. Pero si prefiere un teléfono convencional de escritorio o para hacer conferencias, también tiene la opción de escoger entre varios dispositivos certificados por Teams. Cualquiera que sea el caso, siempre podrá desviar sus llamadas a donde se encuentre, así como hacer llamadas desde el número de teléfono de la oficina.

Si le interesa probar Business Voice, consulte [¿Qué necesito para adquirir y usar Microsoft 365 Business Voice?](business-voice/what-to-buy.md).

## <a name="deploy-clients"></a>Implementación de clientes

Cuando esté listo para que sus usuarios comiencen a usar Teams, estos pueden instalar el cliente de Teams en su equipo Windows, Mac o Linux, o en su dispositivo Android o iOS. Los usuarios pueden descargar el cliente de Teams directamente desde <https://teams.microsoft.com/downloads>.

Asegúrese de que quienes vayan a emplear Teams tengan una licencia de Teams. Para obtener más información acerca de cómo asignar una licencia de Teams, consulte [Administrar el acceso del usuario a Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Para obtener recomendaciones sobre cómo planear la implementación del cliente de Teams, complete el módulo [Implementar clientes de Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) en Microsoft Learn.

Si su organización usa Microsoft Endpoint Configuration Manager, alguna directiva de grupo o un mecanismo de distribución de terceros para implementar el software en los equipos de los usuarios, consulte [Instalar Microsoft Teams a través de Microsoft Endpoint Configuration Manager](msi-deployment.md).

Si desea obtener información detallada acerca de la implementación de clientes de Teams, consulte [Obtener clientes para Microsoft Teams](get-clients.md).

## <a name="training"></a>Aprendizaje

Para obtener información sobre cómo entrenar a los usuarios y administradores para que usen Teams, consulte [Aprendizaje de Microsoft Teams](training-microsoft-teams-landing-page.md).