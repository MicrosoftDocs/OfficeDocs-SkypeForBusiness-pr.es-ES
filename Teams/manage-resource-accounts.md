---
title: Administrar cuentas de recursos en Teams
ms.author: dstrome
author: dstrome
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
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Más información sobre la administración de cuentas de recursos en Microsoft Teams
ms.openlocfilehash: e7e7e644d64aeb043e6403fd60d22ebcef155ebe
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628366"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="84a3a-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84a3a-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="84a3a-104">Una cuenta de recursos también se conoce como un *objeto de usuario deshabilitado* en Azure ad, y se puede usar para representar recursos en general.</span><span class="sxs-lookup"><span data-stu-id="84a3a-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="84a3a-105">En Exchange podría usarse para representar salas de conferencias, por ejemplo, y permitirles que tengan un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="84a3a-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="84a3a-106">Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="84a3a-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="84a3a-107">En Microsoft Teams o Skype empresarial online, cada cola de llamadas de sistema o operador automático debe tener al menos una cuenta de recursos asociada.</span><span class="sxs-lookup"><span data-stu-id="84a3a-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="84a3a-108">Si una cuenta de recursos necesita un número de teléfono asignado dependerá del uso previsto de la cola de llamadas asociada o del operador automático, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="84a3a-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="84a3a-109">También puede consultar los artículos sobre las colas de llamadas y los operadores automáticos vinculados al final de este artículo antes de asignar un número de teléfono a una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![ejemplo de cuentas de recursos y licencias de usuario](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="84a3a-111">Este artículo se aplica a Microsoft Teams y a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="84a3a-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="84a3a-112">Para cuentas de recursos alojados en Skype empresarial Server 2019, consulte [configurar cuentas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="84a3a-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="84a3a-113">Información general</span><span class="sxs-lookup"><span data-stu-id="84a3a-113">Overview</span></span>

<span data-ttu-id="84a3a-114">Si su organización ya usa al menos una licencia de sistema telefónico, para asignar un número de teléfono a una cola de llamadas de sistema, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="84a3a-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="84a3a-115">Obtener un número de servicio.</span><span class="sxs-lookup"><span data-stu-id="84a3a-115">Obtain a service number.</span></span>
2. <span data-ttu-id="84a3a-116">Obtener un sistema telefónico gratis: [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) o una licencia de sistema telefónico de pagos para usar con la cuenta de recursos o una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="84a3a-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="84a3a-117">Crear la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-117">Create the resource account.</span></span> <span data-ttu-id="84a3a-118">Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="84a3a-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="84a3a-119">Asigne el sistema telefónico o un sistema telefónico (licencia de usuario virtual) a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="84a3a-120">Asigne un número de teléfono de servicio a la cuenta de recursos a la que acaba de asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="84a3a-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="84a3a-121">Crear una cola de llamadas de sistema telefónicas o un operador automático</span><span class="sxs-lookup"><span data-stu-id="84a3a-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="84a3a-122">Vincular la cuenta de recursos con una cola de llamadas o un operador automático.</span><span class="sxs-lookup"><span data-stu-id="84a3a-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="84a3a-123">Si el operador automático o la cola de llamadas están anidados bajo un operador automático de nivel superior, la cuenta de recursos asociada solo necesita un número de teléfono si desea tener varios puntos de entrada en la estructura de las colas de llamadas y los operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="84a3a-124">Para redirigir las llamadas a las personas de su organización que estén conectadas en línea, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="84a3a-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="84a3a-125">Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="84a3a-125">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="84a3a-126">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84a3a-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="84a3a-127">Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="84a3a-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="84a3a-128">Para evitar problemas con la cuenta de recursos, siga estos pasos en este orden.</span><span class="sxs-lookup"><span data-stu-id="84a3a-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="84a3a-129">Si la cola de llamadas del sistema telefónicas o el operador automático que está creando va a estar anidado y no necesitará un número de teléfono, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="84a3a-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="84a3a-130">Crear la cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="84a3a-130">Create the resource account</span></span>
2. <span data-ttu-id="84a3a-131">Crear una cola de llamadas de sistema telefónicas o un operador automático</span><span class="sxs-lookup"><span data-stu-id="84a3a-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="84a3a-132">Asociar la cuenta de recursos a una cola de llamadas de sistema telefónico o un operador automático</span><span class="sxs-lookup"><span data-stu-id="84a3a-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="84a3a-133">Crear una cuenta de recursos con un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="84a3a-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="84a3a-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="84a3a-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="84a3a-135">Un número de teléfono no se asigna directamente al operador automático o a la cola de llamadas, sino a la cuenta de recursos asociada al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="84a3a-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="84a3a-136">Para un operador automático de nivel superior o una cola de llamadas, es necesario vincular un número de teléfono a su operador automático.</span><span class="sxs-lookup"><span data-stu-id="84a3a-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="84a3a-137">Para crear una cuenta de recursos que use un número de teléfono, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="84a3a-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="84a3a-138">Puerto o recibe un número de servicio de pago o gratuito.</span><span class="sxs-lookup"><span data-stu-id="84a3a-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="84a3a-139">El número no se puede asignar a ningún otro servicio de voz o cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="84a3a-140">Antes de asignar un número de teléfono a una cuenta de recursos, necesita obtener o migrar los números de teléfono de pago o gratuitos existentes.</span><span class="sxs-lookup"><span data-stu-id="84a3a-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="84a3a-141">Después de recibir los números > **de teléfono de**pago o gratuitos, aparecerán en > **los números de teléfono**del **centro de administración de Microsoft Teams**, y el **tipo de número** se indicará como **servicio-** gratuito.</span><span class="sxs-lookup"><span data-stu-id="84a3a-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="84a3a-142">Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="84a3a-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="84a3a-143">Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual del sistema telefónico de sistema de costos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="84a3a-144">Esto proporciona capacidades de sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y de operador automático.</span><span class="sxs-lookup"><span data-stu-id="84a3a-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="84a3a-145">Obtener una licencia de usuario virtual del sistema telefónico o una licencia de sistema telefónico normal.</span><span class="sxs-lookup"><span data-stu-id="84a3a-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="84a3a-146">Para obtener la licencia de usuario virtual, a partir del centro de administración de Microsoft 365, vaya a**suscripciones del complemento** **servicios** > de compra de **facturación** > y desplácese hasta el final: verá la licencia "phone system-virtual User".</span><span class="sxs-lookup"><span data-stu-id="84a3a-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="84a3a-147">Seleccione **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="84a3a-147">Select **Buy now**.</span></span> <span data-ttu-id="84a3a-148">Hay un costo cero, pero sigue siendo necesario seguir estos pasos para adquirir la licencia.</span><span class="sxs-lookup"><span data-stu-id="84a3a-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="84a3a-149">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="84a3a-149">Create a new resource account.</span></span> <span data-ttu-id="84a3a-150">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="84a3a-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="84a3a-151">Asigne un sistema telefónico: [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) o licencia de sistema telefónico a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="84a3a-152">Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md) y [asignar licencias a un usuario](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="84a3a-152">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="84a3a-153">Asignar el número de servicio a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="84a3a-154">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="84a3a-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="84a3a-155">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="84a3a-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="84a3a-156">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="84a3a-157">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="84a3a-158">Vincule la cuenta de recursos al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="84a3a-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="84a3a-159">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="84a3a-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="84a3a-160">Al crear una cuenta de recursos al crear un operador automático, las licencias se aplican automáticamente.</span><span class="sxs-lookup"><span data-stu-id="84a3a-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="84a3a-161">Crear una cuenta de recursos sin un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="84a3a-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="84a3a-162">Un operador automático o una cola de llamadas anidados requerirán una cuenta de recursos pero, en muchos casos, la cuenta de recursos correspondiente no necesitará un número de teléfono y las licencias necesarias para admitir un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="84a3a-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="84a3a-163">Para crear una cuenta de recursos que no necesite un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="84a3a-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="84a3a-164">Crear una cuenta de recursos nueva.</span><span class="sxs-lookup"><span data-stu-id="84a3a-164">Create a new resource account.</span></span> <span data-ttu-id="84a3a-165">Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="84a3a-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="84a3a-166">Configure una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="84a3a-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="84a3a-167">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="84a3a-168">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="84a3a-169">Asignar la cuenta de recursos a la cola de llamadas o al operador automático.</span><span class="sxs-lookup"><span data-stu-id="84a3a-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="84a3a-170">Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="84a3a-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="84a3a-171">Crear una cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84a3a-171">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="84a3a-172">Una vez que haya comprado una licencia de sistema telefónico, usando el centro de administración de Microsoft Teams, vaya a**cuentas de recursos** **de configuración** > de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="84a3a-172">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Captura de pantalla de la página cuentas de recursos](media/r-a-master.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/teamscallout1.png)

<span data-ttu-id="84a3a-175">Para crear una cuenta de recurso, haga clic en **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="84a3a-175">To create a new resource account click **+ Add**.</span></span> <span data-ttu-id="84a3a-176">En la ventana emergente, rellene el **nombre para mostrar**, **username** (el nombre de dominio debe rellenarse automáticamente) y el tipo de **cuenta de recursos** para la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-176">In the pop-up, fill out the **Display name**, **Username** (the domain name should populate automatically), and **Resource account type**  for the resource account.</span></span> <span data-ttu-id="84a3a-177">El tipo de cuenta de recursos puede ser el **operador automático** o la **cola de llamadas** en función de la aplicación que desee asociar a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-177">Resource account type can be either **Auto attendant** or **Call queue** depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="84a3a-178">Cuando esté listo, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="84a3a-178">When you are ready,  click **Save**.</span></span>

![Captura de pantalla de las opciones de nueva cuenta de recursos](media/res-acct.png)

<span data-ttu-id="84a3a-180">A continuación, aplique una licencia a la cuenta de recursos en el centro de administración de O365, como se describe en [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="84a3a-180">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="84a3a-181">Editar cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="84a3a-181">Edit resource account</span></span> 

<span data-ttu-id="84a3a-182">![Icono del número 2, que hace referencia a una llamada en la](media/teamscallout2.png) captura de pantalla anterior, puede editar el **nombre para mostrar** de la cuenta de recursos y el tipo de **cuenta de recursos** con la opción **Editar** .</span><span class="sxs-lookup"><span data-stu-id="84a3a-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="84a3a-183">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="84a3a-183">Click **Save** when you are done.</span></span>

![Captura de pantalla de la opción Editar cuenta de recursos](media/r-a-edit.png)

<span data-ttu-id="84a3a-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="84a3a-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="84a3a-186">Asignar o cancelar la asignación de números de teléfono y servicios</span><span class="sxs-lookup"><span data-stu-id="84a3a-186">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="84a3a-187">![Icono del número 3, que hace referencia a una llamada en la](media/teamscallout3.png) captura de pantalla anterior una vez que ha creado la cuenta de recurso y se le ha asignado la licencia, puede hacer clic en **asignar/desasignar** para asignar un número de servicio a la cuenta de recursos, configurar el tipo de número de teléfono o asignar la cuenta de recursos a un operador automático o cola de llamadas específicos que ya exista</span><span class="sxs-lookup"><span data-stu-id="84a3a-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="84a3a-188">La asignación de un número de enrutamiento directo puede realizarse solo con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="84a3a-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="84a3a-189">Si aún no ha creado la cola de llamadas o el operador automático que va a asociar a la cuenta de recursos, deje el campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="84a3a-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account,leave that field blank.</span></span> <span data-ttu-id="84a3a-190">Puede vincular la cuenta de recursos mientras la crea.</span><span class="sxs-lookup"><span data-stu-id="84a3a-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="84a3a-191">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="84a3a-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="84a3a-192">Las opciones para el **tipo de número de teléfono** son:</span><span class="sxs-lookup"><span data-stu-id="84a3a-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="84a3a-193">Ninguna</span><span class="sxs-lookup"><span data-stu-id="84a3a-193">None</span></span>
- <span data-ttu-id="84a3a-194">Online</span><span class="sxs-lookup"><span data-stu-id="84a3a-194">Online</span></span>
- <span data-ttu-id="84a3a-195">Gratuitos</span><span class="sxs-lookup"><span data-stu-id="84a3a-195">Toll-free</span></span>
- <span data-ttu-id="84a3a-196">Local</span><span class="sxs-lookup"><span data-stu-id="84a3a-196">On-premises</span></span>

![Captura de pantalla de las opciones de asignar/quitar asignación](media/r-a-assign.png)

<span data-ttu-id="84a3a-198">Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, tendrá que usar PowerShell, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="84a3a-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84a3a-199">Si su cuenta de recursos no tiene una licencia válida, una comprobación interna provocará un error al intentar asignar el número de teléfono a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="84a3a-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="84a3a-200">No podrás asignar el número ni asociar la cuenta de recursos con una cola de llamadas o un operador automático.</span><span class="sxs-lookup"><span data-stu-id="84a3a-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84a3a-201">Un número de teléfono no se asigna directamente al operador automático o a la cola de llamadas, sino a la cuenta de recursos asociada al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="84a3a-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="84a3a-202">Cambiar una cuenta de recursos existente para usar una licencia de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="84a3a-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="84a3a-203">Si decide cambiar las licencias de la cuenta de recursos existente de una licencia de sistema telefónico a una licencia de usuario virtual, tendrá que adquirir la licencia de usuario virtual gratuita y, a continuación, seguir los pasos vinculados en el centro de administración de Microsoft 365 para [mover usuarios a una suscripción diferente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="84a3a-203">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="84a3a-204">Quitar siempre una licencia de sistema telefónico completo y asignar la licencia de usuario virtual en la misma actividad de licencia.</span><span class="sxs-lookup"><span data-stu-id="84a3a-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="84a3a-205">Si quita la licencia anterior, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="84a3a-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="84a3a-206">Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para la licencia de usuario virtual y quite la cuenta de recursos dañados.</span><span class="sxs-lookup"><span data-stu-id="84a3a-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="84a3a-207">Crear una cuenta de recursos en PowerShell</span><span class="sxs-lookup"><span data-stu-id="84a3a-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="84a3a-208">En función de si la cuenta de recursos se encuentra en línea o en Skype empresarial Server 2019, tendrá que conectar con el aviso de PowerShell adecuado con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="84a3a-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="84a3a-209">En los siguientes ejemplos de cmdlets de PowerShell se muestra cómo crear una cuenta de recursos conectada en línea con [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="84a3a-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="84a3a-210">Cuentas de recursos alojados en Skype empresarial Server 2019 que se pueden usar con las colas de llamadas en la nube y los operadores automáticos de la nube, vea [configurar colas de llamadas en la](/skypeforbusiness/hybrid/configure-call-queue.md) nube o [configurar operadores automáticos de la nube](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="84a3a-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="84a3a-211">Las implementaciones híbridas (números alojados en enrutamiento directo) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) en un servidor local de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="84a3a-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="84a3a-212">Los IDENTIFICADOres de la aplicación que necesita usar al crear las instancias de la aplicación son:</span><span class="sxs-lookup"><span data-stu-id="84a3a-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="84a3a-213">**Operador automático:** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="84a3a-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="84a3a-214">**Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="84a3a-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="84a3a-215">Si desea que los usuarios de Skype empresarial Server 2019 puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos en Skype empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="84a3a-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="84a3a-216">Cuando los registros SRV de DNS para sipfederationtls se resuelven en Skype empresarial Server 2019, las cuentas de recursos **deben** crearse en Skype empresarial Server 2019 con el shell de administración de SfB y se pueden sincronizar con Azure ad en línea.</span><span class="sxs-lookup"><span data-stu-id="84a3a-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="84a3a-217">Para crear una cuenta de recursos en línea para usarla con un operador automático, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="84a3a-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="84a3a-218">No podrá usar la cuenta de recursos hasta que aplique una licencia.</span><span class="sxs-lookup"><span data-stu-id="84a3a-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="84a3a-219">Para obtener información sobre cómo aplicar una licencia a una cuenta en el centro de administración de O365, vea [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , así como [asignar licencias de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="84a3a-219">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="84a3a-220">Faculta Una vez que se aplica la licencia correcta a la cuenta de recursos, puede asignar un número de teléfono a la cuenta de recursos, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="84a3a-220">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="84a3a-221">No todas las cuentas de recursos requerirán un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="84a3a-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="84a3a-222">Si no aplicó una licencia a la cuenta de recursos, la asignación de número de teléfono fallará.</span><span class="sxs-lookup"><span data-stu-id="84a3a-222">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="84a3a-223">Para obtener más información sobre este comando [, vea Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="84a3a-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="84a3a-224">Es más fácil establecer el número de teléfono en línea con el centro de administración de Microsoft Teams, como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="84a3a-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="84a3a-225">Para asignar un número de teléfono de enrutamiento directo a una cuenta de recursos (alojada en Microsoft Teams o en Skype empresarial Server 2019), use el siguiente cmdlet para Skype empresarial online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="84a3a-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="84a3a-226">Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84a3a-226">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="84a3a-227">Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a**cuentas de recursos**de **configuración** > de toda la organización, seleccione la cuenta de recursos en la que necesita cambiar la configuración y, a continuación, haga clic en el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="84a3a-227">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="84a3a-228">en la pantalla **Editar cuenta de recursos** , podrá cambiar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="84a3a-228">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="84a3a-229">**Nombre para mostrar** de la cuenta</span><span class="sxs-lookup"><span data-stu-id="84a3a-229">**Display name** for the account</span></span>
- <span data-ttu-id="84a3a-230">Cola de llamadas o operador automático que usa la cuenta</span><span class="sxs-lookup"><span data-stu-id="84a3a-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="84a3a-231">Número de teléfono asignado a la cuenta</span><span class="sxs-lookup"><span data-stu-id="84a3a-231">Phone number assigned to the account</span></span>

<span data-ttu-id="84a3a-232">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="84a3a-232">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="84a3a-233">Eliminar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="84a3a-233">Delete a resource account</span></span>

<span data-ttu-id="84a3a-234">Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente.</span><span class="sxs-lookup"><span data-stu-id="84a3a-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="84a3a-235">Puede hacerlo usando los siguientes commandlet:</span><span class="sxs-lookup"><span data-stu-id="84a3a-235">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="84a3a-236">Una vez que lo haga, puede eliminar la cuenta de recursos del portal de administración de O365, en la pestaña usuarios.</span><span class="sxs-lookup"><span data-stu-id="84a3a-236">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="84a3a-237">Para desvincular un número de teléfono de enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="84a3a-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="84a3a-238">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="84a3a-238">Troubleshooting</span></span>

<span data-ttu-id="84a3a-239">En caso de que no vea el número de teléfono asignado a la cuenta de recursos en el centro de administración de Teams y no pueda asignarle el número, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="84a3a-239">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="84a3a-240">Si el atributo Departamento muestra el punto de conexión de aplicaciones de Skype empresarial, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="84a3a-240">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="84a3a-241">Actualice la página web del centro de administración de equipos después de ejecutar el cmldet y debería poder asignar el número correctamente.</span><span class="sxs-lookup"><span data-stu-id="84a3a-241">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="84a3a-242">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="84a3a-242">Related Information</span></span>

<span data-ttu-id="84a3a-243">Para las implementaciones híbridas con Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="84a3a-243">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="84a3a-244">Planear los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-244">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="84a3a-245">Planear las colas de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-245">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="84a3a-246">Configurar cuentas de recursos locales</span><span class="sxs-lookup"><span data-stu-id="84a3a-246">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="84a3a-247">Para las implementaciones de Teams o Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="84a3a-247">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="84a3a-248">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="84a3a-248">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="84a3a-249">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-249">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="84a3a-250">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="84a3a-250">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="84a3a-251">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="84a3a-251">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="84a3a-252">Nuevo: CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="84a3a-252">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="84a3a-253">Nuevo: CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="84a3a-253">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="84a3a-254">Sistema telefónico-licencia de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="84a3a-254">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
