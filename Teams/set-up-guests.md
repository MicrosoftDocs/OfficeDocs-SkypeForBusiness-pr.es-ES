---
title: Activar o desactivar el acceso de invitado a Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Active o desactive el acceso de invitado en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498124"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="7ddb4-103">Activar o desactivar el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ddb4-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="7ddb4-104">Como administrador de Office 365, debe habilitar la característica de invitado antes de que usted o los usuarios de su organización (específicamente, los propietarios de los equipos) puedan agregar a invitados.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="7ddb4-105">La configuración de invitado se establece en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="7ddb4-106">Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="7ddb4-107">Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que la característica de invitado no esté habilitada o que la configuración no haya entrado aún en vigor.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="7ddb4-108">Para habilitar la experiencia completa de la característica de acceso de invitado, es muy importante que conozca bien la dependencia de autorización principal entre Microsoft Teams, Azure Active Directory y Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="7ddb4-109">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="7ddb4-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="7ddb4-110">Configurar el acceso de invitado en los equipos & Skype para centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="7ddb4-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="7ddb4-111">Inicie sesión en los equipos de & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="7ddb4-112">Seleccione **configuración de toda la organización** > **acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="7ddb4-113">Configurar el conmutador de alternancia de **Permitir el acceso de invitado en los equipos de Microsoft** **activado**.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="7ddb4-114">Permitir modificador de acceso de Invitado activado</span><span class="sxs-lookup"><span data-stu-id="7ddb4-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="7ddb4-115">Establecer el alterna para **llamar a**, **reuniones**y **mensajería** a **activado** o **desactivado**, según el acceso que desea permitir.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-115">Set the toggles for **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the access you want to allow.</span></span>

5.  <span data-ttu-id="7ddb4-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-116">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="7ddb4-117">Uso de PowerShell para activar o desactivar el acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="7ddb4-117">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="7ddb4-118">Descargar el Skype para el módulo de PowerShell en línea de negocio dehttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="7ddb4-118">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="7ddb4-119">Conectar una sesión de PowerShell para la Skype de extremo de negocio en línea.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-119">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="7ddb4-120">Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecer en `$True`.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="7ddb4-121">Ahora puede tener los usuarios invitados en los equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-121">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="7ddb4-122">Más información</span><span class="sxs-lookup"><span data-stu-id="7ddb4-122">More information</span></span>

<span data-ttu-id="7ddb4-123">Vea el siguiente vídeo para obtener más detalles sobre el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="7ddb4-123">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="7ddb4-124">Agregar invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ddb4-124">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
