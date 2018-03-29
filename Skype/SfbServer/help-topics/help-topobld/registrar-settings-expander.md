---
title: Registrar configuración Expander
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Resistencia proporciona alta disponibilidad y recuperación ante desastres para el grupo de registro. Al proporcionar una copia de seguridad Registrar en caso de que el registrador principal, la copia de seguridad registrador puede asumir el registrador fallido, permitiendo a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de qué sistemas han fracasado con el registrador principal.
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="a8c93-105">Registrar configuración Expander</span><span class="sxs-lookup"><span data-stu-id="a8c93-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="a8c93-106">Resistencia proporciona alta disponibilidad y recuperación ante desastres para el grupo de registro.</span><span class="sxs-lookup"><span data-stu-id="a8c93-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="a8c93-107">Al proporcionar una copia de seguridad Registrar en caso de que el registrador principal, la copia de seguridad registrador puede asumir el registrador fallido, permitiendo a los usuarios iniciar sesión y comunicarse.</span><span class="sxs-lookup"><span data-stu-id="a8c93-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="a8c93-108">Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de qué sistemas han fracasado con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="a8c93-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="a8c93-109">En la sección de **resistencia** del cuadro de diálogo **Editar propiedades** para su dispositivo de sucursal que sobreviven o un servidor de sucursal que sobreviven, puede cambiar los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8c93-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="a8c93-110">**Servicio de usuario asociados y grupo de registrador auxiliar** En la lista desplegable, seleccione el grupo de servidores Front-End de Enterprise Edition o Standard Edition servidor Front-End que va a actuar como el registrador de la copia de seguridad para el dispositivo de sucursal que sobreviven o el servidor de sucursal que sobreviven.</span><span class="sxs-lookup"><span data-stu-id="a8c93-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="a8c93-111">**Habilitar la conmutación por error y conmutación por recuperación** Seleccione esta opción para permitir la detección automática de un error al Registrar y la determinación automática que el registrador principal es la copia de seguridad y está listo para reanudar el proceso de Registrar.</span><span class="sxs-lookup"><span data-stu-id="a8c93-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="a8c93-112">**Intervalo de detección del error (seg.)** Escriba el número de segundos que deben transcurrir antes de que se determine que el principal registrador ha fallado.</span><span class="sxs-lookup"><span data-stu-id="a8c93-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="a8c93-113">El valor predeterminado es de 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="a8c93-113">The default value is 120 seconds.</span></span> <span data-ttu-id="a8c93-114">Este campo es obligatorio si se selecciona **Permitir Failover y Failback**.</span><span class="sxs-lookup"><span data-stu-id="a8c93-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="a8c93-115">**Intervalo de detección reserva (s)** Escriba el número de segundos que deben transcurrir antes de que se determine que el registrador principal se copia.</span><span class="sxs-lookup"><span data-stu-id="a8c93-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="a8c93-116">El valor predeterminado es 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="a8c93-116">The default value is 240 seconds.</span></span> <span data-ttu-id="a8c93-117">Este campo es obligatorio si se selecciona **Permitir Failover y Fallback**.</span><span class="sxs-lookup"><span data-stu-id="a8c93-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="a8c93-118">Cuando defina el intervalo de detección del error y el intervalo de detección reserva, ser cuidado de no introducir un intervalo que hará que la conmutación por error y reserva que se produzca si el registrador no responde durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a8c93-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="a8c93-119">Es posible que el registrador principal puede no responder durante cortos períodos de tiempo según la carga de servidores o el grupo.</span><span class="sxs-lookup"><span data-stu-id="a8c93-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

