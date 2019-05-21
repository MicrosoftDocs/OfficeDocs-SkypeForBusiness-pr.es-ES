---
title: Expansor de configuración de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La resistencia proporciona una alta disponibilidad y una recuperación ante desastres para el grupo de servidores de registro. Al proporcionar un registrador de copias de seguridad en caso de que se produzca un error en el registrador principal, el registrador de la copia de seguridad puede tomar el control del registrador incorrecto, lo que permite a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar la funcionalidad reducida en función de los sistemas que hayan fallado con el registrador principal.
ms.openlocfilehash: 122124140c93afb3ce58b1d9423839f3e21dbcad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277842"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="c1bd1-105">Expansor de configuración de registrador</span><span class="sxs-lookup"><span data-stu-id="c1bd1-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="c1bd1-106">La resistencia proporciona una alta disponibilidad y una recuperación ante desastres para el grupo de servidores de registro.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="c1bd1-107">Al proporcionar un registrador de copias de seguridad en caso de que se produzca un error en el registrador principal, el registrador de la copia de seguridad puede tomar el control del registrador incorrecto, lo que permite a los usuarios iniciar sesión y comunicarse.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="c1bd1-108">Los usuarios pueden experimentar la funcionalidad reducida en función de los sistemas que hayan fallado con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="c1bd1-109">En la sección **resistencia** del cuadro de diálogo **Editar propiedades** del equipo de sucursal o servidor de sucursal supervivientes que se pueda modificar, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1bd1-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="c1bd1-110">**Servicio de usuario asociado y grupo de registro de la copia de seguridad** En la lista desplegable, seleccione el grupo de servidores front-end de Enterprise Edition o el servidor front-end Standard Edition que actuará como registrador de copias de seguridad de la aplicación de sucursales que es modificable o el servidor de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="c1bd1-111">**Habilitar la conmutación por error y la conmutación por recuperación** Seleccione esta opción para permitir la detección automática de una entidad de registro fallida y la determinación automática de que el registrador principal está en la copia de seguridad y listo para reanudar el proceso de registro.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="c1bd1-112">**Intervalo de detección de errores (s)** Escriba el número de segundos que deben transcurrir antes de determinar que el registrador principal ha fallado.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="c1bd1-113">El valor predeterminado es 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-113">The default value is 120 seconds.</span></span> <span data-ttu-id="c1bd1-114">Este campo es obligatorio si selecciona **Habilitar conmutación por error y conmutación por recuperación**.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="c1bd1-115">**Intervalo de detección de reserva (s)** Escriba el número de segundos que deben transcurrir antes de determinar que se hace una copia de seguridad del registrador principal.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="c1bd1-116">El valor predeterminado es 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-116">The default value is 240 seconds.</span></span> <span data-ttu-id="c1bd1-117">Este campo es obligatorio si selecciona **Habilitar conmutación por error y**retrasar.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="c1bd1-118">Cuando defina el intervalo de detección de errores y el intervalo de detección de reserva, tenga cuidado de no introducir un intervalo que hará que la conmutación por error y la reserva se produzcan si el registrador no responde durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="c1bd1-119">Es posible que el registrador principal no responda por breves períodos de tiempo en función de la carga del grupo de servidores o los servidores.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

