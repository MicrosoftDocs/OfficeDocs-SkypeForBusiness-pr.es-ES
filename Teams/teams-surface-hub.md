---
title: Implementación de equipos de Microsoft para el concentrador de superficie
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
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
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132006"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="1aa52-103">Implementación de equipos de Microsoft para el concentrador de superficie</span><span class="sxs-lookup"><span data-stu-id="1aa52-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="1aa52-104">Antes de implementar Microsoft Teams Microsoft Surface concentrador, asegúrese de que haya cumplido con el hardware, sistema operativo y otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="1aa52-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="1aa52-105">Para obtener más información, consulte la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="1aa52-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

> [!NOTE]
> <span data-ttu-id="1aa52-106">Si se están realizando la transición de Skype para profesionales en línea, debe confirmar que se ha asignado una licencia de Microsoft Teams al usuario.</span><span class="sxs-lookup"><span data-stu-id="1aa52-106">If you are transitioning from Skype for Business Online, you need to confirm that a Microsoft Teams license is assigned to the user.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="1aa52-107">Instalación de los equipos para exponer concentrador desde el almacén de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1aa52-107">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="1aa52-108">Estas instrucciones son para la instalación de los equipos de concentrador de superficie de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="1aa52-108">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="1aa52-109">Iniciar el almacén de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1aa52-109">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="1aa52-110">a.</span><span class="sxs-lookup"><span data-stu-id="1aa52-110">a.</span></span> <span data-ttu-id="1aa52-111">Puntee en **Iniciar** > **todas las aplicaciones** > **configuración**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-111">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="1aa52-112">b.</span><span class="sxs-lookup"><span data-stu-id="1aa52-112">b.</span></span> <span data-ttu-id="1aa52-113">Puntee en **dispositivo de concentrador de superficie de cuenta, administración**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-113">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="1aa52-114">c.</span><span class="sxs-lookup"><span data-stu-id="1aa52-114">c.</span></span> <span data-ttu-id="1aa52-115">En la izquierda, puntee en la ficha **aplicaciones y características** .</span><span class="sxs-lookup"><span data-stu-id="1aa52-115">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="1aa52-116">d.</span><span class="sxs-lookup"><span data-stu-id="1aa52-116">d.</span></span> <span data-ttu-id="1aa52-117">En la derecha, puntee en el botón **Abrir almacén** .</span><span class="sxs-lookup"><span data-stu-id="1aa52-117">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="1aa52-118">De Microsoft Store, busque *Los equipos de Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="1aa52-118">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="1aa52-119">Se mostrarán los **Equipos de Microsoft para el concentrador de superficie** .</span><span class="sxs-lookup"><span data-stu-id="1aa52-119">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="1aa52-120">Puntee en el botón **obtener la aplicación** para instalar.</span><span class="sxs-lookup"><span data-stu-id="1aa52-120">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="1aa52-121">Una vez finalizada la instalación, reinicie el concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="1aa52-121">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="1aa52-122">No puntee en **Iniciar** desde la página de lista de la tienda.</span><span class="sxs-lookup"><span data-stu-id="1aa52-122">Do not tap **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="1aa52-123">Hacer que los equipos de la aplicación de las reuniones y llamadas de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="1aa52-123">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="1aa52-124">Hay dos opciones para configurar la directiva de aplicación de llamadas y las reuniones de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="1aa52-124">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="1aa52-125">**Opción 1**: configurar a través de la clave USB.</span><span class="sxs-lookup"><span data-stu-id="1aa52-125">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="1aa52-126">**Opción 2**: configurar a través de MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="1aa52-126">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="1aa52-127">Opción 1: Configurar a través de la clave USB</span><span class="sxs-lookup"><span data-stu-id="1aa52-127">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="1aa52-128">Los paquetes se pueden encontrar en esta [página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="1aa52-128">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="1aa52-129">Elija la adecuada para el paquete que va a instalar y cópielo a una clave USB.</span><span class="sxs-lookup"><span data-stu-id="1aa52-129">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="1aa52-130">El archivo .ppkg correcto para usar depende de la directiva de aplicación predeterminado que desea aplicar la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1aa52-130">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="1aa52-131">Número</span><span class="sxs-lookup"><span data-stu-id="1aa52-131">Number</span></span>  |<span data-ttu-id="1aa52-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aa52-132">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1aa52-133">0</span><span class="sxs-lookup"><span data-stu-id="1aa52-133">0</span></span>     | <span data-ttu-id="1aa52-134">Aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="1aa52-134">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="1aa52-135">1</span><span class="sxs-lookup"><span data-stu-id="1aa52-135">1</span></span>     | <span data-ttu-id="1aa52-136">Aplicación preferida de los equipos en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="1aa52-136">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="1aa52-137">2</span><span class="sxs-lookup"><span data-stu-id="1aa52-137">2</span></span>     | <span data-ttu-id="1aa52-138">Aplicación exclusiva de los equipos en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="1aa52-138">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="1aa52-139">Adjunta la clave USB en el dispositivo del concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="1aa52-139">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="1aa52-140">Abra la aplicación de **configuración** en un dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="1aa52-140">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="1aa52-141">Abra **administración de cuentas de dispositivo concentrador expuesta**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-141">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="1aa52-142">Abra **administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-142">Open **Device Management**.</span></span> 
5. <span data-ttu-id="1aa52-143">Haga clic en **Agregar o quitar un paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-143">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="1aa52-144">Haga clic en **Agregar paquete**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-144">Click **Add Package**.</span></span>
7. <span data-ttu-id="1aa52-145">Seleccione la opción de **Medios extraíble** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1aa52-145">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="1aa52-146">Agregar el paquete apropiado de <strong>TeamsRTMMode\*.ppkg</strong> que anteriormente se ha copiado a la clave USB.</span><span class="sxs-lookup"><span data-stu-id="1aa52-146">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="1aa52-147">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="1aa52-147">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="1aa52-148">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="1aa52-148">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="1aa52-149">Opción 2: Configurar a través de MDM como Intune</span><span class="sxs-lookup"><span data-stu-id="1aa52-149">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="1aa52-150">Use lo siguiente para configurar la directiva de aplicación predeterminada llamadas y reuniones a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="1aa52-150">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="1aa52-151">Vea también el blog, [implementar los equipos de Microsoft para aplicación de concentrador de superficie con Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="1aa52-151">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="1aa52-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="1aa52-152">Setting</span></span>   |<span data-ttu-id="1aa52-153">Valor</span><span class="sxs-lookup"><span data-stu-id="1aa52-153">Value</span></span>    |<span data-ttu-id="1aa52-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aa52-154">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="1aa52-155"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="1aa52-155">Path</span></span>      | <span data-ttu-id="1aa52-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="1aa52-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="1aa52-157">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1aa52-157">Data Type</span></span> | <span data-ttu-id="1aa52-158">entero (0-2)</span><span class="sxs-lookup"><span data-stu-id="1aa52-158">integer (0-2)</span></span>   |<span data-ttu-id="1aa52-159">0 - aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="1aa52-159">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="1aa52-160">1 - equipos aplicación preferida en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="1aa52-160">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="1aa52-161">2 - equipos aplicación exclusivo en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="1aa52-161">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="1aa52-162">Operaciones</span><span class="sxs-lookup"><span data-stu-id="1aa52-162">Operations</span></span>| <span data-ttu-id="1aa52-163">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="1aa52-163">Get, Set</span></span>        |

|<span data-ttu-id="1aa52-164">Configuración</span><span class="sxs-lookup"><span data-stu-id="1aa52-164">Setting</span></span>   |<span data-ttu-id="1aa52-165">Valor</span><span class="sxs-lookup"><span data-stu-id="1aa52-165">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="1aa52-166"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="1aa52-166">Path</span></span>      | <span data-ttu-id="1aa52-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="1aa52-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="1aa52-168">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1aa52-168">Data Type</span></span> | <span data-ttu-id="1aa52-169">¡cadena - cadena de conjunto a los equipos el identificador del paquete de aplicación como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Los equipos**</span><span class="sxs-lookup"><span data-stu-id="1aa52-169">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="1aa52-170">Operaciones</span><span class="sxs-lookup"><span data-stu-id="1aa52-170">Operations</span></span>| <span data-ttu-id="1aa52-171">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="1aa52-171">Get, Set</span></span>        |

<span data-ttu-id="1aa52-172">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="1aa52-172">Restart the Surface Hub device.</span></span> <span data-ttu-id="1aa52-173">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="1aa52-173">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

