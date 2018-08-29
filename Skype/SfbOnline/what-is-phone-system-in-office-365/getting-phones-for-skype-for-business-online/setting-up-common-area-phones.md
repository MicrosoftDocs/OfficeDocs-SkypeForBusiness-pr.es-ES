---
title: Configurar teléfonos de área común
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar las opciones de teléfonos de área común.
ms.openlocfilehash: a2abc74960b04b7b39e4e31961c849009fb9543f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23248340"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="3378c-103">Configurar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="3378c-103">Set up common area phones</span></span>
<span data-ttu-id="3378c-104">Por lo general, un teléfono de área común (CAP) se coloca en un área como un vestíbulo u otra área que está disponible para muchas personas.</span><span class="sxs-lookup"><span data-stu-id="3378c-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="3378c-105">Por ejemplo, un teléfono del área de recepción, un teléfono de la puerta o un teléfono de la sala de reuniones; los CAP se configuran como dispositivos en lugar de como usuarios y se conectan automáticamente a una red.</span><span class="sxs-lookup"><span data-stu-id="3378c-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="3378c-106">En los pasos a continuación, le ayudaremos a configurar una cuenta para un sistema telefónico con planes de llamadas, de modo que pueda implementar este tipo de teléfonos en su organización.</span><span class="sxs-lookup"><span data-stu-id="3378c-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="3378c-107">Requisitos previos de los teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="3378c-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="3378c-108">Lo primero que debe hacer es confirmar que tiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3378c-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="3378c-109">Adquiera una licencia de teléfono de área común y un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3378c-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="3378c-110">Busque y compre teléfonos aprobados (vea la lista [aquí](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="3378c-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
 - <span data-ttu-id="3378c-111">Actualice el firmware de sus teléfonos (consulte el firmware compatible [en este tema](getting-phones-for-skype-for-business-online.md)).</span><span class="sxs-lookup"><span data-stu-id="3378c-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="3378c-112">Puede verificar el firmware en su teléfono haciendo esto:</span><span class="sxs-lookup"><span data-stu-id="3378c-112">You can check the firmware on you phone by doing this:</span></span>
    - <span data-ttu-id="3378c-113">**Los teléfonos Polycom VVX**: Ir a la **configuración de** > **estado** > **plataforma** > **aplicación** > **principal**.</span><span class="sxs-lookup"><span data-stu-id="3378c-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="3378c-114">**Teléfonos Yealink**: vaya al **estado** de la pantalla del teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="3378c-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="3378c-115">**Teléfonos AudioCodes**: vaya al **menú** > **Estado del dispositivo** > **versión de Firmware** desde la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="3378c-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    - <span data-ttu-id="3378c-116">**Teléfonos de Lync Phone Edition (LPE)**: vaya al **menú** > **Información del sistema** desde la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="3378c-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="3378c-117">Las actualizaciones de firmware las administra el servicio de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3378c-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="3378c-118">Todos los firmware de teléfono certificados para Skype for Business se cargan en el servidor de actualización de Skype for Business, y la actualización del dispositivo está habilitada en todos los teléfonos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3378c-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="3378c-119">En función del tiempo de inactividad del teléfono y de los intervalos de sondeo, los teléfonos descargarán e instalarán automáticamente las últimas compilaciones certificadas.</span><span class="sxs-lookup"><span data-stu-id="3378c-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="3378c-120">Puede deshabilitar la configuración de actualización del dispositivo usando el cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) y configurando el parámetro *EnableDeviceUpdate* como `false`.</span><span class="sxs-lookup"><span data-stu-id="3378c-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="3378c-121">Configurar un teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="3378c-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="3378c-122">Tendrá que seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3378c-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="3378c-123">Paso 1: comprar las licencias</span><span class="sxs-lookup"><span data-stu-id="3378c-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="3378c-124">En el centro de administración de Office 365, entre en **Facturación** > **Servicios de compra**, y agregue **Otros planes**.</span><span class="sxs-lookup"><span data-stu-id="3378c-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="3378c-126">Haga clic en **Teléfono de área común** > **Comprar ahora** > y en la página de **Pago** haga clic en **Compra ahora**.</span><span class="sxs-lookup"><span data-stu-id="3378c-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="3378c-127">Haga clic para expandir las **Suscripciones de complementos** y luego haga clic para comprar un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3378c-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="3378c-128">Elija la **nacionales llamar al Plan** o la **planeación de la llamada nacional e internacional**.</span><span class="sxs-lookup"><span data-stu-id="3378c-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="3378c-129">No necesita una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="3378c-129">You don't need a Phone System license.</span></span> <span data-ttu-id="3378c-130">Está incluida en la licencia del **teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="3378c-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="3378c-131">Para obtener más información sobre las licencias, vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="3378c-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="3378c-132">Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias</span><span class="sxs-lookup"><span data-stu-id="3378c-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="3378c-133">En el centro de administración de Office 365, entre en **Usuarios** > **Usuarios activos** > **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="3378c-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="3378c-134">Indique un **Nombre de usuario** del estilo de "Principal" para el primer nombre y "Recepción" para el segundo nombre.</span><span class="sxs-lookup"><span data-stu-id="3378c-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="3378c-135">Indique un **Nombre para mostrar** si no se autogenera uno del estilo de "Recepción principal".</span><span class="sxs-lookup"><span data-stu-id="3378c-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="3378c-136">Indique un **Nombre de usuario** del estilo de "RecepciónPrincipal" o "VestíbuloPrincipal".</span><span class="sxs-lookup"><span data-stu-id="3378c-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="3378c-137">Para teléfonos de área común, quizá desee establecer una contraseña manualmente o tener la misma para todos los teléfonos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="3378c-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="3378c-138">Además, puede plantearse deseleccionar **Hacer que este usuario cambie su contraseña cuando se conecte por primera vez**.</span><span class="sxs-lookup"><span data-stu-id="3378c-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="3378c-139">¡ESPERE!</span><span class="sxs-lookup"><span data-stu-id="3378c-139">WAIT!!</span></span> <span data-ttu-id="3378c-140">¡No haga clic en **Agregar**!</span><span class="sxs-lookup"><span data-stu-id="3378c-140">Don't click **Add**!!</span></span> <span data-ttu-id="3378c-141">Uf, si ya ha hecho clic en **Agregar** haga esto: entre en el centro de administración de Office 365> **Usuarios** > **Usuarios activos** y luego encuentre al usuario.</span><span class="sxs-lookup"><span data-stu-id="3378c-141">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="3378c-142">Después, en la página de propiedades del usuario, haga clic en **Licencias de producto** y después haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3378c-142">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="3378c-143">En la página de **Licencias de producto**, active **Teléfono de área común** y elija un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.</span><span class="sxs-lookup"><span data-stu-id="3378c-143">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="3378c-144">Estando aún allí, asigne las licencias a este usuario.</span><span class="sxs-lookup"><span data-stu-id="3378c-144">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="3378c-145">En la misma página, haga clic para expandir las **Licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="3378c-145">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="3378c-146">Active lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3378c-146">Turn on the following:</span></span>
    - <span data-ttu-id="3378c-147">Teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="3378c-147">Common Area Phone</span></span>
    - <span data-ttu-id="3378c-148">Luego debe elegir un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.</span><span class="sxs-lookup"><span data-stu-id="3378c-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

    <span data-ttu-id="3378c-149">La asignación de licencias tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="3378c-149">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="3378c-151">Para su interés, el Plan 2 de Skype for Business se incluye con la licencia del **teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="3378c-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="3378c-152">Para más detalles, consulte [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="3378c-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="3378c-153">Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="3378c-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="3378c-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Asignar un número de teléfono al usuario mediante el **centro de administración de Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="3378c-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="3378c-155">En el centro de administración de Office 365 > **centros de administración** > **Skype para la empresa**.</span><span class="sxs-lookup"><span data-stu-id="3378c-155">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="3378c-156">En el **centro de administración de Skype for Business** >  **Voz** > **Números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="3378c-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="3378c-157">Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="3378c-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="3378c-158">En la página **Asignar**, en el cuadro **Usuario de voz** indique el nombre del usuario que se utiliza para el teléfono y luego seleccione el usuario en el desplegable **Seleccionar un usuario de voz**.</span><span class="sxs-lookup"><span data-stu-id="3378c-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="3378c-159">Allí deberá agregar también una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="3378c-159">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="3378c-160">Tras hacer la búsqueda, revise **Seleccionar dirección de emergencia** para elegir la correcta en su caso.</span><span class="sxs-lookup"><span data-stu-id="3378c-160">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="3378c-161">Haga clic en **Guardar** y el usuario debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="3378c-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="3378c-163">Los usuarios solo aparecerán si tienen aplicada una licencia de **sistema telefónico**.</span><span class="sxs-lookup"><span data-stu-id="3378c-163">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="3378c-164">Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="3378c-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="3378c-165">Para más información, consulte [Obtener números de teléfono para los usuarios](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="3378c-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="3378c-166">Por si se lo está preguntando, también puede coger el número de teléfono que tenga con otra compañía y "*pasarlo*" o transferirlo a Office 365.</span><span class="sxs-lookup"><span data-stu-id="3378c-166">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="3378c-167">Vea, [transferir los números de teléfono para Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="3378c-167">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="3378c-168">Paso 4: configurar el teléfono</span><span class="sxs-lookup"><span data-stu-id="3378c-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="3378c-169">**Configurar el modo en el teléfono**</span><span class="sxs-lookup"><span data-stu-id="3378c-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="3378c-170">El teléfono o teléfonos que posea deben tener activado el **Modo de teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="3378c-170">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="3378c-171">Quizá convenga verificarlo para asegurarse de que así es.</span><span class="sxs-lookup"><span data-stu-id="3378c-171">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="3378c-172">**Aquí tiene un ejemplo de cómo configurar un teléfono Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="3378c-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="3378c-173">Habilite el modo de teléfono de área común en un Polycom VVX siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3378c-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="3378c-174">En su explorador, conéctese a la interfaz web para poder habilitar el modo CAP.</span><span class="sxs-lookup"><span data-stu-id="3378c-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="3378c-175">Luego entre en **Configuración** y, en la opción **Configuración de Skype for Business**, seleccione **Teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="3378c-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="3378c-176">Haga clic en **Sí** para guardar su configuración.</span><span class="sxs-lookup"><span data-stu-id="3378c-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="3378c-177">Ahora que el modo CAP está habilitado, configure el teléfono usando la pantalla del mismo.</span><span class="sxs-lookup"><span data-stu-id="3378c-177">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="3378c-178">La pantalla debería mostrar **CaAP está habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3378c-178">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="3378c-179">Luego haga esto:</span><span class="sxs-lookup"><span data-stu-id="3378c-179">Then do the following:</span></span>

    1. <span data-ttu-id="3378c-180">Haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="3378c-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="3378c-181">Seleccione **avanzada**.</span><span class="sxs-lookup"><span data-stu-id="3378c-181">Select **Advanced**.</span></span>
    3. <span data-ttu-id="3378c-182">Escriba la contraseña.</span><span class="sxs-lookup"><span data-stu-id="3378c-182">Enter the password.</span></span>
    4. <span data-ttu-id="3378c-183">En **Configuración de administración**, seleccione **Configuración del teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="3378c-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="3378c-184">Habilite **CAP** y **Modo de administración CAP**.</span><span class="sxs-lookup"><span data-stu-id="3378c-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="3378c-185">Haga clic en **Guardar configuración**.</span><span class="sxs-lookup"><span data-stu-id="3378c-185">Click **Save Config**.</span></span>

- <span data-ttu-id="3378c-186">Bien, ahora su teléfono está listo para que pueda conectarse en la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="3378c-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="3378c-187">Conéctese seleccionando **Configuración** > **Características** > **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="3378c-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="3378c-188">Seleccione **Credenciales de usuario** y luego **conexión web (CAP)** para generar un código.</span><span class="sxs-lookup"><span data-stu-id="3378c-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="3378c-189">Entre en el [portal de aprovisionamiento](https://aka.ms/skypecap) y conéctese como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="3378c-189">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="3378c-190">Escriba el nombre para mostrar (por ejemplo, Recepción principal).</span><span class="sxs-lookup"><span data-stu-id="3378c-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="3378c-191">Si está marcado **Buscar solo teléfonos de área común**, desactive la casilla de verificación y busque de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3378c-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="3378c-192">En la ventana del código de vinculación, escriba el código que se muestra en el teléfono y haga clic en **Aprovisionar**.</span><span class="sxs-lookup"><span data-stu-id="3378c-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="3378c-193">Tras este último paso, el teléfono debería conectarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3378c-193">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="3378c-194">El sitio de aprovisionamiento de CAP indica que restablecerá la contraseña de la cuenta CAP a una contraseña aleatoria.</span><span class="sxs-lookup"><span data-stu-id="3378c-194">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="3378c-195">Tenga en cuenta que la cuenta a la que hace referencia el CAP es la cuenta de Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="3378c-195">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="3378c-196">Solo si creó la cuenta en AAD el proceso es directo.</span><span class="sxs-lookup"><span data-stu-id="3378c-196">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="3378c-197">Si ha sincronizado un Active Directory local con AAD, asegúrese de tomar nota de las credenciales que está utilizando, las cuales las cambiará el aprovisionamiento de CAP.</span><span class="sxs-lookup"><span data-stu-id="3378c-197">If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span></span>


### <a name="related-topics"></a><span data-ttu-id="3378c-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3378c-198">Related topics</span></span>

- <span data-ttu-id="3378c-199">Obtenga más información sobre teléfonos disponibles en [Implementar teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="3378c-199">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="3378c-200">Obtener teléfonos con Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3378c-200">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


