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
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Administración de cuentas de recursos en Microsoft Teams
ms.openlocfilehash: 60fcfe34c665805eac90b5e5be862786e9e68de5
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "30210783"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="1d986-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d986-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="1d986-104">Una cuenta de recursos es también conocida como un objeto de usuario deshabilitado en Azure Active Directory y puede usarse para representar los recursos en general.</span><span class="sxs-lookup"><span data-stu-id="1d986-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="1d986-105">En Exchange pueden usarse para representar salas de conferencias, por ejemplo y permitir que tengan un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="1d986-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="1d986-106">Una cuenta de recursos puede estar alojada en Microsoft 365 o local mediante Skype para Business server, y estas cuentas se crean utilizando los comandos de Powershell.</span><span class="sxs-lookup"><span data-stu-id="1d986-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="1d986-107">En Microsoft Teams o Skype para profesionales en línea, cada llamada de cola o auto attendant se requiere para tienen una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="1d986-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="1d986-108">Si una cuenta de recursos necesita un número de teléfono asignado se dependen el uso intencionado de la cola de llamada asociada o el operador automático.</span><span class="sxs-lookup"><span data-stu-id="1d986-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="1d986-109">Hacer referencia a los artículos en las colas de llamadas y automáticos vinculado en la parte inferior de este artículo antes de asignar a un número de teléfono a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="1d986-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="1d986-110">En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="1d986-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="1d986-111">Requisitos previos para asignar a un número de teléfono a una cuenta de recurso</span><span class="sxs-lookup"><span data-stu-id="1d986-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="1d986-112">Para empezar a es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="1d986-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="1d986-113">Su organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema telefónico** o una licencia Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="1d986-113">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="1d986-114">El número de licencias de usuario de **Sistema telefónico** que se asignan afecta al número de números de servicio que están disponibles para ser usadas para las cuentas de recursos asignadas a las colas u operadores automáticos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1d986-114">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for resource accounts assigned to call queues or auto attendants.</span></span> <span data-ttu-id="1d986-115">El número de cuentas de recursos que puede hacer que depende el número de licencias de **Sistema telefónico** y **Conferencias de Audio** que se asignan en la organización.</span><span class="sxs-lookup"><span data-stu-id="1d986-115">The number of resource accounts you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="1d986-116">Para obtener más información acerca de las licencias, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1d986-116">To learn more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d986-117">Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1d986-117">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="1d986-118">Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="1d986-118">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="1d986-119">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d986-119">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="1d986-120">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="1d986-120">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="1d986-121">Para obtener más información acerca de planes de llamada de Office 365, vea [Llamar a planes de Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1d986-121">To learn more about Office 365 Calling Plans, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>
- <span data-ttu-id="1d986-122">Sólo se pueden asignar números de pago y los números de teléfono gratuito de servicio que se obtuvo en el **Centro de administración de equipos de Microsoft** o se transfiere desde otro proveedor de servicios a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="1d986-122">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="1d986-123">Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="1d986-123">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="1d986-124">Los números de teléfono del usuario (suscriptor) no se pueden asignar a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="1d986-124">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="1d986-125">Se pueden usar solo números de pago de servicio o números de teléfono gratuito.</span><span class="sxs-lookup"><span data-stu-id="1d986-125">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="1d986-126">Para asignar un número de teléfono a una cuenta de recurso, necesitará obtener o transferir su pago existente o un servicio gratuito números.</span><span class="sxs-lookup"><span data-stu-id="1d986-126">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="1d986-127">Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el **Centro de administración de equipos de Microsoft** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="1d986-127">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="1d986-128">Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) o si desea transferir y el número de servicio existente, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1d986-128">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d986-129">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d986-129">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="1d986-130">Vaya a [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="1d986-130">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="1d986-131">Crear una cuenta de recursos en Powershell</span><span class="sxs-lookup"><span data-stu-id="1d986-131">Create a resource account in Powershell</span></span>

 <span data-ttu-id="1d986-132">Debe crear una cuenta de recurso ejecutando el cmdlet de Powershell apropiado según sea necesario (para una o más cuentas de recursos) y asigne un nombre a cada uno de ellos y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="1d986-132">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="1d986-133">Actualmente no hay ninguna opción para crear una cuenta de recursos en el centro de administración de Microsoft Teams, pero puede editar los números de teléfono y cambiar la llamada cola o auto attendant asignaciones para una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="1d986-133">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="1d986-134">Dependiendo de si su número de teléfono se encuentra en línea o local, sería necesario para conectarse a la adecuada símbolo del sistema Powershell con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="1d986-134">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="1d986-135">Las implementaciones de híbrido (números de números hospedados en el enrutamiento directo, OPCH y CCE) se utilizará [CsHybridApplicationEndpoint de nuevo](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para crear una cuenta de recurso que se hospeda en local.</span><span class="sxs-lookup"><span data-stu-id="1d986-135">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="1d986-136">En línea sólo las implementaciones utilizarán [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para una cuenta de recurso que se hospeda en línea.</span><span class="sxs-lookup"><span data-stu-id="1d986-136">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="1d986-137">El siguiente es un ejemplo de un entorno en línea de la creación de una cuenta de recursos:</span><span class="sxs-lookup"><span data-stu-id="1d986-137">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

<span data-ttu-id="1d986-138">Para obtener más información acerca de este comando, vea [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1d986-138">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="1d986-139">Es más fácil de establecer el número de teléfono con el centro de administración de Microsoft Teams, tal como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="1d986-139">It's easiest to set the phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="1d986-140">También puede usar el `Set-CsOnlineApplicationInstance` de comando a un asignar un número de teléfono a la cuenta del recurso después de su creación inicial tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="1d986-140">You can also use the `Set-CsOnlineApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

<span data-ttu-id="1d986-141">Para obtener más información acerca de este comando, vea [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1d986-141">See [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="1d986-142">Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d986-142">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="1d986-143">Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización**  > **las cuentas de recursos**, seleccione la cuenta de recursos que necesita para cambiar la configuración para y, a continuación, haga clic en el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="1d986-143">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="1d986-144">en la pantalla **Editar la cuenta del recurso** , podrá cambiar el:</span><span class="sxs-lookup"><span data-stu-id="1d986-144">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="1d986-145">**Nombre para mostrar** para la cuenta</span><span class="sxs-lookup"><span data-stu-id="1d986-145">**Display name** for the account</span></span>
- <span data-ttu-id="1d986-146">Cola de llamadas u operadores automáticos que usa la cuenta</span><span class="sxs-lookup"><span data-stu-id="1d986-146">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="1d986-147">Número de teléfono asignado a la cuenta</span><span class="sxs-lookup"><span data-stu-id="1d986-147">Phone number assigned to the account</span></span>

<span data-ttu-id="1d986-148">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1d986-148">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="1d986-149">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="1d986-149">Related Information</span></span>

<span data-ttu-id="1d986-150">Para las implementaciones que son híbrida con Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="1d986-150">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="1d986-151">Planeación de operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="1d986-151">Plan Cloud auto attendant</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="1d986-152">Configurar operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="1d986-152">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="1d986-153">Para las implementaciones en los equipos o Skype para empresarial en línea:</span><span class="sxs-lookup"><span data-stu-id="1d986-153">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="1d986-154">¿Qué son los operadores automáticos del Sistema telefónico?</span><span class="sxs-lookup"><span data-stu-id="1d986-154">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="1d986-155">Configurar un operador automático de Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="1d986-155">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="1d986-156">Ejemplo de pequeña empresa - configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="1d986-156">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="1d986-157">Crear una cola de llamadas de Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="1d986-157">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="1d986-158">Nueva CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="1d986-158">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="1d986-159">Nueva CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="1d986-159">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
