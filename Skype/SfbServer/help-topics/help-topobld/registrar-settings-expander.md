---
title: Registrar configuración Expander
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Resistencia proporciona alta disponibilidad y recuperación ante desastres para el grupo de registro. Al proporcionar una copia de seguridad Registrar en caso de que el registrador principal, la copia de seguridad registrador puede asumir el registrador fallido, permitiendo a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de qué sistemas han fracasado con el registrador principal.
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander"></a>Registrar configuración Expander
 
Resistencia proporciona alta disponibilidad y recuperación ante desastres para el grupo de registro. Al proporcionar una copia de seguridad Registrar en caso de que el registrador principal, la copia de seguridad registrador puede asumir el registrador fallido, permitiendo a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de qué sistemas han fracasado con el registrador principal.
  
En la sección de **resistencia** del cuadro de diálogo **Editar propiedades** para su dispositivo de sucursal que sobreviven o un servidor de sucursal que sobreviven, puede cambiar los siguientes valores:
  
- **Servicio de usuario asociados y grupo de registrador auxiliar** En la lista desplegable, seleccione el grupo de servidores Front-End de Enterprise Edition o Standard Edition servidor Front-End que va a actuar como el registrador de la copia de seguridad para el dispositivo de sucursal que sobreviven o el servidor de sucursal que sobreviven.
    
- **Habilitar la conmutación por error y conmutación por recuperación** Seleccione esta opción para permitir la detección automática de un error al Registrar y la determinación automática que el registrador principal es la copia de seguridad y está listo para reanudar el proceso de Registrar.
    
- **Intervalo de detección del error (seg.)** Escriba el número de segundos que deben transcurrir antes de que se determine que el principal registrador ha fallado. El valor predeterminado es de 120 segundos. Este campo es obligatorio si se selecciona **Permitir Failover y Failback**.
    
- **Intervalo de detección reserva (s)** Escriba el número de segundos que deben transcurrir antes de que se determine que el registrador principal se copia. El valor predeterminado es 240 segundos. Este campo es obligatorio si se selecciona **Permitir Failover y Fallback**.
    
> [!IMPORTANT]
> Cuando defina el intervalo de detección del error y el intervalo de detección reserva, ser cuidado de no introducir un intervalo que hará que la conmutación por error y reserva que se produzca si el registrador no responde durante un breve período de tiempo. Es posible que el registrador principal puede no responder durante cortos períodos de tiempo según la carga de servidores o el grupo. 
  

