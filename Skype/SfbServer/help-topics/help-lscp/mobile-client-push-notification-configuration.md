---
title: Configuración de notificaciones de inserción de cliente móvil
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Para configurar las notificaciones de inserción de Microsoft y las notificaciones push de Apple, debe crear una directiva para definir qué tipos de notificaciones push necesita.
ms.openlocfilehash: 571efc74050dc7b7cf55677167a803ddcd8c8f14
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293392"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="03b5d-103">Cliente móvil: Configuración de notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="03b5d-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="03b5d-104">Para configurar las **notificaciones de inserción de Microsoft** y las notificaciones push de **Apple**, debe crear una directiva para definir qué tipos de notificaciones push necesita.</span><span class="sxs-lookup"><span data-stu-id="03b5d-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="03b5d-105">En la pantalla principal de configuración, puede hacer clic en **Actualizar** para actualizar y volver a rellenar la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="03b5d-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="03b5d-106">Se proporciona un cuadro de búsqueda para restringir la lista de directivas mostradas.</span><span class="sxs-lookup"><span data-stu-id="03b5d-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="03b5d-107">A medida que escriba el nombre que está buscando, la lista de directivas se reducirá automáticamente.</span><span class="sxs-lookup"><span data-stu-id="03b5d-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03b5d-p102">La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="03b5d-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="03b5d-111">Hay dos opciones disponibles para la creación y edición de directivas:</span><span class="sxs-lookup"><span data-stu-id="03b5d-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="03b5d-112">**Nuevo**: haga clic para crear una nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="03b5d-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="03b5d-113">Debe proporcionar un sitio para que la Directiva se aplique a.</span><span class="sxs-lookup"><span data-stu-id="03b5d-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="03b5d-114">A continuación, configure las opciones de la notificación push.</span><span class="sxs-lookup"><span data-stu-id="03b5d-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="03b5d-115">Para la configuración de notificaciones de **inserción**, solo puede crear directivas para sitios que ya haya creado.</span><span class="sxs-lookup"><span data-stu-id="03b5d-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="03b5d-116">**Editar**: Seleccione una directiva y haga clic en Editar para seleccionar una acción de una lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="03b5d-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="03b5d-117">Solo puede editar los sitios que ya ha creado o editar la directiva global:</span><span class="sxs-lookup"><span data-stu-id="03b5d-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="03b5d-118">**Mostrar detalles...**: muestra información sobre la Directiva seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="03b5d-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="03b5d-119">Podrás realizar cambios en la directiva existente.</span><span class="sxs-lookup"><span data-stu-id="03b5d-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="03b5d-120">**Seleccionar todo**: Si tiene varias directivas y necesita seleccionar todas las directivas, haga clic en seleccionar todas.</span><span class="sxs-lookup"><span data-stu-id="03b5d-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="03b5d-121">**Eliminar**: quitará la Directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="03b5d-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="03b5d-122">Si usa **seleccionar todo** y **eliminar** , se eliminarán todas las directivas</span><span class="sxs-lookup"><span data-stu-id="03b5d-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="03b5d-123">No puede eliminar la directiva **global** predeterminada.</span><span class="sxs-lookup"><span data-stu-id="03b5d-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="03b5d-124">Si intenta eliminarla, se le notificará que la directiva global se ha devuelto a los valores predeterminados (es decir, se ha desactivado toda la configuración), pero la Directiva no se puede quitar.</span><span class="sxs-lookup"><span data-stu-id="03b5d-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="03b5d-125">Crear una nueva Directiva o editar una directiva existente está asociado a dos acciones:</span><span class="sxs-lookup"><span data-stu-id="03b5d-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="03b5d-126">**Confirmar** La acción confirmar crea o actualiza la Directiva y guarda los cambios.</span><span class="sxs-lookup"><span data-stu-id="03b5d-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="03b5d-127">**Cancelar** La acción cancelar descarta los cambios que se hayan realizado desde la última acción de confirmación.</span><span class="sxs-lookup"><span data-stu-id="03b5d-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="03b5d-128">Si cancelas, se perderán los cambios realizados.</span><span class="sxs-lookup"><span data-stu-id="03b5d-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="03b5d-129">Hay dos opciones posibles para la configuración de las **notificaciones push**.</span><span class="sxs-lookup"><span data-stu-id="03b5d-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="03b5d-130">La configuración se asocia a los servicios de notificaciones de inserción para Microsoft y a Apple.</span><span class="sxs-lookup"><span data-stu-id="03b5d-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="03b5d-131">Para habilitar la notificación de inserción para cualquiera de los servicios, active la casilla situada junto al nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="03b5d-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="03b5d-132">Para desactivar la casilla, selecciónela para desactivarla.</span><span class="sxs-lookup"><span data-stu-id="03b5d-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="03b5d-133">Una vez que haya realizado las selecciones, puede confirmar o cancelar.</span><span class="sxs-lookup"><span data-stu-id="03b5d-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="03b5d-134">Al hacer clic en confirmar se guardarán los cambios en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="03b5d-134">Clicking commit will save the changes to the policy.</span></span>
  

