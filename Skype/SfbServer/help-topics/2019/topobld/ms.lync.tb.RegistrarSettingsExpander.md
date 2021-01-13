---
title: Expansor de configuración de registrador
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La opción Resistencia brinda alta disponibilidad al grupo de registrador. Al proporcionar un registrador de reserva en caso de error en el registrador principal, el de reserva puede ocuparse del registrador erróneo para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el registrador principal, los usuarios pueden llegar a tener un uso restringido de las funciones.
ms.openlocfilehash: cb7a5204b3b282c73f9440e61267b723b112b735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822120"
---
# <a name="registrar-settings-expander"></a>Expansor de configuración de registrador
 
La opción Resistencia brinda alta disponibilidad al grupo de registrador. Al proporcionar un registrador de reserva en caso de error en el registrador principal, el de reserva puede ocuparse del registrador erróneo para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el registrador principal, los usuarios pueden llegar a tener un uso restringido de las funciones.
  
En la sección **Resistencia** del cuadro de diálogo **Editar propiedades**  de la aplicación o el servidor de sucursal con funciones de supervivencia, puede cambiar las opciones siguientes:
  
- **Servicio de usuario asociado y grupo de registrador de reserva** En la lista desplegable, seleccione el grupo de servidores front-end Enterprise Edition o el servidor front-end Standard Edition que va a actuar como registrador de reserva para la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.
    
- **Habilitar conmutación por error y conmutación por recuperación** Seleccione esta opción para permitir la detección automática de un registrador con errores y la determinación automática de que el registrador principal está de reserva y listo para reanudar el proceso de registrador.
    
- **Intervalo de detección de errores (seg.)** Escriba el número de segundos que debe transcurrir antes de que se determine que el registrador principal ha fallado. El valor predeterminado es 120 segundos. Este campo es obligatorio si se selecciona **Habilitar conmutación por error y conmutación por recuperación**.
    
- **Intervalo de detección de reserva (seg.)** Escriba el número de segundos que deben transcurrir antes de que se determine que se ha hecho una copia de seguridad del registrador principal. El valor predeterminado es 240 segundos. Este campo es obligatorio si se selecciona **Habilitar conmutación por error y conmutación por recuperación**.
    
> [!IMPORTANT]
> Al definir el intervalo de detección de errores y el de detección de reserva, procure no especificar un intervalo que active la conmutación por error y la reserva si durante un periodo de tiempo breve el registrador no responde. Es posible que el registrador principal no responda durante periodos breves, según la carga de los servidores o el grupo de servidores. 
  

