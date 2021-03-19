---
title: Consideraciones y permisos de las aplicaciones de Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: El administrador puede obtener información sobre los datos y permisos que las aplicaciones de Microsoft Teams solicitan a su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1e6628467d4300130c39a3bade87919fb064a14f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874710"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="143ac-103">Consideraciones y permisos de las aplicaciones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="143ac-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="143ac-104">Las aplicaciones de Microsoft Teams son una forma de agregar una o más capacidades _a_ un paquete de aplicaciones que se puede instalar, actualizar y desinstalar.</span><span class="sxs-lookup"><span data-stu-id="143ac-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="143ac-105">Las funcionalidades incluyen:</span><span class="sxs-lookup"><span data-stu-id="143ac-105">The capabilities include:</span></span>

- <span data-ttu-id="143ac-106">Bots</span><span class="sxs-lookup"><span data-stu-id="143ac-106">Bots</span></span>
- <span data-ttu-id="143ac-107">Extensiones de mensajería</span><span class="sxs-lookup"><span data-stu-id="143ac-107">Messaging extensions</span></span>
- <span data-ttu-id="143ac-108">Pestañas</span><span class="sxs-lookup"><span data-stu-id="143ac-108">Tabs</span></span>
- <span data-ttu-id="143ac-109">Conectores</span><span class="sxs-lookup"><span data-stu-id="143ac-109">Connectors</span></span>

<span data-ttu-id="143ac-110">Los usuarios consienten las aplicaciones y las administran desde una perspectiva de directiva.</span><span class="sxs-lookup"><span data-stu-id="143ac-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="143ac-111">Sin embargo, en su mayoría, los permisos y el perfil de riesgo de una aplicación se definen por los permisos y perfiles de riesgo de las capacidades que contiene la aplicación.</span><span class="sxs-lookup"><span data-stu-id="143ac-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="143ac-112">Por lo tanto, este artículo se centra en los permisos y consideraciones en el nivel de capacidad.</span><span class="sxs-lookup"><span data-stu-id="143ac-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="143ac-113">Los permisos enumerados a continuación en [mayúsculas,](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE, no aparecen en ninguna parte de la documentación para desarrolladores de [Microsoft Teams](https://aka.ms/teamsdevdocs) ni en los permisos de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="143ac-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="143ac-114">Son simplemente una abreviada descriptiva para el propósito de este artículo.</span><span class="sxs-lookup"><span data-stu-id="143ac-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="143ac-115">Título</span><span class="sxs-lookup"><span data-stu-id="143ac-115">Title</span></span>   | <span data-ttu-id="143ac-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="143ac-116">Description</span></span>    |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="143ac-118">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="143ac-118">Decision point</span></span>|<ul><li><span data-ttu-id="143ac-119">Use las tablas siguientes como guía para comprender qué permisos solicitan las aplicaciones que está investigando.</span><span class="sxs-lookup"><span data-stu-id="143ac-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/><span data-ttu-id="143ac-121">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="143ac-121">Next step</span></span>|<ul><li><span data-ttu-id="143ac-122">Investigue la aplicación o el servicio en sí para decidir si desea permitir el acceso a ella dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="143ac-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="143ac-123">Por ejemplo, los bots envían y reciben mensajes de los usuarios y, excepto los bots personalizados empresariales, se encuentran fuera del límite de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="143ac-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="143ac-124">Por lo tanto, cualquier aplicación que incluya un bot requiere esos permisos y tiene ese perfil de riesgo, como mínimo.</span><span class="sxs-lookup"><span data-stu-id="143ac-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="143ac-125">Vea también [Solicitar permisos de dispositivo para la pestaña Microsoft Teams.](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)</span><span class="sxs-lookup"><span data-stu-id="143ac-125">See also [Request device permissions for your Microsoft Teams tab](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="143ac-126">Consideraciones y permisos globales de la aplicación</span><span class="sxs-lookup"><span data-stu-id="143ac-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="143ac-127">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="143ac-127">Required permissions</span></span>

<span data-ttu-id="143ac-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="143ac-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="143ac-129">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="143ac-129">Optional permissions</span></span>

<span data-ttu-id="143ac-130">Ninguna</span><span class="sxs-lookup"><span data-stu-id="143ac-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="143ac-131">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="143ac-131">Considerations</span></span>

- <span data-ttu-id="143ac-132">Una aplicación debe revelar qué datos usa y para qué se usan los datos en sus términos de uso y vínculos a la directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="143ac-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="143ac-133">[El consentimiento específico de los](resource-specific-consent.md) recursos proporciona un conjunto de permisos que las aplicaciones pueden solicitar, que aparece en la pantalla de instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="143ac-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="143ac-134">Para obtener más información sobre los permisos de consentimiento específicos de los recursos, vea [Referencia de permisos de Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="143ac-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="143ac-135">Las aplicaciones también pueden necesitar permisos distintos de los permisos de consentimiento específicos de los recursos.</span><span class="sxs-lookup"><span data-stu-id="143ac-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="143ac-136">Después de instalar una aplicación, es posible que la aplicación solicite permisos de Graph a través de un aviso de consentimiento.</span><span class="sxs-lookup"><span data-stu-id="143ac-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="143ac-137">Para obtener más información, vea [Descripción de las experiencias de consentimiento de aplicaciones de Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)</span><span class="sxs-lookup"><span data-stu-id="143ac-137">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="143ac-138">Puede configurar los permisos y el consentimiento de la API en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="143ac-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="143ac-139">Para obtener más información, vea [Marco de consentimiento de Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="143ac-139">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="143ac-140">Bots y extensiones de mensajería</span><span class="sxs-lookup"><span data-stu-id="143ac-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="143ac-141">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="143ac-141">Required permissions</span></span>

- <span data-ttu-id="143ac-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="143ac-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="143ac-143">El bot puede recibir mensajes de los usuarios y responderles. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="143ac-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="143ac-144">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="143ac-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="143ac-145">Después de que un usuario haya enviado un mensaje a un bot, el bot puede enviar al usuario mensajes directos (también denominados *mensajes proactivos* en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="143ac-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="143ac-146">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="143ac-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="143ac-147">Los bots agregados a los equipos pueden obtener una lista de nombres e IDs de los canales de un equipo.</span><span class="sxs-lookup"><span data-stu-id="143ac-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="143ac-148">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="143ac-148">Optional permissions</span></span>

- <span data-ttu-id="143ac-149">IDENTIDAD.</span><span class="sxs-lookup"><span data-stu-id="143ac-149">IDENTITY.</span></span> <span data-ttu-id="143ac-150">Cuando se usa en un canal, los bots de la aplicación pueden acceder a la información básica de identidad de los miembros del equipo (nombre, apellido, nombre principal de usuario [UPN], dirección de correo electrónico); cuando se usa en un chat personal o grupal, el bot puede acceder a la misma información para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="143ac-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="143ac-151">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="143ac-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="143ac-152">Permite a los bots de una aplicación enviar mensajes directos (proactivos) a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha hablado con el bot antes.</span><span class="sxs-lookup"><span data-stu-id="143ac-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="143ac-153">Los siguientes no son permisos explícitos, pero están implícitos por RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en los que se pueden usar los bots, declarados en el manifiesto:</span><span class="sxs-lookup"><span data-stu-id="143ac-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="143ac-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="143ac-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="143ac-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="143ac-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="143ac-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="143ac-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="143ac-157">SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controla si un bot puede enviar y recibir archivos en chat personal (aún no es compatible con chats grupales o canales).</span><span class="sxs-lookup"><span data-stu-id="143ac-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="143ac-158">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="143ac-158">Considerations</span></span>

- <span data-ttu-id="143ac-159">Los bots solo tienen acceso a los equipos a los que se han agregado o a los usuarios que los han instalado.</span><span class="sxs-lookup"><span data-stu-id="143ac-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="143ac-160">Los bots solo reciben mensajes en los que los usuarios los mencionan explícitamente.</span><span class="sxs-lookup"><span data-stu-id="143ac-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="143ac-161">Estos datos abandonan la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="143ac-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="143ac-162">Los bots solo pueden responder a las conversaciones en las que se les menciona.</span><span class="sxs-lookup"><span data-stu-id="143ac-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="143ac-163">Después de que un usuario haya conversado con un bot, si el bot almacena el id. de ese usuario, puede enviar mensajes directos a ese usuario en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="143ac-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="143ac-164">En teoría, es posible que los mensajes de bot contengan vínculos a sitios de suplantación de identidad (phishing) o malware, pero Microsoft puede bloquear los bots por el usuario, el administrador de inquilinos o de forma global.</span><span class="sxs-lookup"><span data-stu-id="143ac-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="143ac-165">Un bot puede recuperar (y puede almacenar) información de identidad muy básica para los miembros del equipo a los que se ha agregado la aplicación, o para usuarios individuales en chats personales o grupales.</span><span class="sxs-lookup"><span data-stu-id="143ac-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="143ac-166">Para obtener más información sobre estos usuarios, el bot debe requerir que inicien sesión en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="143ac-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="143ac-167">Los bots pueden recuperar (y pueden almacenar) la lista de canales de un equipo; estos datos abandonan la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="143ac-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="143ac-168">Cuando se envía un archivo a un bot, el archivo abandona la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="143ac-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="143ac-169">Enviar y recibir archivos requiere la aprobación del usuario para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="143ac-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="143ac-170">De forma predeterminada, los bots no tienen la capacidad de actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión; tan pronto como el usuario inicia sesión, el bot tendrá un token de acceso con el que puede hacer cosas adicionales.</span><span class="sxs-lookup"><span data-stu-id="143ac-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="143ac-171">Exactamente cuáles son esas cosas adicionales depende del bot y de dónde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada en y puede tener su propio https://apps.dev.microsoft.com/ conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="143ac-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="143ac-172">Los bots se informan siempre que se agregan o eliminan usuarios de un equipo.</span><span class="sxs-lookup"><span data-stu-id="143ac-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="143ac-173">Los bots no ven las direcciones IP de los usuarios ni otra información de referencia.</span><span class="sxs-lookup"><span data-stu-id="143ac-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="143ac-174">Toda la información proviene de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="143ac-174">All information comes from Microsoft.</span></span> <span data-ttu-id="143ac-175">(Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, la interfaz de usuario de inicio de sesión verá las direcciones IP de los usuarios e información referente).</span><span class="sxs-lookup"><span data-stu-id="143ac-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="143ac-176">Las extensiones de mensajería, por otro lado, sí ven las direcciones IP de los usuarios y la información de referencia.</span><span class="sxs-lookup"><span data-stu-id="143ac-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="143ac-177">Las directrices de la aplicación (y nuestro proceso de revisión de AppSource) requieren discreción en la publicación de mensajes de chat personales a los usuarios (mediante POST_MESSAGE_TEAM permiso) para fines válidos.</span><span class="sxs-lookup"><span data-stu-id="143ac-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="143ac-178">En caso de abuso, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear los bots de forma centralizada si es necesario.</span><span class="sxs-lookup"><span data-stu-id="143ac-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="143ac-179"><sup>1</sup> Algunos bots solo envían mensajes (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="143ac-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="143ac-180">Se denominan bots "solo notificación", pero el término no hace referencia a lo que se permite o no permite que un bot haga, significa que el bot no quiere exponer una experiencia conversacional.</span><span class="sxs-lookup"><span data-stu-id="143ac-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="143ac-181">Teams usa este campo para deshabilitar la funcionalidad de la interfaz de usuario que normalmente se habilitaría; el bot no está restringido en lo que se permite hacer en comparación con los bots que exponen una experiencia conversacional.</span><span class="sxs-lookup"><span data-stu-id="143ac-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="143ac-182"><sup>2</sup> Regido por la propiedad supportsFiles Boolean en el objeto bot del manifest.jsarchivo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="143ac-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="143ac-183">Si un bot tiene su propio inicio de sesión, hay una segunda experiencia de consentimiento diferente la primera vez que el usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="143ac-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="143ac-184">Actualmente, los permisos de Azure AD asociados a cualquiera de las capacidades de una aplicación de Teams (bot, pestaña, conector o extensión de mensajería) son completamente independientes de los permisos de Teams que se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="143ac-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="143ac-185">Pestañas</span><span class="sxs-lookup"><span data-stu-id="143ac-185">Tabs</span></span>

<span data-ttu-id="143ac-186">Una pestaña es un sitio web que se ejecuta dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="143ac-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="143ac-187">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="143ac-187">Required permissions</span></span>

<span data-ttu-id="143ac-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="143ac-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="143ac-189">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="143ac-189">Optional permissions</span></span>

<span data-ttu-id="143ac-190">Ninguno (actualmente)</span><span class="sxs-lookup"><span data-stu-id="143ac-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="143ac-191">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="143ac-191">Considerations</span></span>

- <span data-ttu-id="143ac-192">El perfil de riesgo de una pestaña es casi idéntico al mismo sitio web que se ejecuta en una pestaña del explorador.</span><span class="sxs-lookup"><span data-stu-id="143ac-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="143ac-193">Una pestaña también obtiene el contexto en el que se está ejecutando, incluido el nombre de inicio de sesión y upn del usuario actual, el id. de objeto de Azure AD para el usuario actual, el id. del grupo de Microsoft 365 en el que reside (si es un equipo), el id. de inquilino y la configuración regional actual del usuario.</span><span class="sxs-lookup"><span data-stu-id="143ac-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="143ac-194">Sin embargo, para asignar estos id. a la información de un usuario, la pestaña tendría que hacer que el usuario inicie sesión en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="143ac-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="143ac-195">Conectores</span><span class="sxs-lookup"><span data-stu-id="143ac-195">Connectors</span></span>

<span data-ttu-id="143ac-196">Un conector publica mensajes en un canal cuando se producen eventos en un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="143ac-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="143ac-197">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="143ac-197">Required permissions</span></span>

<span data-ttu-id="143ac-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="143ac-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="143ac-199">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="143ac-199">Optional permissions</span></span>

<span data-ttu-id="143ac-200">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="143ac-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="143ac-201">Algunos conectores admiten mensajes que se pueden usar, lo que permite a los usuarios publicar respuestas dirigidas al mensaje del conector, por ejemplo agregando una respuesta a un problema de GitHub o agregando una fecha a una tarjeta de Trello.</span><span class="sxs-lookup"><span data-stu-id="143ac-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="143ac-202">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="143ac-202">Considerations</span></span>

- <span data-ttu-id="143ac-203">El sistema que publica los mensajes del conector no sabe a quién se publica o quién recibe los mensajes: no se revela información sobre el destinatario.</span><span class="sxs-lookup"><span data-stu-id="143ac-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="143ac-204">(Microsoft es el destinatario real, no el inquilino; Microsoft realiza la publicación real en el canal).</span><span class="sxs-lookup"><span data-stu-id="143ac-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="143ac-205">No hay datos que abandone la red corporativa cuando los mensajes del conector se publican en un canal.</span><span class="sxs-lookup"><span data-stu-id="143ac-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="143ac-206">Los conectores que admiten mensajes que se pueden usar (REPLYTO_CONNECTOR_MESSAGE permiso) tampoco ven la información de la dirección IP y del remitente; esta información se envía a Microsoft y, a continuación, se enruta a puntos de conexión HTTP que se registraron previamente con Microsoft en el portal conectores.</span><span class="sxs-lookup"><span data-stu-id="143ac-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="143ac-207">Cada vez que se configura un conector para un canal, se crea una dirección URL única para esa instancia del conector.</span><span class="sxs-lookup"><span data-stu-id="143ac-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="143ac-208">Si se elimina esa instancia del conector, la dirección URL ya no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="143ac-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="143ac-209">Los mensajes del conector no pueden contener datos adjuntos de archivo.</span><span class="sxs-lookup"><span data-stu-id="143ac-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="143ac-210">La dirección URL de la instancia del conector debe tratarse como secreta/confidencial: cualquier persona que tenga esa dirección URL puede publicarla, como una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="143ac-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="143ac-211">Por lo tanto, existe algún riesgo de correo no deseado o vínculos a sitios de suplantación de identidad (phishing) o malware.</span><span class="sxs-lookup"><span data-stu-id="143ac-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="143ac-212">Si esto sucediera, los propietarios de los equipos pueden eliminar la instancia del conector.</span><span class="sxs-lookup"><span data-stu-id="143ac-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="143ac-213">Si el servicio que envía los mensajes del conector se pone en peligro y empieza a enviar vínculos de correo no deseado,phishing/malware, un administrador de inquilinos puede impedir que se creen nuevas instancias de conector y Microsoft puede bloquearlas de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="143ac-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="143ac-214">Actualmente no es posible saber qué conectores admiten mensajes de acción (REPLYTO_CONNECTOR_MESSAGE permisos).</span><span class="sxs-lookup"><span data-stu-id="143ac-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="143ac-215">Webhooks salientes</span><span class="sxs-lookup"><span data-stu-id="143ac-215">Outgoing webhooks</span></span>

<span data-ttu-id="143ac-216">*Los webhooks salientes* se crean sobre la marcha por los propietarios del equipo o los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="143ac-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="143ac-217">No son capacidades de las aplicaciones de Teams; esta información se incluye para su integridad.</span><span class="sxs-lookup"><span data-stu-id="143ac-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="143ac-218">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="143ac-218">Required permissions</span></span>

<span data-ttu-id="143ac-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="143ac-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="143ac-220">Puede recibir mensajes de los usuarios y responderles.</span><span class="sxs-lookup"><span data-stu-id="143ac-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="143ac-221">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="143ac-221">Optional permissions</span></span>

<span data-ttu-id="143ac-222">Ninguna</span><span class="sxs-lookup"><span data-stu-id="143ac-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="143ac-223">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="143ac-223">Considerations</span></span>

- <span data-ttu-id="143ac-224">Los webhooks salientes son similares a los bots, pero tienen menos privilegios.</span><span class="sxs-lookup"><span data-stu-id="143ac-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="143ac-225">Deben mencionarse explícitamente, igual que los bots.</span><span class="sxs-lookup"><span data-stu-id="143ac-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="143ac-226">Cuando se registra un webhook saliente, se genera un secreto, que permite al webhook saliente comprobar que el remitente es Microsoft Teams en lugar de un atacante malintencionado.</span><span class="sxs-lookup"><span data-stu-id="143ac-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="143ac-227">Este secreto debe seguir siendo un secreto; cualquier persona que tenga acceso a él puede suplantar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="143ac-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="143ac-228">Si el secreto está en peligro, el webhook saliente se puede eliminar y volver a crear, y se generará un nuevo secreto.</span><span class="sxs-lookup"><span data-stu-id="143ac-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="143ac-229">Aunque es posible crear un webhook saliente que no valide el secreto, se recomienda no hacerlo.</span><span class="sxs-lookup"><span data-stu-id="143ac-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="143ac-230">Además de recibir y responder a mensajes, los webhooks salientes no pueden hacer mucho: no pueden enviar mensajes de forma proactiva, no pueden enviar ni recibir archivos, no pueden hacer nada más que los bots puedan hacer excepto recibir y responder a mensajes.</span><span class="sxs-lookup"><span data-stu-id="143ac-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
