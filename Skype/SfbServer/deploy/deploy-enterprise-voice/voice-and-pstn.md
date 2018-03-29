---
title: Configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Resumen: Conozca cómo configurar directivas de voz, registros de uso PSTN y rutas de voz de Skype para Business Server 2015.'
ms.openlocfilehash: d238703b98ebe532b2370456212760620c30ebf4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business-2015"></a><span data-ttu-id="78b51-103">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="78b51-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>
 
<span data-ttu-id="78b51-104">**Resumen:** Obtenga información sobre cómo configurar directivas de voz, registros de uso PSTN y rutas de voz en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="78b51-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="78b51-p101">Las directivas de voz, los registros de uso de RTC y las rutas de voz están totalmente relacionados. Para configurar las directivas de voz, debe seleccionar un grupo de características de llamada y luego asignar a la directiva un grupo de registros de uso de RTC, que especifican los derechos que se otorgarán a los usuarios o grupos a los que se les asigne la directiva de voz. A las rutas de voz también se les asignan registros de uso de RTC, que sirven para asociar las rutas con los usuarios autorizados para usarlas. Es decir, los usuarios solo pueden realizar llamadas que usan rutas para las que tienen registros de uso de RTC coincidentes.</span><span class="sxs-lookup"><span data-stu-id="78b51-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="78b51-109">El flujo de trabajo recomendado para una nueva implementación de Enterprise Voice es comenzar configurando una directiva de voz que incluya los registros de uso de RTC adecuados y, a continuación, asociar las rutas apropiadas para cada registro de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="78b51-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="78b51-110">También puede crear directivas de voz con ámbito de *usuario* y asignarlos a usuarios individuales o grupos.</span><span class="sxs-lookup"><span data-stu-id="78b51-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="78b51-111">Para consultar los pasos detallados que se deben seguir para realizar cada una de estas tareas, consulte los procedimientos que se explican en esta sección.</span><span class="sxs-lookup"><span data-stu-id="78b51-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="78b51-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="78b51-112">In this section</span></span>

- [<span data-ttu-id="78b51-113">Crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="78b51-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="78b51-114">Configurar escape del correo de voz de Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="78b51-114">Configure voice mail escape in Skype for Business 2015</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="78b51-115">Ver los registros de uso PSTN en Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="78b51-115">View PSTN usage records in Skype for Business 2015</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="78b51-116">Crear o modificar una ruta de voz de Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="78b51-116">Create or modify a voice route in Skype for Business 2015</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="78b51-117">Exportar o importar un archivo de configuración de ruta de voz de Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="78b51-117">Export or import a voice route configuration file in Skype for Business 2015</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="78b51-118">Publicar los cambios pendientes a la configuración de enrutamiento de voz de Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="78b51-118">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
    

