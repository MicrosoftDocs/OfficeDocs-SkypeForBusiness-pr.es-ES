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
ms.openlocfilehash: 9c397f3d08bd99b477f5c0568aa62938e59cdf6416e5c5ccfbe5771465c86012
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281003"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expansor de configuración de registrador de Lync Server para 2010
 
Modifique la configuración de la **Resistencia** y configure las siguientes propiedades:
  
- Seleccione **Servicio de usuario asociado y grupo de registrador de reserva** en la lista.
    
    Opcionalmente, puede activar la casilla **Conmutación por error y conmutación por recuperación automática para voz**.
    
    Configure el **Intervalo de detección de errores de voz (s)** y el **Intervalo de conmutación por recuperación de voz (s)**. De forma predeterminada, los intervalos son de 120 segundos para la detección de errores de voz y de 240 segundos para la conmutación por recuperación de voz.
    
    > [!CAUTION]
    > El número de segundos que se definen para los intervalos de conmutación por error y de conmutación por recuperación deben probarse detenidamente para garantizar que la resistencia funciona según lo previsto. Si se define el intervalo como bajo (es decir, inferior a 120 segundos) o la conmutación por error y la conmutación por recuperación se definen demasiado próximas, puede resultar en que la conmutación por error y la conmutación por recuperación reales no funcionen correctamente. 
  
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

