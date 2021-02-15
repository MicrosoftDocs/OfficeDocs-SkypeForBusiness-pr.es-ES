---
title: Configuración de notificaciones de inserción de cliente móvil
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Para configurar Notificaciones de inserción de Microsoft y Notificaciones de inserción de Apple, debe crear una directiva para definir qué tipos de notificaciones de inserción requiere.
ms.openlocfilehash: 693b954fffbbce56a2d95ce29128482937b6fa05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836680"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="634f3-103">Cliente móvil: Configuración de notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="634f3-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="634f3-104">Para configurar **Notificaciones de inserción de Microsoft** y **Notificaciones de inserción de Apple**, debe crear una directiva para definir qué tipos de notificaciones de inserción requiere.</span><span class="sxs-lookup"><span data-stu-id="634f3-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="634f3-p101">En la pantalla de configuración principal, puede hacer clic en **Actualizar** para actualizar y volver a llenar la lista de directivas. Se proporciona un cuadro de búsqueda para delimitar la lista de directivas mostradas. Conforme escriba el nombre que está buscando, la lista de directivas se filtra automáticamente.</span><span class="sxs-lookup"><span data-stu-id="634f3-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="634f3-108">Las opciones de configuración de directiva que se aplican en un nivel de directiva pueden sobrescribir la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="634f3-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="634f3-109">La prioridad de la directiva es: la directiva de usuario (más influencia) invalida una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="634f3-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="634f3-110">Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="634f3-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="634f3-111">Hay dos selecciones disponibles para la creación y edición de directivas:</span><span class="sxs-lookup"><span data-stu-id="634f3-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="634f3-p103">**Nueva**: haga clic para crear una nueva directiva. Debe proporcionar un sitio para que se aplique la directiva. Después, configure los ajustes para la notificación de inserciones. Para **Configuración de notificación de inserciones**, solo puede crear directivas para sitios que ya haya creado.</span><span class="sxs-lookup"><span data-stu-id="634f3-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="634f3-p104">**Editar**: seleccione una directiva y haga clic en Editar para seleccionar una acción del menú desplegable. Solo puede editar sitios que ya haya creado o editar la directiva global:</span><span class="sxs-lookup"><span data-stu-id="634f3-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="634f3-p105">**Mostrar detalles…**: muestra información sobre la directiva seleccionada actualmente. Podrá realizar cambios en la directiva existente.</span><span class="sxs-lookup"><span data-stu-id="634f3-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="634f3-120">**Seleccionar todo**: si tiene un número de directivas y necesita seleccionarlas todas, haga clic en Seleccionar todo.</span><span class="sxs-lookup"><span data-stu-id="634f3-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="634f3-p106">**Eliminar**: quitará la directiva seleccionada. Al usar **Seleccionar todo** y **Eliminar**, se eliminarán todas las directivas.</span><span class="sxs-lookup"><span data-stu-id="634f3-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="634f3-p107">No es posible eliminar la directiva **Global** predeterminada. Si intenta eliminarla, se le notificará que la directiva Global ha vuelto a los valores predeterminados (es decir, se eliminarán todos los ajustes), pero la directiva no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="634f3-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="634f3-125">La creación de una directiva nueva o la edición de una directiva existente están asociadas con dos acciones:</span><span class="sxs-lookup"><span data-stu-id="634f3-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="634f3-126">**Commit** La acción de confirmación crea o actualiza la directiva y guarda los cambios</span><span class="sxs-lookup"><span data-stu-id="634f3-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="634f3-127">**Cancelar** La acción cancelar descarta los cambios realizados desde la última acción de confirmación.</span><span class="sxs-lookup"><span data-stu-id="634f3-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="634f3-128">Si cancela, se perderán los cambios realizados.</span><span class="sxs-lookup"><span data-stu-id="634f3-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="634f3-p109">Hay dos opciones posibles para **Configuración de notificaciones de inserción**. Los valores se asocian con los servicios de notificación de inserciones de Microsoft y Apple. Puede habilitar la notificación de inserciones para cualquier servicio activando la casilla que hay junto al nombre del servicio. Puede desactivar la casilla seleccionándola para desmarcarla. Una vez que haya hecho las selecciones, confirme o cancele. Al hacer clic en Confirmar, se guardarán todos los cambios en la directiva.</span><span class="sxs-lookup"><span data-stu-id="634f3-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

