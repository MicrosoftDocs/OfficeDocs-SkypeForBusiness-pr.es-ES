---
title: Expansor de configuración de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: La opción Resistencia brinda alta disponibilidad al grupo de registrador. Al proporcionar un registrador de reserva en caso de error en el registrador principal, el de reserva puede ocuparse del registrador erróneo para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el registrador principal, los usuarios pueden llegar a tener un uso restringido de las funciones.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217161"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="b5455-105">Expansor de configuración de registrador</span><span class="sxs-lookup"><span data-stu-id="b5455-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="b5455-p102">La opción Resistencia brinda alta disponibilidad al grupo de registrador. Al proporcionar un registrador de reserva en caso de error en el registrador principal, el de reserva puede ocuparse del registrador erróneo para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el registrador principal, los usuarios pueden llegar a tener un uso restringido de las funciones.</span><span class="sxs-lookup"><span data-stu-id="b5455-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="b5455-109">En la sección **Resistencia** del cuadro de diálogo **Editar propiedades**  de la aplicación o el servidor de sucursal con funciones de supervivencia, puede cambiar las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5455-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="b5455-110">**Servicio de usuario asociado y grupo de registrador de reserva** En la lista desplegable, seleccione el grupo de servidores front-end Enterprise Edition o el servidor front-end Standard Edition que va a actuar como registrador de reserva de la aplicación de sucursal con funciones de supervivencia o del servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="b5455-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="b5455-111">**Habilitar la conmutación por error y la conmutación por recuperación** Seleccione esta opción para permitir la detección automática de un registrador erróneo y la determinación automática de que el registrador principal vuelve a estar preparado para reanudar el proceso de registrador.</span><span class="sxs-lookup"><span data-stu-id="b5455-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="b5455-112">**Intervalo de detección de errores (s)** Escriba el número de segundos que deben transcurrir antes de que se determine que el registrador principal ha generado un error.</span><span class="sxs-lookup"><span data-stu-id="b5455-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="b5455-113">El valor predeterminado es 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="b5455-113">The default value is 120 seconds.</span></span> <span data-ttu-id="b5455-114">Este campo es obligatorio si se selecciona **Habilitar conmutación por error y conmutación por recuperación**.</span><span class="sxs-lookup"><span data-stu-id="b5455-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="b5455-115">**Intervalo de detección de reserva (s)** Escriba el número de segundos que deben transcurrir antes de que se determine que se realiza una copia de seguridad del registrador principal.</span><span class="sxs-lookup"><span data-stu-id="b5455-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="b5455-116">El valor predeterminado es 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="b5455-116">The default value is 240 seconds.</span></span> <span data-ttu-id="b5455-117">Este campo es obligatorio si se selecciona **Habilitar conmutación por error y conmutación por recuperación**.</span><span class="sxs-lookup"><span data-stu-id="b5455-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b5455-p105">Al definir el intervalo de detección de errores y el de detección de reserva, procure no especificar un intervalo que active la conmutación por error y la reserva si durante un periodo de tiempo breve el registrador no responde. Es posible que el registrador principal no responda durante periodos breves, según la carga de los servidores o el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b5455-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

