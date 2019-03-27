---
title: Clientes móviles crear o editar la configuración de notificaciones de inserción
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: Las notificaciones de inserción y el centro de enrutamiento de notificaciones de inserción (PNCH) son dos partes esenciales de la característica de movilidad. La notificación de inserción es el proceso por el cual un mensaje se envía al PNCH. El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que el tiempo de espera se agota.
ms.openlocfilehash: 96c20e19444f275076b18830a89d74dba93df39b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880210"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="94753-105">Cliente móvil: Crear o editar configuración de notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="94753-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="94753-p102">Las notificaciones de inserción y el centro de enrutamiento de notificaciones de inserción (PNCH) son dos partes esenciales de la característica de movilidad. La notificación de inserción es el proceso por el cual un mensaje se envía al PNCH. El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que el tiempo de espera se agota.</span><span class="sxs-lookup"><span data-stu-id="94753-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="94753-109">El período de tiempo se define en el centro de enrutamiento de notificaciones de inserción y ni el usuario ni el administrador de la implementación pueden configurarlo.</span><span class="sxs-lookup"><span data-stu-id="94753-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="94753-110">Haga lo siguiente para habilitar las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="94753-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="94753-p103">**Ámbito:** tenga en cuenta el ámbito de esta directiva. Puede ser **Global** (se aplica a todos los usuarios de la implementación) o **Sitio** (solo para usuarios asignados a servidores hospedados en el sitio especificado).</span><span class="sxs-lookup"><span data-stu-id="94753-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94753-p104">La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="94753-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="94753-116">Seleccione qué servicios de notificación de inserción desea habilitar activando la casilla correspondiente:</span><span class="sxs-lookup"><span data-stu-id="94753-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="94753-117">**Notificación de inserción de habilitar Microsoft** habilitará la notificación de inserción a la de PNCH basada en la nube para Windows Phone con la Skype para la aplicación empresarial</span><span class="sxs-lookup"><span data-stu-id="94753-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="94753-118">**Notificación de inserción de Apple habilitar** habilitará la notificación de inserción para PNCH de Apple para dispositivos que ejecutan iOS de Apple (por ejemplo, iPhone, iPad) y usan el Skype para la aplicación empresarial</span><span class="sxs-lookup"><span data-stu-id="94753-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="94753-p105">Una vez editada la directiva, haga clic en **Confirmar** para guardar los cambios. Si prefiere eliminar los cambios realizados, seleccione **Cancelar**. No se guardará ningún cambio en la directiva.</span><span class="sxs-lookup"><span data-stu-id="94753-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

