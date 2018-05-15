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
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="98d0f-103">Configurar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="98d0f-103">Set up common area phones</span></span>
<span data-ttu-id="98d0f-104">Normalmente, se coloca un teléfono de área común (CAP) en un área como una sala de espera o a otra área que está disponible para una gran cantidad de personas.</span><span class="sxs-lookup"><span data-stu-id="98d0f-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="98d0f-105">Por ejemplo, un teléfono de área de recepción de teléfono puerta teléfono o salas de reuniones, las mayúsculas se configuran como dispositivos en lugar de los usuarios e iniciar sesión automáticamente en una red.</span><span class="sxs-lookup"><span data-stu-id="98d0f-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="98d0f-106">En los pasos siguientes, le ayudaremos a configurar para el sistema telefónico con planes de llamar a una cuenta, por lo que puede implementar estos tipos de teléfonos para su organización.</span><span class="sxs-lookup"><span data-stu-id="98d0f-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="98d0f-107">Requisitos previos para teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="98d0f-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="98d0f-108">Lo primero que debe hacer es confirmar que tiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98d0f-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="98d0f-109">Licencia de teléfono de área común de compra y un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="98d0f-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="98d0f-110">Buscar y comprar teléfonos aprobados (ver la lista [aquí](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="98d0f-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="98d0f-111">Actualice el firmware en los teléfonos (vea admitido firmware [en este tema](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="98d0f-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="98d0f-112">Puede comprobar el firmware de teléfono haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98d0f-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="98d0f-113">**Los teléfonos Polycom VVX**: Ir a la **configuración de** > **estado** > **plataforma** > **aplicación** > **principal**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="98d0f-114">**Teléfonos Yealink**: vaya al **estado** de la pantalla del teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="98d0f-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="98d0f-115">**Teléfonos AudioCodes**: vaya al **menú** > **Estado del dispositivo** > **versión de Firmware** desde la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="98d0f-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="98d0f-116">**Teléfonos de Lync Phone Edition (LPE)**: vaya al **menú** > **Información del sistema** desde la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="98d0f-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="98d0f-117">Actualizaciones de firmware se administran mediante el Skype para servicio empresarial.</span><span class="sxs-lookup"><span data-stu-id="98d0f-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="98d0f-118">Cada Skype para la empresa certificada firmware del teléfono se cargó en la Skype para servidor de actualización de negocio, y actualización de dispositivos está habilitado en todos los teléfonos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98d0f-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="98d0f-119">Según el tiempo de inactividad en el teléfono y los intervalos de sondeo, teléfonos automáticamente descargar e instalar las compilaciones certificadas más recientes.</span><span class="sxs-lookup"><span data-stu-id="98d0f-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="98d0f-120">Puede deshabilitar la configuración de actualización de dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) y establecer el parámetro *EnableDeviceUpdate* en `false`.</span><span class="sxs-lookup"><span data-stu-id="98d0f-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="98d0f-121">Configuración de un teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="98d0f-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="98d0f-122">Debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98d0f-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="98d0f-123">Configurar una cuenta de usuario para el teléfono</span><span class="sxs-lookup"><span data-stu-id="98d0f-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="98d0f-124">Paso 1: comprar las licencias</span><span class="sxs-lookup"><span data-stu-id="98d0f-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="98d0f-125">En el centro de administración de Office 365, vaya a **facturación** > **Servicios de compra**, y agregar **otros planes**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP license.png](../../images/cap-license.png)
2. <span data-ttu-id="98d0f-127">Haga clic en **Teléfono de área común** > **comprar ahora** > en la página de **finalización de compra** haga clic en **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="98d0f-128">Haga clic en expandir **las suscripciones del complemento** y, a continuación, haga clic en para adquirir un Plan de llamar a.</span><span class="sxs-lookup"><span data-stu-id="98d0f-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="98d0f-129">Elija la **nacionales llamar al Plan** o la **planeación de la llamada nacional e internacional**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="98d0f-130">No necesita una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="98d0f-130">You don't need a Phone System license.</span></span> <span data-ttu-id="98d0f-131">Ha incluido con la licencia de **Teléfono de área común** .</span><span class="sxs-lookup"><span data-stu-id="98d0f-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="98d0f-132">Para obtener más información sobre las licencias, vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="98d0f-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="98d0f-133">Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias</span><span class="sxs-lookup"><span data-stu-id="98d0f-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="98d0f-134">En el centro de administración de Office 365, vaya a **los usuarios** > **Usuarios activos** > **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="98d0f-135">Colocar en un **nombre de usuario** , como "Main" para el nombre y el "Recepción" para el segundo nombre.</span><span class="sxs-lookup"><span data-stu-id="98d0f-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="98d0f-136">Colocar en un **nombre para mostrar** si no es así generar automáticamente como "Recepción principal".</span><span class="sxs-lookup"><span data-stu-id="98d0f-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="98d0f-137">Colocar en un **nombre de usuario** , como "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="98d0f-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="98d0f-138">Para teléfonos de área común, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área común.</span><span class="sxs-lookup"><span data-stu-id="98d0f-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="98d0f-139">Además, es posible que piense anula la selección de **realizar este usuario cambiar su contraseña cuando inician sesión por primera vez en**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="98d0f-140">¡ESPERAR!</span><span class="sxs-lookup"><span data-stu-id="98d0f-140">WAIT!!</span></span> <span data-ttu-id="98d0f-141">No haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-141">Don't click **Add**!!</span></span> <span data-ttu-id="98d0f-142">Ugh, si hizo clic en **Agregar** el hacer esto: Centro de administración de Office 365 > **usuarios** > **usuarios activos** y, a continuación, busque el usuario.</span><span class="sxs-lookup"><span data-stu-id="98d0f-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="98d0f-143">A continuación, en la página de propiedades del usuario, haga clic en **licencias de producto** y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="98d0f-144">En la página **licencias de producto** , encienda el **Teléfono de área común** y de selección ya sea un **Nacionales llamar a planear** o un nacionales y **Llamar a planear internacional**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="98d0f-145">Si son aún no existe, asigne las licencias para este usuario.</span><span class="sxs-lookup"><span data-stu-id="98d0f-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="98d0f-146">En la misma página, haga clic para expandir **las licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="98d0f-147">Para activar el siguiente:</span><span class="sxs-lookup"><span data-stu-id="98d0f-147">Turn on the following:</span></span>
    - <span data-ttu-id="98d0f-148">Teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="98d0f-148">Common Area Phone</span></span>
    - <span data-ttu-id="98d0f-149">A continuación, tendrá que escoger ya sea un **Llamar a planear nacionales** o un nacionales y **Llamar a planear internacional**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="98d0f-150">Asignación de las licencias tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="98d0f-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="98d0f-152">Como ya debe saber, Skype para empresarial Plan 2 se incluye con la licencia de **Teléfono de área común** .</span><span class="sxs-lookup"><span data-stu-id="98d0f-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="98d0f-153">Para obtener más detalles, vea [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="98d0f-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="98d0f-154">Paso 3: asignar a un número de teléfono al usuario</span><span class="sxs-lookup"><span data-stu-id="98d0f-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="98d0f-155">![logotipo-sfb-30x30.png](../../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="98d0f-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="98d0f-156">En el centro de administración de Office 365 > **centros de administración** > **Skype para la empresa**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="98d0f-157">En el **Skype para el centro de administración de negocio** >  **voz** > **los números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="98d0f-158">Seleccione un número de la lista de números de teléfono y haga clic en **asignar**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="98d0f-159">En la página **asignar** , en el cuadro de **usuario de voz** , escriba el nombre del usuario que se usa para el teléfono, a continuación, seleccione el usuario en, **Seleccione un usuario de voz de** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="98d0f-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="98d0f-160">Mientras esté allí necesita agregar una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="98d0f-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="98d0f-161">Una vez que buscar, mire en la **Seleccione emergencia dirección** para elegir el adecuado para usted.</span><span class="sxs-lookup"><span data-stu-id="98d0f-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="98d0f-162">Haga clic en **Guardar** y el usuario debe tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="98d0f-162">Click **Save** and your user should look like this:</span></span>

    ![CAP-usuario-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="98d0f-164">Los usuarios sólo aparecerá si tienen una licencia de **Sistema telefónico** aplicada.</span><span class="sxs-lookup"><span data-stu-id="98d0f-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="98d0f-165">Si ya ha realizado esta, a continuación, en ocasiones, se tarda un poco para que el usuario aparezca en la lista.</span><span class="sxs-lookup"><span data-stu-id="98d0f-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="98d0f-166">Para obtener más cosas, vea [Introducción de los números de teléfono para los usuarios](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="98d0f-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="98d0f-167">Si se lo está preguntando, también puede tomarse su número de teléfono que tiene con otro operador y "*puerto*" o transferirlos a través de Office 365.</span><span class="sxs-lookup"><span data-stu-id="98d0f-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="98d0f-168">Vea, [transferir los números de teléfono para Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="98d0f-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="98d0f-169">Paso 4: configurar el teléfono</span><span class="sxs-lookup"><span data-stu-id="98d0f-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="98d0f-170">**Establecer el modo en un teléfono**</span><span class="sxs-lookup"><span data-stu-id="98d0f-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="98d0f-171">El teléfono o teléfonos que tiene deben tener activado el modo de teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="98d0f-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="98d0f-172">Es posible que desee comprobar para asegurarse de que lo hacen.</span><span class="sxs-lookup"><span data-stu-id="98d0f-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="98d0f-173">**Este es un ejemplo de cómo configurar un teléfono Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="98d0f-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="98d0f-174">Habilitar el modo de teléfono de área común para el VVX Polycom siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98d0f-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="98d0f-175">En el explorador, conéctese a la interfaz web para que se puede habilitar el modo de capital.</span><span class="sxs-lookup"><span data-stu-id="98d0f-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="98d0f-176">A continuación, vaya a **configuración** y en la opción de **Skype para configuración de negocio** , seleccione **Teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="98d0f-177">Haga clic en **Sí** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="98d0f-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="98d0f-178">Ahora que está habilitado el modo de capital, configurar el teléfono mediante la pantalla del teléfono.</span><span class="sxs-lookup"><span data-stu-id="98d0f-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="98d0f-179">La presentación debe mostrar **CaAP está habilitado**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="98d0f-180">A continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98d0f-180">Then do the following:</span></span>

    1. <span data-ttu-id="98d0f-181">Haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="98d0f-182">Seleccione **avanzada**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="98d0f-183">Escriba la contraseña.</span><span class="sxs-lookup"><span data-stu-id="98d0f-183">Enter the password.</span></span>
    4. <span data-ttu-id="98d0f-184">En **la configuración de administración**, seleccione **Configuración de teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="98d0f-185">Habilitar el **modo de administración de CAP**y **CAP** .</span><span class="sxs-lookup"><span data-stu-id="98d0f-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="98d0f-186">Haga clic en **Guardar configuración**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-186">Click **Save Config**.</span></span>

- <span data-ttu-id="98d0f-187">Ahora bien, el teléfono está listo para poder iniciar sesión en la pantalla principal.</span><span class="sxs-lookup"><span data-stu-id="98d0f-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="98d0f-188">Iniciar sesión mediante la selección de **configuración** > **características** > **Skype para la empresa.**</span><span class="sxs-lookup"><span data-stu-id="98d0f-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="98d0f-189">Seleccione **Las credenciales de usuario**y seleccione **Inicio de sesión de web (CAP)** para generar un código.</span><span class="sxs-lookup"><span data-stu-id="98d0f-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="98d0f-190">Vaya al [portal de aprovisionamiento](http://aka.ms/skypecap)e iniciar sesión como **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="98d0f-191">Escriba el nombre para mostrar (por ejemplo, Main recepción).</span><span class="sxs-lookup"><span data-stu-id="98d0f-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="98d0f-192">Si está activada la opción **Buscar sólo los teléfonos de área común** , desactive la casilla de verificación y busque de nuevo.'</span><span class="sxs-lookup"><span data-stu-id="98d0f-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="98d0f-193">En la ventana de código de emparejamiento, escriba el código que aparece en el teléfono y haga clic en **aprovisionar**.</span><span class="sxs-lookup"><span data-stu-id="98d0f-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="98d0f-194">Después de este último paso, el teléfono debe iniciar sesión automáticamente.</span><span class="sxs-lookup"><span data-stu-id="98d0f-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="98d0f-195">See also</span><span class="sxs-lookup"><span data-stu-id="98d0f-195">Related topics</span></span>

- <span data-ttu-id="98d0f-196">Obtener más información acerca de los teléfonos disponibles en la [Implementación de Skype para teléfonos empresarial en línea](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="98d0f-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="98d0f-197">Obtener teléfonos con Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="98d0f-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


