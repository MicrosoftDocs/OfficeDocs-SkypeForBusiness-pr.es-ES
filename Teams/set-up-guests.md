---
title: Activar o desactivar el acceso de invitado a Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Active o desactive el acceso de invitado en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: af8cb3f6c8ba764bfd813b9d65479404dfbf1983
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462447"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="49907-103">Activar o desactivar el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49907-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="49907-104">Como administrador de Office 365, debe habilitar la característica de invitado antes de que usted o los usuarios de su organización (específicamente, los propietarios de los equipos) puedan agregar a invitados.</span><span class="sxs-lookup"><span data-stu-id="49907-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="49907-105">La configuración de invitado se establece en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49907-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="49907-106">Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="49907-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="49907-107">Si un usuario ve el mensaje "Póngase en contacto con el administrador" al intentar agregar un invitado a su equipo, es probable que todavía no se ha habilitado la característica de invitado o que la configuración no es efectiva todavía.</span><span class="sxs-lookup"><span data-stu-id="49907-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49907-108">Para habilitar la experiencia completa de la característica de acceso de invitado, es muy importante que conozca bien la dependencia de autorización principal entre Microsoft Teams, Azure Active Directory y Office 365.</span><span class="sxs-lookup"><span data-stu-id="49907-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="49907-109">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="49907-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="49907-110">Acceso de invitado frente a acceso externo (federación de)</span><span class="sxs-lookup"><span data-stu-id="49907-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="49907-111">Configurar el acceso de invitado en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49907-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="49907-112">Inicie sesión en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49907-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="49907-113">Seleccione **configuración de toda la organización** > **acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="49907-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="49907-114">Configurar el conmutador de alternancia de **Permitir el acceso de invitado en los equipos de Microsoft** **activado**.</span><span class="sxs-lookup"><span data-stu-id="49907-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="49907-115">Permitir modificador de acceso de Invitado activado</span><span class="sxs-lookup"><span data-stu-id="49907-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="49907-116">Establecer el alterna en **mensajería** , **reunión**y **llamada**a **activado** o **desactivado**, dependiendo de las capacidades que desea permitir para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="49907-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="49907-117">**Realizar llamadas privadas** – activar esta opción **en** para permitir que los invitados realizar llamadas de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="49907-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="49907-118">**Permitir IP vídeo** - activar esta opción **en** para permitir que los invitados a usar vídeo en sus llamadas y las reuniones.</span><span class="sxs-lookup"><span data-stu-id="49907-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="49907-119">**Modo de uso compartido de pantalla** : esta configuración controla la disponibilidad de pantalla de uso compartido para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="49907-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="49907-120">Habilite esta configuración a **deshabilitado** para quitar la capacidad de los invitados a compartir sus pantallas en los equipos.</span><span class="sxs-lookup"><span data-stu-id="49907-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="49907-121">Habilite esta configuración a **única aplicación** para permitir el uso compartido de aplicaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="49907-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="49907-122">Habilite esta configuración a **pantalla completa** para permitir el uso compartido de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="49907-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="49907-123">**Permitir Reunirse ahora** – activar esta opción **en** para permitir que los invitados a usar la característica Reunirse ahora en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49907-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="49907-124">**Editar los mensajes enviados** : activar esta opción **en** para permitir que los invitados editar los mensajes envió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="49907-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="49907-125">**Los invitados pueden eliminar los mensajes enviados** : activar esta opción **en** para permitir que los invitados eliminar los mensajes envió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="49907-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="49907-126">**Chat** – activar esta opción **en** para dar invitados de la capacidad de usar chat en los equipos.</span><span class="sxs-lookup"><span data-stu-id="49907-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="49907-127">**Use Giphys en las conversaciones** – activar esta opción **en** para permitir que los invitados a usar Giphys en las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="49907-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="49907-128">Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="49907-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="49907-129">A cada Giphy se le asigna una clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="49907-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="49907-130">**Clasificación de contenido Giphy** – seleccionar una clasificación de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="49907-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="49907-131">**Permitir todo el contenido** - invitados podrán insertar todos los Giphys en los chats, independientemente de la clasificación del contenido.</span><span class="sxs-lookup"><span data-stu-id="49907-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="49907-132">**Moderado** - invitados podrán insertar Giphys en los chats, pero se limitará moderadamente de contenido para adultos.</span><span class="sxs-lookup"><span data-stu-id="49907-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="49907-133">**Strict** – invitados podrán insertar Giphys en los chats, pero se limitará estrictamente de inserción de contenido para adultos.</span><span class="sxs-lookup"><span data-stu-id="49907-133">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="49907-134">**Use Memes en las conversaciones** - activar esta opción **en** para permitir que los invitados a usar Memes en las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="49907-134">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="49907-135">**Usar pegatinas en conversaciones** – activar esta opción **en** para permitir que los invitados a usar pegatinas en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="49907-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="49907-136">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="49907-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="49907-137">Uso de PowerShell para activar o desactivar el acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="49907-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="49907-138">Descargar el Skype para el módulo de PowerShell en línea de negocio dehttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="49907-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="49907-139">Conectar una sesión de PowerShell para la Skype de extremo de negocio en línea.</span><span class="sxs-lookup"><span data-stu-id="49907-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="49907-140">Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecer en `$True`.</span><span class="sxs-lookup"><span data-stu-id="49907-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="49907-141">Ahora puede tener los usuarios invitados en los equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="49907-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="49907-142">Más información</span><span class="sxs-lookup"><span data-stu-id="49907-142">More information</span></span>

<span data-ttu-id="49907-143">Vea el siguiente vídeo para obtener más detalles sobre el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="49907-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="49907-144">Agregar invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49907-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
