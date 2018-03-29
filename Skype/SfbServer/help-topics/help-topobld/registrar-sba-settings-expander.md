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
# <a name="registrar-sba-settings-expander"></a>Registrar SBA configuración Expander
 
Modificar las opciones de **resiliencia** y configurar las siguientes propiedades:
  
- Seleccione **servicio de usuario asociados y grupo de registrador auxiliar** de la lista.
    
    Opcionalmente, active la casilla de verificación **automático failover y failback para voz** .
    
    Configurar el **intervalo de detección del error de voz (s)** y el **intervalo de recuperación tras error de voz (s)**. De forma predeterminada, los intervalos son 120 segundos para la detección de fallos de voz y 240 segundos para la conmutación por recuperación de voz.
    
    > [!CAUTION]
    > El número de segundos que defina para los intervalos de failover y failback debe probarse cuidadosamente para asegurarse de que la resistencia funciona como se esperaba. Establecer un intervalo bajo (es decir, menos de 120 segundos) o la conmutación por error y establecer demasiado estrechamente podrán provocar la conmutación no funciona según lo previsto y real. 
  
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  
## <a name="see-also"></a>Vea también

#### 

[Planeación para Telefonía IP empresarial resiliencia](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

