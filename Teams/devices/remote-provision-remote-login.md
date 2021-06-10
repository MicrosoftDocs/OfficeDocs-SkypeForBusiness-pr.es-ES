---
title: Aprovisionamiento remoto e inicio de sesión para Teams dispositivos Android
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo aprovisionar e iniciar sesión de forma remota Teams dispositivos Android
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059194"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="e8ce8-103">Aprovisionamiento remoto e inicio de sesión para Teams dispositivos Android</span><span class="sxs-lookup"><span data-stu-id="e8ce8-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="e8ce8-104">Los administradores de TI pueden aprovisionar e iniciar sesión de forma remota en Teams dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="e8ce8-105">Para aprovisionar un dispositivo de forma remota, el administrador debe cargar los IDs mac de los dispositivos que se aprovisionan y crear un código de verificación.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="e8ce8-106">Todo el proceso se puede completar de forma remota desde el Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="e8ce8-107">Revisar los dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="e8ce8-107">Review the supported devices</span></span>

<span data-ttu-id="e8ce8-108">En la lista siguiente se muestran los requisitos de firmware del dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="e8ce8-109">Categoría de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8ce8-109">Device category</span></span>|<span data-ttu-id="e8ce8-110">Modelo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8ce8-110">Device model</span></span>|<span data-ttu-id="e8ce8-111">Versión de firmware</span><span class="sxs-lookup"><span data-stu-id="e8ce8-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="e8ce8-112">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-112">Teams phones</span></span>|<span data-ttu-id="e8ce8-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="e8ce8-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="e8ce8-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="e8ce8-114">58.15.0.124</span></span>|
|<span data-ttu-id="e8ce8-115">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-115">Teams phones</span></span>|<span data-ttu-id="e8ce8-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="e8ce8-116">Yealink VP59</span></span>|<span data-ttu-id="e8ce8-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="e8ce8-117">91.15.0.58</span></span>|
|<span data-ttu-id="e8ce8-118">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-118">Teams phones</span></span>|<span data-ttu-id="e8ce8-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="e8ce8-119">Yealink CP960</span></span>|<span data-ttu-id="e8ce8-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="e8ce8-120">73.15.0.117</span></span>|
|<span data-ttu-id="e8ce8-121">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-121">Teams phones</span></span>|<span data-ttu-id="e8ce8-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="e8ce8-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="e8ce8-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="e8ce8-123">122.15.0.36</span></span>|
|<span data-ttu-id="e8ce8-124">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-124">Teams phones</span></span>|<span data-ttu-id="e8ce8-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="e8ce8-125">Crestron UC-2</span></span>|<span data-ttu-id="e8ce8-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="e8ce8-126">1.0.3.52</span></span>|
|<span data-ttu-id="e8ce8-127">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-127">Teams phones</span></span>|  <span data-ttu-id="e8ce8-128">Poly Trio C60</span><span class="sxs-lookup"><span data-stu-id="e8ce8-128">Poly Trio C60</span></span>|  <span data-ttu-id="e8ce8-129">7.0.2.1071</span><span class="sxs-lookup"><span data-stu-id="e8ce8-129">7.0.2.1071</span></span>|
|<span data-ttu-id="e8ce8-130">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-130">Teams phones</span></span>|  <span data-ttu-id="e8ce8-131">CCX400/CCX500/CCX600</span><span class="sxs-lookup"><span data-stu-id="e8ce8-131">CCX400/CCX500/CCX600</span></span>    |<span data-ttu-id="e8ce8-132">7.0.2.1072</span><span class="sxs-lookup"><span data-stu-id="e8ce8-132">7.0.2.1072</span></span>|
|<span data-ttu-id="e8ce8-133">Teams teléfonos</span><span class="sxs-lookup"><span data-stu-id="e8ce8-133">Teams phones</span></span>|  <span data-ttu-id="e8ce8-134">Códigos de audio C448HD/C450HD/C470HD</span><span class="sxs-lookup"><span data-stu-id="e8ce8-134">Audio Codes C448HD/C450HD/C470HD</span></span>|   <span data-ttu-id="e8ce8-135">1.10.120</span><span class="sxs-lookup"><span data-stu-id="e8ce8-135">1.10.120</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="e8ce8-136">Agregar una dirección MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8ce8-136">Add a device MAC address</span></span>

<span data-ttu-id="e8ce8-137">Complete los pasos siguientes para aprovisionar un nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-137">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="e8ce8-138">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="e8ce8-138">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="e8ce8-139">Expandir **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-139">Expand **Devices**.</span></span>
3. <span data-ttu-id="e8ce8-140">Seleccione **Aprovisionar nuevo dispositivo** en la **pestaña** Acciones.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-140">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="e8ce8-141">En la **ventana Aprovisionar nuevos dispositivos,** puede agregar la dirección MAC manualmente o cargar un archivo.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-141">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="e8ce8-142">Agregar manualmente una dirección MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8ce8-142">Manually add a device MAC address</span></span>

1. <span data-ttu-id="e8ce8-143">En la **pestaña Activación en** espera, seleccione Agregar **id. de MAC.**</span><span class="sxs-lookup"><span data-stu-id="e8ce8-143">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![Agregar manualmente una dirección mac del dispositivo](../media/remote-provision-6.png)

1. <span data-ttu-id="e8ce8-145">Escriba el id. de MAC.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-145">Enter the MAC ID.</span></span>
1. <span data-ttu-id="e8ce8-146">Escriba una ubicación que ayude a los técnicos a identificar dónde instalar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-146">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="e8ce8-147">Seleccione **Aplicar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-147">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="e8ce8-148">Upload un archivo para agregar una dirección MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8ce8-148">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="e8ce8-149">En la **pestaña Activación en** espera, seleccione Upload de **MAC.**</span><span class="sxs-lookup"><span data-stu-id="e8ce8-149">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="e8ce8-150">Descargue la plantilla de archivo.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-150">Download the file template.</span></span>
3. <span data-ttu-id="e8ce8-151">Escriba el id. y la ubicación de MAC y, después, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-151">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="e8ce8-152">**Seleccione archivo** y, a continuación, **seleccione Upload**.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-152">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="e8ce8-153">Generar un código de verificación</span><span class="sxs-lookup"><span data-stu-id="e8ce8-153">Generate a verification code</span></span>

<span data-ttu-id="e8ce8-154">Necesita un código de verificación para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-154">You need a verification code for the devices.</span></span> <span data-ttu-id="e8ce8-155">El código de verificación se genera en masa o en el nivel del dispositivo y es válido durante 24 horas.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-155">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="e8ce8-156">En la **pestaña Activación en** espera, seleccione un id. de MAC existente.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-156">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="e8ce8-157">Se crea una contraseña para la dirección MAC y se muestra en la **columna Código de** verificación.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-157">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="e8ce8-158">Proporcione la lista de los IDs MAC y los códigos de verificación a los técnicos de campo.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-158">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="e8ce8-159">Puede exportar los detalles directamente en un archivo y compartir el archivo con el técnico que está realizando el trabajo de instalación real.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-159">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="e8ce8-160">Aprovisionar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8ce8-160">Provision the device</span></span>

<span data-ttu-id="e8ce8-161">Cuando el dispositivo está encendido y conectado a la red, el técnico aprovisiona el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-161">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="e8ce8-162">Estos pasos se completan en Teams dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-162">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="e8ce8-163">El técnico selecciona **Aprovisionar dispositivo** en **el Configuración**.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-163">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Opción Aprovisionar nuevo dispositivo desde la pestaña Acciones](../media/provision-device1.png)
  
2. <span data-ttu-id="e8ce8-165">El técnico escribe el código de verificación específico del dispositivo en el campo de entrada proporcionado.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-165">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Aprovisionar verificación de nuevo dispositivo](../media/provision-device-verification1.png)

   <span data-ttu-id="e8ce8-167">Una vez que el dispositivo se aprovisiona correctamente, el nombre del inquilino aparece en la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-167">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Nombre del inquilino en la página de inicio de sesión](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="e8ce8-169">Iniciar sesión de forma remota</span><span class="sxs-lookup"><span data-stu-id="e8ce8-169">Sign in remotely</span></span>

<span data-ttu-id="e8ce8-170">El dispositivo aprovisionado aparece en la **pestaña Esperando inicio de sesión.** Inicie el proceso de inicio de sesión remoto seleccionando el dispositivo individual.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-170">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="e8ce8-171">Seleccione un dispositivo en la **pestaña Esperando inicio de sesión.**</span><span class="sxs-lookup"><span data-stu-id="e8ce8-171">Select a device from the **Awaiting sign in** tab.</span></span>

   ![La ventana con una lista de dispositivos listos para iniciar sesión.](../media/remote-device1.png)

2. <span data-ttu-id="e8ce8-173">Siga las instrucciones de **Iniciar sesión en un usuario** y, a continuación, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e8ce8-173">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![la ventana Iniciar sesión en un usuario para un dispositivo individual](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="e8ce8-175">Artículo relacionado</span><span class="sxs-lookup"><span data-stu-id="e8ce8-175">Related article</span></span>

- [<span data-ttu-id="e8ce8-176">Administrar los dispositivos en Teams</span><span class="sxs-lookup"><span data-stu-id="e8ce8-176">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="e8ce8-177">Actualizar Teams dispositivos de forma remota</span><span class="sxs-lookup"><span data-stu-id="e8ce8-177">Update Teams devices remotely</span></span>](remote-update.md)
