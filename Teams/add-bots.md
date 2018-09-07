---
title: Agregar bots para chats privados y canales en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lucarras
description: Obtenga más información sobre cómo agregar bots en Microsoft Teams para chats privados y canales, crear bots personalizados y transferir localmente su propio bot para chats privados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84ddb68dd5251d943e1fe3b6cca1aae2cf8fcb45
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867656"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Agregar bots para chats privados y canales en Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Bots son programas automatizados que responden a las consultas o dar a las actualizaciones y notificaciones acerca de los usuarios obtener información detallada, busque interesantes o desean mantenerse informado acerca de. Bots permiten a los usuarios interactuar con servicios de nube como administración de tareas, programación y sondeo a través de las conversaciones de chat en Microsoft Teams. Bots para Microsoft Teams se basan en el [Marco de trabajo de Microsoft Bot](https://go.microsoft.com/fwlink/?linkid=854370). Los bots que se desarrollan mediante este marco de trabajo se puede habilitar fácilmente para Microsoft Teams. Para obtener más información, vea [características de administración de equipos de Microsoft en su organización de Office 365](enable-features-office-365.md).

Actualmente, Microsoft Teams admite bots en chats privados y canales dentro de un equipo. Los administradores pueden controlar si el uso de bots está permitido o prohibido en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span>

Los bots desarrollados por la comunidad se pueden utilizar en Microsoft Teams. La funcionalidad del bot y la transferencia local del bot deben estar habilitadas a nivel del inquilino para que los bots personalizados puedan ser funcionales. Los bots se pueden usar en chats privados o en canales. Para los canales, los propietarios o los miembros del equipo pueden agregar bots.

Para obtener más información, consulte la sección "Usar bots" en [Aplicaciones y servicios](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b). 




<a name="create-custom-bots-for-microsoft-teams"></a>Crear bots personalizados para Microsoft Teams
--------------------------------------

Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft Bot Framework. Consulte las instrucciones de [Crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber cómo puede desarrollar y publicar sus propios bots.

Al crear un bot y registrarlo en Bot Framework, puede elegir si desea publicarlo. Si no lo publica, el bot sigue siendo privado. También puede requerir que los usuarios tengan que iniciar sesión antes de usar el bot. Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot. Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.

Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.

<a name="side-load-your-own-bot-for-private-chat"></a>Transfiera localmente su propio bot para chats privados.
---------------------------------------

1. Después de haber creado el bot, vaya a la **Configuración de la aplicación** para el robot desarrollado, a continuación, en **configuración de la aplicación**, copie el valor de la opción **MicrosoftAppId** . ![Página de captura de pantalla de configuración de la aplicación para un componente con el identificador de la aplicación Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  En Microsoft Teams, en el panel **Chat**, seleccione el icono **Agregar chat**. En **Para**, pegue el **identificador de aplicación de Microsoft** del bot. ![Captura de pantalla de un panel de chat con el icono de Agregar chat y la línea Para con el identificador de aplicación de Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  El identificador de la aplicación se resolverá con el **nombre del bot** y después podrá iniciar una conversación de chat con el bot.
