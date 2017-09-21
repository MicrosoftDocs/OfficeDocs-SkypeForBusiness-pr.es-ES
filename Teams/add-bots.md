---
title: "Agregar bots para chats privados y canales en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: tutorial
ms.service: msteams
description: "Obtenga más información sobre cómo agregar bots en Microsoft Teams para chats privados y canales, crear bots personalizados y transferir localmente su propio bot para chats privados."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5ce0886a8bf509de53f7956a76b8ba503989aa14
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Agregar bots para chats privados y canales en Microsoft Teams
==========================================================

Los bots son programas automatizados configurados para responder a consultas o para ofrecer actualizaciones y notificaciones sobre detalles que a los usuarios les resultan interesantes o de los que quieren mantenerse informado. Los bots permiten que los usuarios interactúen con servicios en la nube, como la administración de tareas, la programación y los sondeos, mediante conversaciones de chat en Microsoft Teams. Los bots de Microsoft Teams se crean en [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370), y los bots desarrollados con este marco se pueden habilitar fácilmente para Microsoft Teams.

Actualmente, Microsoft Teams admite bots en chats privados y canales dentro de un equipo. Los administradores pueden controlar si el uso de bots está permitido o prohibido en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span>

Los bots desarrollados por la comunidad y que estén disponibles, se pueden aprovechar en Microsoft Teams. La funcionalidad del bot y la transferencia local del bot deben estar habilitadas a nivel del inquilino para que los bots personalizados puedan ser funcionales. Los bots se pueden usar en chats privados o en canales. Para los canales, los propietarios o los miembros del equipo pueden agregar bots.

<a name="add-bots-for-private-chat-and-channels"></a>Agregar bots para chats privados y canales
--------------------------------------

Hay dos maneras de integrar un bot para los chats privados y los canales:

1.  Instalar bots disponibles públicamente para **chats privados** o **canales**. (Esta es la primera opción).

2.  Alternativamente, para encontrar bots, vaya a **Chat**, busque un **contacto** y haga clic en **Descubrir aplicaciones**.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  Seleccione con qué **bot** desea tener una conversación, tal como se muestra a continuación.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  Una vez seleccionado, proporcione los **permisos** del bot y seleccione si desea usar **bots en un chat privado** o seleccione un **equipo** en el que usarlo.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  También puede usar un bot en el canal de un equipo. Para ello, haga clic en **Ver equipo y bots**. Aquí puede descubrir bots adicionales.

6.  Los bots se pueden quitar en cualquier momento de un equipo. Solo tiene que hacer clic en **Ver equipo y bots** para ver todos los bots y después **quitar** el que desee.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a>Crear bots personalizados para Microsoft Teams
--------------------------------------

Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft Bot Framework. Consulte las instrucciones de [Crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber cómo puede desarrollar y publicar sus propios bots.

Cuando cree un bot y lo registre con Bot Framework, puede elegir publicarlo o no. Si no lo publica, el bot sigue siendo privado. También puede requerir que los usuarios tengan que iniciar sesión antes de bot. Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot. Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.

Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.

<a name="side-load-your-own-bot-for-private-chat"></a>Transfiera localmente su propio bot para chats privados.
---------------------------------------

1.  Una vez que haya creado su bot, vaya a la [página](https://go.microsoft.com/fwlink/?linkid=854374) del **Panel de bots** del bot que ha desarrollado y, en **Detalles**, copie el **Identificador de aplicación de Microsoft**.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  En Microsoft Teams, en el panel **Chat**, seleccione el icono **Agregar chat**. En **A:,** pegue el **identificador de aplicación de Microsoft** del bot.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  El identificador de la aplicación se resolverá con el **nombre del bot** y después podrá iniciar una conversación de chat con el bot.
