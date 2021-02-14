---
title: Configuración de creación o edición de notificaciones de inserción del cliente móvil
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: La notificación de inserción y el Centro de intercambio de notificaciones de inserción (PNCH) son dos partes clave de la característica de movilidad. La notificación de inserción es el proceso mediante el cual un mensaje se envía al PNCH. El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que caduca el periodo de espera.
ms.openlocfilehash: 3c72c5b123a906d74cfeb0a1fef5c1e765fe030c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808750"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="83fa8-105">Cliente móvil: Crear o editar configuración de notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="83fa8-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="83fa8-106">La notificación de inserción y el Centro de intercambio de notificaciones de inserción (PNCH) son dos partes clave de la característica de movilidad.</span><span class="sxs-lookup"><span data-stu-id="83fa8-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="83fa8-107">La notificación de inserción es el proceso mediante el cual un mensaje se envía al PNCH.</span><span class="sxs-lookup"><span data-stu-id="83fa8-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="83fa8-108">El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que caduca el periodo de espera.</span><span class="sxs-lookup"><span data-stu-id="83fa8-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="83fa8-109">El periodo de tiempo se define en el centro de enrutamiento de notificaciones de inserción y ni el usuario ni el administrador de su implementación pueden configurarlo.</span><span class="sxs-lookup"><span data-stu-id="83fa8-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="83fa8-110">Para habilitar las notificaciones de inserción, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83fa8-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="83fa8-111">**Ámbito:** Tenga en cuenta el ámbito de esta directiva.</span><span class="sxs-lookup"><span data-stu-id="83fa8-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="83fa8-112">Puede ser **Global**, que se aplica a todos los usuarios de esta implementación, o **Sitio**, que solo son usuarios asignados a servidores locales en el sitio especificado.</span><span class="sxs-lookup"><span data-stu-id="83fa8-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="83fa8-113">Las opciones de configuración de directiva que se aplican en un nivel de directiva pueden sobrescribir la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="83fa8-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="83fa8-114">La prioridad de la directiva es: la directiva de usuario (más influencia) invalida una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="83fa8-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="83fa8-115">Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="83fa8-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="83fa8-116">Seleccione qué servicios de notificación de inserción desea habilitar activando la casilla de:</span><span class="sxs-lookup"><span data-stu-id="83fa8-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="83fa8-117">**Habilitar la notificación de inserción de Microsoft** habilitará la notificación de inserción en el PNCH basado en la nube para Windows Phone con la aplicación skype empresarial</span><span class="sxs-lookup"><span data-stu-id="83fa8-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="83fa8-118">**Habilitar la** notificación de inserción de Apple habilitará la notificación de inserción al PNCH de Apple para dispositivos que ejecutan iOS de Apple (por ejemplo, iPhone, iPad) y usan la aplicación skype empresarial</span><span class="sxs-lookup"><span data-stu-id="83fa8-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="83fa8-p105">Una vez editada la directiva, haga clic en **Confirmar** para guardar los cambios. Si necesita eliminar los cambios realizados, seleccione **Cancelar**. No se guardará ningún cambio en la directiva.</span><span class="sxs-lookup"><span data-stu-id="83fa8-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

