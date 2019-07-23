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
ms.openlocfilehash: 1dd3fd8c7a9300b9c887cbc0c3cd3611b378d0c9
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821065"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="f3758-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3758-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="f3758-104">Una cuenta de recursos también se conoce como un *objeto de usuario* deshabilitado en Azure Active Directory y se puede usar para representar recursos en general.</span><span class="sxs-lookup"><span data-stu-id="f3758-104">A resource account is also known as a *disabled user object* in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="f3758-105">En Exchange podría usarse para representar salas de conferencias, por ejemplo, y permitirles que tengan un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f3758-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="f3758-106">Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f3758-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="f3758-107">En Microsoft Teams o Skype empresarial online, cada cola de llamadas de sistema telefónica o operador automático debe tener una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="f3758-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="f3758-108">Si una cuenta de recursos necesita un número de teléfono asignado, dependerá del uso previsto de la cola de llamadas asociada o del operador automático.</span><span class="sxs-lookup"><span data-stu-id="f3758-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="f3758-109">Consulte los artículos sobre las colas de llamadas y los operadores automáticos vinculados al final de este artículo antes de asignar un número de teléfono a una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="f3758-110">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="f3758-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="f3758-111">Para cuentas de recursos alojados en Skype empresarial Server 2019, consulte [configurar cuentas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="f3758-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>


## <a name="overview"></a><span data-ttu-id="f3758-112">Información general</span><span class="sxs-lookup"><span data-stu-id="f3758-112">Overview</span></span>

<span data-ttu-id="f3758-113">Suponiendo que su organización use al menos una licencia de sistema telefónica, para asignar un número de teléfono a un servicio de sistema telefónico, tendrá que dirigir las diversas dependencias de la siguiente secuencia:</span><span class="sxs-lookup"><span data-stu-id="f3758-113">Assuming that your organization is using at least one Phone System License, to assigning a Phone System service a phone number, you will need to address the various dependencies in the following sequence:</span></span>

1. <span data-ttu-id="f3758-114">Obtener un número de servicio.</span><span class="sxs-lookup"><span data-stu-id="f3758-114">Obtain a service number.</span></span>
2. <span data-ttu-id="f3758-115">Obtener una licencia de [usuario virtual](teams-add-on-licensing/virtual-user.md) del sistema telefónico o una licencia de sistema telefónico normal para usarla con la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-115">Obtain a Phone System [Virtual user license](teams-add-on-licensing/virtual-user.md) or a regular Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="f3758-116">Crear la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-116">Create the resource account.</span></span> <span data-ttu-id="f3758-117">Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f3758-117">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="f3758-118">Asigne la licencia de usuario virtual del sistema telefónico o del sistema telefónico a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-118">Assign the Phone System or a Phone System Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="f3758-119">Asigne un número de teléfono de servicio a la cuenta de recursos a la que acaba de asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="f3758-119">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="f3758-120">Crear un servicio de sistema de teléfono (una cola de llamadas o un operador automático).</span><span class="sxs-lookup"><span data-stu-id="f3758-120">Create a Phone System service (a call queue or auto attendant).</span></span>
7. <span data-ttu-id="f3758-121">Vincular la cuenta de recursos con un servicio.</span><span class="sxs-lookup"><span data-stu-id="f3758-121">Link the resource account with a service.</span></span>

<span data-ttu-id="f3758-122">Si el operador automático o la cola de llamadas están anidados bajo un operador automático de nivel superior, la cuenta de recursos asociada solo necesita un número de teléfono si desea tener varios puntos de entrada en la estructura de las colas de llamadas y los operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="f3758-122">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="f3758-123">Para redirigir las llamadas a las personas de su organización que estén conectadas en línea, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3758-123">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="f3758-124">Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f3758-124">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="f3758-125">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3758-125">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f3758-126">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f3758-126">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="f3758-127">Para evitar problemas con la cuenta de recursos, siga estos pasos en este orden.</span><span class="sxs-lookup"><span data-stu-id="f3758-127">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="f3758-128">Si el servicio del sistema telefónico que está creando va a estar anidado y no necesitará un número de teléfono, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3758-128">If the Phone System service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="f3758-129">Crear la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="f3758-129">Create the resource account</span></span>  
2. <span data-ttu-id="f3758-130">Crear un servicio de sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="f3758-130">Create a Phone System service</span></span>
3. <span data-ttu-id="f3758-131">Asociar la cuenta de recursos con un servicio de sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="f3758-131">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="f3758-132">Crear una cuenta de recursos con un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="f3758-132">Create a resource account with a phone number</span></span>

<span data-ttu-id="f3758-133">Para crear una cuenta de recursos que use un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="f3758-133">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="f3758-134">Puerto o recibe un número de servicio de pago o gratuito.</span><span class="sxs-lookup"><span data-stu-id="f3758-134">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="f3758-135">El número no se puede asignar a ningún otro servicio de voz o cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-135">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="f3758-136">Antes de asignar un número de teléfono a una cuenta de recursos, tendrá que obtener o migrar los números de teléfono de pago o gratuitos existentes.</span><span class="sxs-lookup"><span data-stu-id="f3758-136">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f3758-137">Una vez que obtenga los números de teléfono de pago o gratuitos, aparecerán en los\*\*\*\* > **números de teléfono**del **Centro** > de administración de Microsoft Teams, y el **tipo de número** que aparece en la lista aparecerá como **servicio-** gratuito.</span><span class="sxs-lookup"><span data-stu-id="f3758-137">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f3758-138">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f3758-138">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="f3758-139">Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual del sistema telefónico de sistema de costos.</span><span class="sxs-lookup"><span data-stu-id="f3758-139">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="f3758-140">Esto proporciona capacidades de sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y de operador automático.</span><span class="sxs-lookup"><span data-stu-id="f3758-140">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="f3758-141">Obtener una licencia de usuario virtual del sistema telefónico o una licencia de sistema telefónico normal.</span><span class="sxs-lookup"><span data-stu-id="f3758-141">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span> 

   <span data-ttu-id="f3758-142">Para obtener la licencia virtual, desde el centro de administración de Microsoft 365, vaya a suscripciones del**complemento** **servicios** > de compra de **facturación** > y desplácese hasta el final: verá la licencia "phone system-virtual User".</span><span class="sxs-lookup"><span data-stu-id="f3758-142">To get the virtual license, from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="f3758-143">Seleccione **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f3758-143">Select **Buy now**.</span></span> <span data-ttu-id="f3758-144">Hay un costo cero, pero sigue siendo necesario seguir estos pasos para adquirir la licencia.</span><span class="sxs-lookup"><span data-stu-id="f3758-144">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="f3758-145">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="f3758-145">Create a new resource account.</span></span> <span data-ttu-id="f3758-146">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="f3758-146">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="f3758-147">Asigne una licencia de [usuario virtual](teams-add-on-licensing/virtual-user.md) o de sistema telefónico a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-147">Assign  [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="f3758-148">Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md) y [asignar licencias a un usuario](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="f3758-148">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="f3758-149">Asignar el número de servicio a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-149">Assign the service number to the resource account.</span></span> <span data-ttu-id="f3758-150">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="f3758-150">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="f3758-151">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3758-151">Set up one of the following:</span></span>
   - [<span data-ttu-id="f3758-152">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-152">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="f3758-153">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-153">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="f3758-154">Vincule la cuenta de recursos al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f3758-154">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="f3758-155">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="f3758-155">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="f3758-156">Crear una cuenta de recursos sin un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="f3758-156">Create a resource account without a phone number</span></span>

<span data-ttu-id="f3758-157">Para crear una cuenta de recursos que no necesite un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="f3758-157">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="f3758-158">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="f3758-158">Create a new resource account.</span></span> <span data-ttu-id="f3758-159">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="f3758-159">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="f3758-160">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3758-160">Set up one of the following:</span></span>
   - [<span data-ttu-id="f3758-161">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-161">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="f3758-162">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-162">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="f3758-163">Asignar la cuenta de recursos al servicio.</span><span class="sxs-lookup"><span data-stu-id="f3758-163">Assign the resource account to the service.</span></span> <span data-ttu-id="f3758-164">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="f3758-164">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="f3758-165">Crear una cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3758-165">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="f3758-166">Una vez que haya comprado una licencia de sistema telefónico, usando el centro de administración de Microsoft Teams, vaya a**cuentas de recursos** **de configuración** > de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="f3758-166">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Captura de pantalla de la página cuentas de recursos](media/r-a-master.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<span data-ttu-id="f3758-169">Para crear una cuenta de recursos, haga clic en **+ nueva cuenta**.</span><span class="sxs-lookup"><span data-stu-id="f3758-169">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="f3758-170">En la ventana emergente, rellene el nombre para mostrar y el nombre de usuario de la cuenta de recursos (el nombre de dominio debe llenarse automáticamente) y luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f3758-170">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Captura de pantalla de las opciones de la nueva cuenta de recursos](media/res-acct.png)

<span data-ttu-id="f3758-172">A continuación, aplique una licencia a la cuenta de recursos en el centro de administración de O365, como se describe en [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="f3758-172">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="f3758-173">Editar el nombre de la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="f3758-173">Edit resource account name</span></span>

<span data-ttu-id="f3758-174">![Icono del número 2, que hace referencia a una llamada en la](media/sfbcallout2.png) captura de pantalla anterior, puede editar el nombre para mostrar la cuenta de recursos mediante la opción **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f3758-174">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="f3758-175">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="f3758-175">Click **Save** when you are done.</span></span>
<span data-ttu-id="f3758-176">![Captura de pantalla de la opción Editar cuenta de recursos](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="f3758-176">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="f3758-177">Asignar o cancelar la asignación de números de teléfono y servicios</span><span class="sxs-lookup"><span data-stu-id="f3758-177">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="f3758-178">![Icono del número 3, que hace referencia a una llamada en la](media/sfbcallout3.png) captura de pantalla anterior una vez que ha creado la cuenta de recurso y asignada la licencia, puede hacer clic en **asignar/anular asignación** para asignar un número de servicio a la cuenta de recursos o asignar el recurso. cuenta a un operador automático o a una cola de llamadas que ya exista.</span><span class="sxs-lookup"><span data-stu-id="f3758-178">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="f3758-179">La asignación de un número de enrutamiento directo puede realizarse solo con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f3758-179">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="f3758-180">Si la cola de llamadas o el operador automático siguen necesitando crearse, puede vincular la cuenta de recursos mientras la crea.</span><span class="sxs-lookup"><span data-stu-id="f3758-180">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="f3758-181">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="f3758-181">Click **Save** when you are done.</span></span>

<span data-ttu-id="f3758-182">Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, tendrá que usar PowerShell, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3758-182">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3758-183">Si su cuenta de recursos no tiene una licencia de usuario virtual o de teléfono, una comprobación interna producirá un error cuando intente asignar el número de teléfono a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3758-183">If your resource account doesn't have a Virtual User or Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="f3758-184">No podrá asignar el número ni asociar la cuenta de recursos con un servicio.</span><span class="sxs-lookup"><span data-stu-id="f3758-184">You won't be able to assign the number or associate the resource account with a service.</span></span>

![Captura de pantalla de las opciones de asignar/quitar asignación](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="f3758-186">Cambiar una cuenta de recursos existente para usar una licencia de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="f3758-186">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="f3758-187">Si decide cambiar las licencias de la cuenta de recursos existente de una licencia de sistema telefónico a una licencia de usuario virtual, tendrá que aquire la licencia de usuario virtual gratuita y, a continuación, seguir los pasos vinculados en el centro de administración de Microsoft 365 para [mover usuarios a un plan diferente](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="f3758-187">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to  aquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="f3758-188">Quitar siempre una licencia de sistema telefónico completo y asignar la licencia de usuario virtual en la misma actividad de licencia.</span><span class="sxs-lookup"><span data-stu-id="f3758-188">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="f3758-189">Si quita la licencia anterior, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="f3758-189">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="f3758-190">Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para la licencia de usuario virtual y quite la cuenta de recursos dañados.</span><span class="sxs-lookup"><span data-stu-id="f3758-190">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="f3758-191">Crear una cuenta de recursos en PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3758-191">Create a resource account in Powershell</span></span>

<span data-ttu-id="f3758-192">En función de si su cuenta de recursos se encuentra en línea o local, tendrá que conectar con el símbolo del sistema de PowerShell adecuado con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="f3758-192">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="f3758-193">Los siguientes ejemplos de cmdlet de PowerShell suponen que la cuenta de recursos está conectada en línea mediante [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para crear una cuenta de recursos que se ha conectado en línea.</span><span class="sxs-lookup"><span data-stu-id="f3758-193">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="f3758-194">Las cuentas de recursos hospedadas localmente en Skype empresarial Server 2019 que pueden usarse con las colas de llamadas en la nube y los operadores automáticos de la nube, consulte [configurar colas de llamadas en la](/skypeforbusiness/hybrid/configure-call-queue.md) nube o [configurar operadores automáticos de la nube](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="f3758-194">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="f3758-195">Las implementaciones híbridas (números alojados en enrutamiento directo) usarán [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f3758-195">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="f3758-196">Los IDENTIFICADOres de la aplicación que necesita usar al crear las instancias de la aplicación son:</span><span class="sxs-lookup"><span data-stu-id="f3758-196">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="f3758-197">**Operador automático:** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="f3758-197">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="f3758-198">**Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="f3758-198">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="f3758-199">Si quiere que los usuarios locales puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos locales, ya que las cuentas de recursos en línea no se sincronizan con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3758-199">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="f3758-200">Para crear una cuenta de recursos en línea para usarla con un operador automático, use el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="f3758-200">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="f3758-201">No podrá usar la cuenta de recursos hasta que aplique una licencia.</span><span class="sxs-lookup"><span data-stu-id="f3758-201">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="f3758-202">Para obtener información sobre cómo aplicar una licencia a una cuenta en el centro de administración de O365, vea [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , así como [asignar licencias de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="f3758-202">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="f3758-203">Faculta Una vez que se aplica la licencia correcta a la cuenta de recursos, puede establecer un número de teléfono para la cuenta de recursos, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="f3758-203">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="f3758-204">No todas las cuentas de recursos requerirán un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f3758-204">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="f3758-205">Si no aplicó una licencia a la cuenta de recursos, la asignación de número de teléfono fallará.</span><span class="sxs-lookup"><span data-stu-id="f3758-205">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="f3758-206">Para obtener más información sobre este comando [, vea Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f3758-206">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="f3758-207">Es más fácil establecer el número de teléfono en línea con el centro de administración de Microsoft Teams, como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f3758-207">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="f3758-208">Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f3758-208">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="f3758-209">Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3758-209">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="f3758-210">Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a**cuentas de recursos**de **configuración**  > de toda la organización, seleccione la cuenta de recursos en la que necesita cambiar la configuración y, a continuación, haga clic en el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f3758-210">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="f3758-211">en la pantalla **Editar cuenta de recursos** , podrá cambiar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="f3758-211">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="f3758-212">**Nombre para mostrar** de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f3758-212">**Display name** for the account</span></span>
- <span data-ttu-id="f3758-213">Cola de llamadas o operador automático que usa la cuenta</span><span class="sxs-lookup"><span data-stu-id="f3758-213">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="f3758-214">Número de teléfono asignado a la cuenta</span><span class="sxs-lookup"><span data-stu-id="f3758-214">Phone number assigned to the account</span></span>

<span data-ttu-id="f3758-215">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f3758-215">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="f3758-216">Eliminar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="f3758-216">Delete a resource account</span></span>

<span data-ttu-id="f3758-217">Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente.</span><span class="sxs-lookup"><span data-stu-id="f3758-217">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="f3758-218">Puede hacerlo usando los siguientes commandlet:</span><span class="sxs-lookup"><span data-stu-id="f3758-218">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="f3758-219">Una vez que lo haga, puede eliminar la cuenta de recursos del portal de administración de O365, en la pestaña usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3758-219">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f3758-220">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="f3758-220">Troubleshooting</span></span>

<span data-ttu-id="f3758-221">En caso de que no vea el número de teléfono asignado a la cuenta de recursos en el centro de administración de Teams y no pueda asignarle el número, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3758-221">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="f3758-222">Si el atributo Departamento muestra el punto de conexión de aplicaciones de Skype empresarial, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f3758-222">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="f3758-223">Actualice la página web del centro de administración de equipos después de ejecutar el cmldet y debería poder asignar el número correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3758-223">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="f3758-224">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="f3758-224">Related Information</span></span>

<span data-ttu-id="f3758-225">Para las implementaciones híbridas con Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f3758-225">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="f3758-226">Planear los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-226">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="f3758-227">Planear las colas de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-227">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="f3758-228">Configurar cuentas de recursos locales</span><span class="sxs-lookup"><span data-stu-id="f3758-228">Configure onprem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="f3758-229">Para las implementaciones de Teams o Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="f3758-229">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="f3758-230">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="f3758-230">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="f3758-231">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-231">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="f3758-232">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="f3758-232">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="f3758-233">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="f3758-233">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="f3758-234">Nuevo: CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="f3758-234">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="f3758-235">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f3758-235">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="f3758-236">Licencia de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="f3758-236">Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
