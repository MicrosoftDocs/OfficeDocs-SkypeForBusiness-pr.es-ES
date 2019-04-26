---
title: Configuración de notificación de inserción de clientes móviles
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Para configurar las notificaciones de inserción de Microsoft y las notificaciones de inserción de Apple, debe crear una directiva para definir los tipos de notificaciones de inserción que requieren.
ms.openlocfilehash: a2dafb190d0eb1c29d1dfb7cc07af40a10fb107c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215790"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="aca5d-103">Cliente móvil: Configuración de notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="aca5d-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="aca5d-104">Para configurar las **notificaciones de inserción de Microsoft** y **las notificaciones de inserción de Apple**, debe crear una directiva para definir qué tipos de notificaciones de inserción que necesite.</span><span class="sxs-lookup"><span data-stu-id="aca5d-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="aca5d-105">En la pantalla de configuración principal, haga clic en **Actualizar** para actualizar y volver a rellenar la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="aca5d-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="aca5d-106">Se proporciona un cuadro de búsqueda para limitar la lista de directivas que se muestra.</span><span class="sxs-lookup"><span data-stu-id="aca5d-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="aca5d-107">Mientras se escribe el nombre que se va a buscar, la lista de directivas se reduce automáticamente.</span><span class="sxs-lookup"><span data-stu-id="aca5d-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aca5d-p102">La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="aca5d-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="aca5d-111">Hay dos selecciones están disponibles para la creación de directivas y de edición:</span><span class="sxs-lookup"><span data-stu-id="aca5d-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="aca5d-112">**New**: haga clic aquí para crear una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="aca5d-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="aca5d-113">Debe proporcionar un sitio para que se aplican a la directiva.</span><span class="sxs-lookup"><span data-stu-id="aca5d-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="aca5d-114">A continuación, configure la configuración de la notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="aca5d-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="aca5d-115">**Configuración de notificación de inserción**, sólo puede crear directivas para los sitios que ya ha creado.</span><span class="sxs-lookup"><span data-stu-id="aca5d-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="aca5d-116">**Editar**: seleccione una directiva y haga clic en Editar para seleccionar una acción de una lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="aca5d-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="aca5d-117">Sólo puede editar sitios que ya ha creado o editar la directiva Global:</span><span class="sxs-lookup"><span data-stu-id="aca5d-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="aca5d-118">**Mostrar detalles …**: muestra información acerca de la directiva seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="aca5d-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="aca5d-119">Podrá realizar cambios en la directiva existente.</span><span class="sxs-lookup"><span data-stu-id="aca5d-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="aca5d-120">**Seleccionar todo**: si tiene un número de directivas y necesita seleccionar todas las directivas, haga clic en Seleccionar todo</span><span class="sxs-lookup"><span data-stu-id="aca5d-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="aca5d-121">**Eliminar**: se quita la directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="aca5d-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="aca5d-122">En **Seleccionar todo** y **Eliminar** quitará todas las directivas</span><span class="sxs-lookup"><span data-stu-id="aca5d-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="aca5d-123">No se puede eliminar la directiva **Global** predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aca5d-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="aca5d-124">Si intenta eliminarlo, se le notificará que se ha devuelto la directiva Global para los valores predeterminados (es decir, se borran todas las opciones), pero no se puede quitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="aca5d-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="aca5d-125">Crear una nueva directiva o editar una directiva existente está asociado a dos acciones:</span><span class="sxs-lookup"><span data-stu-id="aca5d-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="aca5d-126">**Confirmar** La acción Confirmar crea o actualiza la directiva y guarda los cambios</span><span class="sxs-lookup"><span data-stu-id="aca5d-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="aca5d-127">**Cancelar** La acción Cancelar descarta los cambios que se han realizado desde la última acción de confirmación.</span><span class="sxs-lookup"><span data-stu-id="aca5d-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="aca5d-128">Si cancela, se perderán todos los cambios realizados.</span><span class="sxs-lookup"><span data-stu-id="aca5d-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="aca5d-129">Son las dos configuraciones posibles para la **Configuración de notificación de inserción**.</span><span class="sxs-lookup"><span data-stu-id="aca5d-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="aca5d-130">La configuración se asocian con los servicios de notificación de inserción de Microsoft y de Apple.</span><span class="sxs-lookup"><span data-stu-id="aca5d-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="aca5d-131">Habilitar notificación de inserción para alguno de los servicios mediante la selección de la casilla de verificación situada junto al nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="aca5d-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="aca5d-132">Puede desactivar la casilla de verificación mediante la selección para desactivarla.</span><span class="sxs-lookup"><span data-stu-id="aca5d-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="aca5d-133">Una vez realizadas las selecciones, confirmar o cancela.</span><span class="sxs-lookup"><span data-stu-id="aca5d-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="aca5d-134">Hacer clic en Confirmar va a guardar los cambios en la directiva.</span><span class="sxs-lookup"><span data-stu-id="aca5d-134">Clicking commit will save the changes to the policy.</span></span>
  

