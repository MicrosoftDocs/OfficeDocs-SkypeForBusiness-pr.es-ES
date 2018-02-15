---
title: Agregar bots para chats privados y canales en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: "Obtenga más información sobre cómo agregar bots en Microsoft Teams para chats privados y canales, crear bots personalizados y transferir localmente su propio bot para chats privados."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53758ae9d48ff04666e1f0e89272fca75289f0fc
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="e77a4-103">Agregar bots para chats privados y canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e77a4-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="e77a4-p101">Los bots son programas automatizados que responden a consultas u ofrecen actualizaciones y notificaciones sobre detalles que a los usuarios les resultan interesantes o sobre los que quieren mantenerse informado. Los bots permiten que los usuarios interactúen con servicios en la nube, como la administración de tareas, la programación y los sondeos, mediante conversaciones de chat en Microsoft Teams. Los bots de Microsoft Teams se crean en [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370), y los bots desarrollados con este marco se pueden habilitar fácilmente para Microsoft Teams. Para obtener más información, consulte [Habilitar características de Microsoft Teams en su organización de Office 365](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e77a4-p101">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). The bots that are developed using this framework can be enabled easily for Microsoft Teams. For more information, see [Enable Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="e77a4-p102">Actualmente, Microsoft Teams admite bots en chats privados y canales dentro de un equipo. Los administradores pueden controlar si el uso de bots está permitido o prohibido en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="e77a4-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="e77a4-111">Los bots desarrollados por la comunidad se pueden utilizar en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e77a4-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="e77a4-112">La funcionalidad del bot y la transferencia local del bot deben estar habilitadas a nivel del inquilino para que los bots personalizados puedan ser funcionales.</span><span class="sxs-lookup"><span data-stu-id="e77a4-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="e77a4-113">Los bots se pueden usar en chats privados o en canales.</span><span class="sxs-lookup"><span data-stu-id="e77a4-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="e77a4-114">Para los canales, los propietarios o los miembros del equipo pueden agregar bots.</span><span class="sxs-lookup"><span data-stu-id="e77a4-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="e77a4-115">Para obtener más información, consulte la sección "Usar bots" en [Aplicaciones y servicios](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="e77a4-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="e77a4-116">Crear bots personalizados para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e77a4-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="e77a4-p104">Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft Bot Framework. Consulte las instrucciones de [Crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber cómo puede desarrollar y publicar sus propios bots.</span><span class="sxs-lookup"><span data-stu-id="e77a4-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="e77a4-119">Al crear un bot y registrarlo en Bot Framework, puede elegir si desea publicarlo.</span><span class="sxs-lookup"><span data-stu-id="e77a4-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="e77a4-120">Si no lo publica, el bot sigue siendo privado.</span><span class="sxs-lookup"><span data-stu-id="e77a4-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="e77a4-121">También puede requerir que los usuarios tengan que iniciar sesión antes de usar el bot.</span><span class="sxs-lookup"><span data-stu-id="e77a4-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="e77a4-122">Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot.</span><span class="sxs-lookup"><span data-stu-id="e77a4-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="e77a4-123">Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.</span><span class="sxs-lookup"><span data-stu-id="e77a4-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="e77a4-124">Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="e77a4-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="e77a4-125">Transfiera localmente su propio bot para chats privados.</span><span class="sxs-lookup"><span data-stu-id="e77a4-125">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="e77a4-126">Después de crear su bot, vaya la [página ](https://go.microsoft.com/fwlink/?linkid=854374)del **Panel de bots** del bot que ha desarrollado y, en **Detalles**, copie el **identificador de aplicación de Microsoft**.![Captura de pantalla de la página de detalles de un bot con el identificador de aplicación de Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="e77a4-126">After you have created your bot, go to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and then under **Details**, copy the **Microsoft App ID**.![Screenshot of details page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span> 



2.  <span data-ttu-id="e77a4-127">En Microsoft Teams, en el panel **Chat**, seleccione el icono **Agregar chat**.</span><span class="sxs-lookup"><span data-stu-id="e77a4-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="e77a4-128">En **Para**, pegue el **identificador de aplicación de Microsoft** del bot.</span><span class="sxs-lookup"><span data-stu-id="e77a4-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="e77a4-129">![Captura de pantalla de un panel de chat con el icono de Agregar chat y la línea Para con el identificador de aplicación de Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="e77a4-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="e77a4-130">El identificador de la aplicación se resolverá con el **nombre del bot** y después podrá iniciar una conversación de chat con el bot.</span><span class="sxs-lookup"><span data-stu-id="e77a4-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
