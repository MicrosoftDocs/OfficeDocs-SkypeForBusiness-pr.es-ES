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
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a4b0013e3e3ca31baea21e4e733a9606f3765c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885286"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="de8a5-103">Activar o desactivar el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de8a5-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="de8a5-104">Como administrador de Office 365, debe habilitar la característica de invitado antes de que usted o los usuarios de su organización (específicamente, los propietarios de los equipos) puedan agregar a invitados.</span><span class="sxs-lookup"><span data-stu-id="de8a5-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="de8a5-105">La configuración de invitado se establece en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="de8a5-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="de8a5-106">Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="de8a5-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="de8a5-107">Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que la característica de invitado no esté habilitada o que la configuración no haya entrado aún en vigor.</span><span class="sxs-lookup"><span data-stu-id="de8a5-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de8a5-108">Para habilitar la experiencia completa de la característica de acceso de invitado, es muy importante que conozca bien la dependencia de autorización principal entre Microsoft Teams, Azure Active Directory y Office 365.</span><span class="sxs-lookup"><span data-stu-id="de8a5-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="de8a5-109">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="de8a5-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="de8a5-110">Diferencias entre el acceso de invitados y el acceso externo (federación)</span><span class="sxs-lookup"><span data-stu-id="de8a5-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="de8a5-111">Configurar el acceso de invitado en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de8a5-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="de8a5-112">Inicie sesión en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de8a5-112">Manage Teams in the Microsoft Teams admin center</span></span>

2.  <span data-ttu-id="de8a5-113">Seleccione **Configuración de toda la organización** > **Acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="de8a5-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="de8a5-114">Establezca **Permitir el acceso de invitado en Microsoft Teams** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="de8a5-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="de8a5-115">Opción Permitir el acceso de invitado en Microsoft Teams activada</span><span class="sxs-lookup"><span data-stu-id="de8a5-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="de8a5-116">Establezca los botones en **Llamadas**, **Reunión** y **Mensajería** como **Activado** o **Desactivado**, según las funciones que quiera permitir para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="de8a5-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="de8a5-117">**Realizar llamadas privadas**: cambie esta opción a **Activado** para permitir que los invitados realicen llamadas entre compañeros.</span><span class="sxs-lookup"><span data-stu-id="de8a5-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="de8a5-118">**Permitir vídeo IP**: cambie esta opción a **Activado** para permitir que los invitados usen vídeo en sus llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="de8a5-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="de8a5-119">**Modo de pantalla compartida**: esta configuración controla la disponibilidad de la pantalla compartida para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="de8a5-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="de8a5-120">Establezca esta opción como **Desactivado** para eliminar la posibilidad de que los invitados compartan sus pantallas en Teams.</span><span class="sxs-lookup"><span data-stu-id="de8a5-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="de8a5-121">Establezca esta opción como **Solicitud única** para permitir el uso compartido de aplicaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="de8a5-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="de8a5-122">Establezca esta opción como **Pantalla completa** para permitir el uso de pantalla completa compartida.</span><span class="sxs-lookup"><span data-stu-id="de8a5-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="de8a5-123">**Permitir Reunirse ahora**: establezca esta opción como **Activado** para permitir que los invitados usen la característica Reunirse ahora en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de8a5-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="de8a5-124">**Editar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados editen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="de8a5-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="de8a5-125">**Los invitados pueden eliminar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados eliminen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="de8a5-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="de8a5-126">**Chat**: establezca esta opción como **Activado** para permitir a los invitados usar el chat en Teams.</span><span class="sxs-lookup"><span data-stu-id="de8a5-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="de8a5-127">**Usar Giphy en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen Giphy en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="de8a5-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="de8a5-128">Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="de8a5-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="de8a5-129">A cada Giphy se le asigna una clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="de8a5-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="de8a5-130">**Clasificación de contenido Giphy**: seleccione una clasificación de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="de8a5-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="de8a5-131">**Permitir todo el contenido**: los invitados podrán insertar todos los Giphy en chats, independientemente de la clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="de8a5-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="de8a5-132">**Moderado**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.</span><span class="sxs-lookup"><span data-stu-id="de8a5-132">**Moderate**  This means that your users will be able to insert Giphys in chats but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="de8a5-133">**Estricto**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma estricta.</span><span class="sxs-lookup"><span data-stu-id="de8a5-133">**Strict**  This means that your users will be able to insert Giphys in chats but will be strictly restricted from adult content.</span></span>
    - <span data-ttu-id="de8a5-134">**Usar memes en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen memes en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="de8a5-134">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="de8a5-135">**Usar adhesivos en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen adhesivos en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="de8a5-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="de8a5-136">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="de8a5-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="de8a5-137">Usar PowerShell para activar o desactivar el acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="de8a5-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="de8a5-138">Descargue el módulo de PowerShell de Skype Empresarial Online en https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="de8a5-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="de8a5-139">Conecte una sesión de PowerShell al punto de conexión de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="de8a5-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="de8a5-140">Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecerlo en `$True`.</span><span class="sxs-lookup"><span data-stu-id="de8a5-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="de8a5-141">Ahora puede tener usuarios invitados en Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="de8a5-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="de8a5-142">Más información</span><span class="sxs-lookup"><span data-stu-id="de8a5-142">More information</span></span>

<span data-ttu-id="de8a5-143">Consulte el siguiente vídeo para obtener más detalles sobre el acceso de invitados:</span><span class="sxs-lookup"><span data-stu-id="de8a5-143">Watch the following videos for more details about guest access:</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="de8a5-144">Agregar invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de8a5-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
