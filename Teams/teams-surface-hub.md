---
title: Implementación de equipos de Microsoft para el concentrador de superficie
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 09/26/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configuración de administración para Microsoft Teams para concentrador de superficie.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: aca03693a7abea6e26f175cc49f0142894749160
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372184"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="8e49a-103">Implementación de equipos de Microsoft para el concentrador de superficie</span><span class="sxs-lookup"><span data-stu-id="8e49a-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="8e49a-104">Antes de implementar Microsoft Teams Microsoft Surface concentrador, asegúrese de que haya cumplido con el hardware, sistema operativo y otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="8e49a-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="8e49a-105">Para obtener más información, consulte la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="8e49a-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="8e49a-106">Instalación de los equipos para exponer concentrador desde el almacén de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8e49a-106">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="8e49a-107">Estas instrucciones son para la instalación de los equipos de concentrador de superficie de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="8e49a-107">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="8e49a-108">Iniciar el almacén de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="8e49a-108">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="8e49a-109">a.</span><span class="sxs-lookup"><span data-stu-id="8e49a-109">a.</span></span> <span data-ttu-id="8e49a-110">Puntee en **Iniciar** > **todas las aplicaciones** > **configuración**.</span><span class="sxs-lookup"><span data-stu-id="8e49a-110">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="8e49a-111">b.</span><span class="sxs-lookup"><span data-stu-id="8e49a-111">b.</span></span> <span data-ttu-id="8e49a-112">Puntee en **dispositivo de concentrador de superficie de cuenta, administración**.</span><span class="sxs-lookup"><span data-stu-id="8e49a-112">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="8e49a-113">c.</span><span class="sxs-lookup"><span data-stu-id="8e49a-113">c.</span></span> <span data-ttu-id="8e49a-114">En la izquierda, puntee en la ficha **aplicaciones y características** .</span><span class="sxs-lookup"><span data-stu-id="8e49a-114">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="8e49a-115">d.</span><span class="sxs-lookup"><span data-stu-id="8e49a-115">d.</span></span> <span data-ttu-id="8e49a-116">En la derecha, puntee en el botón **Abrir almacén** .</span><span class="sxs-lookup"><span data-stu-id="8e49a-116">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="8e49a-117">De Microsoft Store, busque *Los equipos de Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="8e49a-117">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="8e49a-118">Se mostrarán los **Equipos de Microsoft para el concentrador de superficie** .</span><span class="sxs-lookup"><span data-stu-id="8e49a-118">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="8e49a-119">Puntee en el botón **obtener la aplicación** para instalar.</span><span class="sxs-lookup"><span data-stu-id="8e49a-119">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="8e49a-120">Una vez finalizada la instalación, reinicie el concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="8e49a-120">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="8e49a-121">Puntee en no en el **Inicio** de la lista de página de la tienda.</span><span class="sxs-lookup"><span data-stu-id="8e49a-121">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="8e49a-122">Hacer que los equipos de la aplicación de las reuniones y llamadas de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="8e49a-122">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="8e49a-123">Hay dos opciones para configurar la directiva de aplicación de llamadas y las reuniones de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="8e49a-123">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="8e49a-124">**Opción 1**: configurar a través de la clave USB.</span><span class="sxs-lookup"><span data-stu-id="8e49a-124">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="8e49a-125">**Opción 2**: configurar a través de MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="8e49a-125">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="8e49a-126">Opción 1: Configurar a través de la clave USB</span><span class="sxs-lookup"><span data-stu-id="8e49a-126">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="8e49a-127">Los paquetes se pueden encontrar en esta [página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="8e49a-127">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="8e49a-128">Elija la adecuada para el paquete que va a instalar y cópielo a una clave USB.</span><span class="sxs-lookup"><span data-stu-id="8e49a-128">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="8e49a-129">El archivo .ppkg correcto para usar depende de la directiva de aplicación predeterminado que desea aplicar la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8e49a-129">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="8e49a-130">Número</span><span class="sxs-lookup"><span data-stu-id="8e49a-130">Number</span></span>  |<span data-ttu-id="8e49a-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e49a-131">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8e49a-132">0</span><span class="sxs-lookup"><span data-stu-id="8e49a-132">0</span></span>     | <span data-ttu-id="8e49a-133">Aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="8e49a-133">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="8e49a-134">1</span><span class="sxs-lookup"><span data-stu-id="8e49a-134">1</span></span>     | <span data-ttu-id="8e49a-135">Aplicación preferida de los equipos en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="8e49a-135">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="8e49a-136">2</span><span class="sxs-lookup"><span data-stu-id="8e49a-136">2</span></span>     | <span data-ttu-id="8e49a-137">Aplicación exclusiva de los equipos en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="8e49a-137">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="8e49a-138">Adjunta la clave USB en el dispositivo del concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="8e49a-138">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="8e49a-139">Abra la aplicación de **configuración** en un dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="8e49a-139">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="8e49a-140">Abra **administración de cuentas de dispositivo concentrador expuesta**.</span><span class="sxs-lookup"><span data-stu-id="8e49a-140">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="8e49a-141">Abra **administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8e49a-141">Open **Device Management**.</span></span> 
5. <span data-ttu-id="8e49a-142">Haga clic en **Agregar o quitar un paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="8e49a-142">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="8e49a-143">Haga clic en **Agregar paquete**.</span><span class="sxs-lookup"><span data-stu-id="8e49a-143">Click **Add Package**.</span></span>
7. <span data-ttu-id="8e49a-144">Seleccione la opción de **Medios extraíble** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="8e49a-144">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="8e49a-145">Agregar el paquete apropiado de <strong>TeamsRTMMode\*.ppkg</strong> que anteriormente se ha copiado a la clave USB.</span><span class="sxs-lookup"><span data-stu-id="8e49a-145">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="8e49a-146">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="8e49a-146">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="8e49a-147">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="8e49a-147">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="8e49a-148">Opción 2: Configurar a través de MDM como Intune</span><span class="sxs-lookup"><span data-stu-id="8e49a-148">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="8e49a-149">Use lo siguiente para configurar la directiva de aplicación predeterminada llamadas y reuniones a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="8e49a-149">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="8e49a-150">Vea también el blog, [implementar los equipos de Microsoft para aplicación de concentrador de superficie con Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="8e49a-150">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="8e49a-151">Configuración</span><span class="sxs-lookup"><span data-stu-id="8e49a-151">Setting</span></span>   |<span data-ttu-id="8e49a-152">Valor</span><span class="sxs-lookup"><span data-stu-id="8e49a-152">Value</span></span>    |<span data-ttu-id="8e49a-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e49a-153">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="8e49a-154"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="8e49a-154">Path</span></span>      | <span data-ttu-id="8e49a-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="8e49a-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="8e49a-156">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8e49a-156">Data Type</span></span> | <span data-ttu-id="8e49a-157">entero (0-2)</span><span class="sxs-lookup"><span data-stu-id="8e49a-157">integer (0-2)</span></span>   |<span data-ttu-id="8e49a-158">0 - aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="8e49a-158">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="8e49a-159">1 - equipos aplicación preferida en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="8e49a-159">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="8e49a-160">2 - equipos aplicación exclusivo en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="8e49a-160">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="8e49a-161">Operaciones</span><span class="sxs-lookup"><span data-stu-id="8e49a-161">Operations</span></span>| <span data-ttu-id="8e49a-162">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="8e49a-162">Get, Set</span></span>        |

|<span data-ttu-id="8e49a-163">Configuración</span><span class="sxs-lookup"><span data-stu-id="8e49a-163">Setting</span></span>   |<span data-ttu-id="8e49a-164">Valor</span><span class="sxs-lookup"><span data-stu-id="8e49a-164">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="8e49a-165"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="8e49a-165">Path</span></span>      | <span data-ttu-id="8e49a-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="8e49a-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="8e49a-167">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8e49a-167">Data Type</span></span> | <span data-ttu-id="8e49a-168">¡cadena - cadena de conjunto a los equipos el identificador del paquete de aplicación como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Los equipos**</span><span class="sxs-lookup"><span data-stu-id="8e49a-168">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="8e49a-169">Operaciones</span><span class="sxs-lookup"><span data-stu-id="8e49a-169">Operations</span></span>| <span data-ttu-id="8e49a-170">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="8e49a-170">Get, Set</span></span>        |

<span data-ttu-id="8e49a-171">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="8e49a-171">Restart the Surface Hub device.</span></span> <span data-ttu-id="8e49a-172">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="8e49a-172">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

