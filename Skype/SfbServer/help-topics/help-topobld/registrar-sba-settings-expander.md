---
title: Registrar SBA configuración Expander
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
description: 'Modificar las opciones de resiliencia y configurar las siguientes propiedades:'
ms.openlocfilehash: cdc367d1f010749e72ea2144e757d673bd41ba4a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="1cf25-103">Registrar SBA configuración Expander</span><span class="sxs-lookup"><span data-stu-id="1cf25-103">Registrar SBA Settings Expander</span></span>
 
<span data-ttu-id="1cf25-104">Modificar las opciones de **resiliencia** y configurar las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1cf25-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="1cf25-105">Seleccione **servicio de usuario asociados y grupo de registrador auxiliar** de la lista.</span><span class="sxs-lookup"><span data-stu-id="1cf25-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="1cf25-106">Opcionalmente, active la casilla de verificación **automático failover y failback para voz** .</span><span class="sxs-lookup"><span data-stu-id="1cf25-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="1cf25-107">Configurar el **intervalo de detección del error de voz (s)** y el **intervalo de recuperación tras error de voz (s)**.</span><span class="sxs-lookup"><span data-stu-id="1cf25-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="1cf25-108">De forma predeterminada, los intervalos son 120 segundos para la detección de fallos de voz y 240 segundos para la conmutación por recuperación de voz.</span><span class="sxs-lookup"><span data-stu-id="1cf25-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="1cf25-109">El número de segundos que defina para los intervalos de failover y failback debe probarse cuidadosamente para asegurarse de que la resistencia funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="1cf25-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="1cf25-110">Establecer un intervalo bajo (es decir, menos de 120 segundos) o la conmutación por error y establecer demasiado estrechamente podrán provocar la conmutación no funciona según lo previsto y real.</span><span class="sxs-lookup"><span data-stu-id="1cf25-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
 <span data-ttu-id="1cf25-111">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1cf25-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="1cf25-112">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1cf25-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="1cf25-113">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="1cf25-113">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1cf25-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cf25-114">See also</span></span>

#### 

[<span data-ttu-id="1cf25-115">Planeación para Telefonía IP empresarial resiliencia</span><span class="sxs-lookup"><span data-stu-id="1cf25-115">Planning for Enterprise Voice Resiliency</span></span>](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

