---
title: Aprovisionamiento remoto e inicio de sesión para dispositivos Android de Teams
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
description: Obtenga información sobre cómo aprovisionar e iniciar sesión de forma remota en dispositivos Android de Teams
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410384"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="bd4e0-103">Aprovisionamiento remoto e inicio de sesión para dispositivos Android de Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="bd4e0-104">Los administradores de TI pueden aprovisionar e iniciar sesión de forma remota en un dispositivo Android de Teams.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="bd4e0-105">Para aprovisionar un dispositivo de forma remota, el administrador debe cargar los IDs mac de los dispositivos que se aprovisionan y crear un código de verificación.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="bd4e0-106">Todo el proceso se puede completar de forma remota desde el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="bd4e0-107">Revisar los dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="bd4e0-107">Review the supported devices</span></span>

<span data-ttu-id="bd4e0-108">En la lista siguiente se muestran los requisitos de firmware del dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="bd4e0-109">Categoría de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd4e0-109">Device category</span></span>|<span data-ttu-id="bd4e0-110">Modelo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd4e0-110">Device model</span></span>|<span data-ttu-id="bd4e0-111">Versión de firmware</span><span class="sxs-lookup"><span data-stu-id="bd4e0-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="bd4e0-112">Teléfonos de Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-112">Teams phones</span></span>|<span data-ttu-id="bd4e0-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="bd4e0-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="bd4e0-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="bd4e0-114">58.15.0.124</span></span>|
|<span data-ttu-id="bd4e0-115">Teléfonos de Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-115">Teams phones</span></span>|<span data-ttu-id="bd4e0-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="bd4e0-116">Yealink VP59</span></span>|<span data-ttu-id="bd4e0-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="bd4e0-117">91.15.0.58</span></span>|
|<span data-ttu-id="bd4e0-118">Teléfonos de Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-118">Teams phones</span></span>|<span data-ttu-id="bd4e0-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="bd4e0-119">Yealink CP960</span></span>|<span data-ttu-id="bd4e0-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="bd4e0-120">73.15.0.117</span></span>|
|<span data-ttu-id="bd4e0-121">Teléfonos de Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-121">Teams phones</span></span>|<span data-ttu-id="bd4e0-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="bd4e0-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="bd4e0-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="bd4e0-123">122.15.0.36</span></span>|
|<span data-ttu-id="bd4e0-124">Teléfonos de Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-124">Teams phones</span></span>|<span data-ttu-id="bd4e0-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="bd4e0-125">Crestron UC-2</span></span>|<span data-ttu-id="bd4e0-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="bd4e0-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="bd4e0-127">Agregar una dirección MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd4e0-127">Add a device MAC address</span></span>

<span data-ttu-id="bd4e0-128">Complete los pasos siguientes para aprovisionar un nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="bd4e0-129">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="bd4e0-130">Expandir **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="bd4e0-131">Seleccione **Aprovisionar nuevo dispositivo** en la **pestaña** Acciones.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="bd4e0-132">En la **ventana Aprovisionar nuevos dispositivos,** puede agregar la dirección MAC manualmente o cargar un archivo.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="bd4e0-133">Agregar manualmente una dirección MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd4e0-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="bd4e0-134">En la **pestaña Activación en** espera, seleccione Agregar **id. de MAC.**</span><span class="sxs-lookup"><span data-stu-id="bd4e0-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![Agregar manualmente una dirección mac del dispositivo](../media/remote-provision-6.png)

1. <span data-ttu-id="bd4e0-136">Escriba el id. de MAC.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="bd4e0-137">Escriba una ubicación que ayude a los técnicos a identificar dónde instalar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="bd4e0-138">Seleccione **Aplicar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="bd4e0-139">Cargar un archivo para agregar una dirección MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd4e0-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="bd4e0-140">En la **pestaña Activación en** espera, seleccione Cargar los **IDs mac.**</span><span class="sxs-lookup"><span data-stu-id="bd4e0-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="bd4e0-141">Descargue la plantilla de archivo.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-141">Download the file template.</span></span>
3. <span data-ttu-id="bd4e0-142">Escriba el id. y la ubicación de MAC y, después, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="bd4e0-143">**Seleccione archivo** y, a continuación, **seleccione Cargar**.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="bd4e0-144">Generar un código de verificación</span><span class="sxs-lookup"><span data-stu-id="bd4e0-144">Generate a verification code</span></span>

<span data-ttu-id="bd4e0-145">Necesita un código de verificación para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-145">You need a verification code for the devices.</span></span> <span data-ttu-id="bd4e0-146">El código de verificación se genera en masa o en el nivel del dispositivo y es válido durante 24 horas.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="bd4e0-147">En la **pestaña Activación en** espera, seleccione un id. de MAC existente.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="bd4e0-148">Se crea una contraseña para la dirección MAC y se muestra en la **columna Código de** verificación.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="bd4e0-149">Proporcione la lista de los IDs MAC y los códigos de verificación a los técnicos de campo.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="bd4e0-150">Puede exportar los detalles directamente en un archivo y compartir el archivo con el técnico que está realizando el trabajo de instalación real.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="bd4e0-151">Aprovisionar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd4e0-151">Provision the device</span></span>

<span data-ttu-id="bd4e0-152">Cuando el dispositivo está encendido y conectado a la red, el técnico aprovisiona el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="bd4e0-153">Estos pasos se completan en el dispositivo de Teams.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="bd4e0-154">El técnico selecciona **Aprovisionar dispositivo** en **configuración.**</span><span class="sxs-lookup"><span data-stu-id="bd4e0-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Opción Aprovisionar nuevo dispositivo desde la pestaña Acciones](../media/provision-device1.png)
  
2. <span data-ttu-id="bd4e0-156">El técnico escribe el código de verificación específico del dispositivo en el campo de entrada proporcionado.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Aprovisionar verificación de nuevo dispositivo](../media/provision-device-verification1.png)

   <span data-ttu-id="bd4e0-158">Una vez que el dispositivo se aprovisiona correctamente, el nombre del inquilino aparece en la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Nombre del inquilino en la página de inicio de sesión](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="bd4e0-160">Iniciar sesión de forma remota</span><span class="sxs-lookup"><span data-stu-id="bd4e0-160">Sign in remotely</span></span>

<span data-ttu-id="bd4e0-161">El dispositivo aprovisionado aparece en la **pestaña Esperando inicio de sesión.** Inicie el proceso de inicio de sesión remoto seleccionando el dispositivo individual.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="bd4e0-162">Seleccione un dispositivo en la **pestaña Esperando inicio de sesión.**</span><span class="sxs-lookup"><span data-stu-id="bd4e0-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![La ventana con una lista de dispositivos listos para iniciar sesión.](../media/remote-device1.png)

2. <span data-ttu-id="bd4e0-164">Siga las instrucciones de **Iniciar sesión en un usuario** y, a continuación, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bd4e0-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![la ventana Iniciar sesión en un usuario para un dispositivo individual](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="bd4e0-166">Artículo relacionado</span><span class="sxs-lookup"><span data-stu-id="bd4e0-166">Related article</span></span>

- [<span data-ttu-id="bd4e0-167">Administrar los dispositivos en Teams</span><span class="sxs-lookup"><span data-stu-id="bd4e0-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="bd4e0-168">Actualizar dispositivos de Teams de forma remota</span><span class="sxs-lookup"><span data-stu-id="bd4e0-168">Update Teams devices remotely</span></span>](remote-update.md)
