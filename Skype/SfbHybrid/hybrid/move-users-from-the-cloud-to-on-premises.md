---
title: Mover usuarios de la nube a local
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
description: Obtenga información sobre cómo mover usuarios de Skype Empresarial Online a local.
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221340"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="cebc9-103">Mover usuarios de la nube a local</span><span class="sxs-lookup"><span data-stu-id="cebc9-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="cebc9-104">Si es necesario, puede mover un usuario que se migró previamente de local a la nube (ya sea usando Skype Empresarial Online o Solo Teams) de nuevo a local.</span><span class="sxs-lookup"><span data-stu-id="cebc9-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="cebc9-105">Para volver a mover usuarios del modo Skype Empresarial Online o TeamsOnly a una implementación local de Skype Empresarial Server, use el cmdlet Move-CsUser o el Panel de control de Skype Empresarial Server, que son herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="cebc9-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="cebc9-106">Cuando mueve un usuario de vuelta a una implementación local, debe decidir a qué grupo mover el usuario.</span><span class="sxs-lookup"><span data-stu-id="cebc9-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="cebc9-107">Si el usuario estaba anteriormente en modo TeamsOnly y está usando una versión anterior a Skype Empresarial Server 2015 con CU8, también debe quitar la asignación de modo TeamsOnly de TeamsUpgradePolicy para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="cebc9-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="cebc9-108">Los usuarios locales no deben tener mode= TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="cebc9-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="cebc9-109">Las versiones posteriores de Skype Empresarial Server quitan automáticamente esta asignación.</span><span class="sxs-lookup"><span data-stu-id="cebc9-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="cebc9-110">Para obtener más información, [vea Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span><span class="sxs-lookup"><span data-stu-id="cebc9-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cebc9-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cebc9-111">Prerequisites</span></span>

- <span data-ttu-id="cebc9-112">La organización debe tener Azure AD Connect configurado correctamente y estar sincronizando todos los atributos relevantes para el usuario, como se describe en [Configurar Azure AD Connect](configure-azure-ad-connect.md).</span><span class="sxs-lookup"><span data-stu-id="cebc9-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="cebc9-113">El usuario que se va a mover de nuevo en línea a local ya debe existir en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="cebc9-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="cebc9-114">Skype Empresarial híbrido debe configurarse, como se describe en [Configurar Skype Empresarial híbrido.](configure-federation-with-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="cebc9-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="cebc9-115">Mover a los usuarios de nuevo a la implementación local</span><span class="sxs-lookup"><span data-stu-id="cebc9-115">Moving users back to on-premises</span></span>

<span data-ttu-id="cebc9-116">Una vez que mueva un usuario de la nube de vuelta a la implementación local:</span><span class="sxs-lookup"><span data-stu-id="cebc9-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="cebc9-117">El usuario interactúa con la implementación de Skype Empresarial Server para su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="cebc9-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="cebc9-118">Los contactos que existían en Skype Empresarial Online o Teams se migran a Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cebc9-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="cebc9-119">Los dos conjuntos de contactos se combinan y, a continuación, se migran de nuevo a local.</span><span class="sxs-lookup"><span data-stu-id="cebc9-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="cebc9-120">Además, los contactos que ya existen en Teams permanecen en Teams.</span><span class="sxs-lookup"><span data-stu-id="cebc9-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="cebc9-121">Si el usuario también usa Teams, no podrá interoperar con usuarios de Skype Empresarial ni podrá comunicarse con usuarios de organizaciones federadas.</span><span class="sxs-lookup"><span data-stu-id="cebc9-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="cebc9-122">Las reuniones en Skype Empresarial Online *no* se migran automáticamente de nuevo a local.</span><span class="sxs-lookup"><span data-stu-id="cebc9-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="cebc9-123">Los usuarios deben volver a programar sus reuniones o, si lo desean, usar la Herramienta [de migración de reuniones.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)</span><span class="sxs-lookup"><span data-stu-id="cebc9-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="cebc9-124">Mover usuarios con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cebc9-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="cebc9-125">Move-CsUser está disponible desde una ventana local de PowerShell del Shell de administración de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="cebc9-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="cebc9-126">Debe tener privilegios suficientes tanto en el entorno local como en la organización de servicios en la nube (Microsoft 365 u Office 365), como se describe en Credenciales administrativas [necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="cebc9-126">You must have sufficient privileges in both the on-premises environment as well as the cloud service organization (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="cebc9-127">Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de `-Credential` Microsoft 365 u Office 365 con el rol administrativo necesario.</span><span class="sxs-lookup"><span data-stu-id="cebc9-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="cebc9-128">Para mover un usuario a local mediante Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="cebc9-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="cebc9-129">Especifique el usuario que se moverá mediante el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="cebc9-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="cebc9-130">Especifique el parámetro -Target con el nombre de dominio completo del grupo local deseado que hospedará al usuario.</span><span class="sxs-lookup"><span data-stu-id="cebc9-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="cebc9-131">Si no tiene una cuenta con permisos suficientes tanto en el servicio local como en el servicio en la nube (Microsoft 365 u Office 365), use el parámetro -credential para proporcionar a una cuenta permisos suficientes en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="cebc9-131">If you do not have one account with sufficient permissions in both on-premises and the cloud service (Microsoft 365 or Office 365), use the -credential parameter to supply an account with sufficient permissions in Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="cebc9-132">Si la cuenta con permisos en Microsoft 365 u Office 365 no termina en "on.microsoft.com", debe especificar el parámetro -HostedMigrationOverrideUrl, con el valor correcto como se describe en Credenciales administrativas [necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="cebc9-132">If the account with permissions in Microsoft 365 or Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="cebc9-133">La siguiente secuencia de cmdlets se puede usar para mover un usuario a Skype Empresarial Server y se supone que la credencial de Microsoft 365 u Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje Get-Credential usuario.</span><span class="sxs-lookup"><span data-stu-id="cebc9-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="cebc9-134">Mover usuarios con el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cebc9-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cebc9-135">Abra la aplicación Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cebc9-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="cebc9-136">En el panel de navegación izquierdo, elija **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="cebc9-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="cebc9-137">Use **Buscar** para localizar los usuarios a los que desea volver a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="cebc9-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="cebc9-138">Seleccione los usuarios y, a  continuación, en el desplegable Acción situado encima de la lista, elija Mover usuarios seleccionados **a local.**</span><span class="sxs-lookup"><span data-stu-id="cebc9-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="cebc9-139">En el asistente, seleccione el grupo de usuarios que hospedará al usuario y haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="cebc9-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="cebc9-140">Si se le solicita, inicie sesión en Microsoft 365 u Office 365 con una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="cebc9-140">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="cebc9-141">Haga **clic en** Siguiente y, a **continuación,** en Siguiente una vez más para mover el usuario.</span><span class="sxs-lookup"><span data-stu-id="cebc9-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="cebc9-142">Tenga en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.</span><span class="sxs-lookup"><span data-stu-id="cebc9-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="cebc9-143">Quitar el modo TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="cebc9-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="cebc9-144">Si está usando una versión anterior a Skype Empresarial 2015 con CU8 y el usuario se está trasladando de nuevo a local en modo TeamsOnly, debe quitar la instancia UpgradeToTeams antes de mover el usuario `TeamsUpgradePolicy` localmente.</span><span class="sxs-lookup"><span data-stu-id="cebc9-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="cebc9-145">Puede conceder explícitamente una directiva con un modo diferente o simplemente quitar la asignación de directiva existente para que ese usuario use la directiva global (siempre que la directiva global de su espacio empresarial no sea UpgradeToTeams).</span><span class="sxs-lookup"><span data-stu-id="cebc9-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="cebc9-146">Para quitar la asignación del usuario de TeamsUpgradePolicy, ejecute el siguiente cmdlet desde una ventana de PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="cebc9-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="cebc9-147">Como alternativa, para asignar otra instancia de TeamsUpgradePolicy que no tiene mode=TeamsOnly, puede especificar el nombre de la instancia deseada como el valor del parámetro PolicyName en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cebc9-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="cebc9-148">Para ver una lista de las instancias disponibles de TeamsUpgradePolicy, ejecute Get-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="cebc9-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="cebc9-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="cebc9-149">See also</span></span>

[<span data-ttu-id="cebc9-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cebc9-150">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
