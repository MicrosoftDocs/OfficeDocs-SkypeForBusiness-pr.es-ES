---
title: Mover usuarios de local a Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Obtenga información sobre cómo mover los usuarios a Skype para profesionales en línea.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244000"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="9a9b6-103">Mover usuarios de local a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9a9b6-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="9a9b6-104">Después de mover un usuario de local a Skype para profesionales en línea, el usuario interactúa con Skype para empresarial en línea para su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="9a9b6-105">Todos los contactos que se encontraba local que estará disponibles en Skype para profesionales en línea, y se actualizan las reuniones existentes que el usuario organizó para el futuro a para que los vínculos señalan Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="9a9b6-106">Si el usuario está habilitado para conferencias de Audio, las reuniones también incluirá las coordenadas de marcado.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="9a9b6-107">Para mover usuarios de un entorno local a Skype para profesionales en línea, use el cmdlet Move-CsUser o el Skype para el Panel de Control de servidor empresarial, que son herramientas local.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="9a9b6-108">Antes de mover los usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover los usuarios a la nube.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="9a9b6-109">Mover usuarios con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="9a9b6-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="9a9b6-110">Move-CsUser está disponible desde un Skype local para la ventana de PowerShell de Shell de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="9a9b6-111">Debe tener privilegios suficientes en ambos el entorno local, así como en el inquilino de Office 365, tal como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="9a9b6-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="9a9b6-112">Puede usar una única cuenta que tiene privilegios en ambos entornos, o puede iniciar un Skype in situ para la ventana de Shell de administración de servidor empresarial con las credenciales locales y usar el `-Credential` parámetro para especificar las credenciales para una Office 365 cuenta con la función administrativa de Office 365 es necesaria.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="9a9b6-113">Para mover un usuario a online mediante Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="9a9b6-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="9a9b6-114">Especifique el usuario para mover mediante el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="9a9b6-115">Especifique el destino parámetro - con el valor "sipfed.online.lync. <span>com ".</span><span class="sxs-lookup"><span data-stu-id="9a9b6-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="9a9b6-116">Si no tiene una cuenta con permisos suficientes en ambos en local y Office 365, use el - parámetro de credenciales para proporcionar una cuenta con permisos suficientes en Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="9a9b6-117">Si la cuenta con permisos en Office 365 no termina en "on.microsoft. <span>com ", a continuación, debe especificar el parámetro - HostedMigrationOverrideUrl, con el valor correcto, tal como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="9a9b6-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="9a9b6-118">La siguiente secuencia de cmdlet puede usarse para mover un usuario a Skype para profesionales en línea y se da por supuesto la credencial de Office 365 es una cuenta independiente y se proporciona como entrada para el símbolo del sistema de Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="9a9b6-119">Mover usuarios con Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="9a9b6-119">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="9a9b6-120">Abra el Skype para el Control de servidor empresarial aplicación de Panel.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-120">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="9a9b6-121">En el panel de navegación izquierdo, elija **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-121">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="9a9b6-122">Use **Buscar** para buscar el usuario o usuarios que le gustaría mover a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-122">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="9a9b6-123">Seleccione los usuarios y, a continuación, en la lista desplegable **acción** encima de la lista, elija **mover usuarios seleccionados a Skype para profesionales en línea**.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-123">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="9a9b6-124">En el asistente, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-124">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="9a9b6-125">Si se le solicita, inicie sesión en Office 365, con una cuenta que termina en. onmicrosoft.com y tiene permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-125">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="9a9b6-126">Haga clic en **siguiente**y, a continuación, **siguiente** una vez más para mover el usuario.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-126">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="9a9b6-127">Tenga en cuenta que los mensajes de estado sobre el éxito o el fracaso se proporcionan en la parte superior de la aplicación de Panel de Control principal, no en el asistente.</span><span class="sxs-lookup"><span data-stu-id="9a9b6-127">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a9b6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a9b6-128">See also</span></span>

[<span data-ttu-id="9a9b6-129">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="9a9b6-129">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)