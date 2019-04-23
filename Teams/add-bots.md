---
title: Agregar bots para chats privados y canales en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: d2b651e627f2b9375023984883562b1eaa696b1c
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959173"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Agregar bots para chats privados y canales en Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Los bots son programas automatizados que responden a las consultas o dan actualizaciones y notificaciones sobre detalles que puedan resultar interesantes para los usuarios o sobre los que quieran mantenerse informados. Bots permiten a los usuarios interactuar con servicios de nube como administración de tareas, programación y sondeo a través de las conversaciones de chat en Microsoft Teams. Bots para Microsoft Teams se basan en el [Marco de trabajo de Microsoft Bot](https://go.microsoft.com/fwlink/?linkid=854370). Los bots que se desarrollan mediante este marco de trabajo se puede habilitar fácilmente para Microsoft Teams. Para obtener más información, vea [configuración de administración de equipos de Microsoft para su organización](enable-features-office-365.md).

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

<a name="side-load-your-bot-for-channels"></a>Lado cargar su bot de canales
-----------------------------------

Si desea compartir su bot con sus compañeros, aquí es cómo agregar a los canales de diferentes equipos:

1. Cuando haya [creado un paquete de aplicación para su bot](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/apps/apps-upload), abra equipos y busque el equipo en el que se podrá ser lado carga el robot.
2. Seleccione **más** (...) junto al nombre del equipo.
3. Seleccione **Administrar equipo** y, a continuación, seleccione la pestaña de **aplicaciones** .
4. En la parte inferior derecha de la pantalla, seleccione **carga una aplicación personalizada**.
5. Vaya a la ubicación del paquete de aplicación, selecciónelo y, a continuación, haga clic en **Abrir**.
