---
title: Expansor de configuración de registrador de Lync Server para 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Edite la configuración de resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: adc3d3f0be42d542583cf269a7acf83d98df8dd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819342"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="5c9d7-103">Expansor de configuración de registrador de Lync Server para 2010</span><span class="sxs-lookup"><span data-stu-id="5c9d7-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="5c9d7-104">Edite la configuración de **resistencia** y configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="5c9d7-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="5c9d7-105">Seleccione el grupo de registro de la **copia de seguridad asociado** de la lista.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="5c9d7-106">De manera opcional, active la casilla **conmutación automática por error para voz** .</span><span class="sxs-lookup"><span data-stu-id="5c9d7-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="5c9d7-107">Configure el **intervalo de detección de errores de voz (s)** y el intervalo de conmutación por recuperación de **voz (s)**.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="5c9d7-108">De forma predeterminada, los intervalos son de 120 segundos para la detección de errores de voz y de 240 segundos para la conmutación por voz.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5c9d7-109">El número de segundos que defina para los intervalos de conmutación por error y failback debe probarse detenidamente para asegurarse de que la resistencia funciona de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="5c9d7-110">Configurar el intervalo en Low (es decir, menos de 120 segundos) o el conjunto de conmutación por error y conmutación por recuperación demasiado estrecho puede dar lugar a que la conmutación por error y la conmutación de conmutación reales no funcionen de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="5c9d7-111">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="5c9d7-112">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="5c9d7-113">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="5c9d7-113">**Help** Displays this help screen.</span></span>
  

