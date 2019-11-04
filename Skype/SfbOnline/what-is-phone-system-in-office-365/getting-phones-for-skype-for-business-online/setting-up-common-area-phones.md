---
title: Configurar teléfonos de área común
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Aprenda los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar los valores de los teléfonos comunes de área.
ms.openlocfilehash: a245db1a2033f08d50e9a3c1a32f27981a3eb702
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924901"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="e6ebb-103">Configurar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="e6ebb-103">Set up common area phones</span></span>
<span data-ttu-id="e6ebb-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="e6ebb-107">Requisitos previos de los teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="e6ebb-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="e6ebb-108">Lo primero que debe hacer es confirmar que tiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="e6ebb-109">Adquiera una licencia de teléfono de área común y un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="e6ebb-110">Busque y compre teléfonos aprobados (vea la lista [aquí](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="e6ebb-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="e6ebb-113">**Teléfonos VVX de Polycom**: vaya **a configuración** > **Estado** > **plataforma** > **aplicación** > **principal**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="e6ebb-114">**Teléfonos Yealink**: Ve al **Estado** en la pantalla principal del teléfono.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="e6ebb-115">**Teléfonos AudioCodes**: vaya a **menú menu** > \*\*\*\* > **versión de firmware** de estado de dispositivo desde la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="e6ebb-116">**Teléfonos Lync Phone Edition (LPE)**: vaya a \*\*\*\* > **información del sistema** de menús desde la pantalla Inicio.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="e6ebb-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="e6ebb-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="e6ebb-121">Configurar un teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="e6ebb-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="e6ebb-122">Tendrá que seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="e6ebb-123">Paso 1: comprar las licencias</span><span class="sxs-lookup"><span data-stu-id="e6ebb-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="e6ebb-124">En el centro de administración, vaya a**servicios de compra**de **facturación** > y agregue **otros planes**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-124">In the admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="e6ebb-126">Haga clic en **Teléfono de área común** > **Comprar ahora** > y en la página de **Pago** haga clic en **Compra ahora**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="e6ebb-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="e6ebb-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="e6ebb-131">Para obtener más información sobre las licencias, vea [licencias complementarias de Skype empresarial y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="e6ebb-132">Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias</span><span class="sxs-lookup"><span data-stu-id="e6ebb-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="e6ebb-133">En el centro de administración, vaya **a** > usuarios**activos usuarios** > ,**Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-133">In the admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="e6ebb-134">Indique un **Nombre de usuario** del estilo de "Principal" para el primer nombre y "Recepción" para el segundo nombre.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="e6ebb-135">Indique un **Nombre para mostrar** si no se autogenera uno del estilo de "Recepción principal".</span><span class="sxs-lookup"><span data-stu-id="e6ebb-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="e6ebb-136">Indique un **Nombre de usuario** del estilo de "RecepciónPrincipal" o "VestíbuloPrincipal".</span><span class="sxs-lookup"><span data-stu-id="e6ebb-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="e6ebb-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="e6ebb-139">Estando aún allí, asigne las licencias a este usuario.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="e6ebb-140">En la misma página, haga clic para expandir las **Licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="e6ebb-141">Active lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-141">Turn on the following:</span></span>
   - <span data-ttu-id="e6ebb-142">Teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="e6ebb-142">Common Area Phone</span></span>
   - <span data-ttu-id="e6ebb-143">Luego debe elegir un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="e6ebb-144">La asignación de licencias tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="e6ebb-146">Para su interés, el Plan 2 de Skype for Business se incluye con la licencia del **teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="e6ebb-147">Para más detalles, consulte [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="e6ebb-148">Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="e6ebb-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="e6ebb-149">![Un icono que muestra el logotipo](../../images/sfb-logo-30x30.png) de Skype empresarial asignar un número de teléfono al usuario con el centro de **Administración de Skype empresarial**</span><span class="sxs-lookup"><span data-stu-id="e6ebb-149">![An icon showing the Skype for Business logo](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="e6ebb-150">En el centro de administración > **centros** > de administración**de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-150">In the admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="e6ebb-151">En el **centro de administración de Skype for Business** >  **Voz** > **Números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="e6ebb-152">Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="e6ebb-153">En la página **Asignar**, en el cuadro **Usuario de voz** indique el nombre del usuario que se utiliza para el teléfono y luego seleccione el usuario en el desplegable **Seleccionar un usuario de voz**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="e6ebb-154">Allí deberá agregar también una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="e6ebb-155">Tras hacer la búsqueda, revise **Seleccionar dirección de emergencia** para elegir la correcta en su caso.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="e6ebb-156">Haga clic en **Guardar** y el usuario debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="e6ebb-158">Los usuarios solo aparecerán si tienen aplicada una licencia de **sistema telefónico**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="e6ebb-159">Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="e6ebb-160">Para más información, consulte [Obtener números de teléfono para los usuarios](/microsoftteams/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="e6ebb-161">Por si se lo está preguntando, también puede coger el número de teléfono que tenga con otra compañía y "*pasarlo*" o transferirlo a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="e6ebb-162">Consulte [transferir números de teléfono a teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-162">See, [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="e6ebb-163">Paso 4: configurar el teléfono</span><span class="sxs-lookup"><span data-stu-id="e6ebb-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="e6ebb-164">**Configurar el modo en el teléfono**</span><span class="sxs-lookup"><span data-stu-id="e6ebb-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="e6ebb-165">El teléfono o teléfonos que posea deben tener activado el **Modo de teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="e6ebb-166">Quizá convenga verificarlo para asegurarse de que así es.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="e6ebb-167">**Aquí tiene un ejemplo de cómo configurar un teléfono Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="e6ebb-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="e6ebb-168">Habilite el modo de teléfono de área común en un Polycom VVX siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="e6ebb-169">En su explorador, conéctese a la interfaz web para poder habilitar el modo CAP.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="e6ebb-170">Luego entre en **Configuración** y, en la opción **Configuración de Skype for Business**, seleccione **Teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="e6ebb-171">Haga clic en **Sí** para guardar su configuración.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="e6ebb-172">Ahora que el modo CAP está habilitado, configure el teléfono usando la pantalla del mismo.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="e6ebb-173">La pantalla debería mostrar **CaAP está habilitado**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="e6ebb-174">Luego haga esto:</span><span class="sxs-lookup"><span data-stu-id="e6ebb-174">Then do the following:</span></span>

    1. <span data-ttu-id="e6ebb-175">Haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="e6ebb-176">Seleccione **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="e6ebb-177">Escriba la contraseña.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-177">Enter the password.</span></span>
    4. <span data-ttu-id="e6ebb-178">En **Configuración de administración**, seleccione **Configuración del teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="e6ebb-179">Habilite **CAP** y **Modo de administración CAP**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="e6ebb-180">Haga clic en **Guardar configuración**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-180">Click **Save Config**.</span></span>

- <span data-ttu-id="e6ebb-181">Bien, ahora su teléfono está listo para que pueda conectarse en la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="e6ebb-182">Conéctese seleccionando **Configuración** > **Características** > **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="e6ebb-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="e6ebb-183">Seleccione **Credenciales de usuario** y luego **conexión web (CAP)** para generar un código.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="e6ebb-184">Entre en el [portal de aprovisionamiento](https://aka.ms/skypecap) y conéctese como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="e6ebb-185">Escriba el nombre para mostrar (por ejemplo, Recepción principal).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="e6ebb-186">Si está marcado **Buscar solo teléfonos de área común**, desactive la casilla de verificación y busque de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="e6ebb-187">En la ventana del código de vinculación, escriba el código que se muestra en el teléfono y haga clic en **Aprovisionar**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="e6ebb-188">Tras este último paso, el teléfono debería conectarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="e6ebb-189">El sitio de aprovisionamiento de CAP indica que restablecerá la contraseña de la cuenta CAP a una contraseña aleatoria.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="e6ebb-190">Tenga en cuenta que la cuenta a la que hace referencia el CAP es la cuenta de Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="e6ebb-191">Solo si creó la cuenta en AAD el proceso es directo.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="e6ebb-192">Si sincronizó un Active Directory local con AAD y usa un IDP o ADFS de terceros, se producirá un error de aprovisionamiento CAP.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="e6ebb-193">En este caso, solo tiene que usar una cuenta de Office 365/Azure Active Directory (por ejemplo, una cuenta con dominio **onmicrosoft.com** ) para que funcione el aprovisionamiento Cap.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-193">In this case, you need to use an Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="e6ebb-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e6ebb-194">Related topics</span></span>

- <span data-ttu-id="e6ebb-195">Obtenga más información sobre teléfonos disponibles en [Implementar teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="e6ebb-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="e6ebb-196">Obtener teléfonos para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e6ebb-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


