---
title: Agregar bots para chats privados y canales en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: Obtenga información sobre cómo agregar bots en Microsoft Teams para chats personales, chats grupales y canales, y cargue sus propios bots para chats personales, chats grupales y canales.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5f7ef2d548031528aa41b9fdb75831fe46d36d
ms.sourcegitcommit: c13bd343c3f3d14c7b8ff710ac5a4fec17ab88b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "34859692"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>Agregar bots para chats personales, chats grupales y canales en Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Los bots son programas automatizados que responden a las consultas o dan actualizaciones y notificaciones sobre detalles que puedan resultar interesantes para los usuarios o sobre los que quieran mantenerse informados. Los bots permiten a los usuarios interactuar con servicios en la nube, como la administración de tareas, la programación y el sondeo, a través de conversaciones de chat en Microsoft Teams. Los bots para Teams se han creado en [Microsoft bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). Los bots desarrollados con este marco se pueden habilitar fácilmente para Teams. Para obtener más información, vea [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).

En la actualidad, Teams admite bots en chats personales, chats grupales y canales dentro de un equipo. Los administradores pueden controlar si se permite o prohíbe el uso de bots en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span>

Los bots desarrollados por la comunidad pueden ser aprovechados en Teams. La funcionalidad del bot y la capacidad de cargar aplicaciones personalizadas (también conocidas como la transferencia local) deben habilitarse en el nivel del espacio empresarial para que los bots personalizados sean funcionales. Los bots se pueden usar en chats personales, chats grupales y canales. Para los canales, los propietarios o los miembros del equipo pueden agregar bots.

Para obtener más información, consulte [aplicaciones y servicios](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).

> [!IMPORTANT]
> No se recomienda agregar un bot por GUID, sin fines de prueba. Esto limita gravemente la funcionalidad de un bot. Los bots en el uso de producción deben agregarse a teams como parte de una aplicación. Consulte [crear un bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) y [probar y depurar el bot de Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Crear bots personalizados para Microsoft Teams
--------------------------------------

Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft bot Framework. Consulte las instrucciones para [crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para obtener información sobre cómo puede desarrollar y publicar sus propios bots.

Al crear un bot y registrarlo en Bot Framework, puede elegir si desea publicarlo. Si no lo publica, el bot sigue siendo privado. También puede requerir que los usuarios tengan que iniciar sesión antes de usar el bot. Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot. Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.

Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.

<a name="upload-your-bot-for-personal-chat"></a>Carga tu bot para conversaciones personales
---------------------------------------

1. Después de crear su bot, vaya a la **configuración** de la aplicación para el bot que desarrolló y, después, en configuración de la **aplicación**, copie el valor de la configuración **MicrosoftAppId** . ![Captura de pantalla de la página de configuración de la aplicación para un bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  En Teams, en el panel **chat** , seleccione el **icono Agregar conversación**. En **para**, pegue el identificador de **aplicación de Microsoft**de su bot. ![Captura de pantalla de un panel de chat con identificador de aplicación de Microsoft resaltado](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. El identificador de la aplicación se resolverá en el **nombre de bot** y, a continuación, podrás iniciar una conversación de chat con ese bot.

<a name="upload-your-bot-for-group-chats-or-channels"></a>Cargar un bot para chats grupales o canales
-----------------------------------

Si desea compartir su bot con sus colegas, aquí le mostramos cómo agregarlo a chats grupales o canales de diferentes equipos:

1. Después [de crear un paquete de la aplicación para su bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra Teams y busque el equipo en el que va a cargar el bot.
2. Agregue **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, aplicación a teams.
3. En App Studio, seleccione la pestaña **Editor** de manifiestos. ![captura de pantalla de la pestaña del editor de manifiestos.](media/Adding_Bot_To_Teams.png)
4. Para agregar un bot, en capacidades, seleccione el bot y elija Agregar un bot existente. Después, elija un bot existente o escriba el identificador de un bot existente.
![Muestra cómo seleccionar el bot que ya ha creado.](media/Select_Existing_Bot.png)
5. Vaya a la ubicación del paquete de la aplicación, selecciónelo y, a continuación, haga clic en **abrir**.
6. Selecciona el nombre de tu bot. (No olvides seleccionar la casilla **conversación en grupo** o **equipo** en la sección ámbito).
7. Seleccione **probar y distribuir**.
8. Seleccione la conversación de grupo o el equipo al que desea conectar el bot.

    Su bot estará disponible en su equipo o chat grupal en Teams.
