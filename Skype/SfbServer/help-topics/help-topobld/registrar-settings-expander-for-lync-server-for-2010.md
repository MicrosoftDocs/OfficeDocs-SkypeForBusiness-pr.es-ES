---
title: Expansor de configuración de registrador de Lync Server para 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Modifique la configuración de la Resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: 92df9deeba1287dab4dc7d84b089fa81ca2e51ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818330"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="3ed57-103">Expansor de configuración de registrador de Lync Server para 2010</span><span class="sxs-lookup"><span data-stu-id="3ed57-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="3ed57-104">Modifique la configuración de la **Resistencia** y configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3ed57-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="3ed57-105">Seleccione **Servicio de usuario asociado y grupo de registrador de reserva** en la lista.</span><span class="sxs-lookup"><span data-stu-id="3ed57-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="3ed57-106">Opcionalmente, puede activar la casilla **Conmutación por error y conmutación por recuperación automática para voz**.</span><span class="sxs-lookup"><span data-stu-id="3ed57-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="3ed57-p101">Configure el **Intervalo de detección de errores de voz (s)** y el **Intervalo de conmutación por recuperación de voz (s)**. De forma predeterminada, los intervalos son de 120 segundos para la detección de errores de voz y de 240 segundos para la conmutación por recuperación de voz.</span><span class="sxs-lookup"><span data-stu-id="3ed57-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3ed57-p102">El número de segundos que se definen para los intervalos de conmutación por error y de conmutación por recuperación deben probarse detenidamente para garantizar que la resistencia funciona según lo previsto. Si se define el intervalo como bajo (es decir, inferior a 120 segundos) o la conmutación por error y la conmutación por recuperación se definen demasiado próximas, puede resultar en que la conmutación por error y la conmutación por recuperación reales no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ed57-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="3ed57-111">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3ed57-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="3ed57-112">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3ed57-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="3ed57-113">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="3ed57-113">**Help** Displays this help screen.</span></span>
  

