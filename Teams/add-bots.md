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
ms.openlocfilehash: a4e921ea668fc59b520fdb068355db82bfe24481
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400541"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="58ae1-103">Agregar bots para chats privados y canales en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58ae1-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="58ae1-104">Los bots son programas automatizados que responden a las consultas o dan actualizaciones y notificaciones sobre detalles que puedan resultar interesantes para los usuarios o sobre los que quieran mantenerse informados.</span><span class="sxs-lookup"><span data-stu-id="58ae1-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="58ae1-105">Bots permiten a los usuarios interactuar con servicios de nube como administración de tareas, programación y sondeo a través de las conversaciones de chat en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="58ae1-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="58ae1-106">Bots para Microsoft Teams se basan en el [Marco de trabajo de Microsoft Bot](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="58ae1-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="58ae1-107">Los bots que se desarrollan mediante este marco de trabajo se puede habilitar fácilmente para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="58ae1-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="58ae1-108">Para obtener más información, vea [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="58ae1-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="58ae1-p102">Actualmente, Microsoft Teams admite bots en chats privados y canales dentro de un equipo. Los administradores pueden controlar si el uso de bots está permitido o prohibido en el inquilino de Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="58ae1-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="58ae1-111">Los bots desarrollados por la comunidad se pueden utilizar en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="58ae1-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="58ae1-112">La funcionalidad del bot y la transferencia local del bot deben estar habilitadas a nivel del inquilino para que los bots personalizados puedan ser funcionales.</span><span class="sxs-lookup"><span data-stu-id="58ae1-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="58ae1-113">Los bots se pueden usar en chats privados o en canales.</span><span class="sxs-lookup"><span data-stu-id="58ae1-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="58ae1-114">Para los canales, los propietarios o los miembros del equipo pueden agregar bots.</span><span class="sxs-lookup"><span data-stu-id="58ae1-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="58ae1-115">Para obtener más información, consulte la sección "Usar bots" en [Aplicaciones y servicios](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="58ae1-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="58ae1-116">Crear bots personalizados para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58ae1-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="58ae1-p104">Puede crear fácilmente un bot que se integre en sus aplicaciones LOB mediante Microsoft Bot Framework. Consulte las instrucciones de [Crear y probar un bot para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber cómo puede desarrollar y publicar sus propios bots.</span><span class="sxs-lookup"><span data-stu-id="58ae1-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="58ae1-119">Al crear un bot y registrarlo en Bot Framework, puede elegir si desea publicarlo.</span><span class="sxs-lookup"><span data-stu-id="58ae1-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="58ae1-120">Si no lo publica, el bot sigue siendo privado.</span><span class="sxs-lookup"><span data-stu-id="58ae1-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="58ae1-121">También puede requerir que los usuarios tengan que iniciar sesión antes de usar el bot.</span><span class="sxs-lookup"><span data-stu-id="58ae1-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="58ae1-122">Si el inicio de sesión es obligatorio, solo los empleados de la organización podrán acceder al bot, aunque se conozca el identificador de la aplicación del bot.</span><span class="sxs-lookup"><span data-stu-id="58ae1-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="58ae1-123">Consulte [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) en GitHub para ver un ejemplo de código de cómo autenticar a los usuarios con Active Directory mediante bots.</span><span class="sxs-lookup"><span data-stu-id="58ae1-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="58ae1-124">Los bots se pueden probar con [emulador de Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) antes de que implementen en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="58ae1-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="58ae1-125">Transfiera localmente su propio bot para chats privados.</span><span class="sxs-lookup"><span data-stu-id="58ae1-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="58ae1-126">Después de haber creado el bot, vaya a la **Configuración de la aplicación** para el robot desarrollado, a continuación, en **configuración de la aplicación**, copie el valor de la opción **MicrosoftAppId** . ![Página de captura de pantalla de configuración de la aplicación para un componente con el identificador de la aplicación Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="58ae1-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="58ae1-127">En Microsoft Teams, en el panel **Chat**, seleccione el icono **Agregar chat**.</span><span class="sxs-lookup"><span data-stu-id="58ae1-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="58ae1-128">En **Para**, pegue el **identificador de aplicación de Microsoft** del bot.</span><span class="sxs-lookup"><span data-stu-id="58ae1-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="58ae1-129">![Captura de pantalla de un panel de chat con el icono de Agregar chat y la línea Para con el identificador de aplicación de Microsoft resaltado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="58ae1-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="58ae1-130">El identificador de la aplicación se resolverá con el **nombre del bot** y después podrá iniciar una conversación de chat con el bot.</span><span class="sxs-lookup"><span data-stu-id="58ae1-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="58ae1-131">Lado cargar su bot de canales</span><span class="sxs-lookup"><span data-stu-id="58ae1-131">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="58ae1-132">Si desea compartir su bot con sus compañeros, aquí es cómo agregar a los canales de diferentes equipos:</span><span class="sxs-lookup"><span data-stu-id="58ae1-132">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="58ae1-133">Cuando haya [creado un paquete de aplicación para su bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra equipos y busque el equipo en el que se podrá ser lado carga el robot.</span><span class="sxs-lookup"><span data-stu-id="58ae1-133">After you have [created an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="58ae1-134">Agregar **[Aplicación Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, aplicación a los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="58ae1-134">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Microsoft Teams.</span></span>
3. <span data-ttu-id="58ae1-135">En aplicación Studio, seleccione la ficha **Editor del manifiesto** ![de manifiesto de la captura de pantalla de ficha del Editor.](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="58ae1-135">In App Studio, select the **Manifest Editor** Tab. ![Manifest Editor Tab Screenshot.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="58ae1-136">Para agregar su bot, en funciones, seleccione bot y elegido agregar un componente existente, a continuación, se tiene la opción de seleccionar un componente existente en el de una lista o escriba el identificador de uno de los bots existentes.</span><span class="sxs-lookup"><span data-stu-id="58ae1-136">To add your bot, In capabilities, select bot and chose to add an existing bot, then you will have the option to chose an existing bot from a drop or enter the Id of one of your existing bots.</span></span>
<span data-ttu-id="58ae1-137">![Seleccione su bot ya creado.](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="58ae1-137">![Select your bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="58ae1-138">Vaya a la ubicación del paquete de aplicación, selecciónelo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="58ae1-138">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="58ae1-139">Seleccione nombre de su bot (no olvide comprobar la casilla de verificación "Equipo" en la sección ámbito)</span><span class="sxs-lookup"><span data-stu-id="58ae1-139">Select your bot's name (Don't forget to check the "Team" checkbox under the scope section)</span></span>
7. <span data-ttu-id="58ae1-140">Seleccione la prueba y distribuir la opción.</span><span class="sxs-lookup"><span data-stu-id="58ae1-140">Select the Test and distribute option.</span></span>
8. <span data-ttu-id="58ae1-141">Seleccione el equipo donde desea conectar su bot a en el cuadro de diálogo que aparece.</span><span class="sxs-lookup"><span data-stu-id="58ae1-141">Select the team where you wish to connect your bot to in the dialog which pops up.</span></span>

<span data-ttu-id="58ae1-142">Con esto, su bot estará disponible en el equipo de su Team Microsoft.</span><span class="sxs-lookup"><span data-stu-id="58ae1-142">With this, your bot will be available in your Microsoft Team's team.</span></span>
