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
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110626"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="208d3-103">Mover usuarios locales a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="208d3-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="208d3-104">Después de mover un usuario local a Skype Empresarial Online, el usuario interactúa con Skype Empresarial Online para su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="208d3-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="208d3-105">Los contactos que existían localmente estarán disponibles en Skype Empresarial Online y las reuniones existentes que el usuario haya organizado para el futuro se actualizarán para que los vínculos apunten a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="208d3-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="208d3-106">Si el usuario está habilitado para Audioconferencia, las reuniones también incluirán coordenadas de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="208d3-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="208d3-107">Para mover usuarios de un entorno local a Skype Empresarial Online, use el cmdlet Move-CsUser o el Panel de control de Skype Empresarial Server, que son herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="208d3-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="208d3-108">Antes de mover usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube.</span><span class="sxs-lookup"><span data-stu-id="208d3-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="208d3-109">Mover usuarios con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="208d3-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="208d3-110">Move-CsUser está disponible desde una ventana local de PowerShell del Shell de administración de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="208d3-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="208d3-111">Debe tener privilegios suficientes tanto en el entorno local como en la organización de Microsoft 365/Office 365, tal como se describe en Credenciales administrativas [necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="208d3-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="208d3-112">Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de `-Credential` Microsoft 365 u Office 365 con el rol administrativo necesario.</span><span class="sxs-lookup"><span data-stu-id="208d3-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="208d3-113">Para mover un usuario a línea mediante Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="208d3-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="208d3-114">Especifique el usuario que se moverá mediante el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="208d3-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="208d3-115">Especifique el parámetro -Target con el valor "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="208d3-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="208d3-116">Si no tiene una cuenta con permisos suficientes tanto en office local como en Office 365, use el parámetro -credential para proporcionar a una cuenta los permisos suficientes en Office 365.</span><span class="sxs-lookup"><span data-stu-id="208d3-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="208d3-117">Si la cuenta con permisos en Office 365 no termina en ".onmicrosoft. <span> com", a continuación, debe especificar el parámetro -HostedMigrationOverrideUrl, con el valor correcto como se describe en [Credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="208d3-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="208d3-118">La siguiente secuencia de cmdlets se puede usar para mover un usuario a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="208d3-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="208d3-119">Se supone que la credencial de Microsoft 365 u Office 365 es una cuenta independiente y se proporciona como entrada para el Get-Credential solicitud.</span><span class="sxs-lookup"><span data-stu-id="208d3-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="208d3-120">Si la cuenta de administrador está habilitada para MFA (autenticación multifactor), no especifique el parámetro -Credential.</span><span class="sxs-lookup"><span data-stu-id="208d3-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="208d3-121">Se pedirá al administrador credenciales.</span><span class="sxs-lookup"><span data-stu-id="208d3-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="208d3-122">Mover usuarios con el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="208d3-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="208d3-123">Abra la aplicación Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="208d3-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="208d3-124">En la navegación izquierda, elija **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="208d3-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="208d3-125">Use **Buscar** para localizar los usuarios que desea mover a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="208d3-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="208d3-126">Seleccione los usuarios y, a  continuación, en el desplegable Acción situado encima de la lista, elija Mover usuarios seleccionados **a Skype Empresarial Online**.</span><span class="sxs-lookup"><span data-stu-id="208d3-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="208d3-127">En el asistente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="208d3-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="208d3-128">Si se le solicita, inicie sesión en Microsoft 365 u Office 365 con una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="208d3-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="208d3-129">Haga **clic en** Siguiente y, a continuación, en Siguiente una vez más para mover al usuario. </span><span class="sxs-lookup"><span data-stu-id="208d3-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="208d3-130">Ten en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.</span><span class="sxs-lookup"><span data-stu-id="208d3-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="208d3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="208d3-131">See also</span></span>

[<span data-ttu-id="208d3-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="208d3-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)