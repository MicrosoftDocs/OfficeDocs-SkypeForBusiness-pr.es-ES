---
title: Registrar configuración Expander para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Modificar las opciones de resiliencia y configurar las siguientes propiedades:'
ms.openlocfilehash: 88a2d75ff6f0225328a0f27743e0129950a5ca91
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Registrar configuración Expander para Lync Server 2010
 
Modificar las opciones de **resiliencia** y configurar las siguientes propiedades:
  
- Seleccione **grupo de registrador auxiliar asociada** de la lista.
    
    Opcionalmente, active la casilla de verificación **automático failover y failback para voz** .
    
    Configurar el **intervalo de detección del error de voz (s)** y el **intervalo de recuperación tras error de voz (s)**. De forma predeterminada, los intervalos son 120 segundos para la detección de fallos de voz y 240 segundos para la conmutación por recuperación de voz.
    
    > [!CAUTION]
    > El número de segundos que defina para los intervalos de failover y failback debe probarse cuidadosamente para asegurarse de que la resistencia funciona como se esperaba. Establecer un intervalo bajo (es decir, menos de 120 segundos) o la conmutación por error y establecer demasiado estrechamente podrán provocar la conmutación no funciona según lo previsto y real. 
  
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  

