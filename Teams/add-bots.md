---
title: Agregar bots para chats privados y canales en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: Obtenga más información sobre cómo agregar bots en Microsoft Teams para chats privados y canales, crear bots personalizados y transferir localmente su propio bot para chats privados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08417f4aafae8c7fd844cb253a889b833d0e6266
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2018
ms.locfileid: "19856031"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="2becd-103">Agregar bots para chats privados y canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2becd-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="2becd-104">Bots son programas automatizados que responden a las consultas o dar a las actualizaciones y notificaciones acerca de los usuarios obtener información detallada, busque interesantes o desean mantenerse informado acerca de.</span><span class="sxs-lookup"><span data-stu-id="2becd-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="2becd-105">Bots permiten a los usuarios interactuar con servicios de nube como administración de tareas, programación y sondeo a través de las conversaciones de chat en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2becd-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="2becd-106">Bots para Microsoft Teams se basan en el [Marco de trabajo de Microsoft Bot](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="2becd-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="2becd-107">Los bots que se desarrollan mediante este marco de trabajo se puede habilitar fácilmente para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2becd-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="2becd-108">Para obtener más información, vea [características de administración de equipos de Microsoft en su organización de Office 365](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2becd-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="2becd-p102">Actualmente, Microsoft Teams admite bots en chats privados y canales dentro de un equipo. Los administradores pueden controlar si el uso de bots está permitido o prohibido en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="2becd-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="2becd-111">Los bots desarrollados por la comunidad se pueden utilizar en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2becd-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="2becd-112">La funcionalidad del bot y la transferencia local del bot deben estar habilitadas a nivel del inquilino para que los bots personalizados puedan ser funcionales.</span><span class="sxs-lookup"><span data-stu-id="2becd-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="2becd-113">Los bots se pueden usar en chats privados o en canales.</span><span class="sxs-lookup"><span data-stu-id="2becd-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="2becd-114">Para los canales, los propietarios o los miembros del equipo pueden agregar bots.</span><span class="sxs-lookup"><span data-stu-id="2becd-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="2becd-115">Para obtener más información, consulte la sección "Usar bots" en [Aplicaciones y servicios](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="2becd-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="2becd-116">Crear bots personalizados para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2becd-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="2becd-p104">Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft Bot Framework. Consulte las instrucciones de [Crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber cómo puede desarrollar y publicar sus propios bots.</span><span class="sxs-lookup"><span data-stu-id="2becd-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="2becd-119">Al crear un bot y registrarlo en Bot Framework, puede elegir si desea publicarlo.</span><span class="sxs-lookup"><span data-stu-id="2becd-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="2becd-120">Si no lo publica, el bot sigue siendo privado.</span><span class="sxs-lookup"><span data-stu-id="2becd-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="2becd-121">También puede requerir que los usuarios tengan que iniciar sesión antes de usar el bot.</span><span class="sxs-lookup"><span data-stu-id="2becd-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="2becd-122">Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot.</span><span class="sxs-lookup"><span data-stu-id="2becd-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="2becd-123">Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.</span><span class="sxs-lookup"><span data-stu-id="2becd-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="2becd-124">Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="2becd-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="2becd-125">Transfiera localmente su propio bot para chats privados.</span><span class="sxs-lookup"><span data-stu-id="2becd-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="2becd-126">Después de haber creado el bot, vaya a la **Configuración de la aplicación** para el robot desarrollado, a continuación, en **configuración de la aplicación**, copie el valor de la opción **MicrosoftAppId** . ![Página de captura de pantalla de configuración de la aplicación para un componente con el identificador de la aplicación Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="2becd-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="2becd-127">En Microsoft Teams, en el panel **Chat**, seleccione el icono **Agregar chat**.</span><span class="sxs-lookup"><span data-stu-id="2becd-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="2becd-128">En **Para**, pegue el **identificador de aplicación de Microsoft** del bot.</span><span class="sxs-lookup"><span data-stu-id="2becd-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="2becd-129">![Captura de pantalla de un panel de chat con el icono de Agregar chat y la línea Para con el identificador de aplicación de Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="2becd-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="2becd-130">El identificador de la aplicación se resolverá con el **nombre del bot** y después podrá iniciar una conversación de chat con el bot.</span><span class="sxs-lookup"><span data-stu-id="2becd-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
