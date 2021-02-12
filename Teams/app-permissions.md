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
description: El administrador puede saber qué datos y permisos solicitan las aplicaciones de Microsoft Teams a su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739388"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="49eeb-103">Consideraciones y permisos de las aplicaciones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49eeb-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="49eeb-104">Las aplicaciones de Microsoft Teams son una forma de agregar una o varias funcionalidades en un _paquete de aplicaciones_ que se pueden instalar, actualizar y desinstalar.</span><span class="sxs-lookup"><span data-stu-id="49eeb-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="49eeb-105">Las funcionalidades incluyen:</span><span class="sxs-lookup"><span data-stu-id="49eeb-105">The capabilities include:</span></span>

- <span data-ttu-id="49eeb-106">Bots</span><span class="sxs-lookup"><span data-stu-id="49eeb-106">Bots</span></span>
- <span data-ttu-id="49eeb-107">Extensiones de mensajería</span><span class="sxs-lookup"><span data-stu-id="49eeb-107">Messaging extensions</span></span>
- <span data-ttu-id="49eeb-108">Fichas</span><span class="sxs-lookup"><span data-stu-id="49eeb-108">Tabs</span></span>
- <span data-ttu-id="49eeb-109">Conectores</span><span class="sxs-lookup"><span data-stu-id="49eeb-109">Connectors</span></span>

<span data-ttu-id="49eeb-110">Los usuarios tienen que dar su consentimiento a las aplicaciones y su administración corre a cargo de los departamentos de TI desde una perspectiva de políticas.</span><span class="sxs-lookup"><span data-stu-id="49eeb-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="49eeb-111">Sin embargo, en la mayoría de los casos, los permisos y el perfil de riesgo de una aplicación se definen mediante los permisos y perfiles de riesgo de las capacidades que contiene la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49eeb-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="49eeb-112">Por ello, en este artículo nos centramos en los permisos y las consideraciones que hay que tener en cuenta a nivel de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="49eeb-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="49eeb-113">Los permisos que se indican a continuación en mayúscula (por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE) no aparecen en la [documentación para desarrolladores de Microsoft Teams](https://aka.ms/teamsdevdocs) ni en los [permisos para Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="49eeb-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="49eeb-114">Son simplemente una descripción breve para este artículo.</span><span class="sxs-lookup"><span data-stu-id="49eeb-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="49eeb-115">Título</span><span class="sxs-lookup"><span data-stu-id="49eeb-115">Title</span></span>   | <span data-ttu-id="49eeb-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="49eeb-116">Description</span></span>    |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="49eeb-118">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="49eeb-118">Decision point</span></span>|<ul><li><span data-ttu-id="49eeb-119">Use las tablas siguientes como guía para comprender qué permisos solicitan las aplicaciones que está investigando.</span><span class="sxs-lookup"><span data-stu-id="49eeb-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/><span data-ttu-id="49eeb-121">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="49eeb-121">Next step</span></span>|<ul><li><span data-ttu-id="49eeb-122">Investigue sobre la aplicación o el servicio para decidir si desea permitir el acceso a ella dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="49eeb-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="49eeb-123">Por ejemplo, los bots envían y reciben mensajes de usuarios y, excepto los bots personalizados de empresa, están ubicados fuera del límite de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="49eeb-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="49eeb-124">Por lo tanto, cualquier aplicación que incluya un bot requiere esos permisos y tiene ese perfil de riesgo, como mínimo.</span><span class="sxs-lookup"><span data-stu-id="49eeb-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="49eeb-125">Consideraciones y permisos de aplicación globales</span><span class="sxs-lookup"><span data-stu-id="49eeb-125">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="49eeb-126">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="49eeb-126">Required permissions</span></span>

<span data-ttu-id="49eeb-127">Ninguna</span><span class="sxs-lookup"><span data-stu-id="49eeb-127">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="49eeb-128">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="49eeb-128">Optional permissions</span></span>

<span data-ttu-id="49eeb-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="49eeb-129">None</span></span>

### <a name="considerations"></a><span data-ttu-id="49eeb-130">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="49eeb-130">Considerations</span></span>

- <span data-ttu-id="49eeb-131">Una aplicación debe revelar los datos que usa y para qué se usan en sus términos de uso y vínculos a la directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="49eeb-131">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="49eeb-132">[El consentimiento específico de](resource-specific-consent.md) los recursos proporciona un conjunto de permisos que las aplicaciones pueden solicitar, que aparece en la pantalla de instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49eeb-132">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="49eeb-133">Para obtener más información sobre los permisos de consentimiento específicos de recursos, consulte [Referencia de permisos de Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="49eeb-133">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="49eeb-134">Es posible que las aplicaciones también necesiten permisos que no son permisos de consentimiento específicos de recursos.</span><span class="sxs-lookup"><span data-stu-id="49eeb-134">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="49eeb-135">Una vez instalada una aplicación, es posible que la aplicación solicite permisos de Graph a través de un aviso de consentimiento.</span><span class="sxs-lookup"><span data-stu-id="49eeb-135">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="49eeb-136">Para obtener más información, consulta [Descripción de las experiencias de consentimiento de aplicaciones](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="49eeb-136">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="49eeb-137">Puedes configurar los permisos de la API y el consentimiento en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="49eeb-137">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="49eeb-138">Para obtener más información, consulte el marco [de consentimiento de Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="49eeb-138">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="49eeb-139">Bots y extensiones de mensajería</span><span class="sxs-lookup"><span data-stu-id="49eeb-139">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="49eeb-140">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="49eeb-140">Required permissions</span></span>

- <span data-ttu-id="49eeb-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="49eeb-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="49eeb-142">El bot puede recibir mensajes de los usuarios y responderles. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="49eeb-142">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="49eeb-143">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="49eeb-143">POST_MESSAGE_USER.</span></span> <span data-ttu-id="49eeb-144">Después de que un usuario haya enviado un mensaje a un bot, este puede enviar mensajes directos al usuario (también denominados mensajes proactivos *en* cualquier momento).</span><span class="sxs-lookup"><span data-stu-id="49eeb-144">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="49eeb-145">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="49eeb-145">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="49eeb-146">Los bots agregados a los equipos pueden obtener una lista de nombres e iDs de los canales de un equipo.</span><span class="sxs-lookup"><span data-stu-id="49eeb-146">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="49eeb-147">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="49eeb-147">Optional permissions</span></span>

- <span data-ttu-id="49eeb-148">IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="49eeb-148">IDENTITY.</span></span> <span data-ttu-id="49eeb-149">Cuando se usa en un canal, los bots de la aplicación pueden acceder a la información básica de identidad de los miembros del equipo (nombre, apellidos, nombre principal de usuario [UPN], dirección de correo electrónico). cuando se usa en un chat personal o grupal, el bot puede acceder a la misma información para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="49eeb-149">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="49eeb-150">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="49eeb-150">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="49eeb-151">Permite a los bots de una aplicación enviar mensajes directos (proactivos) a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha hablado con el bot antes.</span><span class="sxs-lookup"><span data-stu-id="49eeb-151">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="49eeb-152">Los siguientes no son permisos explícitos, pero están implícitos por RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en los que se pueden usar los bots, declarados en el manifiesto:</span><span class="sxs-lookup"><span data-stu-id="49eeb-152">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="49eeb-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="49eeb-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="49eeb-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="49eeb-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="49eeb-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="49eeb-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="49eeb-156">SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controla si un bot puede enviar y recibir archivos en un chat personal (aún no se admite en chats grupales o canales).</span><span class="sxs-lookup"><span data-stu-id="49eeb-156">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="49eeb-157">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="49eeb-157">Considerations</span></span>

- <span data-ttu-id="49eeb-158">Los bots solo tienen acceso a los equipos a los que se han agregado o a los usuarios que los han instalado.</span><span class="sxs-lookup"><span data-stu-id="49eeb-158">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="49eeb-159">Los bots solo reciben mensajes en los que los usuarios los mencionan explícitamente.</span><span class="sxs-lookup"><span data-stu-id="49eeb-159">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="49eeb-160">Estos datos dejan de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="49eeb-160">This data leaves the corporate network.</span></span>

- <span data-ttu-id="49eeb-161">Los bots solo pueden responder a las conversaciones en las que se les menciona.</span><span class="sxs-lookup"><span data-stu-id="49eeb-161">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="49eeb-162">Después de que un usuario haya chateado con un bot, si el bot almacena el id. de ese usuario, puede enviarle mensajes directos en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="49eeb-162">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="49eeb-163">Es posible que los mensajes de bot contengan vínculos a sitios de suplantación de identidad o malware, pero el usuario, el administrador de inquilinos o Microsoft puede bloquear los bots de forma global.</span><span class="sxs-lookup"><span data-stu-id="49eeb-163">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="49eeb-164">Un bot puede recuperar (y puede almacenar) información de identidad muy básica para los miembros del equipo a los que se ha agregado la aplicación, o para usuarios individuales en chats personales o grupales.</span><span class="sxs-lookup"><span data-stu-id="49eeb-164">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="49eeb-165">Para obtener más información sobre estos usuarios, el bot debe requerir que inicien sesión en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="49eeb-165">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="49eeb-166">Los bots pueden recuperar (y podrían almacenar) la lista de canales de un equipo; estos datos dejan de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="49eeb-166">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="49eeb-167">Cuando se envía un archivo a un bot, este abandona la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="49eeb-167">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="49eeb-168">El envío y la recepción de archivos requiere la aprobación del usuario para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="49eeb-168">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="49eeb-169">De forma predeterminada, los bots no pueden actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión. tan pronto como el usuario inicia sesión, el bot tendrá un token de acceso con el que puede realizar otras cosas.</span><span class="sxs-lookup"><span data-stu-id="49eeb-169">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="49eeb-170">Exactamente lo que son esas cosas adicionales depende del bot y de dónde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada y puede tener su propio conjunto https://apps.dev.microsoft.com/ de permisos.</span><span class="sxs-lookup"><span data-stu-id="49eeb-170">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="49eeb-171">Los bots se informan siempre que los usuarios se agregan a un equipo o se eliminan de él.</span><span class="sxs-lookup"><span data-stu-id="49eeb-171">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="49eeb-172">Los bots no ven las direcciones IP de los usuarios ni otra información de referencia.</span><span class="sxs-lookup"><span data-stu-id="49eeb-172">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="49eeb-173">Toda la información proviene de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="49eeb-173">All information comes from Microsoft.</span></span> <span data-ttu-id="49eeb-174">(Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, la interfaz de usuario de inicio de sesión verá las direcciones IP de los usuarios y la información del referenciador).</span><span class="sxs-lookup"><span data-stu-id="49eeb-174">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="49eeb-175">Por otro lado, las extensiones de mensajería pueden ver las direcciones IP de los usuarios y la información de referencia.</span><span class="sxs-lookup"><span data-stu-id="49eeb-175">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="49eeb-176">Las instrucciones de la aplicación (y nuestro proceso de revisión de AppSource) requieren discreción al publicar mensajes de chat personales a los usuarios (mediante POST_MESSAGE_TEAM permiso) para fines válidos.</span><span class="sxs-lookup"><span data-stu-id="49eeb-176">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="49eeb-177">En caso de abuso, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear bots de forma centralizada si es necesario.</span><span class="sxs-lookup"><span data-stu-id="49eeb-177">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="49eeb-178"><sup>1</sup> Algunos bots solo envían mensajes (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="49eeb-178"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="49eeb-179">Se denominan bots de "solo notificación", pero el término no hace referencia a lo que puede o no hacer un bot, significa que el bot no desea exponer una experiencia de conversación.</span><span class="sxs-lookup"><span data-stu-id="49eeb-179">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="49eeb-180">Teams usa este campo para deshabilitar la funcionalidad en la interfaz de usuario que normalmente se habilitaría; el bot no está restringido en lo que está permitido hacer en comparación con los bots que exponen una experiencia de conversación.</span><span class="sxs-lookup"><span data-stu-id="49eeb-180">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="49eeb-181"><sup>2</sup> Se rige por la propiedad booleana supportsFiles en el objeto bot de la manifest.jsarchivo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49eeb-181"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="49eeb-182">Si un bot tiene su propio inicio de sesión, hay una segunda experiencia de consentimiento (diferente) la primera vez que el usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="49eeb-182">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="49eeb-183">Actualmente, los permisos de Azure AD asociados a cualquiera de las funcionalidades dentro de una aplicación de Teams (bot, pestaña, conector o extensión de mensajería) son completamente independientes de los permisos de Teams que se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="49eeb-183">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="49eeb-184">Pestañas</span><span class="sxs-lookup"><span data-stu-id="49eeb-184">Tabs</span></span>

<span data-ttu-id="49eeb-185">Una pestaña es un sitio web que se ejecuta en Teams.</span><span class="sxs-lookup"><span data-stu-id="49eeb-185">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="49eeb-186">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="49eeb-186">Required permissions</span></span>

<span data-ttu-id="49eeb-187">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="49eeb-187">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="49eeb-188">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="49eeb-188">Optional permissions</span></span>

<span data-ttu-id="49eeb-189">Ninguno (actualmente)</span><span class="sxs-lookup"><span data-stu-id="49eeb-189">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="49eeb-190">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="49eeb-190">Considerations</span></span>

- <span data-ttu-id="49eeb-191">El perfil de riesgo para una pestaña es casi idéntico al mismo sitio web que se ejecuta en una pestaña del explorador.</span><span class="sxs-lookup"><span data-stu-id="49eeb-191">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="49eeb-192">Una pestaña también obtiene el contexto en el que se está ejecutando, incluido el nombre de inicio de sesión y el UPN del usuario actual, el id. de objeto de Azure AD para el usuario actual, el id. del grupo de Microsoft 365 en el que reside (si es un equipo), el id. de inquilino y la configuración regional actual del usuario.</span><span class="sxs-lookup"><span data-stu-id="49eeb-192">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="49eeb-193">Sin embargo, para asignar estos id. a la información de un usuario, la pestaña tendría que hacer que el usuario inicie sesión en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="49eeb-193">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="49eeb-194">Conectores</span><span class="sxs-lookup"><span data-stu-id="49eeb-194">Connectors</span></span>

<span data-ttu-id="49eeb-195">Un conector publica mensajes en un canal cuando se producen eventos en un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="49eeb-195">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="49eeb-196">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="49eeb-196">Required permissions</span></span>

<span data-ttu-id="49eeb-197">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="49eeb-197">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="49eeb-198">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="49eeb-198">Optional permissions</span></span>

<span data-ttu-id="49eeb-199">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="49eeb-199">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="49eeb-200">Determinados conectores admiten mensajes que pueden actuar y que permiten a los usuarios publicar respuestas dirigidas en el mensaje del conector, por ejemplo, agregando una respuesta a un problema de GitHub o agregando una fecha a una tarjeta Trello.</span><span class="sxs-lookup"><span data-stu-id="49eeb-200">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="49eeb-201">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="49eeb-201">Considerations</span></span>

- <span data-ttu-id="49eeb-202">El sistema que publica los mensajes del conector no sabe quién publica los mensajes ni quién los recibe: no se revela ninguna información sobre el destinatario.</span><span class="sxs-lookup"><span data-stu-id="49eeb-202">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="49eeb-203">(Microsoft es el destinatario real, no el inquilino; Microsoft realiza la publicación real en el canal).</span><span class="sxs-lookup"><span data-stu-id="49eeb-203">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="49eeb-204">No hay datos que abandone la red corporativa cuando los mensajes de los conectores se publican en un canal.</span><span class="sxs-lookup"><span data-stu-id="49eeb-204">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="49eeb-205">Los conectores que admiten mensajes que pueden actuar (REPLYTO_CONNECTOR_MESSAGE permiso de referencia) tampoco ven la información de la dirección IP ni del autor de la referencia; esta información se envía a Microsoft y, a continuación, se enruta a los puntos de conexión HTTP previamente registrados con Microsoft en el portal Conectores.</span><span class="sxs-lookup"><span data-stu-id="49eeb-205">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="49eeb-206">Cada vez que se configura un conector para un canal, se crea una dirección URL única para esa instancia del conector.</span><span class="sxs-lookup"><span data-stu-id="49eeb-206">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="49eeb-207">Si se elimina la instancia del conector, la dirección URL ya no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="49eeb-207">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="49eeb-208">Los mensajes del conector no pueden contener archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="49eeb-208">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="49eeb-209">La dirección URL de instancia del conector debe tratarse como confidencial o secreta: cualquier persona que tenga esa dirección URL puede publicar en ella, como una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="49eeb-209">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="49eeb-210">Por lo tanto, hay cierto riesgo de correo no deseado o vínculos a sitios de suplantación de identidad o malware.</span><span class="sxs-lookup"><span data-stu-id="49eeb-210">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="49eeb-211">Si esto fuera posible, los propietarios del equipo pueden eliminar la instancia del conector.</span><span class="sxs-lookup"><span data-stu-id="49eeb-211">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="49eeb-212">Si el servicio que envía los mensajes de los conectores se ve comprometida y empieza a enviar vínculos de correo no deseado/suplantación de identidad (phishing/malware), un administrador de inquilinos puede evitar que se creen nuevas instancias de conectores y Microsoft puede bloquearlas de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="49eeb-212">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="49eeb-213">Actualmente no es posible saber qué conectores admiten mensajes que admiten acciones (REPLYTO_CONNECTOR_MESSAGE permiso).</span><span class="sxs-lookup"><span data-stu-id="49eeb-213">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="49eeb-214">Webhooks salientes</span><span class="sxs-lookup"><span data-stu-id="49eeb-214">Outgoing webhooks</span></span>

<span data-ttu-id="49eeb-215">*Los propietarios* del equipo o los miembros del equipo crean los webhooks salientes sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="49eeb-215">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="49eeb-216">No son capacidades de las aplicaciones de Teams; esta información se incluye para su integridad.</span><span class="sxs-lookup"><span data-stu-id="49eeb-216">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="49eeb-217">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="49eeb-217">Required permissions</span></span>

<span data-ttu-id="49eeb-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="49eeb-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="49eeb-219">Puede recibir mensajes de usuarios y responderles.</span><span class="sxs-lookup"><span data-stu-id="49eeb-219">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="49eeb-220">Permisos opcionales</span><span class="sxs-lookup"><span data-stu-id="49eeb-220">Optional permissions</span></span>

<span data-ttu-id="49eeb-221">Ninguna</span><span class="sxs-lookup"><span data-stu-id="49eeb-221">None</span></span>

### <a name="considerations"></a><span data-ttu-id="49eeb-222">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="49eeb-222">Considerations</span></span>

- <span data-ttu-id="49eeb-223">Los webhooks salientes son similares a los bots, pero tienen menos privilegios.</span><span class="sxs-lookup"><span data-stu-id="49eeb-223">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="49eeb-224">Deben mencionarse explícitamente, igual que los bots.</span><span class="sxs-lookup"><span data-stu-id="49eeb-224">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="49eeb-225">Cuando se registra un webhook de salida, se genera un secreto, que permite al webhook saliente comprobar que el remitente es Microsoft Teams en lugar de un atacante malintencionado.</span><span class="sxs-lookup"><span data-stu-id="49eeb-225">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="49eeb-226">Este secreto debe permanecer un secreto; cualquier persona que tenga acceso a él puede hacerse pasar por Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49eeb-226">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="49eeb-227">Si el secreto está en peligro, el webhook saliente se puede eliminar y volver a crear y se generará un nuevo secreto.</span><span class="sxs-lookup"><span data-stu-id="49eeb-227">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="49eeb-228">Aunque es posible crear un webhook saliente que no valide el secreto, se recomienda usar esta opción.</span><span class="sxs-lookup"><span data-stu-id="49eeb-228">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="49eeb-229">Aparte de recibir y responder a mensajes, los webhooks salientes no pueden hacer mucho: no pueden enviar mensajes de manera proactiva, no pueden enviar o recibir archivos, no pueden hacer nada más que los bots pueden hacer excepto recibir y responder mensajes.</span><span class="sxs-lookup"><span data-stu-id="49eeb-229">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
