---
title: Expansor de configuración SBA de registrador
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Editar la configuración de resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: cdc367d1f010749e72ea2144e757d673bd41ba4a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="881f8-103">Expansor de configuración SBA de registrador</span><span class="sxs-lookup"><span data-stu-id="881f8-103">Registrar SBA Settings Expander</span></span>
 
<span data-ttu-id="881f8-104">Editar la configuración de **resistencia** y configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="881f8-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="881f8-105">Seleccione **servicio de usuario asociado y grupo de registrador de copia de seguridad** de la lista.</span><span class="sxs-lookup"><span data-stu-id="881f8-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="881f8-106">De forma opcional, active la casilla de verificación **conmutación automática por error y conmutación por recuperación de Voice** .</span><span class="sxs-lookup"><span data-stu-id="881f8-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="881f8-107">Configurar el **intervalo de detección de error de voz (s)** y el **intervalo de la conmutación por recuperación de Voice (seg.)**.</span><span class="sxs-lookup"><span data-stu-id="881f8-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="881f8-108">De forma predeterminada, los intervalos son 120 para la detección de error de voz y 240 segundos para la conmutación por recuperación de Voice.</span><span class="sxs-lookup"><span data-stu-id="881f8-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="881f8-109">El número de segundos que se definen para los intervalos de conmutación por error y conmutación por recuperación se debería probar detenidamente para asegurarse de que la resistencia funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="881f8-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="881f8-110">Si se establece el intervalo en baja (es decir, menos de 120 segundos) o la conmutación por error y la conmutación por recuperación establecer demasiado estrechamente pueden ocasionar que la conmutación por error real y la conmutación por recuperación no funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="881f8-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
 <span data-ttu-id="881f8-111">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="881f8-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="881f8-112">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="881f8-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="881f8-113">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="881f8-113">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="881f8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="881f8-114">See also</span></span>

#### 

[<span data-ttu-id="881f8-115">Planeación de resistencia de Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="881f8-115">Planning for Enterprise Voice Resiliency</span></span>](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

