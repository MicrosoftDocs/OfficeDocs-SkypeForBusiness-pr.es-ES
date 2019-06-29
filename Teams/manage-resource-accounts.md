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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Más información sobre la administración de cuentas de recursos en Microsoft Teams
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394503"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="6acec-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6acec-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="6acec-104">Una cuenta de recursos también se conoce como un objeto de usuario deshabilitado en Azure Active Directory y se puede usar para representar recursos en general.</span><span class="sxs-lookup"><span data-stu-id="6acec-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="6acec-105">En Exchange podría usarse para representar salas de conferencias, por ejemplo, y permitirles que tengan un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6acec-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="6acec-106">Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6acec-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="6acec-107">En Microsoft Teams o Skype empresarial online, cada cola de llamadas o operador automático debe tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="6acec-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="6acec-108">Si una cuenta de recursos necesita un número de teléfono asignado, dependerá del uso previsto de la cola de llamadas asociada o del operador automático.</span><span class="sxs-lookup"><span data-stu-id="6acec-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="6acec-109">Consulte los artículos sobre las colas de llamadas y los operadores automáticos vinculados al final de este artículo antes de asignar un número de teléfono a una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="6acec-110">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="6acec-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="6acec-111">Para cuentas de recursos alojados en Skype empresarial Server 2019, consulte [configurar cuentas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="6acec-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="6acec-112">Información general</span><span class="sxs-lookup"><span data-stu-id="6acec-112">Overview</span></span>

<span data-ttu-id="6acec-113">Si el servicio del sistema telefónico necesita un número de servicio, las diversas dependencias se pueden cumplir en la siguiente secuencia:</span><span class="sxs-lookup"><span data-stu-id="6acec-113">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="6acec-114">Obtener un número de servicio</span><span class="sxs-lookup"><span data-stu-id="6acec-114">Obtain a service number</span></span>
2. <span data-ttu-id="6acec-115">Comprar una licencia de sistema telefónico (Office 365 Enterprise E1 o E3 con el sistema telefónico agregado u Office 365 Enterprise E5 que incluye el sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="6acec-115">Buy a Phone System license (Office 365 Enterprise E1 or E3 with Phone System added, or Office 365 Enterprise E5 which includes Phone System)</span></span>
3. <span data-ttu-id="6acec-116">Crear la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-116">Create the resource account.</span></span> <span data-ttu-id="6acec-117">Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6acec-117">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="6acec-118">Asigne la licencia de sistema telefónico a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-118">Assign the Phone System license to the resource account.</span></span>
5. <span data-ttu-id="6acec-119">Asigne un número de teléfono a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-119">Assign a phone number to the resource account.</span></span>
6. <span data-ttu-id="6acec-120">Crear un servicio de sistema de teléfono (una cola de llamadas o un operador automático)</span><span class="sxs-lookup"><span data-stu-id="6acec-120">Create a Phone System service (a call queue or auto attendant)</span></span>
7. <span data-ttu-id="6acec-121">Asociar la cuenta de recursos con un servicio: (New-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="6acec-121">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="6acec-122">Si el operador automático o la cola de llamadas están anidados bajo un operador automático de nivel superior, la cuenta de recursos asociada solo necesita un número de teléfono si desea tener varios puntos de entrada en la estructura de las colas de llamadas y los operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="6acec-122">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="6acec-123">Para redirigir las llamadas a las personas de su organización que estén conectadas en línea, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6acec-123">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="6acec-124">Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="6acec-124">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="6acec-125">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6acec-125">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="6acec-126">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="6acec-126">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="6acec-127">Si el servicio del sistema telefónico que está creando va a estar anidado y no necesitará un número de teléfono, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="6acec-127">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="6acec-128">Crear la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="6acec-128">Create the resource account</span></span>  
2. <span data-ttu-id="6acec-129">Crear un servicio de sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="6acec-129">Create a Phone System service</span></span>
3. <span data-ttu-id="6acec-130">Asociar la cuenta de recursos con un servicio de sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="6acec-130">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="6acec-131">Crear una cuenta de recursos con un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="6acec-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="6acec-132">Para crear una cuenta de recursos que use un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="6acec-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="6acec-133">Puerto o recibe un número de servicio de pago o gratuito.</span><span class="sxs-lookup"><span data-stu-id="6acec-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="6acec-134">El número no se puede asignar a ningún otro servicio de voz o cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="6acec-135">Antes de asignar un número de teléfono a una cuenta de recursos, tendrá que obtener o migrar los números de teléfono de pago o gratuitos existentes.</span><span class="sxs-lookup"><span data-stu-id="6acec-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="6acec-136">Una vez que obtenga los números de teléfono de pago o gratuitos, aparecerán en los\*\*\*\* > **números de teléfono**del **Centro** > de administración de Microsoft Teams, y el **tipo de número** que aparece en la lista aparecerá como **servicio-** gratuito.</span><span class="sxs-lookup"><span data-stu-id="6acec-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="6acec-137">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6acec-137">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

2. <span data-ttu-id="6acec-138">Compre una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="6acec-138">Buy a Phone System license.</span></span> <span data-ttu-id="6acec-139">Verá</span><span class="sxs-lookup"><span data-stu-id="6acec-139">See:</span></span>  
   - [<span data-ttu-id="6acec-140">Office 365 Enterprise E1 y E3</span><span class="sxs-lookup"><span data-stu-id="6acec-140">Office 365 Enterprise E1 and E3</span></span>](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [<span data-ttu-id="6acec-141">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="6acec-141">Office 365 Enterprise E5</span></span>](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [<span data-ttu-id="6acec-142">Software Office 365 Enterprise E5 para empresas</span><span class="sxs-lookup"><span data-stu-id="6acec-142">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="6acec-143">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="6acec-143">Create a new resource account.</span></span> <span data-ttu-id="6acec-144">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="6acec-144">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="6acec-145">Asigne la licencia de sistema telefónico a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-145">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="6acec-146">Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md) y [asignar licencias a un usuario](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="6acec-146">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="6acec-147">Asignar el número de servicio a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-147">Assign the service number to the resource account.</span></span> <span data-ttu-id="6acec-148">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="6acec-148">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="6acec-149">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6acec-149">Set up one of the following:</span></span>
   - [<span data-ttu-id="6acec-150">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-150">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="6acec-151">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-151">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="6acec-152">Asignar la cuenta de recursos al servicio.</span><span class="sxs-lookup"><span data-stu-id="6acec-152">Assign the resource account to the service.</span></span> <span data-ttu-id="6acec-153">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="6acec-153">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="6acec-154">Crear una cuenta de recursos sin un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="6acec-154">Create a resource account without a phone number</span></span>

<span data-ttu-id="6acec-155">Para crear una cuenta de recursos que no necesite un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="6acec-155">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="6acec-156">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="6acec-156">Create a new resource account.</span></span> <span data-ttu-id="6acec-157">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="6acec-157">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="6acec-158">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6acec-158">Set up one of the following:</span></span>
   - [<span data-ttu-id="6acec-159">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-159">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="6acec-160">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-160">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="6acec-161">Asignar la cuenta de recursos al servicio.</span><span class="sxs-lookup"><span data-stu-id="6acec-161">Assign the resource account to the service.</span></span> <span data-ttu-id="6acec-162">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="6acec-162">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="6acec-163">Crear una cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6acec-163">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="6acec-164">Una vez que haya comprado una licencia de sistema telefónico y un plan de llamadas, usando el centro de administración de Microsoft Teams, vaya a**cuentas de recursos** **de configuración** > de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="6acec-164">After you've bought a Phone System license and a Calling Plan, using Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Captura de pantalla de la página cuentas de recursos](media/r-a-master.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="6acec-167">Para crear una cuenta de recursos, haga clic en **+ nueva cuenta**.</span><span class="sxs-lookup"><span data-stu-id="6acec-167">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="6acec-168">En la ventana emergente, rellene el nombre para mostrar y el nombre de usuario de la cuenta de recursos (el nombre de dominio debe llenarse automáticamente) y luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6acec-168">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Captura de pantalla de las opciones de la nueva cuenta de recursos](media/res-acct.png)

<span data-ttu-id="6acec-170">A continuación, aplique una licencia a la cuenta de recursos en el centro de administración de O365, como se describe en [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="6acec-170">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="6acec-171">Editar el nombre de la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="6acec-171">Edit resource account name</span></span>

<span data-ttu-id="6acec-172">![Icono del número 2, que hace referencia a una llamada en la](media/sfbcallout2.png) captura de pantalla anterior, puede editar el nombre para mostrar la cuenta de recursos mediante la opción **Editar** .</span><span class="sxs-lookup"><span data-stu-id="6acec-172">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="6acec-173">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="6acec-173">Click **Save** when you are done.</span></span>
<span data-ttu-id="6acec-174">![Captura de pantalla de la opción Editar cuenta de recursos](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="6acec-174">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="6acec-175">Asignar o cancelar la asignación de números de teléfono y servicios</span><span class="sxs-lookup"><span data-stu-id="6acec-175">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="6acec-176">![Icono del número 3, que hace referencia a una llamada en la](media/sfbcallout3.png) captura de pantalla anterior una vez que ha creado la cuenta de recurso y asignada la licencia, puede hacer clic en **asignar/anular asignación** para asignar un número de servicio a la cuenta de recursos o asignar el recurso. cuenta a un operador automático o a una cola de llamadas que ya exista.</span><span class="sxs-lookup"><span data-stu-id="6acec-176">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="6acec-177">La asignación de un número de enrutamiento directo puede realizarse solo con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6acec-177">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="6acec-178">Si la cola de llamadas o el operador automático siguen necesitando crearse, puede vincular la cuenta de recursos mientras la crea.</span><span class="sxs-lookup"><span data-stu-id="6acec-178">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="6acec-179">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="6acec-179">Click **Save** when you are done.</span></span>

<span data-ttu-id="6acec-180">Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, tendrá que usar PowerShell, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="6acec-180">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6acec-181">Si su inquilino no tiene una licencia de sistema de teléfono, una comprobación interna provocará un error cuando intente asignar el número de teléfono a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="6acec-181">If your tenant doesn't have a Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="6acec-182">No podrá asignar el número ni asociar la cuenta de recursos con un servicio.</span><span class="sxs-lookup"><span data-stu-id="6acec-182">You won't be able to assign the number or associate the resource account with a service.</span></span>

![Captura de pantalla de las opciones de asignar/quitar asignación](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="6acec-184">Crear una cuenta de recursos en PowerShell</span><span class="sxs-lookup"><span data-stu-id="6acec-184">Create a resource account in Powershell</span></span>

<span data-ttu-id="6acec-185">En función de si su cuenta de recursos se encuentra en línea o local, tendrá que conectar con el símbolo del sistema de PowerShell adecuado con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="6acec-185">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="6acec-186">Los siguientes ejemplos de cmdlet de PowerShell suponen que la cuenta de recursos está conectada en línea mediante [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para crear una cuenta de recursos que se ha conectado en línea.</span><span class="sxs-lookup"><span data-stu-id="6acec-186">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="6acec-187">Las cuentas de recursos hospedadas localmente en Skype empresarial Server 2019 que pueden usarse con las colas de llamadas en la nube y los operadores automáticos de la nube, consulte [configurar colas de llamadas en la](/skypeforbusiness/hybrid/configure-call-queue.md) nube o [configurar operadores automáticos de la nube](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="6acec-187">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="6acec-188">Las implementaciones híbridas (números alojados en enrutamiento directo) usarán [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6acec-188">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="6acec-189">Los IDENTIFICADOres de la aplicación que necesita usar al crear las instancias de la aplicación son:</span><span class="sxs-lookup"><span data-stu-id="6acec-189">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="6acec-190">**Operador automático:** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="6acec-190">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="6acec-191">**Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="6acec-191">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="6acec-192">Si quiere que los usuarios locales puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos locales, ya que las cuentas de recursos en línea no se sincronizan con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6acec-192">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="6acec-193">Para crear una cuenta de recursos en línea para usarla con un operador automático, use el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="6acec-193">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="6acec-194">No podrá usar la cuenta de recursos hasta que aplique una licencia.</span><span class="sxs-lookup"><span data-stu-id="6acec-194">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="6acec-195">Para obtener información sobre cómo aplicar una licencia a una cuenta en el centro de administración de O365, vea [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , así como [asignar licencias de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="6acec-195">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="6acec-196">Faculta Una vez que se aplica la licencia correcta a la cuenta de recursos, puede establecer un número de teléfono para la cuenta de recursos, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="6acec-196">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="6acec-197">No todas las cuentas de recursos requerirán un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6acec-197">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="6acec-198">Si no aplicó una licencia a la cuenta de recursos, la asignación de número de teléfono fallará.</span><span class="sxs-lookup"><span data-stu-id="6acec-198">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="6acec-199">Para obtener más información sobre este comando [, vea Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="6acec-199">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="6acec-200">Es más fácil establecer el número de teléfono en línea con el centro de administración de Microsoft Teams, como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6acec-200">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="6acec-201">Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6acec-201">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="6acec-202">Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6acec-202">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="6acec-203">Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a**cuentas de recursos**de **configuración**  > de toda la organización, seleccione la cuenta de recursos en la que necesita cambiar la configuración y, a continuación, haga clic en el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="6acec-203">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="6acec-204">en la pantalla **Editar cuenta de recursos** , podrá cambiar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="6acec-204">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="6acec-205">**Nombre para mostrar** de la cuenta</span><span class="sxs-lookup"><span data-stu-id="6acec-205">**Display name** for the account</span></span>
- <span data-ttu-id="6acec-206">Cola de llamadas o operador automático que usa la cuenta</span><span class="sxs-lookup"><span data-stu-id="6acec-206">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="6acec-207">Número de teléfono asignado a la cuenta</span><span class="sxs-lookup"><span data-stu-id="6acec-207">Phone number assigned to the account</span></span>

<span data-ttu-id="6acec-208">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6acec-208">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="6acec-209">Eliminar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="6acec-209">Delete a resource account</span></span>

<span data-ttu-id="6acec-210">Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente.</span><span class="sxs-lookup"><span data-stu-id="6acec-210">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="6acec-211">Puede hacerlo usando los siguientes commandlet:</span><span class="sxs-lookup"><span data-stu-id="6acec-211">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="6acec-212">Una vez que lo haga, puede eliminar la cuenta de recursos del portal de administración de O365, en la pestaña usuarios.</span><span class="sxs-lookup"><span data-stu-id="6acec-212">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6acec-213">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="6acec-213">Troubleshooting</span></span>

<span data-ttu-id="6acec-214">En caso de que no vea el número de teléfono asignado a la cuenta de recursos en el centro de administración de Teams y no pueda asignarle el número, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6acec-214">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="6acec-215">Si el atributo Departamento muestra el punto de conexión de aplicaciones de Skype empresarial, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6acec-215">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> <span data-ttu-id="6acec-216">Actualice la página web del centro de administración de equipos después de ejecutar el cmldet y debería poder asignar el número correctamente.</span><span class="sxs-lookup"><span data-stu-id="6acec-216">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="6acec-217">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="6acec-217">Related Information</span></span>

<span data-ttu-id="6acec-218">Para las implementaciones híbridas con Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="6acec-218">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="6acec-219">Planear los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-219">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="6acec-220">Configurar los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-220">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="6acec-221">Para las implementaciones de Teams o Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="6acec-221">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="6acec-222">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="6acec-222">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="6acec-223">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-223">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="6acec-224">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="6acec-224">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="6acec-225">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="6acec-225">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="6acec-226">Nuevo: CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="6acec-226">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="6acec-227">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="6acec-227">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
