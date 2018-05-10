---
title: Implementación de teléfonos de Skype Empresarial Online
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar las opciones de teléfonos de área común.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
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
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a><span data-ttu-id="0051e-103">Teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="0051e-103">Common Area Phones</span></span>
<span data-ttu-id="0051e-104">Un teléfono de área común o CAP, es normalmente se colocan en un área compartido y no asociado a un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="0051e-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="0051e-105">Por ejemplo, un teléfono de área de recepción de teléfono puerta teléfono o salas de reuniones, mayúsculas se configuran como dispositivos en lugar de los usuarios e inicie sesión automáticamente en la red.</span><span class="sxs-lookup"><span data-stu-id="0051e-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="0051e-106">En los pasos siguientes, le ayudaremos a configurar una cuenta de sistema de teléfono de Microsoft con planes de llamar a y, a continuación, implementar un extremo.</span><span class="sxs-lookup"><span data-stu-id="0051e-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="0051e-107">Requisitos previos para teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="0051e-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="0051e-108">Confirme que dispone de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0051e-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="0051e-109">Adquirido SKU de teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="0051e-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="0051e-110">Firmware actualizado (vea admiten Firmware de temahttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="0051e-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="0051e-111">Teléfonos aprobados (ver la lista enhttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="0051e-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 


## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="0051e-112">Comprobar el firmware de su teléfono</span><span class="sxs-lookup"><span data-stu-id="0051e-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="0051e-113">**Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="0051e-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="0051e-114">**Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.</span><span class="sxs-lookup"><span data-stu-id="0051e-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="0051e-115">**Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.</span><span class="sxs-lookup"><span data-stu-id="0051e-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="0051e-116">**Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.</span><span class="sxs-lookup"><span data-stu-id="0051e-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="0051e-117">Actualizaciones de firmware se administran mediante el Skype para servicio empresarial.</span><span class="sxs-lookup"><span data-stu-id="0051e-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="0051e-118">Cada Skype para la empresa certificada firmware del teléfono se cargó en la Skype para servidor de actualización de negocio, y actualización de dispositivos está habilitado en todos los teléfonos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0051e-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="0051e-119">Según el tiempo de inactividad en el teléfono y los intervalos de sondeo, teléfonos automáticamente descargar e instalar las compilaciones certificadas más recientes.</span><span class="sxs-lookup"><span data-stu-id="0051e-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="0051e-120">Puede deshabilitar la configuración de actualización de dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) y establecer el parámetro _EnableDeviceUpdate_ en `false`.</span><span class="sxs-lookup"><span data-stu-id="0051e-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="0051e-121">Crear CAP</span><span class="sxs-lookup"><span data-stu-id="0051e-121">Create CAP</span></span>
<span data-ttu-id="0051e-122">Cree el extremo mediante la configuración de la configuración antes de configurar el teléfono físico.</span><span class="sxs-lookup"><span data-stu-id="0051e-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="0051e-123">El teléfono de área común SKU de compra.</span><span class="sxs-lookup"><span data-stu-id="0051e-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="0051e-124">Configurar el teléfono de área común<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="0051e-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="0051e-125">**Crear usuario**</span><span class="sxs-lookup"><span data-stu-id="0051e-125">**Create user**</span></span> 
1. <span data-ttu-id="0051e-126">Asignar el teléfono de área común SKU</span><span class="sxs-lookup"><span data-stu-id="0051e-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="0051e-127">Asignar una llamada a planear (si se usa el sistema telefónico de Microsoft con planes de llamada).</span><span class="sxs-lookup"><span data-stu-id="0051e-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="0051e-128">Asignar a un número de teléfono disponibles en el Skype para el centro de administración de negocio, o solicitar un nuevo número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="0051e-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="0051e-129">**Crear nuevo usuario**</span><span class="sxs-lookup"><span data-stu-id="0051e-129">**Create New User**</span></span>

1. <span data-ttu-id="0051e-130">En el panel de aprovisionamiento, tienen una opción para escribir un nombre y el apellido (por ejemplo, recepción principal).</span><span class="sxs-lookup"><span data-stu-id="0051e-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="0051e-131">Escriba un nombre para mostrar (requerido), por ejemplo, "Main recepción".</span><span class="sxs-lookup"><span data-stu-id="0051e-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="0051e-132">Escriba un nombre de usuario (obligatorio), por ejemplo "MainReception" @"dominio" (nombre de la compañía o enterprise)</span><span class="sxs-lookup"><span data-stu-id="0051e-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="0051e-133">Escriba la ubicación (país).</span><span class="sxs-lookup"><span data-stu-id="0051e-133">Enter Location (country).</span></span>

<span data-ttu-id="0051e-134">**Asignar el teléfono de área común SKU** En el centro de administración de Office 365, vaya a **facturación > Servicios de compra** y agregue el **Teléfono de área común**</span><span class="sxs-lookup"><span data-stu-id="0051e-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="0051e-135">**Asignar el Plan de llamadas en SKU de capital**</span><span class="sxs-lookup"><span data-stu-id="0051e-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="0051e-136">Seleccione un Plan de llamada para habilitar el teléfono.</span><span class="sxs-lookup"><span data-stu-id="0051e-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="0051e-137">Agregar el capital para habilitar el sistema telefónico y Skype para Online Plan 2 de negocio en el SKU de capital.</span><span class="sxs-lookup"><span data-stu-id="0051e-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="0051e-138">**Asignar a un número de teléfono**</span><span class="sxs-lookup"><span data-stu-id="0051e-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="0051e-139">Buscar números de teléfono disponibles en **voz > números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="0051e-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="0051e-140">Seleccione un número en la lista disponible del número de números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="0051e-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="0051e-141">Confirme la selección mediante la selección de **voz** y **Los números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="0051e-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="0051e-142">[Nota] Los usuarios de voz mostrarán sólo si tiene la licencia del sistema telefónico aplicada, aunque incluso después de aplicar, puede tardar tiempo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="0051e-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="0051e-143">En algún momento volver a abrir Skype para administración empresarial centro de ayuda.</span><span class="sxs-lookup"><span data-stu-id="0051e-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="0051e-144">Configurar el teléfono</span><span class="sxs-lookup"><span data-stu-id="0051e-144">Configure Phone</span></span>

<span data-ttu-id="0051e-145">**Preparar los teléfonos físicos**</span><span class="sxs-lookup"><span data-stu-id="0051e-145">**Prepare the physical phones**</span></span> 

<span data-ttu-id="0051e-146">Su teléfono seleccionado debe tener el modo de teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="0051e-146">Your selected phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="0051e-147">***Teléfono Polycom VVX de ejemplo***</span><span class="sxs-lookup"><span data-stu-id="0051e-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="0051e-148">Habilitar el modo de teléfono de área común en Polycom VVX siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0051e-148">Enable Common Area Phone Mode on Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="0051e-149">En el explorador, use la interfaz web para habilitar el modo de CAP en el VVX</span><span class="sxs-lookup"><span data-stu-id="0051e-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="0051e-150">Vaya a **configuración** y en la Skype para la opción de configuración de negocio, seleccione **Teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="0051e-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="0051e-151">Haga clic en **Guardar** para guardar las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="0051e-151">Click **Save** to save your configuration settings.</span></span>

<span data-ttu-id="0051e-152">Ahora que está habilitado el modo de teléfono de capital, configurar el teléfono mediante la pantalla del teléfono.</span><span class="sxs-lookup"><span data-stu-id="0051e-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span>

1. <span data-ttu-id="0051e-153">En la configuración, seleccione **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="0051e-153">In the Settings, select **Advanced**.</span></span>
2. <span data-ttu-id="0051e-154">Escriba la contraseña.</span><span class="sxs-lookup"><span data-stu-id="0051e-154">Enter password.</span></span>
3. <span data-ttu-id="0051e-155">En la configuración de administración, seleccione **Configuración de teléfono de área común**.</span><span class="sxs-lookup"><span data-stu-id="0051e-155">In Administration settings, select **Common Area Phone Settings**.</span></span>
4. <span data-ttu-id="0051e-156">Habilitar el teléfono de área común y administración de capital</span><span class="sxs-lookup"><span data-stu-id="0051e-156">Enable Common Area Phone and CAP Admin</span></span>
5. <span data-ttu-id="0051e-157">Seleccione **Guardar Config**.</span><span class="sxs-lookup"><span data-stu-id="0051e-157">Select **Save Config**.</span></span>

<span data-ttu-id="0051e-158">El teléfono está listo para aprovisionarse, que hará al iniciar sesión en la pantalla principal.</span><span class="sxs-lookup"><span data-stu-id="0051e-158">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="0051e-159">Iniciar sesión mediante la selección de **Configuración > funciones > Skype para la empresa.**</span><span class="sxs-lookup"><span data-stu-id="0051e-159">Sign in by selecting **settings > features > Skype for Business.**</span></span>
2. <span data-ttu-id="0051e-160">Seleccione las credenciales de usuario y seleccione Seleccionar **Inicio de sesión de web (CAP)** para generar un código..</span><span class="sxs-lookup"><span data-stu-id="0051e-160">Select User Credentials, and select select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="0051e-161">Vaya al portal de aprovisionamiento http://aka.ms/skypecape iniciar sesión como **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="0051e-161">Go to the provisioning portal http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="0051e-162">Escriba el nombre para mostrar (por ejemplo, Main recepción) para ver su extremo.</span><span class="sxs-lookup"><span data-stu-id="0051e-162">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="0051e-163">[Nota] Si "Búsqueda para teléfonos de área común sólo" está desprotegido, desactive la casilla de verificación y volver a buscar.</span><span class="sxs-lookup"><span data-stu-id="0051e-163">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="0051e-164">En la ventana de código de emparejamiento, escriba el código que aparece en el teléfono y haga clic en **aprovisionar**.</span><span class="sxs-lookup"><span data-stu-id="0051e-164">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="0051e-165">WHT este último paso, el teléfono debe iniciar sesión automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0051e-165">Wht this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="0051e-166">Encontrará más información acerca de los teléfonos disponibles [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="0051e-166">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


