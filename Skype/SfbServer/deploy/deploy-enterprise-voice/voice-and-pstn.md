---
title: Configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Resumen: obtenga información sobre cómo configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype Empresarial Server.'
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830452"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="28641-103">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="28641-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="28641-104">**Resumen:** Obtenga información sobre cómo configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="28641-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="28641-p101">Las directivas de voz, los registros de uso de RTC y las rutas de voz son aspecto totalmente relacionados. Para configurar las directivas de voz debe seleccionar un grupo de características de llamada y luego asignar a la directiva un grupo de registros de uso de RTC, que especifican los derechos que se otorgarán a los usuarios o grupos a los que se les asigne la directiva de voz. A las rutas de voz también se les asignan registros de uso de RTC, que sirven para asociar las rutas con los usuarios autorizados para usarlas. Es decir, los usuarios solo pueden realizar llamadas que usan rutas para las que tienen registros de uso de RTC coincidentes.</span><span class="sxs-lookup"><span data-stu-id="28641-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="28641-109">El flujo de trabajo recomendado para una nueva implementación de Enterprise Voice es comenzar configurando una directiva de voz que incluya los registros de uso de RTC adecuados y, a continuación, asociar las rutas apropiadas para cada registro de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="28641-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="28641-110">También puede crear directivas de voz con ámbito  *de*  usuario y asignarlas a usuarios o grupos individuales.</span><span class="sxs-lookup"><span data-stu-id="28641-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="28641-111">Para consultar los pasos detallados que se deben seguir para realizar cada una de estas tareas, consulte los procedimientos que se explican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="28641-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="28641-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="28641-112">In this section</span></span>

- [<span data-ttu-id="28641-113">Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="28641-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="28641-114">Configurar el escape de correo de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="28641-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="28641-115">Ver registros de uso de RTC en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="28641-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="28641-116">Crear o modificar una ruta de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="28641-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="28641-117">Exportar o importar un archivo de configuración de ruta de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="28641-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="28641-118">Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="28641-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

