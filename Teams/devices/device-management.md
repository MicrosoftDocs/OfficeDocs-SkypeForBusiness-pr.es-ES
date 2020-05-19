---
title: Administrar sus dispositivos en Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Obtenga información sobre cómo administrar dispositivos usados con equipos de su organización.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366a24706a80f6fe96cc8a3733022cc64f78ba7e
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281719"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="dc7b9-103">Administrar sus dispositivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc7b9-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="dc7b9-104">Como administrador, puede administrar los dispositivos que se usan con los equipos de su organización desde el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="dc7b9-105">Puede ver y administrar el inventario de dispositivos de su organización y realizar tareas como actualizar, reiniciar y supervisar los diagnósticos de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="dc7b9-106">También puede crear y asignar perfiles de configuración a un dispositivo o a grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="dc7b9-107">¿Qué dispositivos puede administrar?</span><span class="sxs-lookup"><span data-stu-id="dc7b9-107">What devices can you manage?</span></span>
<span data-ttu-id="dc7b9-108">Puede administrar cualquier dispositivo que esté certificado e inscrito en Teams.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="dc7b9-109">Un dispositivo se inscribe automáticamente la primera vez que un usuario inicia sesión en Teams en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="dc7b9-110">Para obtener una lista de los dispositivos certificados que se pueden administrar, consulte:</span><span class="sxs-lookup"><span data-stu-id="dc7b9-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="dc7b9-111">Teléfonos de conferencia</span><span class="sxs-lookup"><span data-stu-id="dc7b9-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="dc7b9-112">Teléfonos de escritorio</span><span class="sxs-lookup"><span data-stu-id="dc7b9-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="dc7b9-113">Barras de colaboración</span><span class="sxs-lookup"><span data-stu-id="dc7b9-113">Collaboration bars</span></span>

<span data-ttu-id="dc7b9-114">Los dispositivos se administran en el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com) , en **dispositivos** , en la barra de navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="dc7b9-115">Si tiene Microsoft Intune, los dispositivos se inscriton automáticamente en Intune.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="dc7b9-116">Una vez que se ha inscrito un dispositivo, se confirma el cumplimiento del dispositivo y se aplican las directivas de acceso condicional al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="dc7b9-117">Administrar teléfonos y barras de colaboración en Teams</span><span class="sxs-lookup"><span data-stu-id="dc7b9-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="dc7b9-118">Aunque los teléfonos y las barras de colaboración se administran de la misma manera en el centro de administración de Microsoft Teams, tienen sus propias secciones en el navegación de la izquierda, en **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="dc7b9-119">Esto le permite administrar cada tipo de dispositivo por separado.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="dc7b9-120">Desde aquí, puede ver y administrar teléfonos y barras de colaboración inscritos en los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="dc7b9-121">La información que verás para cada dispositivo incluye el nombre del dispositivo, el fabricante, el modelo, el usuario, el estado, la acción, la última vista y el historial.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="dc7b9-122">Puede personalizar la vista para que muestre la información que se adapte a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="dc7b9-123">Estos son algunos ejemplos de cómo puede administrar los dispositivos de equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="dc7b9-124">Para hacer esto...</span><span class="sxs-lookup"><span data-stu-id="dc7b9-124">To do this...</span></span>  |<span data-ttu-id="dc7b9-125">Haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="dc7b9-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="dc7b9-126">Cambiar la información del dispositivo</span><span class="sxs-lookup"><span data-stu-id="dc7b9-126">Change device information</span></span>   | <span data-ttu-id="dc7b9-127">Seleccione un dispositivo > **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-127">Select a device > **Edit**.</span></span> <span data-ttu-id="dc7b9-128">Puede editar detalles como el nombre del dispositivo, la etiqueta de activos y agregar notas.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="dc7b9-129">Administrar actualizaciones de software</span><span class="sxs-lookup"><span data-stu-id="dc7b9-129">Manage software updates</span></span>   |<span data-ttu-id="dc7b9-130">Seleccione un dispositivo > **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-130">Select a device > **Update**.</span></span> <span data-ttu-id="dc7b9-131">Puede ver la lista de actualizaciones de software y firmware disponibles para el dispositivo y elegir las actualizaciones que desea instalar.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="dc7b9-132">Reiniciar un dispositivo</span><span class="sxs-lookup"><span data-stu-id="dc7b9-132">Restart a device</span></span>   |<span data-ttu-id="dc7b9-133">Seleccione un dispositivo > **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="dc7b9-134">Ver el historial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="dc7b9-134">View device history</span></span>  | <span data-ttu-id="dc7b9-135">Seleccione un dispositivo > **historial**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-135">Select a device > **History**.</span></span> <span data-ttu-id="dc7b9-136">Puede ver el historial de actualizaciones del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="dc7b9-137">Ver diagnósticos</span><span class="sxs-lookup"><span data-stu-id="dc7b9-137">View diagnostics</span></span>  | <span data-ttu-id="dc7b9-138">Seleccione un dispositivo > **diagnósticos**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="dc7b9-139">Usar perfiles de configuración en Teams</span><span class="sxs-lookup"><span data-stu-id="dc7b9-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="dc7b9-140">Use perfiles de configuración para administrar la configuración y las características de los dispositivos de equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="dc7b9-141">Puede crear o cargar perfiles de configuración para incluir opciones y características que desee habilitar o deshabilitar y, después, asignar un perfil a un dispositivo o a grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="dc7b9-142">Crear un perfil de configuración</span><span class="sxs-lookup"><span data-stu-id="dc7b9-142">Create a configuration profile</span></span>

1. <span data-ttu-id="dc7b9-143">En el navegación de la izquierda, vaya a perfiles de configuración de **dispositivos**  >  **Configuration profiles**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="dc7b9-144">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-144">Click **Add**.</span></span>
3. <span data-ttu-id="dc7b9-145">Escriba un nombre para el perfil y, si lo desea, agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="dc7b9-146">Especifique la configuración que desee para el perfil y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="dc7b9-147">Asignar un perfil de configuración</span><span class="sxs-lookup"><span data-stu-id="dc7b9-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="dc7b9-148">En el navegación de la izquierda, vaya a perfiles de configuración de **dispositivos**  >  **Configuration profiles**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="dc7b9-149">Seleccione el **Perfil de configuración** que desea asignar y, a continuación, haga clic en **asignar al dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="dc7b9-150">En el panel **asignar dispositivos a un perfil de configuración** , busque y seleccione los dispositivos que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="dc7b9-151">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="dc7b9-151">Click **Save**.</span></span>
