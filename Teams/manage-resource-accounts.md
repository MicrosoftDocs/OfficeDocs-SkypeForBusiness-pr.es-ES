---
title: Administrar cuentas de recursos en Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Obtenga información acerca de cómo administrar las cuentas de recursos en Microsoft Teams
ms.openlocfilehash: 055e419e5a82233676e5b66857589216b4dbca6d
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517235"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="bd206-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd206-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="bd206-104">Una cuenta de recursos es también conocida como un objeto de usuario deshabilitado en Azure Active Directory y puede usarse para representar los recursos en general.</span><span class="sxs-lookup"><span data-stu-id="bd206-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="bd206-105">En Exchange pueden usarse para representar salas de conferencias, por ejemplo y permitir que tengan un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="bd206-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="bd206-106">Una cuenta de recursos puede estar alojada en Microsoft 365 o local mediante Skype para Business server, y estas cuentas se crean utilizando los comandos de Powershell.</span><span class="sxs-lookup"><span data-stu-id="bd206-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="bd206-107">En Microsoft Teams o Skype para profesionales en línea, cada llamada de cola o auto attendant se requiere para tienen una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="bd206-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="bd206-108">Si una cuenta de recursos necesita un número de teléfono asignado se dependen el uso intencionado de la cola de llamada asociada o el operador automático.</span><span class="sxs-lookup"><span data-stu-id="bd206-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="bd206-109">Hacer referencia a los artículos en las colas de llamadas y automáticos vinculado en la parte inferior de este artículo antes de asignar a un número de teléfono a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="bd206-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="bd206-110">En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="bd206-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="bd206-111">Requisitos previos para asignar a un número de teléfono a una cuenta de recurso</span><span class="sxs-lookup"><span data-stu-id="bd206-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="bd206-112">Para empezar a es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="bd206-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="bd206-113">Una cola de llamada o de operador automático es necesario tener una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="bd206-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="bd206-114">Para obtener información detallada sobre las cuentas de recursos, vea [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="bd206-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="bd206-115">Si tiene previsto asignar un número de enrutamiento directa, debe adquirir y asignar las siguientes licencias para las cuentas de recursos \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico\).</span><span class="sxs-lookup"><span data-stu-id="bd206-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="bd206-116">Si se asigna un número de servicio de Microsoft en su lugar, debe adquirir y asignar las licencias siguientes a la cuenta del recurso \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico y un Plan de llamar a\).</span><span class="sxs-lookup"><span data-stu-id="bd206-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="bd206-117">Microsoft está trabajando en un modelo de licencias adecuado para aplicaciones como automáticos en la nube y las colas de llamadas, para ahora tiene que usar el modelo de licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="bd206-117">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bd206-118">Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd206-118">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="bd206-119">Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="bd206-119">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="bd206-120">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd206-120">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="bd206-121">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="bd206-121">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="bd206-122">Puede asignar a un número de híbrido de enrutamiento directa a la cuenta del recurso.</span><span class="sxs-lookup"><span data-stu-id="bd206-122">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="bd206-123">Para obtener información detallada, vea [Planear el enrutamiento directo](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="bd206-123">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="bd206-124">Planes de llamada de Microsoft, sólo se pueden asignar números de pago y los números de teléfono gratuito de servicio que se obtuvo en el **Centro de administración de equipos de Microsoft** o se transfiere desde otro proveedor de servicios a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="bd206-124">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="bd206-125">Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="bd206-125">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="bd206-126">Los números de teléfono del usuario (suscriptor) no se pueden asignar a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="bd206-126">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="bd206-127">Se pueden usar solo números de pago de servicio o números de teléfono gratuito.</span><span class="sxs-lookup"><span data-stu-id="bd206-127">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="bd206-128">Para asignar un número de teléfono a una cuenta de recurso, necesitará obtener o transferir su pago existente o un servicio gratuito números.</span><span class="sxs-lookup"><span data-stu-id="bd206-128">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="bd206-129">Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el **Centro de administración de equipos de Microsoft** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="bd206-129">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="bd206-130">Para obtener sus números de servicio, vea [los números de teléfono del servicio de obtención](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) o si desea transferir un número de servicio existente, vea [los números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="bd206-130">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd206-131">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio.</span><span class="sxs-lookup"><span data-stu-id="bd206-131">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="bd206-132">Vaya a [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bd206-132">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="bd206-133">Crear una cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd206-133">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="bd206-134">Para crear una cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización** > **las cuentas de recursos**, a continuación, haga clic en **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bd206-134">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, then click **+ Add**.</span></span> <span data-ttu-id="bd206-135">En el menú emergente, rellene el nombre para mostrar y nombre de usuario para la cuenta del recurso (el nombre de dominio debe rellenar automáticamente), a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bd206-135">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![cuenta de recurso](media/res-acct.png)

<span data-ttu-id="bd206-137">También necesitará aplicar una licencia a la cuenta del recurso, tal como se describe en [asignar licencias a los usuarios de Office 365 para profesionales](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="bd206-137">You will also need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span></span>

<span data-ttu-id="bd206-138">Una vez que haya creado la cuenta del recurso y asignado la licencia, puede hacer clic en **Asignar o Cancelar asignación** para asignar a un número de teléfono a la cuenta del recurso, o para asignar la cuenta de recurso a una cola de llamada o de operador automático.</span><span class="sxs-lookup"><span data-stu-id="bd206-138">Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a phone number to the resource account, or to assign the resource account to an auto attendant or call queue.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="bd206-139">Crear una cuenta de recursos en Powershell</span><span class="sxs-lookup"><span data-stu-id="bd206-139">Create a resource account in Powershell</span></span>

 <span data-ttu-id="bd206-140">Debe crear una cuenta de recurso ejecutando el cmdlet de Powershell apropiado según sea necesario (para una o más cuentas de recursos) y asigne un nombre a cada uno de ellos y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="bd206-140">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="bd206-141">Actualmente no hay ninguna opción para crear una cuenta de recursos en el centro de administración de Microsoft Teams, pero puede editar los números de teléfono y cambiar la llamada cola o auto attendant asignaciones para una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="bd206-141">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="bd206-142">Dependiendo de si su número de teléfono se encuentra en línea o local, sería necesario para conectarse a la adecuada símbolo del sistema Powershell con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="bd206-142">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="bd206-143">Las implementaciones de híbrido (números de números hospedados en el enrutamiento directo, OPCH y CCE) se utilizará [CsHybridApplicationEndpoint de nuevo](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para crear una cuenta de recurso que se hospeda en local.</span><span class="sxs-lookup"><span data-stu-id="bd206-143">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="bd206-144">En línea sólo las implementaciones utilizarán [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para una cuenta de recurso que se hospeda en línea.</span><span class="sxs-lookup"><span data-stu-id="bd206-144">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="bd206-145">El siguiente es un ejemplo de un entorno en línea de creación de cuenta de recurso con un operador automático de ApplicationID.</span><span class="sxs-lookup"><span data-stu-id="bd206-145">The following is an online environment example of creating resource account with an auto attendant ApplicationID.</span></span> <span data-ttu-id="bd206-146">Para una cola de llamadas, puede usar el siguiente ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span><span class="sxs-lookup"><span data-stu-id="bd206-146">For a call queue, you can use the following ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="bd206-147">Para obtener más información acerca de este comando, vea [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="bd206-147">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="bd206-148">Es más fácil de establecer el número de teléfono en línea mediante el centro de administración de Microsoft Teams, tal como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="bd206-148">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="bd206-149">También puede usar el `Set-CsOnlineVoiceApplicationInstance` de comando a un asignar un número de teléfono a la cuenta del recurso después de su creación inicial tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="bd206-149">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="bd206-150">Si no se aplican una licencia durante la creación de la cuenta del recurso se producirá un error en la asignación de números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="bd206-150">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="bd206-151">Para obtener más información acerca de este comando, vea [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="bd206-151">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="bd206-152">Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd206-152">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="bd206-153">Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización**  > **las cuentas de recursos**, seleccione la cuenta de recursos que necesita para cambiar la configuración para y, a continuación, haga clic en el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="bd206-153">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="bd206-154">en la pantalla **Editar la cuenta del recurso** , podrá cambiar el:</span><span class="sxs-lookup"><span data-stu-id="bd206-154">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="bd206-155">**Nombre para mostrar** para la cuenta</span><span class="sxs-lookup"><span data-stu-id="bd206-155">**Display name** for the account</span></span>
- <span data-ttu-id="bd206-156">Cola de llamadas u operadores automáticos que usa la cuenta</span><span class="sxs-lookup"><span data-stu-id="bd206-156">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="bd206-157">Número de teléfono asignado a la cuenta</span><span class="sxs-lookup"><span data-stu-id="bd206-157">Phone number assigned to the account</span></span>

<span data-ttu-id="bd206-158">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bd206-158">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="bd206-159">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="bd206-159">Related Information</span></span>

<span data-ttu-id="bd206-160">Para las implementaciones que son híbrida con Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="bd206-160">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="bd206-161">Planear los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="bd206-161">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="bd206-162">Configurar los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="bd206-162">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="bd206-163">Para las implementaciones en los equipos o Skype para empresarial en línea:</span><span class="sxs-lookup"><span data-stu-id="bd206-163">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="bd206-164">¿Qué son los operadores automáticos del Sistema telefónico?</span><span class="sxs-lookup"><span data-stu-id="bd206-164">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="bd206-165">Configurar un operador automático para el sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bd206-165">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="bd206-166">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="bd206-166">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="bd206-167">Crear una cola de llamadas para el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bd206-167">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="bd206-168">Nueva CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="bd206-168">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="bd206-169">Nueva CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="bd206-169">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
