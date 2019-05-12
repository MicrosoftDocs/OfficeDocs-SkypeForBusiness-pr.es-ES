---
title: Expansor de configuración de registrador de Lync Server para 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Editar la configuración de resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: d02462b03b7255860695e373af276a69d92956e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910252"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="2bf37-103">Expansor de configuración de registrador de Lync Server para 2010</span><span class="sxs-lookup"><span data-stu-id="2bf37-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="2bf37-104">Editar la configuración de **resistencia** y configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2bf37-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="2bf37-105">Seleccione **grupo de registrador de copia de seguridad asociado** en la lista.</span><span class="sxs-lookup"><span data-stu-id="2bf37-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="2bf37-106">De forma opcional, active la casilla de verificación **conmutación automática por error y conmutación por recuperación de Voice** .</span><span class="sxs-lookup"><span data-stu-id="2bf37-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="2bf37-107">Configurar el **intervalo de detección de error de voz (s)** y el **intervalo de la conmutación por recuperación de Voice (seg.)**.</span><span class="sxs-lookup"><span data-stu-id="2bf37-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="2bf37-108">De forma predeterminada, los intervalos son 120 para la detección de error de voz y 240 segundos para la conmutación por recuperación de Voice.</span><span class="sxs-lookup"><span data-stu-id="2bf37-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="2bf37-109">El número de segundos que se definen para los intervalos de conmutación por error y conmutación por recuperación se debería probar detenidamente para asegurarse de que la resistencia funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="2bf37-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="2bf37-110">Si se establece el intervalo en baja (es decir, menos de 120 segundos) o la conmutación por error y la conmutación por recuperación establecer demasiado estrechamente pueden ocasionar que la conmutación por error real y la conmutación por recuperación no funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="2bf37-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="2bf37-111">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2bf37-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2bf37-112">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2bf37-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2bf37-113">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="2bf37-113">**Help** Displays this help screen.</span></span>
  

