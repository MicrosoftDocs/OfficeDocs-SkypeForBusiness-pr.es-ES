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
- m365initiative-voice
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
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031026"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="17ec7-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17ec7-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="17ec7-104">Una cuenta de recursos es un objeto de usuario deshabilitado en Azure AD y se puede usar para representar recursos en general.</span><span class="sxs-lookup"><span data-stu-id="17ec7-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="17ec7-105">Por ejemplo, una cuenta de recursos puede usarse en Exchange para representar salas de conferencias y permitirles tener un número de teléfono y un calendario.</span><span class="sxs-lookup"><span data-stu-id="17ec7-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="17ec7-106">Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="17ec7-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="17ec7-107">En Microsoft Teams, es necesario disponer de una cuenta de recursos para cada operador automático o cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="17ec7-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="17ec7-108">A las cuentas de recursos también se les puede asignar números de teléfono de servicio.</span><span class="sxs-lookup"><span data-stu-id="17ec7-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="17ec7-109">Así es como asigna números de teléfono a los operadores automáticos y las colas de llamadas, lo que permite que los autores de llamadas de equipos externos puedan comunicarse con el operador automático o la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="17ec7-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="17ec7-110">En este artículo se explica cómo crear cuentas de recursos y prepararlas para usarlas con los operadores automáticos y las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="17ec7-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="17ec7-111">Antes de iniciar los procedimientos de este artículo, asegúrese de que ha hecho lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="17ec7-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="17ec7-112">Obtener licencias de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="17ec7-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="17ec7-113">Obtener números de servicio</span><span class="sxs-lookup"><span data-stu-id="17ec7-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="17ec7-114">Obtener licencias de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="17ec7-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="17ec7-115">Cada cuenta de recursos requiere una licencia para poder trabajar con los operadores automáticos y las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="17ec7-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="17ec7-116">Puede usar una licencia gratuita *de usuario virtual de Microsoft 365 Phone System* .</span><span class="sxs-lookup"><span data-stu-id="17ec7-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="17ec7-117">Para obtener estas licencias, consulte [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="17ec7-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="17ec7-118">Más adelante en este artículo, se explica cómo asignar la licencia a una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="17ec7-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="17ec7-119">Para obtener la licencia de usuario virtual, en el centro de administración de Microsoft 365 **Billing** , vaya a  >  **Purchase services**  >  **suscripciones del complemento** de servicios de compra de facturación y desplácese hasta el final: verá la licencia *de usuario virtual del sistema telefónico* .</span><span class="sxs-lookup"><span data-stu-id="17ec7-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="17ec7-120">Seleccione **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-120">Select **Buy now**.</span></span> <span data-ttu-id="17ec7-121">Hay un costo cero, pero sigue siendo necesario seguir estos pasos para adquirir la licencia.</span><span class="sxs-lookup"><span data-stu-id="17ec7-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="17ec7-122">Obtener números de servicio</span><span class="sxs-lookup"><span data-stu-id="17ec7-122">Obtain service numbers</span></span>

<span data-ttu-id="17ec7-123">Los números de servicio son opcionales para los operadores automáticos y las colas de llamadas, pero necesitará al menos un número de servicio para que las personas que llamen puedan comunicarse con el operador automático y la configuración de la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="17ec7-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="17ec7-124">Para cualquier operador automático o cola de llamadas a los que desee ser alcanzable directamente por un número de servicio, debe tener una cuenta de recursos con un número de servicio asociado.</span><span class="sxs-lookup"><span data-stu-id="17ec7-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="17ec7-125">Las cuentas de recursos pueden usar números de servicio de pago o gratuitos.</span><span class="sxs-lookup"><span data-stu-id="17ec7-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="17ec7-126">Puedes solicitar números nuevos o portar números existentes de otro transportista.</span><span class="sxs-lookup"><span data-stu-id="17ec7-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="17ec7-127">Para obtener nuevos números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="17ec7-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="17ec7-128">Para trasladar un número de otro proveedor, consulte [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="17ec7-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="17ec7-129">Crear una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="17ec7-129">Create a resource account</span></span>

<span data-ttu-id="17ec7-130">Puede crear una cuenta de recursos en el centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="17ec7-130">You can create a resource account in the Teams admin center.</span></span>

![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](media/resource-account-add.png)

1. <span data-ttu-id="17ec7-132">En el centro de administración de Teams, expanda **configuración de toda la organización** y, a continuación, haga clic en **cuentas de recursos**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="17ec7-133">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-133">Click **Add**.</span></span>

3. <span data-ttu-id="17ec7-134">En el panel **Agregar cuenta de recursos** , rellene el campo **nombre para mostrar** , nombre de **usuario** y el **tipo de cuenta recurso**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="17ec7-135">El tipo de cuenta de recurso puede ser **operador automático** o **cola de llamadas** , en función de cómo desee usar esta cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="17ec7-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="17ec7-136">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-136">Click **Save**.</span></span>

![Captura de pantalla de una lista de cuentas de recursos](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="17ec7-138">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="17ec7-138">Assign a license</span></span>

<span data-ttu-id="17ec7-139">Para cada cuenta de recursos, debe asignar una licencia *de sistema telefónico o licencia* *de usuario Virtual de Microsoft 365* .</span><span class="sxs-lookup"><span data-stu-id="17ec7-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Captura de pantalla de la interfaz de usuario de asignación de licencias en el centro de administración de Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="17ec7-141">En el centro de administración de Microsoft 365, haga clic en la cuenta de recursos a la que desea asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="17ec7-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="17ec7-142">En la pestaña **licencias y aplicaciones** , en **licencias** , seleccione **Microsoft 365 Phone System-virtual User**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="17ec7-143">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="17ec7-144">Asignar un número de servicio</span><span class="sxs-lookup"><span data-stu-id="17ec7-144">Assign a service number</span></span>

<span data-ttu-id="17ec7-145">Si está planeando usar la cuenta de recursos con un operador automático o una cola de llamadas que requiera un número de servicio, asigne un número a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="17ec7-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Captura de pantalla de la interfaz de usuario de asignación de número de servicio](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="17ec7-147">En el centro de administración de Teams, en la página **cuentas de recursos** , seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en **asignar o quitar asignación**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="17ec7-148">En la lista desplegable **tipo de número de teléfono** , elija el tipo de número que desea usar.</span><span class="sxs-lookup"><span data-stu-id="17ec7-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="17ec7-149">En el cuadro **número de teléfono asignado** , busque el número que desea usar y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="17ec7-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="17ec7-150">Click **Save**.</span></span>


<span data-ttu-id="17ec7-151">Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, necesita usar PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17ec7-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="17ec7-152">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="17ec7-152">Next steps</span></span>

<span data-ttu-id="17ec7-153">Una vez que haya completado la configuración de la cuenta de recursos y la asignación de un número de servicio si es necesario, estará listo para usar la cuenta de recursos con un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="17ec7-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="17ec7-154">Vea las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="17ec7-154">See the following references:</span></span>

 - [<span data-ttu-id="17ec7-155">Operador automático de la nube</span><span class="sxs-lookup"><span data-stu-id="17ec7-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="17ec7-156">Cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="17ec7-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="17ec7-157">Puede editar el **nombre para mostrar** de la cuenta de recursos y el tipo de **cuenta de recursos** con la opción **Editar** .</span><span class="sxs-lookup"><span data-stu-id="17ec7-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="17ec7-158">Haga clic en **Guardar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="17ec7-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="17ec7-159">Cambiar una cuenta de recursos existente para usar una licencia de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="17ec7-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="17ec7-160">Si decide cambiar las licencias de la cuenta de recursos existente de una licencia de **sistema telefónico** a una licencia de usuario virtual, tendrá que adquirir la licencia de usuario virtual gratuita y, a continuación, seguir los pasos que se indican en el centro de administración de Microsoft 365 para [mover usuarios a una suscripción diferente](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="17ec7-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="17ec7-161">Quitar siempre una licencia de sistema telefónico completo y asignar la licencia de usuario virtual en la misma actividad de licencia.</span><span class="sxs-lookup"><span data-stu-id="17ec7-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="17ec7-162">Si quita la licencia anterior, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="17ec7-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="17ec7-163">Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para la licencia de usuario virtual y quite la cuenta de recursos dañados.</span><span class="sxs-lookup"><span data-stu-id="17ec7-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="17ec7-164">Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="17ec7-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="17ec7-165">Cuentas de recursos alojados en Skype empresarial Server 2019 que se pueden usar con las colas de llamadas en la nube y los operadores automáticos de la nube, consulte [planear colas de llamadas en la](/SkypeforBusiness/hybrid/plan-call-queue) nube o [planear operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="17ec7-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="17ec7-166">Las implementaciones híbridas (números alojados en enrutamiento directo) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) en un servidor local de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="17ec7-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="17ec7-167">Los identificadores de la aplicación que necesita usar durante la creación de las instancias de la aplicación son:</span><span class="sxs-lookup"><span data-stu-id="17ec7-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="17ec7-168">**Operador automático:** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="17ec7-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="17ec7-169">**Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="17ec7-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="17ec7-170">Si desea que los usuarios de Skype empresarial Server 2019 puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos en Skype empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="17ec7-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="17ec7-171">Cuando los registros SRV de DNS para sipfederationtls se resuelven en Skype empresarial Server 2019, las cuentas de recursos **deben** crearse en Skype empresarial Server 2019 con el shell de administración de SfB y sincronizado con Azure ad.</span><span class="sxs-lookup"><span data-stu-id="17ec7-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="17ec7-172">Para las implementaciones híbridas con Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="17ec7-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="17ec7-173">Planear los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="17ec7-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="17ec7-174">Planear las colas de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="17ec7-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="17ec7-175">Configurar cuentas de recursos locales</span><span class="sxs-lookup"><span data-stu-id="17ec7-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="17ec7-176">Eliminar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="17ec7-176">Delete a resource account</span></span>

<span data-ttu-id="17ec7-177">Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente.</span><span class="sxs-lookup"><span data-stu-id="17ec7-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="17ec7-178">Después de hacerlo, puede eliminar la cuenta de recursos en el centro de administración de Microsoft 365, en la pestaña usuarios.</span><span class="sxs-lookup"><span data-stu-id="17ec7-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="17ec7-179">Para desvincular un número de teléfono de enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="17ec7-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
