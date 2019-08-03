---
title: Mover usuarios de local a Skype empresarial online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: Obtenga información sobre cómo mover usuarios a Skype empresarial online.
ms.openlocfilehash: 90d225eb725690566f23b73b3626cbcf1f42c8c7
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2019
ms.locfileid: "36160789"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="42c90-103">Mover usuarios de local a Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="42c90-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="42c90-104">Después de mover un usuario de local a Skype empresarial online, el usuario interactúa con Skype empresarial online para su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="42c90-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="42c90-105">Los contactos que existían de forma local estarán disponibles en Skype empresarial online y las reuniones existentes organizadas por el usuario para el futuro se actualizan para que los vínculos apunten a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="42c90-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="42c90-106">Si el usuario está habilitado para conferencias de audio, las reuniones también incluirán coordenadas de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="42c90-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="42c90-107">Para mover usuarios de un entorno local a Skype empresarial online, use el cmdlet Move-CsUser o el panel de control de Skype empresarial Server, ambos son herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="42c90-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="42c90-108">Antes de mover los usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube.</span><span class="sxs-lookup"><span data-stu-id="42c90-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="42c90-109">Mover usuarios con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="42c90-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="42c90-110">Move-CsUser está disponible en una ventana local de PowerShell del shell de administración de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="42c90-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="42c90-111">Debe tener privilegios suficientes tanto en el entorno local como en el inquilino de Office 365, tal y como se describe en [credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="42c90-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="42c90-112">Puede usar una sola cuenta que tenga privilegios en ambos entornos, o puede iniciar una ventana del shell de administración local de Skype empresarial Server con credenciales locales y usar el `-Credential` parámetro para especificar las credenciales de un Office 365 cuenta con el rol administrativo de Office 365 necesario.</span><span class="sxs-lookup"><span data-stu-id="42c90-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="42c90-113">Para mover un usuario a online mediante Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="42c90-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="42c90-114">Especifique el usuario que se va a mover mediante el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="42c90-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="42c90-115">Especifique el parámetro-Target con el valor "sipfed. online. Lync. <span>com ".</span><span class="sxs-lookup"><span data-stu-id="42c90-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="42c90-116">Si no tiene una cuenta con permisos suficientes en local y Office 365, use el parámetro-credential para proporcionar una cuenta con permisos suficientes en Office 365.</span><span class="sxs-lookup"><span data-stu-id="42c90-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="42c90-117">Si la cuenta con permisos en Office 365 no termina en "activado. Microsoft. <span>com ", debe especificar el parámetro-HostedMigrationOverrideUrl, con el valor correcto tal como se describe en [credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="42c90-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

 > [!NOTE]
 > <span data-ttu-id="42c90-118">Debe determinar el valor de HostedMigrationOverrideUrl correcto para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="42c90-118">You must determine the correct HostedMigrationOverrideUrl value for your tenant.</span></span> <span data-ttu-id="42c90-119">Esto se puede realizar fácilmente desplazándose al centro de administración de Skype empresarial heredado.</span><span class="sxs-lookup"><span data-stu-id="42c90-119">this can be easily done by navigating to the Legacy Skype for Business admin center.</span></span> <span data-ttu-id="42c90-120">determinar el prefijo-XXXXXXX.online.lync.com y anexar/HostedMigration/hostedmigrationservice.svc.</span><span class="sxs-lookup"><span data-stu-id="42c90-120">determine the prefix - XXXXXXX.online.lync.com and append /HostedMigration/hostedmigrationservice.svc.</span></span> <span data-ttu-id="42c90-121">por ejemplo: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc una vez identificado el valor, úselo para la variable $URL como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="42c90-121">for example: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc Once you identified the value, use it for the $url variable as shown below.</span></span>

<span data-ttu-id="42c90-122">La siguiente secuencia de cmdlet se puede usar para mover un usuario a Skype empresarial online y asume que la credencial Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="42c90-122">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="42c90-123">Si la cuenta de administrador es MFA (multi-factor Authentication) habilitada, no especifique el parámetro-Credential.</span><span class="sxs-lookup"><span data-stu-id="42c90-123">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="42c90-124">Se pedirán las credenciales al administrador.</span><span class="sxs-lookup"><span data-stu-id="42c90-124">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="42c90-125">Mover usuarios con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="42c90-125">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="42c90-126">Abra la aplicación del panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="42c90-126">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="42c90-127">En el panel de navegación izquierdo, elija **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="42c90-127">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="42c90-128">Use **Buscar** para localizar al usuario o usuarios que desea mover a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="42c90-128">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="42c90-129">Seleccione el usuario o usuarios y, a continuación, en la lista desplegable de **acciones** situada encima de la lista, elija **mover usuarios seleccionados a Skype empresarial online**.</span><span class="sxs-lookup"><span data-stu-id="42c90-129">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="42c90-130">En el asistente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="42c90-130">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="42c90-131">Si se le solicita, inicie sesión en Office 365, con una cuenta que acabe en. onmicrosoft.com y que tenga permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="42c90-131">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="42c90-132">Haga clic en **siguiente**y \*\*\*\* , a continuación, otra vez más para mover al usuario.</span><span class="sxs-lookup"><span data-stu-id="42c90-132">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="42c90-133">Tenga en cuenta que los mensajes de estado sobre aciertos o errores se proporcionan en la parte superior de la aplicación del panel de control principal, no en el asistente.</span><span class="sxs-lookup"><span data-stu-id="42c90-133">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="42c90-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="42c90-134">See also</span></span>

[<span data-ttu-id="42c90-135">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="42c90-135">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
