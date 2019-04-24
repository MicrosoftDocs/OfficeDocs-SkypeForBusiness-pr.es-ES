---
title: Administrar sus dispositivos en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.devicemanagement.overview
- ms.teamsadmincenter.managedevices.overview
description: Obtenga información sobre cómo administrar dispositivos utilizados con los equipos de la organización.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20798daf34c4759b91c4926b209847aa51ddd668
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199204"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="e8536-103">Administrar sus dispositivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e8536-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="e8536-104">Como administrador, puede administrar todos los dispositivos utilizados con los equipos de la organización desde el & Teams Microsoft Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="e8536-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="e8536-105">Puede ver y administrar el inventario de los dispositivos para su organización y realizar tareas como la actualización, reiniciar y diagnósticos de monitor para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8536-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="e8536-106">También puede crear y asignar perfiles de configuración a un dispositivo o grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8536-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="e8536-107">¿Qué dispositivos pueden administrar?</span><span class="sxs-lookup"><span data-stu-id="e8536-107">What devices can you manage?</span></span>
<span data-ttu-id="e8536-108">Dispositivos deben ser certificados para los equipos e inscritos en los equipos.</span><span class="sxs-lookup"><span data-stu-id="e8536-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="e8536-109">Un dispositivo está inscrito automáticamente la primera vez que un usuario inicia sesión en los equipos en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8536-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="e8536-110">Para obtener una lista de los dispositivos certificados que se pueden administrar, consulte [teléfonos de conferencia](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) y [teléfonos de escritorio](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span><span class="sxs-lookup"><span data-stu-id="e8536-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="e8536-111">Si tiene Microsoft Intune, los dispositivos se inscriben automáticamente en Intune.</span><span class="sxs-lookup"><span data-stu-id="e8536-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="e8536-112">Después de que un dispositivo está inscrito, se confirme el cumplimiento del dispositivo y se aplican las directivas de acceso condicional para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8536-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="e8536-113">Administrar dispositivos en los equipos</span><span class="sxs-lookup"><span data-stu-id="e8536-113">Manage devices in Teams</span></span>

<span data-ttu-id="e8536-114">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="e8536-114">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e8536-115">En el panel de navegación izquierdo, vaya a **dispositivos** > **Administrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e8536-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="e8536-116">Seleccione **todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e8536-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="e8536-117">Desde aquí, puede ver y administrar todos los dispositivos que se inscriben en los equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="e8536-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="e8536-118">La información que aparece para cada dispositivo incluye historial, fabricante, modelo, usuario, estado, acción, último visto y nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8536-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="e8536-119">Puede personalizar la vista para mostrar la información que se ajuste a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="e8536-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="e8536-120">Aquí tiene algunos ejemplos de cómo se pueden administrar dispositivos de los equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="e8536-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="e8536-121">Para hacer esto...</span><span class="sxs-lookup"><span data-stu-id="e8536-121">To do this...</span></span>  |<span data-ttu-id="e8536-122">En este caso</span><span class="sxs-lookup"><span data-stu-id="e8536-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="e8536-123">Cambiar la información de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8536-123">Change device information</span></span>   | <span data-ttu-id="e8536-124">Seleccione un > dispositivo **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e8536-124">Select a device > **Edit**.</span></span> <span data-ttu-id="e8536-125">Puede editar detalles como el nombre del dispositivo, la información de usuario, la etiqueta de activos y agregar notas.</span><span class="sxs-lookup"><span data-stu-id="e8536-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="e8536-126">Administrar las actualizaciones de software</span><span class="sxs-lookup"><span data-stu-id="e8536-126">Manage software updates</span></span>   |<span data-ttu-id="e8536-127">Seleccione una **actualización**de dispositivo >.</span><span class="sxs-lookup"><span data-stu-id="e8536-127">Select a device > **Update**.</span></span> <span data-ttu-id="e8536-128">Puede ver la lista de actualizaciones de software y firmware disponibles para el dispositivo y elija las actualizaciones para instalar.</span><span class="sxs-lookup"><span data-stu-id="e8536-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="e8536-129">Reiniciar un dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8536-129">Restart a device</span></span>   |<span data-ttu-id="e8536-130">Seleccione un > de dispositivo que se **reinicie**.</span><span class="sxs-lookup"><span data-stu-id="e8536-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="e8536-131">Ver el historial de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8536-131">View device history</span></span>  | <span data-ttu-id="e8536-132">Seleccione un **historial**de dispositivo >.</span><span class="sxs-lookup"><span data-stu-id="e8536-132">Select a device > **History**.</span></span> <span data-ttu-id="e8536-133">Puede ver el historial de actualización para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8536-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="e8536-134">Ver diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e8536-134">View diagnostics</span></span>  | <span data-ttu-id="e8536-135">Seleccione un > dispositivo **Diagnósticos**.</span><span class="sxs-lookup"><span data-stu-id="e8536-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="e8536-136">Usar los perfiles de configuración en los equipos</span><span class="sxs-lookup"><span data-stu-id="e8536-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="e8536-137">Use los perfiles de configuración para administrar la configuración y las características de dispositivos de los equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="e8536-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="e8536-138">Puede crear o cargar los perfiles de configuración para incluir la configuración y las características que desea habilitar o deshabilitar y, a continuación, asignar un perfil a un dispositivo o grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8536-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="e8536-139">Crear un perfil de configuración</span><span class="sxs-lookup"><span data-stu-id="e8536-139">Create a configuration profile</span></span>

::: zone target="docs"

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="e8536-141">Uso de la & Teams Microsoft Skype para el centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="e8536-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="e8536-142">En el panel de navegación izquierdo, vaya a **dispositivos** > **Administrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e8536-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="e8536-143">Seleccione **los perfiles de configuración**y, a continuación, seleccione **nuevo perfil de configuración**.</span><span class="sxs-lookup"><span data-stu-id="e8536-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="e8536-144">Escriba un nombre para el perfil y si lo desea, agregue una descripción simplificada.</span><span class="sxs-lookup"><span data-stu-id="e8536-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="e8536-145">Especificar la configuración que desee para el perfil y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e8536-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="e8536-146">Asignar un perfil de configuración</span><span class="sxs-lookup"><span data-stu-id="e8536-146">Assign a configuration profile</span></span>

::: zone target="docs"

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="e8536-148">Uso de la & Teams Microsoft Skype para el centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="e8536-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="e8536-149">En el panel de navegación izquierdo, vaya a **dispositivos** > **Administrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e8536-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="e8536-150">Seleccione el **perfil de configuración**y, a continuación, en **asignado a** en el perfil que desea asignar, haga clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="e8536-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="e8536-151">En el panel **asignar dispositivos a un perfil de configuración** , busque y seleccione los dispositivos que desee asignar.</span><span class="sxs-lookup"><span data-stu-id="e8536-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="e8536-152">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="e8536-152">Click **Save**.</span></span>
