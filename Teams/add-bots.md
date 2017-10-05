---
title: "Agregar bots para chats privados y canales en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Obtenga más información sobre cómo agregar bots en Microsoft Teams para chats privados y canales, crear bots personalizados y transferir localmente su propio bot para chats privados."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 905a105fba269aebb2b01cbccc1a47e7667ca341
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="11f2c-103">Agregar bots para chats privados y canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11f2c-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="11f2c-p101">Los bots son programas automatizados configurados para responder a consultas o para ofrecer actualizaciones y notificaciones sobre detalles que a los usuarios les resultan interesantes o de los que quieren mantenerse informado. Los bots permiten que los usuarios interactúen con servicios en la nube, como la administración de tareas, la programación y los sondeos, mediante conversaciones de chat en Microsoft Teams. Los bots de Microsoft Teams se crean en [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370), y los bots desarrollados con este marco se pueden habilitar fácilmente para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="11f2c-p101">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="11f2c-p102">Actualmente, Microsoft Teams admite bots en chats privados y canales dentro de un equipo. Los administradores pueden controlar si el uso de bots está permitido o prohibido en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="11f2c-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="11f2c-p103">Los bots desarrollados por la comunidad y que estén disponibles, se pueden aprovechar en Microsoft Teams. La funcionalidad del bot y la transferencia local del bot deben estar habilitadas a nivel del inquilino para que los bots personalizados puedan ser funcionales. Los bots se pueden usar en chats privados o en canales. Para los canales, los propietarios o los miembros del equipo pueden agregar bots.</span><span class="sxs-lookup"><span data-stu-id="11f2c-p103">Bots developed by the community and are made available, can be leveraged within Microsoft Teams. The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional. Bots can be used in private chats or in channels. For channels, team owners or members can add bots.</span></span>

<a name="add-bots-for-private-chat-and-channels"></a><span data-ttu-id="11f2c-113">Agregar bots para chats privados y canales</span><span class="sxs-lookup"><span data-stu-id="11f2c-113">Add bots for Private Chat and channels</span></span>
--------------------------------------

<span data-ttu-id="11f2c-114">Hay dos maneras de integrar un bot para los chats privados y los canales:</span><span class="sxs-lookup"><span data-stu-id="11f2c-114">There are two ways to integrate a bot for private chats and channels:</span></span>

1.  <span data-ttu-id="11f2c-p104">Instalar bots disponibles públicamente para **chats privados** o **canales**. (Esta es la primera opción).</span><span class="sxs-lookup"><span data-stu-id="11f2c-p104">Install publicly available bots for **private chat** or **channels**. (This is the first option.)</span></span>

2.  <span data-ttu-id="11f2c-117">Alternativamente, para encontrar bots, vaya a **Chat**, busque un **contacto** y haga clic en **Descubrir aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="11f2c-117">Alternatively, to find bots, navigate to **Chat**, search for a **contact,** and click **Discover apps.**</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="11f2c-118">Seleccione con qué **bot** desea tener una conversación, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="11f2c-118">Select which **Bot** you want to have a conversation with, as shown below.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  <span data-ttu-id="11f2c-119">Una vez seleccionado, proporcione los **permisos** del bot y seleccione si desea usar **bots en un chat privado** o seleccione un **equipo** en el que usarlo.</span><span class="sxs-lookup"><span data-stu-id="11f2c-119">Once selected, provide the bot **permissions,** and select whether you want to use **bots in a private chat** or select a **Team** to use it in.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  <span data-ttu-id="11f2c-p105">También puede usar un bot en el canal de un equipo. Para ello, haga clic en **Ver equipo y bots**. Aquí puede descubrir bots adicionales.</span><span class="sxs-lookup"><span data-stu-id="11f2c-p105">Alternatively, to use a bot within a channel of a team, simply click **View Team and Bots**. Here you can Discover additional bots.</span></span>

6.  <span data-ttu-id="11f2c-p106">Los bots se pueden quitar en cualquier momento de un equipo. Solo tiene que hacer clic en **Ver equipo y bots** para ver todos los bots y después **quitar** el que desee.</span><span class="sxs-lookup"><span data-stu-id="11f2c-p106">At any time, a bot can be removed from the team. Simply click **View Team and Bots,** to see all bots and then **remove** the one you’d like.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="11f2c-124">Crear bots personalizados para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11f2c-124">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="11f2c-p107">Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft Bot Framework. Consulte las instrucciones de [Crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber cómo puede desarrollar y publicar sus propios bots.</span><span class="sxs-lookup"><span data-stu-id="11f2c-p107">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="11f2c-p108">Cuando cree un bot y lo registre con Bot Framework, puede elegir publicarlo o no. Si no lo publica, el bot sigue siendo privado. También puede requerir que los usuarios tengan que iniciar sesión antes de bot. Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot. Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.</span><span class="sxs-lookup"><span data-stu-id="11f2c-p108">When you create a bot and register it with the Bot Framework, you can choose to publish it or not. If you don't publish it, the bot remains private. You can also require your users to log in before using the bot. Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known. See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="11f2c-132">Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="11f2c-132">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="11f2c-133">Transfiera localmente su propio bot para chats privados.</span><span class="sxs-lookup"><span data-stu-id="11f2c-133">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="11f2c-134">Una vez que haya creado su bot, vaya a la [página](https://go.microsoft.com/fwlink/?linkid=854374) del **Panel de bots** del bot que ha desarrollado y, en **Detalles**, copie el **Identificador de aplicación de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="11f2c-134">Once you have created your Bot, navigate to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and under **Details**, copy the **Microsoft App ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="11f2c-p109">En Microsoft Teams, en el panel **Chat**, seleccione el icono **Agregar chat**. En **A:,** pegue el **identificador de aplicación de Microsoft** del bot.</span><span class="sxs-lookup"><span data-stu-id="11f2c-p109">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**. For **To:,** paste your bot's **Microsoft app ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="11f2c-137">El identificador de la aplicación se resolverá con el **nombre del bot** y después podrá iniciar una conversación de chat con el bot.</span><span class="sxs-lookup"><span data-stu-id="11f2c-137">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
