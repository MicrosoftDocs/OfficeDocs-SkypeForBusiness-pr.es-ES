---
title: Mover usuarios de Skype Empresarial Server 2019 a Teams
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
description: 'Summary: Learn how to migrate user settings and move users to Teams.'
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836987"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="1e046-103">Mover usuarios locales a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e046-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="1e046-104">Cuando un usuario se mueve de local a Solo Teams, la casa de Skype Empresarial del usuario se mueve de local a online y al usuario se le asigna TeamsUpgradePolicy con mode=TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1e046-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="1e046-105">Una vez que un usuario se mueve del modo local al modo TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="1e046-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="1e046-106">Todas las llamadas entrantes y los chats de otros usuarios (ya sean enviados desde Skype Empresarial o Teams), llegarán al cliente de Teams del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e046-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="1e046-107">El usuario podrá interoperar con otros usuarios que usan Skype Empresarial (ya sea en línea o local).</span><span class="sxs-lookup"><span data-stu-id="1e046-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="1e046-108">El usuario podrá comunicarse con usuarios de organizaciones federadas.</span><span class="sxs-lookup"><span data-stu-id="1e046-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="1e046-109">Las nuevas reuniones programadas por ese usuario son reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="1e046-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="1e046-110">El usuario todavía puede unirse a cualquier reunión de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="1e046-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="1e046-111">Las reuniones preexistentes del usuario programadas para el futuro se migrarán de local a Teams.</span><span class="sxs-lookup"><span data-stu-id="1e046-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="1e046-112">Los contactos que existían localmente están disponibles en Teams poco después de que el usuario inicie sesión por primera vez.</span><span class="sxs-lookup"><span data-stu-id="1e046-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="1e046-113">Los usuarios no pueden iniciar llamadas o chats desde Skype Empresarial ni pueden programar nuevas reuniones en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="1e046-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="1e046-114">Si intentan abrir el cliente de Skype Empresarial, se les redirigirá para que usen Teams, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="1e046-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="1e046-115">Si el cliente de Teams no está instalado, se le dirigirá a la versión web de Teams mediante su explorador.</span><span class="sxs-lookup"><span data-stu-id="1e046-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="1e046-116">![Mensaje que redirige a un usuario a Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="1e046-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="1e046-117">Antes de mover usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube.</span><span class="sxs-lookup"><span data-stu-id="1e046-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="1e046-118">Asegúrese también de revisar las instrucciones de migración e interoperabilidad para las organizaciones que [usan Teams junto con Skype Empresarial.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="1e046-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="1e046-119">El Almacén de contactos unificado debe deshabilitarse en la cuenta de SfB local para que el contacto se traslade a Teams.</span><span class="sxs-lookup"><span data-stu-id="1e046-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="1e046-120">Hay dos métodos para mover un usuario localmente a Teams:</span><span class="sxs-lookup"><span data-stu-id="1e046-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="1e046-121">Si usa una versión anterior a Skype Empresarial Server 2015 CU8, el movimiento requiere dos pasos (que se pueden crear juntos como un solo paso, si lo desea):</span><span class="sxs-lookup"><span data-stu-id="1e046-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="1e046-122">[Mueva el usuario de Skype Empresarial Server (local) a Skype Empresarial Online](move-users-from-on-premises-to-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="1e046-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="1e046-123">Una vez que el usuario se encuentra en Skype Empresarial Online, asigne al usuario TeamsUpgradePolicy con mode= TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1e046-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="1e046-124">Para conceder el modo TeamsOnly, ejecute el siguiente cmdlet desde una ventana de PowerShell de Skype Empresarial Online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="1e046-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="1e046-125">Si tiene herramientas de administración de Skype Empresarial Server 2015 CU8 o posterior, puede usar el método anterior o puede realizar este movimiento en un paso como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="1e046-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="1e046-126">Además, también puede proporcionar una notificación dentro del cliente de Skype Empresarial antes de moverlos a Teams Only, así como, opcionalmente, hacer que el cliente de Teams descargue silenciosamente el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="1e046-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="1e046-127">Mover un usuario directamente desde Skype Empresarial local a Solo Teams</span><span class="sxs-lookup"><span data-stu-id="1e046-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="1e046-128">Las herramientas de administración locales en Skype Empresarial Server 2015 con CU8, así como en Skype Empresarial Server 2019, permiten mover usuarios locales al modo solo de Teams en un solo paso mediante el cmdlet Move-CsUser de PowerShell o el Panel de control de Skype Empresarial Server, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="1e046-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="1e046-129">Mover a Teams mediante Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="1e046-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="1e046-130">Move-CsUser está disponible desde una ventana local de PowerShell del Shell de administración de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="1e046-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="1e046-131">Los pasos siguientes y los permisos necesarios son los mismos que mover un usuario a Skype Empresarial Online, excepto que también debe especificar el modificador MoveToTeams y debe asegurarse de que al usuario también se le ha concedido una licencia para Teams (además de Skype Empresarial Online).</span><span class="sxs-lookup"><span data-stu-id="1e046-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="1e046-132">Debe tener privilegios suficientes tanto en el entorno local como en el servicio en la nube (Microsoft 365 u Office 365), tal como se describe en Credenciales administrativas [necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="1e046-132">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="1e046-133">Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de `-Credential` Microsoft 365 u Office 365 con el rol administrativo necesario.</span><span class="sxs-lookup"><span data-stu-id="1e046-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="1e046-134">Para mover un usuario al modo solo de Teams con Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="1e046-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="1e046-135">Especifique el usuario que se moverá mediante el `Identity` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1e046-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="1e046-136">Especifique el parámetro -Target con el valor "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="1e046-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="1e046-137">Especifique el `MoveToTeams` modificador.</span><span class="sxs-lookup"><span data-stu-id="1e046-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="1e046-138">Si no tiene una cuenta con permisos suficientes en el servicio local y en la nube (Microsoft 365 u Office 365), use el parámetro para proporcionar una cuenta con permisos suficientes en `-credential` Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e046-138">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="1e046-139">Si la cuenta con permisos en Microsoft 365 u Office 365 no termina en "onmicrosoft. <span> com", debe especificar el `-HostedMigrationOverrideUrl` parámetro, con el valor correcto como se describe en [Credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="1e046-139">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="1e046-140">La siguiente secuencia de cmdlets se puede usar para mover un usuario a TeamsOnly y se supone que la credencial de Microsoft 365 u Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje de Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="1e046-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="1e046-141">Como hay diferentes circunstancias que requieren parámetros diferentes, el comando predeterminado para la mayoría de los casos es:</span><span class="sxs-lookup"><span data-stu-id="1e046-141">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1e046-142">Mover a Teams mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1e046-142">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1e046-143">Abra la aplicación Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1e046-143">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="1e046-144">En la navegación izquierda, elija **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="1e046-144">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="1e046-145">Use **Buscar** para localizar los usuarios que desea mover a Teams.</span><span class="sxs-lookup"><span data-stu-id="1e046-145">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="1e046-146">Seleccione los usuarios y, a continuación, en el desplegable Acción **situado** encima de la lista, elija Mover **usuarios seleccionados a Teams**.</span><span class="sxs-lookup"><span data-stu-id="1e046-146">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="1e046-147">En el asistente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e046-147">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="1e046-148">Si se le solicita, inicie sesión en Microsoft 365 u Office 365 con una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="1e046-148">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="1e046-149">Haga **clic en** Siguiente y, a continuación, en Siguiente una vez más para mover al usuario. </span><span class="sxs-lookup"><span data-stu-id="1e046-149">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="1e046-150">Ten en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.</span><span class="sxs-lookup"><span data-stu-id="1e046-150">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="1e046-151">Notificar a los usuarios locales de Skype Empresarial el próximo traslado a Teams</span><span class="sxs-lookup"><span data-stu-id="1e046-151">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="1e046-152">Las herramientas de administración locales en Skype Empresarial Server 2015 con CU8, así como en Skype Empresarial Server 2019, le permiten notificar a los usuarios locales de Skype Empresarial su próximo traslado a Teams.</span><span class="sxs-lookup"><span data-stu-id="1e046-152">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="1e046-153">Al habilitar estas notificaciones, los usuarios verán una notificación en su cliente de Skype Empresarial (Win32, Mac, web y móvil) como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="1e046-153">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="1e046-154">Si los usuarios hacen **clic en el** botón Pruébalo, el cliente de Teams se iniciará si está instalado; de lo contrario, los usuarios se navegarán a la versión web de Teams en su explorador.</span><span class="sxs-lookup"><span data-stu-id="1e046-154">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="1e046-155">De forma predeterminada, cuando las notificaciones están habilitadas, los clientes de Skype Empresarial de Win32 descargan silenciosamente el cliente de Teams para que el cliente enriquecido esté disponible antes de mover al usuario al modo solo de Teams; sin embargo, también puede deshabilitar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1e046-155">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="1e046-156">Las notificaciones se configuran mediante la versión local de , y la descarga silenciosa para los clientes de Win32 se controla mediante el `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet local.</span><span class="sxs-lookup"><span data-stu-id="1e046-156">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="1e046-157">Es posible que algunos servidores deba reiniciar para que esto funcione en Skype Empresarial 2015 con CU8.</span><span class="sxs-lookup"><span data-stu-id="1e046-157">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Notificación del próximo traslado a Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="1e046-159">Para notificar a los usuarios locales que pronto se actualizarán a Teams, cree una nueva instancia de TeamsUpgradePolicy con NotifySfBUsers=true.</span><span class="sxs-lookup"><span data-stu-id="1e046-159">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="1e046-160">A continuación, asigne esa directiva a los usuarios a los que desea notificar, ya sea asignando la directiva directamente al usuario o estableciendo la directiva en el sitio, grupo o nivel global.</span><span class="sxs-lookup"><span data-stu-id="1e046-160">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="1e046-161">Los cmdlets siguientes crean y conceden una directiva de nivel de usuario:</span><span class="sxs-lookup"><span data-stu-id="1e046-161">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="1e046-162">La descarga automática de Teams a través del cliente Win32 de Skype Empresarial se controla mediante el cmdlet TeamsUpgradeConfiguration local con el parámetro DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="1e046-162">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="1e046-163">Esta configuración se crea en un nivel global, de sitio y de grupo.</span><span class="sxs-lookup"><span data-stu-id="1e046-163">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="1e046-164">Por ejemplo, el siguiente comando crea la configuración del sitio Redmond1:</span><span class="sxs-lookup"><span data-stu-id="1e046-164">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="1e046-165">De forma predeterminada, el valor de DownloadTeams es True; sin embargo, *solo se respeta* si NotifySfbUser = True para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="1e046-165">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e046-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e046-166">See also</span></span>

[<span data-ttu-id="1e046-167">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="1e046-167">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="1e046-168">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1e046-168">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="1e046-169">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1e046-169">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="1e046-170">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1e046-170">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
