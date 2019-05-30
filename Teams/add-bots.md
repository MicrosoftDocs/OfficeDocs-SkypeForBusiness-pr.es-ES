---
title: Agregar bots para chats privados y canales en Microsoft Teams
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: Obtenga más información sobre cómo agregar bots en Microsoft Teams para chats privados y canales, crear bots personalizados y transferir localmente su propio bot para chats privados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6987c14973443e62f0be69f9872c4e248ddb026b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548848"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Agregar bots para chats privados y canales en Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Los bots son programas automatizados que responden a las consultas o dan actualizaciones y notificaciones sobre detalles que puedan resultar interesantes para los usuarios o sobre los que quieran mantenerse informados. Los bots permiten a los usuarios interactuar con servicios en la nube, como la administración de tareas, la programación y el sondeo, a través de conversaciones de chat en Microsoft Teams. Los bots para Microsoft Teams se han creado en [Microsoft bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). Los bots desarrollados con este marco se pueden habilitar fácilmente para Microsoft Teams. Para obtener más información, vea [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).

Actualmente, Microsoft Teams admite bots en chats privados y canales dentro de un equipo. Los administradores pueden controlar si el uso de bots está permitido o prohibido en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span>

Los bots desarrollados por la comunidad se pueden utilizar en Microsoft Teams. La funcionalidad del bot y la transferencia local del bot deben estar habilitadas a nivel del inquilino para que los bots personalizados puedan ser funcionales. Los bots se pueden usar en chats privados o en canales. Para los canales, los propietarios o los miembros del equipo pueden agregar bots.

Para obtener más información, consulte la sección "Usar bots" en [Aplicaciones y servicios](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b). 

> [!IMPORTANT]
> No se recomienda agregar un bot por GUID, sin fines de prueba. Esto limita gravemente la funcionalidad de un bot. Los bots en el uso de producción deben agregarse a teams como parte de una aplicación. Consulte [crear un bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) y [probar y depurar el bot de Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Crear bots personalizados para Microsoft Teams
--------------------------------------

Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft Bot Framework. Consulte las instrucciones de [Crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber cómo puede desarrollar y publicar sus propios bots.

Al crear un bot y registrarlo en Bot Framework, puede elegir si desea publicarlo. Si no lo publica, el bot sigue siendo privado. También puede requerir que los usuarios tengan que iniciar sesión antes de usar el bot. Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot. Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.

Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.

<a name="side-load-your-own-bot-for-private-chat"></a>Transfiera localmente su propio bot para chats privados.
---------------------------------------

1. Una vez que haya creado el bot, vaya a **configuración** de la aplicación para el bot que ha desarrollado y, después, en configuración de la **aplicación**, copie el valor de la configuración **MicrosoftAppId** . ![Captura de pantalla de la página de configuración de la aplicación para un bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  En Microsoft Teams, en el panel **Chat**, seleccione el icono **Agregar chat**. En **Para**, pegue el **identificador de aplicación de Microsoft** del bot. ![Captura de pantalla de un panel de chat con identificador de aplicación de Microsoft resaltado](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  El identificador de la aplicación se resolverá con el **nombre del bot** y después podrá iniciar una conversación de chat con el bot.

<a name="side-load-your-bot-for-channels"></a>Cargar el bot para los canales
-----------------------------------

Si desea compartir su bot con sus colegas, aquí le mostramos cómo agregarlo a los canales de diferentes equipos:

1. Una vez que haya [creado un paquete de la aplicación para su bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra Teams y busque el equipo en el que se cargará el bot.
2. Agregue **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, aplicación a Microsoft Teams.
3. En App Studio, seleccione la pestaña **Editor** de manifiestos. ![captura de pantalla de la pestaña del editor de manifiestos.](media/Adding_Bot_To_Teams.png)
4. Para agregar un bot, en capacidades, seleccione bot y elija Agregar un bot existente, tendrá la opción de elegir un bot existente de la lista desplegable o introducir el identificador de uno de los bots existentes.
![Muestra cómo seleccionar el bot que ya ha creado.](media/Select_Existing_Bot.png)
5. Vaya a la ubicación del paquete de la aplicación, selecciónelo y, a continuación, haga clic en **abrir**.
6. Selecciona el nombre de tu bot (no olvides activar la casilla "equipo" en la sección "ámbito").
7. Seleccione la opción probar y distribuir.
8. Seleccione el equipo al que desea conectar su bot en el cuadro de diálogo que aparece.

Con esto, su bot estará disponible en el equipo de Microsoft Teams.
