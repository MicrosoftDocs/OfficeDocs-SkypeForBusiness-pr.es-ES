---
title: Configurar Operator Connect
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
description: Obtenga más información sobre cómo configurar Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947582"
---
# <a name="configure-operator-connect"></a><span data-ttu-id="fbe50-103">Configurar Operator Connect</span><span class="sxs-lookup"><span data-stu-id="fbe50-103">Configure Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="fbe50-104">Operator Connect solo está disponible actualmente en **versión preliminar pública.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="fbe50-105">La vista previa pública le permite probar las próximas características y proporcionar comentarios.</span><span class="sxs-lookup"><span data-stu-id="fbe50-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="fbe50-106">Es posible que las características incluidas en la versión preliminar pública no estén completas, que puedan sufrir cambios y que no sean compatibles con las nubes de Office 365 Government.</span><span class="sxs-lookup"><span data-stu-id="fbe50-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Clouds.</span></span>

<span data-ttu-id="fbe50-107">En este artículo se describe cómo configurar Operator Connect.</span><span class="sxs-lookup"><span data-stu-id="fbe50-107">This article describes how to configure Operator Connect.</span></span> <span data-ttu-id="fbe50-108">Antes de configurar Operator Connect, asegúrese de leer [Plan para Conexión de](operator-connect-plan.md) operadores para obtener información sobre los requisitos previos y las licencias.</span><span class="sxs-lookup"><span data-stu-id="fbe50-108">Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan.md) for information about prerequisites and licensing.</span></span>

## <a name="enable-an-operator"></a><span data-ttu-id="fbe50-109">Habilitar un operador</span><span class="sxs-lookup"><span data-stu-id="fbe50-109">Enable an operator</span></span>

<span data-ttu-id="fbe50-110">Puede habilitar, editar y quitar operadores en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="fbe50-110">You can enable, edit, and remove operators in the Teams Admin Center.</span></span> <span data-ttu-id="fbe50-111">En el panel de navegación izquierdo, vaya **a Operadores de > voz.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-111">In the left navigation pane, go to **Voice > Operators**.</span></span>

<span data-ttu-id="fbe50-112">Para habilitar un operador:</span><span class="sxs-lookup"><span data-stu-id="fbe50-112">To enable an operator:</span></span>

1. <span data-ttu-id="fbe50-113">**Elija un operador.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-113">**Choose an operator.**</span></span> <span data-ttu-id="fbe50-114">En la **pestaña Todos los** operadores, filtre los operadores disponibles por región o servicio para buscar el operador adecuado para sus necesidades de voz.</span><span class="sxs-lookup"><span data-stu-id="fbe50-114">In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs.</span></span> <span data-ttu-id="fbe50-115">A continuación, seleccione el operador que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="fbe50-115">Then select the operator you want to enable.</span></span>  

2. <span data-ttu-id="fbe50-116">**Seleccione países.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-116">**Select countries.**</span></span> <span data-ttu-id="fbe50-117">En **Configuración del operador,** seleccione los países que desea habilitar con el operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fbe50-117">Under **Operator settings**, select the countries you want to enable with your selected operator.</span></span>

3. <span data-ttu-id="fbe50-118">**Proporcionar información de contacto (opcional).**</span><span class="sxs-lookup"><span data-stu-id="fbe50-118">**Provide contact information (optional).**</span></span> <span data-ttu-id="fbe50-119">Si desea que los operadores se pondrán en contacto con usted con información adicional sobre Conexión del operador, active la casilla y proporcione su información de contacto.</span><span class="sxs-lookup"><span data-stu-id="fbe50-119">If you want operators to contact you with additional information about Operator Connect, check the box and provide your contact information.</span></span>  

4. <span data-ttu-id="fbe50-120">**Aceptar el aviso de transferencia de datos.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-120">**Accept the data transfer notice.**</span></span>

5. <span data-ttu-id="fbe50-121">**Agregue el operador.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-121">**Add your operator.**</span></span> <span data-ttu-id="fbe50-122">Seleccione **Agregar como mi operador** para guardar.</span><span class="sxs-lookup"><span data-stu-id="fbe50-122">Select **Add as my operator** to save.</span></span>

## <a name="set-up-phone-numbers"></a><span data-ttu-id="fbe50-123">Configurar números de teléfono</span><span class="sxs-lookup"><span data-stu-id="fbe50-123">Set up phone numbers</span></span>

<span data-ttu-id="fbe50-124">La forma de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo números existentes desde Planes de llamadas de Microsoft o Enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="fbe50-124">How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.</span></span>

- <span data-ttu-id="fbe50-125">Si necesita adquirir números de teléfono para nuevos usuarios, vea [Adquirir números para nuevos usuarios de Teams.](#acquire-numbers-for-new-teams-users)</span><span class="sxs-lookup"><span data-stu-id="fbe50-125">If you need to acquire phone numbers for new users, see [Acquire numbers for new Teams users](#acquire-numbers-for-new-teams-users).</span></span>

- <span data-ttu-id="fbe50-126">Si desea mover números existentes de Planes de llamadas a Conexión de operadores, vea Mover números de planes [de llamadas a Conexión de operador.](#move-numbers-from-calling-plans-to-operator-connect)</span><span class="sxs-lookup"><span data-stu-id="fbe50-126">If you want to move existing numbers from Calling Plans to Operator Connect, see [Move numbers from Calling Plans to Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).</span></span>

- <span data-ttu-id="fbe50-127">Si desea mover números existentes de Enrutamiento directo a Conexión del operador, vea Mover números de [Enrutamiento directo a Conexión del operador.](#move-numbers-from-direct-routing-to-operator-connect)</span><span class="sxs-lookup"><span data-stu-id="fbe50-127">If you want to move existing numbers from Direct Routing to Operator Connect, see [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span></span>

>[!IMPORTANT]
><span data-ttu-id="fbe50-128">**Direcciones de emergencia:** El operador administra los números de teléfono asociados con las direcciones de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fbe50-128">**Emergency addresses:** Phone numbers associated with emergency addresses are managed by your operator.</span></span> <span data-ttu-id="fbe50-129">Una vez que cree direcciones de emergencia en el Centro de administración de Teams, el operador asignará números de teléfono a esas direcciones de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fbe50-129">Once you create emergency addresses in the Teams admin center, your operator will assign phone numbers to those emergency addresses.</span></span> <span data-ttu-id="fbe50-130">Para realizar cambios en las direcciones de emergencia y sus números de teléfono asignados, póngase en contacto con su operador.</span><span class="sxs-lookup"><span data-stu-id="fbe50-130">To make changes to emergency addresses and their assigned phone numbers, contact your operator.</span></span>

### <a name="acquire-numbers-for-new-teams-users"></a><span data-ttu-id="fbe50-131">Adquirir números para nuevos usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="fbe50-131">Acquire numbers for new Teams users</span></span>

<span data-ttu-id="fbe50-132">Para adquirir números para nuevos usuarios de Teams, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fbe50-132">To acquire numbers for new Teams users, follow these steps:</span></span>

1. <span data-ttu-id="fbe50-133">**Asignar una licencia de Sistema telefónico.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-133">**Assign a Phone System license.**</span></span> <span data-ttu-id="fbe50-134">Puede asignar una licencia de Sistema telefónico a los usuarios desde el Centro de administración de Microsoft 365 o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbe50-134">You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell.</span></span> <span data-ttu-id="fbe50-135">Para obtener más información, vea [Asignar licencias de complementos de Teams a los usuarios.](teams-add-on-licensing/assign-teams-add-on-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="fbe50-135">For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

2. <span data-ttu-id="fbe50-136">**Asegúrese de que solo está en modo Teams.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-136">**Make sure you're in Teams only mode.**</span></span> <span data-ttu-id="fbe50-137">Para comprobar si su organización solo está en modo Teams, en el Centro de administración de Teams, vaya a Configuración de toda la **organización > actualización de Teams.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-137">To check if your organization is in Teams only mode, in the Teams admin center, go to **Org-wide settings > Teams upgrade**.</span></span> <span data-ttu-id="fbe50-138">Para comprobar si un usuario solo está en modo Teams, vaya a **Usuarios** y seleccione una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="fbe50-138">To check if a user is in Teams only mode, go to **Users** and select a user account.</span></span> <span data-ttu-id="fbe50-139">En la **pestaña Cuenta,** en **Actualización de Teams, compruebe** que el modo de coexistencia está establecido en "Solo Teams".</span><span class="sxs-lookup"><span data-stu-id="fbe50-139">In the **Account** tab, under **Teams upgrade,** verify that your coexistence mode is set to 'Teams only.'</span></span>

3. <span data-ttu-id="fbe50-140">**Crear y validar direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-140">**Create and validate emergency addresses.**</span></span> <span data-ttu-id="fbe50-141">En el Centro de administración de Teams, vaya a **Ubicaciones > direcciones de emergencia para** configurar las direcciones de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fbe50-141">In the Teams admin center, go to **Locations > Emergency addresses** to set up emergency addresses.</span></span> <span data-ttu-id="fbe50-142">Para obtener más información, vea [Agregar, cambiar o quitar una ubicación de emergencia para su organización.](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="fbe50-142">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>

4. <span data-ttu-id="fbe50-143">**Adquirir números.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-143">**Acquire numbers.**</span></span> <span data-ttu-id="fbe50-144">Vaya al sitio web de su operador para solicitar y adquirir números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="fbe50-144">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="fbe50-145">Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators)</span><span class="sxs-lookup"><span data-stu-id="fbe50-145">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="fbe50-146">Tendrá que proporcionar su id. de inquilino.</span><span class="sxs-lookup"><span data-stu-id="fbe50-146">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="fbe50-147">Si no conoce su id. de inquilino, vea Buscar su id. de inquilino de [Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fbe50-147">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

5. <span data-ttu-id="fbe50-148">**Asignar números.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-148">**Assign numbers.**</span></span> <span data-ttu-id="fbe50-149">Una vez que el operador complete el pedido, cargarán números a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="fbe50-149">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="fbe50-150">Puede ver los números y el proveedor en el Centro de administración de Teams yendo a Números **de > de teléfono.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-150">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="fbe50-151">Asigne números a los usuarios mediante el Centro de administración de Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbe50-151">Assign numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="fbe50-152">Para obtener más información, vea [Asignar números.](#assign-numbers)</span><span class="sxs-lookup"><span data-stu-id="fbe50-152">For more information, see [Assign numbers](#assign-numbers).</span></span>
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a><span data-ttu-id="fbe50-153">Mover números de planes de llamadas a Operador Connect</span><span class="sxs-lookup"><span data-stu-id="fbe50-153">Move numbers from Calling Plans to Operator Connect</span></span>

1. <span data-ttu-id="fbe50-154">Póngase en contacto con su operador para portabilidad de los números a Operador Connect.</span><span class="sxs-lookup"><span data-stu-id="fbe50-154">Contact your operator to port your numbers to Operator Connect.</span></span> <span data-ttu-id="fbe50-155">Consulte [Operadores](#operators) para buscar el sitio web del operador.</span><span class="sxs-lookup"><span data-stu-id="fbe50-155">See [Operators](#operators) to find your operator's website.</span></span>

2. <span data-ttu-id="fbe50-156">Después de que el operador complete el pedido de porte, puede quitar los números de teléfono del Plan de llamadas de los usuarios y quitar la licencia del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fbe50-156">After your operator completes the porting order, you can unassign your users' Calling Plan phone numbers, and remove the Calling Plan License.</span></span> <span data-ttu-id="fbe50-157">A continuación, el operador puede cargar los números en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="fbe50-157">Then, your operator can upload the numbers to your tenant.</span></span>

3. <span data-ttu-id="fbe50-158">Asignar números de Conexión de operador a los usuarios mediante el Centro de administración de Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbe50-158">Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="fbe50-159">Para obtener más información, vea [Asignar números.](#assign-numbers)</span><span class="sxs-lookup"><span data-stu-id="fbe50-159">For more information, see [Assign numbers](#assign-numbers).</span></span>

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a><span data-ttu-id="fbe50-160">Mover números de Enrutamiento directo a Conexión del operador</span><span class="sxs-lookup"><span data-stu-id="fbe50-160">Move numbers from Direct Routing to Operator Connect</span></span>

1. <span data-ttu-id="fbe50-161">Quite el número de teléfono existente del usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="fbe50-161">Remove the existing telephone number from the user as follows:</span></span>  

   <span data-ttu-id="fbe50-162">Obtenga el URI de línea predefinida existente ejecutando el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fbe50-162">Get the existing On-prem Line URI by running the following PowerShell command:</span></span>

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   <span data-ttu-id="fbe50-163">Para quitar el URI de línea predefinida, ejecute el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fbe50-163">Remove the On-prem Line URI by running the following PowerShell command:</span></span>  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. <span data-ttu-id="fbe50-164">Quite cualquier RTC asociado a los usuarios, de lo contrario, las llamadas se enrutarán a la puerta de enlace especificada en el uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="fbe50-164">Remove any PSTNUsage associated with your users, otherwise calls will be routed to the gateway specified in the PSTN Usage.</span></span> <span data-ttu-id="fbe50-165">Para obtener información sobre cómo quitar el uso de RTC, vea [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fbe50-165">To learn how to remove PSTN usage, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span></span>

3. <span data-ttu-id="fbe50-166">Vaya al sitio web de su operador para solicitar y adquirir números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="fbe50-166">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="fbe50-167">Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators)</span><span class="sxs-lookup"><span data-stu-id="fbe50-167">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="fbe50-168">Tendrá que proporcionar su id. de inquilino.</span><span class="sxs-lookup"><span data-stu-id="fbe50-168">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="fbe50-169">Si no conoce su id. de inquilino, vea Buscar su id. de inquilino de [Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fbe50-169">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

4. <span data-ttu-id="fbe50-170">Una vez que el operador complete el pedido, cargarán números a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="fbe50-170">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="fbe50-171">Puede ver los números y el proveedor en el Centro de administración de Teams yendo a Números **de > de teléfono.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-171">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="fbe50-172">Asignar números de Conexión de operador a los usuarios mediante el Centro de administración de Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbe50-172">Assign Operator Connect numbers to users by using the Teams admin center or by using  PowerShell.</span></span> <span data-ttu-id="fbe50-173">Para obtener más información, vea [Asignar números.](#assign-numbers)</span><span class="sxs-lookup"><span data-stu-id="fbe50-173">For more information, see [Assign numbers](#assign-numbers).</span></span>

   

### <a name="assign-numbers"></a><span data-ttu-id="fbe50-174">Asignar números</span><span class="sxs-lookup"><span data-stu-id="fbe50-174">Assign numbers</span></span>

<span data-ttu-id="fbe50-175">Tanto si va a agregar nuevos usuarios de Teams como si mueve usuarios existentes a Operator Connect, los pasos para asignar números son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fbe50-175">Whether you're adding new Teams users or moving existing users to Operator Connect, the steps for assigning numbers are as follows:</span></span>

<span data-ttu-id="fbe50-176">Para asignar números mediante el Centro de administración de Teams, vaya a **Números de teléfono.**</span><span class="sxs-lookup"><span data-stu-id="fbe50-176">To assign numbers by using the Teams admin center, go to **Phone numbers**.</span></span> <span data-ttu-id="fbe50-177">Los pasos son los mismos que asignar números para planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fbe50-177">The steps are the same as assigning numbers for Calling Plans.</span></span> <span data-ttu-id="fbe50-178">Para obtener más información, vea [Asignar un número de teléfono a un usuario.](assign-change-or-remove-a-phone-number-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="fbe50-178">For more information, see [Assign a phone number to a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

<span data-ttu-id="fbe50-179">Para asignar números mediante PowerShell, use el cmdlet Set-CsOnlineVoiceUser siguiente:</span><span class="sxs-lookup"><span data-stu-id="fbe50-179">To assign numbers by using PowerShell, use the Set-CsOnlineVoiceUser cmdlet as follows:</span></span>

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

<span data-ttu-id="fbe50-180">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fbe50-180">For example:</span></span>

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

<span data-ttu-id="fbe50-181">Para obtener más información sobre cómo asignar números de teléfono a los usuarios, vea Asignar, cambiar o quitar un número de teléfono [para un usuario.](assign-change-or-remove-a-phone-number-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="fbe50-181">For more information about how to assign phone numbers to your users, see [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>



## <a name="manage-your-operators"></a><span data-ttu-id="fbe50-182">Administrar los operadores</span><span class="sxs-lookup"><span data-stu-id="fbe50-182">Manage your operators</span></span>

<span data-ttu-id="fbe50-183">Desde la pestaña Mis operadores, puede ver los operadores y su estado y realizar los siguientes cambios en las selecciones:</span><span class="sxs-lookup"><span data-stu-id="fbe50-183">From the My operators tab, you can view your operators and their status and make the following changes to your selections:</span></span>  

- <span data-ttu-id="fbe50-184">Administrar servicios de operadores por país</span><span class="sxs-lookup"><span data-stu-id="fbe50-184">Manage operator services by country</span></span>
- <span data-ttu-id="fbe50-185">Suspender un operador</span><span class="sxs-lookup"><span data-stu-id="fbe50-185">Suspend an operator</span></span>
- <span data-ttu-id="fbe50-186">Quitar un operador</span><span class="sxs-lookup"><span data-stu-id="fbe50-186">Remove an operator</span></span>

> [!NOTE]
> <span data-ttu-id="fbe50-187">Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios de la organización o el país y ponerse en contacto con el operador para liberar los números.</span><span class="sxs-lookup"><span data-stu-id="fbe50-187">Before removing an operator from your organization or from a country, you must remove all phone numbers assigned to users in the organization or country and contact the operator to release the numbers.</span></span>

## <a name="operators"></a><span data-ttu-id="fbe50-188">Operadores</span><span class="sxs-lookup"><span data-stu-id="fbe50-188">Operators</span></span>

<span data-ttu-id="fbe50-189">Puede adquirir números de teléfono de los siguientes operadores yendo a los sitios web vinculados aquí:</span><span class="sxs-lookup"><span data-stu-id="fbe50-189">You can acquire phone numbers from the following operators by going to the websites linked here:</span></span>


|<span data-ttu-id="fbe50-190">Operador</span><span class="sxs-lookup"><span data-stu-id="fbe50-190">Operator</span></span>  |<span data-ttu-id="fbe50-191">Sitio web del operador</span><span class="sxs-lookup"><span data-stu-id="fbe50-191">Operator website</span></span>  |
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
