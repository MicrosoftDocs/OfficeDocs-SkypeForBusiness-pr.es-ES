---
title: Mover usuarios locales a Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Obtenga información sobre cómo mover usuarios a Skype Empresarial Online.
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305984"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="6bda9-103">Mover usuarios locales a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6bda9-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="6bda9-104">Después de mover un usuario local a Skype Empresarial Online, el usuario interactúa con Skype Empresarial Online para su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6bda9-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="6bda9-105">Los contactos que existían localmente estarán disponibles en Skype Empresarial Online y las reuniones existentes que el usuario haya organizado para el futuro se actualizarán para que los vínculos apunten a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6bda9-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="6bda9-106">Si el usuario está habilitado para Audioconferencia, las reuniones también incluirán coordenadas de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6bda9-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="6bda9-107">Para mover usuarios de un entorno local a Skype Empresarial Online, use el cmdlet Move-CsUser o el Panel de control de Skype Empresarial Server, que son herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="6bda9-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="6bda9-108">Antes de mover usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube.</span><span class="sxs-lookup"><span data-stu-id="6bda9-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="6bda9-109">En preparación para la próxima retirada de Skype Empresarial Online, Microsoft simplificará la forma en que las organizaciones se mueven a Teams en un futuro próximo y ya no será posible pasar a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6bda9-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future and it will no longer be possible to move to Skype for Business Online.</span></span>  <span data-ttu-id="6bda9-110">Una vez que estos cambios estén disponibles, al mover un usuario de local a la nube, los usuarios se asignarán automáticamente al modo TeamsOnly y sus reuniones de locales se convertirán automáticamente Teams reuniones Teams, igual que si se hubiera especificado el modificador, independientemente de si el modificador se ha especificado `-MoveToTeams` realmente.</span><span class="sxs-lookup"><span data-stu-id="6bda9-110">Once these changes are made available, when moving a user from on-premises to the cloud, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="6bda9-111">Esperamos liberar esta funcionalidad antes de la retirada real del 31 de julio de 2021.</span><span class="sxs-lookup"><span data-stu-id="6bda9-111">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>   <span data-ttu-id="6bda9-112">Actualmente, si no se especifica este modificador, los usuarios cambian de estar instalados en Skype Empresarial Server local a Skype Empresarial Online y su modo permanece sin cambios, que es la funcionalidad documentada en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6bda9-112">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged, which is the functionality documented in this article.</span></span>

 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="6bda9-113">Mover usuarios con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="6bda9-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="6bda9-114">Move-CsUser está disponible desde una ventana de PowerShell Skype Empresarial shell de administración local.</span><span class="sxs-lookup"><span data-stu-id="6bda9-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="6bda9-115">Debe tener privilegios suficientes tanto en el entorno local como en la organización Microsoft 365 como se describe en [Credenciales administrativas necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="6bda9-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="6bda9-116">Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de Microsoft 365 con el rol administrativo `-Credential` necesario.</span><span class="sxs-lookup"><span data-stu-id="6bda9-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="6bda9-117">Para mover un usuario a línea mediante Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="6bda9-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="6bda9-118">Especifique el usuario que se moverá mediante el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="6bda9-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="6bda9-119">Especifique el parámetro -Target con el valor "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="6bda9-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="6bda9-120">Si no tiene una cuenta con permisos suficientes tanto en el entorno local como en el Microsoft 365, use el parámetro -credential para proporcionar a una cuenta permisos suficientes en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bda9-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="6bda9-121">Si la cuenta con permisos en Microsoft 365 no termina en ".onmicrosoft. <span> com", a continuación, debe especificar el parámetro -HostedMigrationOverrideUrl, con el valor correcto como se describe en [Credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="6bda9-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="6bda9-122">La siguiente secuencia de cmdlets se puede usar para mover un usuario a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6bda9-122">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="6bda9-123">Se supone que la credencial Microsoft 365 es una cuenta independiente y se proporciona como entrada para el Get-Credential solicitud.</span><span class="sxs-lookup"><span data-stu-id="6bda9-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="6bda9-124">Si la cuenta de administrador está habilitada para MFA (autenticación multifactor), no especifique el parámetro -Credential.</span><span class="sxs-lookup"><span data-stu-id="6bda9-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="6bda9-125">Se pedirá al administrador credenciales.</span><span class="sxs-lookup"><span data-stu-id="6bda9-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="6bda9-126">Mover usuarios con Skype Empresarial Server panel de control</span><span class="sxs-lookup"><span data-stu-id="6bda9-126">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="6bda9-127">Abre la aplicación Skype Empresarial Server panel de control.</span><span class="sxs-lookup"><span data-stu-id="6bda9-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="6bda9-128">En la navegación izquierda, elija **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="6bda9-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="6bda9-129">Use **Buscar** para localizar los usuarios que desea mover a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6bda9-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="6bda9-130">Seleccione los usuarios y, a  continuación, en el desplegable Acción situado encima de la lista, elija Mover usuarios seleccionados **a Skype Empresarial Online**.</span><span class="sxs-lookup"><span data-stu-id="6bda9-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="6bda9-131">En el asistente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6bda9-131">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="6bda9-132">Si se le solicita, inicie sesión Microsoft 365 con una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="6bda9-132">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="6bda9-133">Haga **clic en** Siguiente y, a continuación, en Siguiente una vez más para mover al usuario. </span><span class="sxs-lookup"><span data-stu-id="6bda9-133">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="6bda9-134">Ten en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.</span><span class="sxs-lookup"><span data-stu-id="6bda9-134">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bda9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bda9-135">See also</span></span>

[<span data-ttu-id="6bda9-136">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="6bda9-136">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
