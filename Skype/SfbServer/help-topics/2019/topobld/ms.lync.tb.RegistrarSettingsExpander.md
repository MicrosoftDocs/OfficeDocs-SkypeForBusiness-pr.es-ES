---
title: Expansor de configuración de registrador
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
description: Resistencia proporciona una alta disponibilidad y recuperación ante desastres para el grupo de registrador. Al proporcionar un registrador de reserva en caso de que el registrador principal, la copia de seguridad puede adoptar el registrador para el registrador con errores, lo que permite a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de lo que han producido un error de sistemas con el registrador principal.
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="registrar-settings-expander"></a>Expansor de configuración de registrador
 
Resistencia proporciona una alta disponibilidad y recuperación ante desastres para el grupo de registrador. Al proporcionar un registrador de reserva en caso de que el registrador principal, la copia de seguridad puede adoptar el registrador para el registrador con errores, lo que permite a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar potencialmente funcionalidad reducida, dependiendo de lo que han producido un error de sistemas con el registrador principal.
  
En la sección **resistencia** del cuadro de diálogo **Editar propiedades** para su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, puede cambiar la configuración siguiente:
  
- **Servicio de usuario asociado y grupo de registrador de copia de seguridad** En la lista desplegable, seleccione el grupo de servidores Front-End de Enterprise Edition o Standard Edition servidor Front-End que va a actuar como el registrador de reserva para la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia.
    
- **Habilitar la conmutación por error y conmutación por recuperación** Seleccione esta opción para permitir la detección automática de un error de registrador y de la determinación automática que el registrador principal es la copia de seguridad y listo para reanudar el proceso de registrador.
    
- **Intervalo de detección de errores (seg.)** Escriba el número de segundos que debe transcurrir antes de que se ha determinado que registrador ha fallado la principal. El valor predeterminado es 120 segundos. Este campo es obligatorio si selecciona **Habilitar la conmutación por error y conmutación por recuperación**.
    
- **Intervalo de detección de reserva (seg.)** Escriba el número de segundos que debe transcurrir antes de que se determina que se copia el registrador principal. El valor predeterminado es 240 segundos. Este campo es obligatorio si selecciona **Habilitar la conmutación por error y reserva**.
    
> [!IMPORTANT]
> Al definir el intervalo de detección de error y el intervalo de detección de reserva, ser cuidado de no especifique un intervalo que hará que la conmutación por error y de reserva que se produzca si se produce un error en el registrador responder durante un breve período de tiempo. Es posible que el registrador principal no puede responder durante breves períodos de tiempo en función de la carga del grupo de servidores o servidores. 
  

