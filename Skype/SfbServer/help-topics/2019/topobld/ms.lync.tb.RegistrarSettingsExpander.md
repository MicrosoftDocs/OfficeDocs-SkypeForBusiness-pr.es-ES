---
title: Expansor de configuración de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: Resistencia proporciona una alta disponibilidad y recuperación ante desastres para el grupo de registrador. Al proporcionar un registrador de reserva en caso de que el registrador principal, la copia de seguridad puede adoptar el registrador para el registrador con errores, lo que permite a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de lo que han producido un error de sistemas con el registrador principal.
ms.openlocfilehash: 0902c8490d650208c072ed7d2856738b9bd7f2c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906735"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="664d3-105">Expansor de configuración de registrador</span><span class="sxs-lookup"><span data-stu-id="664d3-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="664d3-106">Resistencia proporciona una alta disponibilidad y recuperación ante desastres para el grupo de registrador.</span><span class="sxs-lookup"><span data-stu-id="664d3-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="664d3-107">Al proporcionar un registrador de reserva en caso de que el registrador principal, la copia de seguridad puede adoptar el registrador para el registrador con errores, lo que permite a los usuarios iniciar sesión y comunicarse.</span><span class="sxs-lookup"><span data-stu-id="664d3-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="664d3-108">Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de lo que han producido un error de sistemas con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="664d3-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="664d3-109">En la sección **resistencia** del cuadro de diálogo **Editar propiedades** para su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, puede cambiar la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="664d3-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="664d3-110">**Servicio de usuario asociado y grupo de registrador de copia de seguridad** En la lista desplegable, seleccione el grupo de servidores Front-End de Enterprise Edition o Standard Edition servidor Front-End que va a actuar como el registrador de reserva para la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="664d3-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="664d3-111">**Habilitar la conmutación por error y conmutación por recuperación** Seleccione esta opción para permitir la detección automática de un error de registrador y de la determinación automática que el registrador principal es la copia de seguridad y listo para reanudar el proceso de registrador.</span><span class="sxs-lookup"><span data-stu-id="664d3-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="664d3-112">**Intervalo de detección de errores (seg.)** Escriba el número de segundos que debe transcurrir antes de que se ha determinado que registrador ha fallado la principal.</span><span class="sxs-lookup"><span data-stu-id="664d3-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="664d3-113">El valor predeterminado es 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="664d3-113">The default value is 120 seconds.</span></span> <span data-ttu-id="664d3-114">Este campo es obligatorio si selecciona **Habilitar la conmutación por error y conmutación por recuperación**.</span><span class="sxs-lookup"><span data-stu-id="664d3-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="664d3-115">**Intervalo de detección de reserva (seg.)** Escriba el número de segundos que debe transcurrir antes de que se determina que se copia el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="664d3-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="664d3-116">El valor predeterminado es 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="664d3-116">The default value is 240 seconds.</span></span> <span data-ttu-id="664d3-117">Este campo es obligatorio si selecciona **Habilitar la conmutación por error y reserva**.</span><span class="sxs-lookup"><span data-stu-id="664d3-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="664d3-118">Al definir el intervalo de detección de error y el intervalo de detección de reserva, ser cuidado de no especifique un intervalo que hará que la conmutación por error y de reserva que se produzca si se produce un error en el registrador responder durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="664d3-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="664d3-119">Es posible que el registrador principal no puede responder durante breves períodos de tiempo en función de la carga del grupo de servidores o servidores.</span><span class="sxs-lookup"><span data-stu-id="664d3-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

