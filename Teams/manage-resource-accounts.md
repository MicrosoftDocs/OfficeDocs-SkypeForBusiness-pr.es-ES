---
title: Administrar cuentas de recursos en Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: En este artículo, aprenderá a crear, editar y administrar cuentas de recursos en Microsoft Teams.
ms.openlocfilehash: 90e8ab26782424c6cc341936f185a253c6d1fbe6
ms.sourcegitcommit: eb8b573a426b6a68c763968c4cd2d45bc0d6a4b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46672861"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="e559a-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e559a-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="e559a-104">Una cuenta de recursos también se conoce como un *objeto de usuario deshabilitado* en Azure ad, y se puede usar para representar recursos en general.</span><span class="sxs-lookup"><span data-stu-id="e559a-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="e559a-105">En Exchange podría usarse para representar salas de conferencias, por ejemplo, y permitirles que tengan un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e559a-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="e559a-106">Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e559a-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="e559a-107">En Microsoft Teams o Skype empresarial online, cada cola de llamadas de sistema o operador automático debe tener al menos una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="e559a-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="e559a-108">Si una cuenta de recursos necesita un número de teléfono asignado dependerá del uso previsto de la cola de llamadas asociada o del operador automático, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="e559a-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="e559a-109">También puede consultar los artículos sobre las colas de llamadas y los operadores automáticos vinculados al final de este artículo antes de asignar un número de teléfono a una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![ejemplo de cuentas de recursos y licencias de usuario](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="e559a-111">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="e559a-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="e559a-112">Para cuentas de recursos alojados en Skype empresarial Server 2019, consulte [configurar cuentas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="e559a-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="e559a-113">Asignar un número de teléfono a una cola de llamadas de sistema</span><span class="sxs-lookup"><span data-stu-id="e559a-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="e559a-114">Si su organización ya usa al menos una licencia de sistema telefónico, para asignar un número de teléfono a una cola de llamadas de sistema, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e559a-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="e559a-115">Obtener un número de servicio.</span><span class="sxs-lookup"><span data-stu-id="e559a-115">Obtain a service number.</span></span>
2. <span data-ttu-id="e559a-116">Obtener un sistema telefónico gratis: [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) o una licencia de sistema telefónico de pagos para usar con la cuenta de recursos o una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="e559a-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="e559a-117">Crear la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-117">Create the resource account.</span></span> <span data-ttu-id="e559a-118">Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e559a-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="e559a-119">Asigne el sistema telefónico o un sistema telefónico (licencia de usuario virtual) a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="e559a-120">Asigne un número de teléfono de servicio a la cuenta de recursos a la que acaba de asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="e559a-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="e559a-121">Crear una cola de llamadas de sistema telefónicas o un operador automático</span><span class="sxs-lookup"><span data-stu-id="e559a-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="e559a-122">Vincular la cuenta de recursos con una cola de llamadas o un operador automático.</span><span class="sxs-lookup"><span data-stu-id="e559a-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="e559a-123">Si el operador automático o la cola de llamadas están anidados bajo un operador automático de nivel superior, la cuenta de recursos asociada solo necesita un número de teléfono si desea tener varios puntos de entrada en la estructura de las colas de llamadas y los operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="e559a-123">If the auto attendant or call queue is nested under a top-level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="e559a-124">Para redirigir las llamadas a las personas de su organización que estén conectadas, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas a Microsoft 365 o de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e559a-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="e559a-125">Consulte [asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="e559a-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="e559a-126">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e559a-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e559a-127">Por ejemplo, ejecute: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e559a-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="e559a-128">Para evitar problemas con la cuenta de recursos, siga estos pasos en este orden.</span><span class="sxs-lookup"><span data-stu-id="e559a-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="e559a-129">Si la cola de llamadas del sistema telefónicas o el operador automático que está creando va a estar anidado y no necesitará un número de teléfono, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e559a-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="e559a-130">Crear la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="e559a-130">Create the resource account</span></span>
2. <span data-ttu-id="e559a-131">Crear una cola de llamadas de sistema telefónicas o un operador automático</span><span class="sxs-lookup"><span data-stu-id="e559a-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="e559a-132">Asociar la cuenta de recursos a una cola de llamadas de sistema telefónico o un operador automático</span><span class="sxs-lookup"><span data-stu-id="e559a-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="e559a-133">Crear una cuenta de recursos con un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="e559a-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="e559a-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="e559a-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e559a-135">Un número de teléfono no se asigna directamente al operador automático o a la cola de llamadas, sino a la cuenta de recursos asociada al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e559a-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="e559a-136">Para un operador automático de nivel superior o una cola de llamadas, es necesario vincular un número de teléfono a su operador automático.</span><span class="sxs-lookup"><span data-stu-id="e559a-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="e559a-137">Para crear una cuenta de recursos que use un número de teléfono, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e559a-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="e559a-138">Puerto o recibe un número de servicio de pago o gratuito.</span><span class="sxs-lookup"><span data-stu-id="e559a-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="e559a-139">El número no se puede asignar a ningún otro servicio de voz o cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="e559a-140">Antes de asignar un número de teléfono a una cuenta de recursos, necesita obtener o migrar los números de teléfono de pago o gratuitos existentes.</span><span class="sxs-lookup"><span data-stu-id="e559a-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="e559a-141">Después de recibir los números de teléfono de pago o gratuitos, aparecerán en los números de teléfono del **centro de administración de Microsoft Teams**  >  **Voice**  >  **Phone numbers**, y el **tipo de número** se indicará como **servicio-** gratuito.</span><span class="sxs-lookup"><span data-stu-id="e559a-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="e559a-142">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e559a-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="e559a-143">Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual del sistema telefónico de sistema de costos.</span><span class="sxs-lookup"><span data-stu-id="e559a-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="e559a-144">Esto proporciona capacidades de sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y de operador automático.</span><span class="sxs-lookup"><span data-stu-id="e559a-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="e559a-145">Obtener una licencia de usuario virtual del sistema telefónico o una licencia de sistema telefónico normal.</span><span class="sxs-lookup"><span data-stu-id="e559a-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="e559a-146">Para obtener la licencia de usuario virtual, en el centro de administración de Microsoft 365 **Billing**, vaya a  >  suscripciones del complemento de**servicios de compra**de facturación  >  **Add-on subscriptions** y desplácese hasta el final: verá la licencia "phone system-virtual User".</span><span class="sxs-lookup"><span data-stu-id="e559a-146">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="e559a-147">Seleccione **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="e559a-147">Select **Buy now**.</span></span> <span data-ttu-id="e559a-148">Hay un costo cero, pero sigue siendo necesario seguir estos pasos para adquirir la licencia.</span><span class="sxs-lookup"><span data-stu-id="e559a-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="e559a-149">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="e559a-149">Create a new resource account.</span></span> <span data-ttu-id="e559a-150">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="e559a-150">See [Create a resource account in the Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in PowerShell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="e559a-151">Asigne un sistema telefónico: [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) o licencia de sistema telefónico a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="e559a-152">Consulte [asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) y [asignar licencias a los usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="e559a-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
5. <span data-ttu-id="e559a-153">Asignar el número de servicio a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="e559a-154">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="e559a-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="e559a-155">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e559a-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="e559a-156">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="e559a-157">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="e559a-158">Vincule la cuenta de recursos al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e559a-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="e559a-159">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="e559a-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="e559a-160">Al crear una cuenta de recursos al crear un operador automático, las licencias se aplican automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e559a-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="e559a-161">Crear una cuenta de recursos sin un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="e559a-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="e559a-162">Un operador automático o una cola de llamadas anidados requerirán una cuenta de recursos pero, en muchos casos, la cuenta de recursos correspondiente no necesitará un número de teléfono y las licencias necesarias para admitir un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e559a-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="e559a-163">Para crear una cuenta de recursos que no necesite un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="e559a-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="e559a-164">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="e559a-164">Create a new resource account.</span></span> <span data-ttu-id="e559a-165">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="e559a-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in PowerShell](#create-a-resource-account-in-powershell).</span></span>

2. <span data-ttu-id="e559a-166">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e559a-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="e559a-167">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="e559a-168">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
   
3. <span data-ttu-id="e559a-169">Asignar la cuenta de recursos a la cola de llamadas o al operador automático.</span><span class="sxs-lookup"><span data-stu-id="e559a-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="e559a-170">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="e559a-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e559a-171">Crear una cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e559a-171">Create a resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="e559a-172">Una vez que haya comprado una licencia de sistema telefónico, en el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a cuentas de recursos de **configuración de toda la organización**  >  **Resource accounts**.</span><span class="sxs-lookup"><span data-stu-id="e559a-172">After you've bought a Phone System license, in the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**.</span></span>

![Captura de pantalla de la página cuentas de recursos](media/r-a-master.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/teamscallout1.png)

<span data-ttu-id="e559a-175">Para crear una nueva cuenta de recursos, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e559a-175">To create a new resource account, click **Add**.</span></span> <span data-ttu-id="e559a-176">En el panel **Agregar cuenta de recursos** , rellene el campo **nombre para mostrar**, nombre de **usuario** (el nombre de dominio debe rellenarse automáticamente) y tipo de **cuenta de recurso** para la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-176">In the **Add resource account** pane, fill out **Display name**, **Username** (the domain name should populate automatically), and **Resource account type** for the resource account.</span></span> <span data-ttu-id="e559a-177">El tipo de cuenta de recurso puede ser de **operador automático** o **cola de llamadas**, en función de la aplicación que desee asociar a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-177">The resource account type can be either **Auto attendant** or **Call queue**, depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="e559a-178">Cuando esté listo, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e559a-178">When you're ready, click **Save**.</span></span>

![Captura de pantalla de las opciones de nueva cuenta de recursos](media/res-acct.png)

<span data-ttu-id="e559a-180">A continuación, aplique una licencia a la cuenta de recursos en el centro de administración de Microsoft 365, como se describe en [asignar licencias a los usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="e559a-180">Next, apply a license to the resource account in the Microsoft 365 Admin center, as described in [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="e559a-181">Editar cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="e559a-181">Edit resource account</span></span> 

<span data-ttu-id="e559a-182">![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior, ](media/teamscallout2.png) puede editar el **nombre para mostrar** de la cuenta de recursos y el tipo de **cuenta de recursos** con la opción **Editar** .</span><span class="sxs-lookup"><span data-stu-id="e559a-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="e559a-183">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="e559a-183">Click **Save** when you are done.</span></span>

![Captura de pantalla de la opción Editar cuenta de recursos](media/r-a-edit.png)

<span data-ttu-id="e559a-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="e559a-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="e559a-186">Asignar o cancelar la asignación de números de teléfono y servicios</span><span class="sxs-lookup"><span data-stu-id="e559a-186">Assign/unassign phone numbers and services</span></span>

<span data-ttu-id="e559a-187">![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior, ](media/teamscallout3.png) después de crear la cuenta de recurso y asignarle la licencia, puede hacer clic en **asignar/desasignar** para asignar un número de servicio a la cuenta de recursos, configurar el tipo de número de teléfono o asignar la cuenta de recursos a un operador automático específico o a una cola de llamadas que ya exista.</span><span class="sxs-lookup"><span data-stu-id="e559a-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) After you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="e559a-188">La asignación de un número de enrutamiento directo puede realizarse solo con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e559a-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="e559a-189">Si aún no ha creado la cola de llamadas o el operador automático que va a asociar a la cuenta de recursos, deje el campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="e559a-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account, leave that field blank.</span></span> <span data-ttu-id="e559a-190">Puede vincular la cuenta de recursos mientras la crea.</span><span class="sxs-lookup"><span data-stu-id="e559a-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="e559a-191">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="e559a-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="e559a-192">Las opciones para el **tipo de número de teléfono** son:</span><span class="sxs-lookup"><span data-stu-id="e559a-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="e559a-193">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e559a-193">None</span></span>
- <span data-ttu-id="e559a-194">Online</span><span class="sxs-lookup"><span data-stu-id="e559a-194">Online</span></span>
- <span data-ttu-id="e559a-195">Gratuitos</span><span class="sxs-lookup"><span data-stu-id="e559a-195">Toll-free</span></span>
- <span data-ttu-id="e559a-196">Local</span><span class="sxs-lookup"><span data-stu-id="e559a-196">On-premises</span></span>

![Captura de pantalla de las opciones de asignar/quitar asignación](media/r-a-assign.png)

<span data-ttu-id="e559a-198">Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, tendrá que usar PowerShell, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e559a-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e559a-199">Si su cuenta de recursos no tiene una licencia válida, una comprobación interna provocará un error al intentar asignar el número de teléfono a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="e559a-200">No podrás asignar el número ni asociar la cuenta de recursos con una cola de llamadas o un operador automático.</span><span class="sxs-lookup"><span data-stu-id="e559a-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e559a-201">Un número de teléfono no se asigna directamente al operador automático o a la cola de llamadas, sino a la cuenta de recursos asociada al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e559a-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="e559a-202">Cambiar una cuenta de recursos existente para usar una licencia de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="e559a-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="e559a-203">Si decide cambiar las licencias de la cuenta de recursos existente de una licencia de sistema telefónico a una licencia de usuario virtual, tendrá que adquirir la licencia de usuario virtual gratuita y, a continuación, seguir los pasos que se indican en el centro de administración de Microsoft 365 para [mover usuarios a una suscripción diferente](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="e559a-203">If you decide to switch the licenses on your existing resource account from a Phone System license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="e559a-204">Quitar siempre una licencia de sistema telefónico completo y asignar la licencia de usuario virtual en la misma actividad de licencia.</span><span class="sxs-lookup"><span data-stu-id="e559a-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="e559a-205">Si quita la licencia anterior, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="e559a-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="e559a-206">Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para la licencia de usuario virtual y quite la cuenta de recursos dañados.</span><span class="sxs-lookup"><span data-stu-id="e559a-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="e559a-207">Crear una cuenta de recursos en PowerShell</span><span class="sxs-lookup"><span data-stu-id="e559a-207">Create a resource account in PowerShell</span></span>

<span data-ttu-id="e559a-208">En función de si la cuenta de recursos se encuentra en línea o en Skype empresarial Server 2019, tendrá que conectar con el aviso de PowerShell adecuado con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="e559a-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate PowerShell prompt with Admin privileges.</span></span>

- <span data-ttu-id="e559a-209">En los siguientes ejemplos de cmdlets de PowerShell se muestra cómo crear una cuenta de recursos conectada en línea con [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e559a-209">The following PowerShell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="e559a-210">Cuentas de recursos alojados en Skype empresarial Server 2019 que se pueden usar con las colas de llamadas en la nube y los operadores automáticos de la nube, consulte [planear colas de llamadas en la](/SkypeforBusiness/hybrid/plan-call-queue) nube o [planear operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="e559a-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="e559a-211">Las implementaciones híbridas (números alojados en enrutamiento directo) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) en un servidor local de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e559a-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="e559a-212">Los IDENTIFICADOres de la aplicación que necesita usar al crear las instancias de la aplicación son:</span><span class="sxs-lookup"><span data-stu-id="e559a-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="e559a-213">**Operador automático:** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="e559a-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="e559a-214">**Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="e559a-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="e559a-215">Si desea que los usuarios de Skype empresarial Server 2019 puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos en Skype empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e559a-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="e559a-216">Cuando los registros SRV de DNS para sipfederationtls se resuelven en Skype empresarial Server 2019, las cuentas de recursos **deben** crearse en Skype empresarial Server 2019 con el shell de administración de SfB y se pueden sincronizar con Azure ad en línea.</span><span class="sxs-lookup"><span data-stu-id="e559a-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="e559a-217">Para crear una cuenta de recursos en línea para usarla con un operador automático, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e559a-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ```powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="e559a-218">No podrá usar la cuenta de recursos hasta que aplique una licencia.</span><span class="sxs-lookup"><span data-stu-id="e559a-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="e559a-219">Para obtener información sobre cómo aplicar una licencia a una cuenta en el centro de administración de Microsoft 365, consulte[asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) y [asignar licencias de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="e559a-219">To learn how to apply a license to an account in the Microsoft 365 admin center, see[Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="e559a-220">Faculta Después de aplicar la licencia correcta a la cuenta de recursos, puede asignar un número de teléfono a la cuenta de recursos, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="e559a-220">(Optional) After the correct license is applied to the resource account, you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="e559a-221">No todas las cuentas de recursos requerirán un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e559a-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="e559a-222">Si no aplicó una licencia a la cuenta de recursos, se producirá un error en la asignación de número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e559a-222">If you didn't apply a license to the resource account, the phone number assignment will fail.</span></span>

   ```powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="e559a-223">Para obtener más información sobre este comando [, vea Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e559a-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e559a-224">Es más fácil establecer el número de teléfono en línea con el centro de administración de Microsoft Teams, como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e559a-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="e559a-225">Para asignar un número de teléfono de enrutamiento directo a una cuenta de recursos (alojada en Microsoft Teams o en Skype empresarial Server 2019), use el siguiente cmdlet para Skype empresarial online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e559a-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online PowerShell:</span></span>

   ```powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e559a-226">Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e559a-226">Manage resource account settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="e559a-227">Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a cuentas de recursos de **configuración de toda**  >  **Resource accounts**la organización, seleccione la cuenta de recursos en la que necesita cambiar la configuración y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e559a-227">To manage resource account settings in Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click **Edit**.</span></span> <span data-ttu-id="e559a-228">En el panel **Editar cuenta de recursos** , puede cambiar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="e559a-228">On the **Edit resource account** pane, you can change these settings:</span></span>

- <span data-ttu-id="e559a-229">**Nombre para mostrar** de la cuenta</span><span class="sxs-lookup"><span data-stu-id="e559a-229">**Display name** for the account</span></span>
- <span data-ttu-id="e559a-230">Cola de llamadas o operador automático que usa la cuenta</span><span class="sxs-lookup"><span data-stu-id="e559a-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="e559a-231">Número de teléfono asignado a la cuenta</span><span class="sxs-lookup"><span data-stu-id="e559a-231">Phone number assigned to the account</span></span>

<span data-ttu-id="e559a-232">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e559a-232">When finished, click **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="e559a-233">Eliminar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="e559a-233">Delete a resource account</span></span>

<span data-ttu-id="e559a-234">Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente.</span><span class="sxs-lookup"><span data-stu-id="e559a-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="e559a-235">Puede hacerlo usando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e559a-235">You can do that using the following cmdlet:</span></span>

```powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="e559a-236">Después de hacerlo, puede eliminar la cuenta de recursos en el centro de administración de Microsoft 365, en la pestaña usuarios.</span><span class="sxs-lookup"><span data-stu-id="e559a-236">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="e559a-237">Para desvincular un número de teléfono de enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e559a-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="e559a-238">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e559a-238">Troubleshooting</span></span>

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e559a-239">No puede ver el número de teléfono asignado a la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e559a-239">You don't see the phone number assigned to the resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="e559a-240">Si no ve el número de teléfono asignado a la cuenta de recursos en el centro de administración de Microsoft Teams y no puede asignarle el número, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e559a-240">If you don't see the phone number assigned to the resource account in the Microsoft Teams admin center and you are unable to assign the number from there, check the following:</span></span>

```powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="e559a-241">Si el atributo Departamento muestra el punto de conexión de aplicaciones de Skype empresarial, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e559a-241">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

```powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="e559a-242">Actualice la página web del centro de administración de equipos después de ejecutar el cmldet y debería poder asignar el número correctamente.</span><span class="sxs-lookup"><span data-stu-id="e559a-242">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a><span data-ttu-id="e559a-243">Recibe una "no podemos usar esta cuenta de recursos para servicios".</span><span class="sxs-lookup"><span data-stu-id="e559a-243">You get a "We can't use this resource account for services."</span></span> <span data-ttu-id="e559a-244">mensaje de error</span><span class="sxs-lookup"><span data-stu-id="e559a-244">error message</span></span>

<span data-ttu-id="e559a-245"><a name="blocksignin"> </a></span><span class="sxs-lookup"><span data-stu-id="e559a-245"><a name="blocksignin"> </a></span></span>

<span data-ttu-id="e559a-246">Recibe el siguiente mensaje de error cuando intenta usar una cuenta de recursos:</span><span class="sxs-lookup"><span data-stu-id="e559a-246">You get the following error message when you try to use a resource account:</span></span>

<span data-ttu-id="e559a-247">"No podemos usar esta cuenta de recursos para servicios.</span><span class="sxs-lookup"><span data-stu-id="e559a-247">"We can't use this resource account for services.</span></span> <span data-ttu-id="e559a-248">La cuenta de recursos debe estar deshabilitada y estar BLOQUEAda para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="e559a-248">The resource account must be DISABLED and BLOCKED from signing in.</span></span> <span data-ttu-id="e559a-249">Debe bloquear los inicios de sesión de esta cuenta de recursos en la página usuarios del centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e559a-249">You must BLOCK sign-ins for this resource account on the Users page in the Microsoft 365 admin center."</span></span>

<span data-ttu-id="e559a-250">Al crear una cuenta de recursos, de forma predeterminada, está deshabilitada e iniciar sesión está bloqueado para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e559a-250">When you create a resource account, by default, it's disabled and sign in is blocked for the account.</span></span> <span data-ttu-id="e559a-251">Esta configuración no debe cambiarse.</span><span class="sxs-lookup"><span data-stu-id="e559a-251">These settings shouldn't be changed.</span></span> <span data-ttu-id="e559a-252">Para resolver este mensaje de error, bloquee la cuenta de recursos para que no inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e559a-252">To resolve this error message, block the resource account from signing in.</span></span> <span data-ttu-id="e559a-253">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e559a-253">To do this:</span></span>

1. <span data-ttu-id="e559a-254">En el centro de administración de Microsoft 365, vaya a **usuarios**, buscar y, a continuación, seleccione la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e559a-254">In the Microsoft 365 admin center, go to **Users**, search for, and then select the resource account.</span></span>
2. <span data-ttu-id="e559a-255">En la parte superior del panel debajo del nombre para mostrar, haga clic en **¿bloquear este usuario?**, active la casilla **de verificación bloquear este usuario para iniciar sesión** y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e559a-255">At the top of the pane under the display name, click **Block this user?**, select the **Block this user from signing in** check box, and then select **Save changes**.</span></span>

   ![Captura de pantalla de la opción bloquear este usuario](media/res-acct-block.png)

    <span data-ttu-id="e559a-257">Después de hacerlo, verás "iniciar sesión bloqueada" en el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="e559a-257">After you do this, you'll see "Sign in blocked" under the display name.</span></span>

      ![Captura de pantalla del mensaje bloqueado de inicio de sesión](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a><span data-ttu-id="e559a-259">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="e559a-259">Related Information</span></span>

<span data-ttu-id="e559a-260">Para las implementaciones híbridas con Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="e559a-260">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="e559a-261">Planear los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-261">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="e559a-262">Planear las colas de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-262">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="e559a-263">Configurar cuentas de recursos locales</span><span class="sxs-lookup"><span data-stu-id="e559a-263">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="e559a-264">Para las implementaciones de Teams o Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="e559a-264">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="e559a-265">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="e559a-265">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="e559a-266">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-266">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="e559a-267">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="e559a-267">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="e559a-268">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="e559a-268">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="e559a-269">Nuevo: CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="e559a-269">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="e559a-270">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="e559a-270">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="e559a-271">Nuevo: CsOnlineApplicationInstanceAssociation</span><span class="sxs-lookup"><span data-stu-id="e559a-271">New-CsOnlineApplicationInstanceAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[<span data-ttu-id="e559a-272">Sistema telefónico-licencia de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="e559a-272">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
