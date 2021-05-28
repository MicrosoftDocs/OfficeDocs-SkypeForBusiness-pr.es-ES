---
title: Configurar operador Conectar
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre cómo configurar operador Conectar.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689913"
---
# <a name="configure-operator-connect"></a><span data-ttu-id="491bd-103">Configurar operador Conectar</span><span class="sxs-lookup"><span data-stu-id="491bd-103">Configure Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="491bd-104">El Conectar operador solo está disponible actualmente en **la vista previa pública.**</span><span class="sxs-lookup"><span data-stu-id="491bd-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="491bd-105">La vista previa pública le permite probar las próximas características y proporcionar comentarios.</span><span class="sxs-lookup"><span data-stu-id="491bd-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="491bd-106">Es posible que las características incluidas en la vista previa pública no se completen, que se someten a cambios y que no se admiten en Office 365 Administración Pública nubes.</span><span class="sxs-lookup"><span data-stu-id="491bd-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Clouds.</span></span>

<span data-ttu-id="491bd-107">En este artículo se describe cómo configurar operador Conectar.</span><span class="sxs-lookup"><span data-stu-id="491bd-107">This article describes how to configure Operator Connect.</span></span> <span data-ttu-id="491bd-108">Antes de configurar Conectar operador, asegúrese de leer Plan para operadores [Conectar](operator-connect-plan.md) información sobre requisitos previos y licencias.</span><span class="sxs-lookup"><span data-stu-id="491bd-108">Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan.md) for information about prerequisites and licensing.</span></span>

## <a name="enable-an-operator"></a><span data-ttu-id="491bd-109">Habilitar un operador</span><span class="sxs-lookup"><span data-stu-id="491bd-109">Enable an operator</span></span>

<span data-ttu-id="491bd-110">Puede habilitar, editar y quitar operadores en el Centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="491bd-110">You can enable, edit, and remove operators in the Teams Admin Center.</span></span> <span data-ttu-id="491bd-111">En el panel de navegación izquierdo, vaya **a Operadores de > voz.**</span><span class="sxs-lookup"><span data-stu-id="491bd-111">In the left navigation pane, go to **Voice > Operators**.</span></span>

<span data-ttu-id="491bd-112">Para habilitar un operador:</span><span class="sxs-lookup"><span data-stu-id="491bd-112">To enable an operator:</span></span>

1. <span data-ttu-id="491bd-113">**Elija un operador.**</span><span class="sxs-lookup"><span data-stu-id="491bd-113">**Choose an operator.**</span></span> <span data-ttu-id="491bd-114">En la **pestaña Todos los** operadores, filtre los operadores disponibles por región o servicio para buscar el operador adecuado para sus necesidades de voz.</span><span class="sxs-lookup"><span data-stu-id="491bd-114">In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs.</span></span> <span data-ttu-id="491bd-115">A continuación, seleccione el operador que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="491bd-115">Then select the operator you want to enable.</span></span>  

2. <span data-ttu-id="491bd-116">**Seleccione países.**</span><span class="sxs-lookup"><span data-stu-id="491bd-116">**Select countries.**</span></span> <span data-ttu-id="491bd-117">En **Configuración del operador,** seleccione los países que desea habilitar con el operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="491bd-117">Under **Operator settings**, select the countries you want to enable with your selected operator.</span></span>

3. <span data-ttu-id="491bd-118">**Proporcionar información de contacto (opcional).**</span><span class="sxs-lookup"><span data-stu-id="491bd-118">**Provide contact information (optional).**</span></span> <span data-ttu-id="491bd-119">Si desea que los operadores se pondrán en contacto con usted con información adicional sobre Conectar operador, active la casilla y proporcione su información de contacto.</span><span class="sxs-lookup"><span data-stu-id="491bd-119">If you want operators to contact you with additional information about Operator Connect, check the box and provide your contact information.</span></span>  

4. <span data-ttu-id="491bd-120">**Aceptar el aviso de transferencia de datos.**</span><span class="sxs-lookup"><span data-stu-id="491bd-120">**Accept the data transfer notice.**</span></span>

5. <span data-ttu-id="491bd-121">**Agregue el operador.**</span><span class="sxs-lookup"><span data-stu-id="491bd-121">**Add your operator.**</span></span> <span data-ttu-id="491bd-122">Seleccione **Agregar como mi operador** para guardar.</span><span class="sxs-lookup"><span data-stu-id="491bd-122">Select **Add as my operator** to save.</span></span>

## <a name="set-up-phone-numbers"></a><span data-ttu-id="491bd-123">Configurar números de teléfono</span><span class="sxs-lookup"><span data-stu-id="491bd-123">Set up phone numbers</span></span>

<span data-ttu-id="491bd-124">La forma de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo números existentes desde Planes de llamadas de Microsoft o Enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="491bd-124">How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.</span></span>

- <span data-ttu-id="491bd-125">Si necesita adquirir números de teléfono para nuevos usuarios, vea Adquirir números para nuevos [Teams usuarios.](#acquire-numbers-for-new-teams-users)</span><span class="sxs-lookup"><span data-stu-id="491bd-125">If you need to acquire phone numbers for new users, see [Acquire numbers for new Teams users](#acquire-numbers-for-new-teams-users).</span></span>

- <span data-ttu-id="491bd-126">Si desea mover números existentes de planes de llamadas a Conectar, vea Mover números de planes de llamadas a [operador Conectar](#move-numbers-from-calling-plans-to-operator-connect).</span><span class="sxs-lookup"><span data-stu-id="491bd-126">If you want to move existing numbers from Calling Plans to Operator Connect, see [Move numbers from Calling Plans to Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).</span></span>

- <span data-ttu-id="491bd-127">Si desea mover números existentes de Enrutamiento directo a Operador Conectar, vea Mover números de enrutamiento directo a [operador Conectar](#move-numbers-from-direct-routing-to-operator-connect).</span><span class="sxs-lookup"><span data-stu-id="491bd-127">If you want to move existing numbers from Direct Routing to Operator Connect, see [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span></span>

>[!IMPORTANT]
><span data-ttu-id="491bd-128">**Direcciones de emergencia:** Las direcciones de emergencia asociadas a un número adquirido del operador se administran directamente con el operador.</span><span class="sxs-lookup"><span data-stu-id="491bd-128">**Emergency addresses:** Emergency addresses associated with a number acquired from the operator are managed directly with the operator.</span></span> <span data-ttu-id="491bd-129">Póngase en contacto con el operador para realizar cualquier cambio.</span><span class="sxs-lookup"><span data-stu-id="491bd-129">Please contact the operator to make any changes.</span></span>

### <a name="acquire-numbers-for-new-teams-users"></a><span data-ttu-id="491bd-130">Adquirir números para nuevos Teams usuarios</span><span class="sxs-lookup"><span data-stu-id="491bd-130">Acquire numbers for new Teams users</span></span>

<span data-ttu-id="491bd-131">Para adquirir números para nuevos Teams usuarios, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="491bd-131">To acquire numbers for new Teams users, follow these steps:</span></span>

1. <span data-ttu-id="491bd-132">**Asigne una Sistema telefónico licencia.**</span><span class="sxs-lookup"><span data-stu-id="491bd-132">**Assign a Phone System license.**</span></span> <span data-ttu-id="491bd-133">Puede asignar una licencia de Sistema telefónico a los usuarios desde el centro de administración de Microsoft 365 o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="491bd-133">You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell.</span></span> <span data-ttu-id="491bd-134">Para obtener más información, vea [Asignar Teams de complementos a los usuarios.](teams-add-on-licensing/assign-teams-add-on-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="491bd-134">For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

2. <span data-ttu-id="491bd-135">**Asegúrese de que está en modo TeamsOnly.**</span><span class="sxs-lookup"><span data-stu-id="491bd-135">**Make sure you're in TeamsOnly mode.**</span></span> <span data-ttu-id="491bd-136">Para comprobarlo, en el Teams de administración, vaya a Configuración de toda **la organización > Teams actualización.**</span><span class="sxs-lookup"><span data-stu-id="491bd-136">To check, in the Teams admin center, go to **Org-wide settings > Teams upgrade**.</span></span> <span data-ttu-id="491bd-137">El modo de coexistencia debe establecerse en Teams solo.</span><span class="sxs-lookup"><span data-stu-id="491bd-137">The coexistence mode should be set to Teams only.</span></span>

3. <span data-ttu-id="491bd-138">**Crear y validar direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="491bd-138">**Create and validate emergency addresses.**</span></span> <span data-ttu-id="491bd-139">En el Teams de administración, vaya a Ubicaciones **> de** emergencia para configurar direcciones de emergencia.</span><span class="sxs-lookup"><span data-stu-id="491bd-139">In the Teams admin center, go to **Locations > Emergency addresses** to set up emergency addresses.</span></span> <span data-ttu-id="491bd-140">Para obtener más información, vea [Agregar, cambiar o quitar una ubicación de emergencia para su organización.](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="491bd-140">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>

4. <span data-ttu-id="491bd-141">**Adquirir números.**</span><span class="sxs-lookup"><span data-stu-id="491bd-141">**Acquire numbers.**</span></span> <span data-ttu-id="491bd-142">Vaya al sitio web de su operador para solicitar y adquirir números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="491bd-142">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="491bd-143">Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators)</span><span class="sxs-lookup"><span data-stu-id="491bd-143">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="491bd-144">Tendrá que proporcionar su id. de inquilino.</span><span class="sxs-lookup"><span data-stu-id="491bd-144">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="491bd-145">Si no conoce su identificador de inquilino, vea Buscar su Microsoft 365 [inquilino para](/onedrive/find-your-office-365-tenant-id) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="491bd-145">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

5. <span data-ttu-id="491bd-146">**Asignar números.**</span><span class="sxs-lookup"><span data-stu-id="491bd-146">**Assign numbers.**</span></span> <span data-ttu-id="491bd-147">Una vez que el operador complete el pedido, cargarán números de prueba a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="491bd-147">Once your operator completes the order, they'll upload test numbers to your tenant.</span></span> <span data-ttu-id="491bd-148">Puede ver los números y el proveedor en el centro Teams de administración yendo a Números **> Teléfono voz.**</span><span class="sxs-lookup"><span data-stu-id="491bd-148">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="491bd-149">Asigne números a los usuarios mediante el centro Teams de administración o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="491bd-149">Assign numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="491bd-150">Para obtener más información, vea [Asignar números.](#assign-numbers)</span><span class="sxs-lookup"><span data-stu-id="491bd-150">For more information, see [Assign numbers](#assign-numbers).</span></span>
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a><span data-ttu-id="491bd-151">Mover números de planes de llamadas a operador Conectar</span><span class="sxs-lookup"><span data-stu-id="491bd-151">Move numbers from Calling Plans to Operator Connect</span></span>

1. <span data-ttu-id="491bd-152">Póngase en contacto con su operador para portabilidad de los números a Operador Conectar.</span><span class="sxs-lookup"><span data-stu-id="491bd-152">Contact your operator to port your numbers to Operator Connect.</span></span> <span data-ttu-id="491bd-153">Consulte [Operadores](#operators) para buscar el sitio web del operador.</span><span class="sxs-lookup"><span data-stu-id="491bd-153">See [Operators](#operators) to find your operator's website.</span></span>

2. <span data-ttu-id="491bd-154">Después de que el operador complete el pedido de porte, puede quitar los números de teléfono del Plan de llamadas de los usuarios y quitar la licencia del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="491bd-154">After your operator completes the porting order, you can unassign your users' Calling Plan phone numbers, and remove the Calling Plan License.</span></span> <span data-ttu-id="491bd-155">A continuación, el operador puede cargar los números en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="491bd-155">Then, your operator can upload the numbers to your tenant.</span></span>

3. <span data-ttu-id="491bd-156">Asigne números Conectar operador a los usuarios mediante el centro Teams administrador o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="491bd-156">Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="491bd-157">Para obtener más información, vea [Asignar números.](#assign-numbers)</span><span class="sxs-lookup"><span data-stu-id="491bd-157">For more information, see [Assign numbers](#assign-numbers).</span></span>

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a><span data-ttu-id="491bd-158">Mover números de Enrutamiento directo a Operador Conectar</span><span class="sxs-lookup"><span data-stu-id="491bd-158">Move numbers from Direct Routing to Operator Connect</span></span>

1. <span data-ttu-id="491bd-159">Quite el número de teléfono existente del usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="491bd-159">Remove the existing telephone number from the user as follows:</span></span>  

   <span data-ttu-id="491bd-160">Obtenga el URI de línea predefinida existente ejecutando el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="491bd-160">Get the existing On-prem Line URI by running the following PowerShell command:</span></span>

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   <span data-ttu-id="491bd-161">Para quitar el URI de línea predefinida, ejecute el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="491bd-161">Remove the On-prem Line URI by running the following PowerShell command:</span></span>  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. <span data-ttu-id="491bd-162">Quite cualquier RTC asociado a los usuarios, de lo contrario, las llamadas se enrutarán a la puerta de enlace especificada en el uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="491bd-162">Remove any PSTNUsage associated with your users, otherwise calls will be routed to the gateway specified in the PSTN Usage.</span></span> <span data-ttu-id="491bd-163">Para obtener información sobre cómo quitar el uso de RTC, vea [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="491bd-163">To learn how to remove PSTN usage, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span></span>

3. <span data-ttu-id="491bd-164">Vaya al sitio web de su operador para solicitar y adquirir números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="491bd-164">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="491bd-165">Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators)</span><span class="sxs-lookup"><span data-stu-id="491bd-165">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="491bd-166">Tendrá que proporcionar su id. de inquilino.</span><span class="sxs-lookup"><span data-stu-id="491bd-166">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="491bd-167">Si no conoce su identificador de inquilino, vea Buscar su Microsoft 365 [inquilino para](/onedrive/find-your-office-365-tenant-id) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="491bd-167">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

4. <span data-ttu-id="491bd-168">Una vez que el operador complete el pedido, cargarán números de prueba a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="491bd-168">Once your operator completes the order, they'll upload test numbers to your tenant.</span></span> <span data-ttu-id="491bd-169">Puede ver los números y el proveedor en el centro Teams de administración yendo a Números **> Teléfono voz.**</span><span class="sxs-lookup"><span data-stu-id="491bd-169">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="491bd-170">Asigne números Conectar operador a los usuarios mediante el centro Teams administrador o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="491bd-170">Assign Operator Connect numbers to users by using the Teams admin center or by using  PowerShell.</span></span> <span data-ttu-id="491bd-171">Para obtener más información, vea [Asignar números.](#assign-numbers)</span><span class="sxs-lookup"><span data-stu-id="491bd-171">For more information, see [Assign numbers](#assign-numbers).</span></span>

   

### <a name="assign-numbers"></a><span data-ttu-id="491bd-172">Asignar números</span><span class="sxs-lookup"><span data-stu-id="491bd-172">Assign numbers</span></span>

<span data-ttu-id="491bd-173">Tanto si va a agregar nuevos Teams usuarios o mover usuarios existentes a Operador Conectar, los pasos para asignar números son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="491bd-173">Whether you're adding new Teams users or moving existing users to Operator Connect, the steps for assigning numbers are as follows:</span></span>

<span data-ttu-id="491bd-174">Para asignar números mediante el centro Teams administración, vaya a **Teléfono números.**</span><span class="sxs-lookup"><span data-stu-id="491bd-174">To assign numbers by using the Teams admin center, go to **Phone numbers**.</span></span> <span data-ttu-id="491bd-175">Los pasos son los mismos que asignar números para planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="491bd-175">The steps are the same as assigning numbers for Calling Plans.</span></span> <span data-ttu-id="491bd-176">Para obtener más información, vea [Asignar un número de teléfono a un usuario.](assign-change-or-remove-a-phone-number-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="491bd-176">For more information, see [Assign a phone number to a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

<span data-ttu-id="491bd-177">Para asignar números mediante PowerShell, use el cmdlet Set-CsOnlineVoiceUser siguiente:</span><span class="sxs-lookup"><span data-stu-id="491bd-177">To assign numbers by using PowerShell, use the Set-CsOnlineVoiceUser cmdlet as follows:</span></span>

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

<span data-ttu-id="491bd-178">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="491bd-178">For example:</span></span>

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

<span data-ttu-id="491bd-179">Para obtener más información sobre cómo asignar números de teléfono a los usuarios, vea Asignar, cambiar o quitar un número de teléfono [para un usuario.](assign-change-or-remove-a-phone-number-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="491bd-179">For more information about how to assign phone numbers to your users, see [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>



## <a name="manage-your-operators"></a><span data-ttu-id="491bd-180">Administrar los operadores</span><span class="sxs-lookup"><span data-stu-id="491bd-180">Manage your operators</span></span>

<span data-ttu-id="491bd-181">Desde la pestaña Mis operadores, puede ver los operadores y su estado y realizar los siguientes cambios en las selecciones:</span><span class="sxs-lookup"><span data-stu-id="491bd-181">From the My operators tab, you can view your operators and their status and make the following changes to your selections:</span></span>  

- <span data-ttu-id="491bd-182">Administrar servicios de operadores por país</span><span class="sxs-lookup"><span data-stu-id="491bd-182">Manage operator services by country</span></span>
- <span data-ttu-id="491bd-183">Suspender un operador</span><span class="sxs-lookup"><span data-stu-id="491bd-183">Suspend an operator</span></span>
- <span data-ttu-id="491bd-184">Quitar un operador</span><span class="sxs-lookup"><span data-stu-id="491bd-184">Remove an operator</span></span>

> [!NOTE]
> <span data-ttu-id="491bd-185">Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios de la organización o el país y ponerse en contacto con el operador para liberar los números.</span><span class="sxs-lookup"><span data-stu-id="491bd-185">Before removing an operator from your organization or from a country, you must remove all phone numbers assigned to users in the organization or country and contact the operator to release the numbers.</span></span>

## <a name="operators"></a><span data-ttu-id="491bd-186">Operadores</span><span class="sxs-lookup"><span data-stu-id="491bd-186">Operators</span></span>

<span data-ttu-id="491bd-187">Puede adquirir números de teléfono de los siguientes operadores yendo a los sitios web vinculados aquí:</span><span class="sxs-lookup"><span data-stu-id="491bd-187">You can acquire phone numbers from the following operators by going to the websites linked here:</span></span>


|<span data-ttu-id="491bd-188">Operador</span><span class="sxs-lookup"><span data-stu-id="491bd-188">Operator</span></span>  |<span data-ttu-id="491bd-189">Sitio web del operador</span><span class="sxs-lookup"><span data-stu-id="491bd-189">Operator website</span></span>  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
