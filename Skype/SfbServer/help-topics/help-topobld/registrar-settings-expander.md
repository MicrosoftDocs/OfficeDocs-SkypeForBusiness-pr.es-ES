---
title: Expansor de configuración de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: La opción Resistencia brinda alta disponibilidad al grupo de registrador. Al proporcionar un registrador de reserva en caso de error en el registrador principal, el de reserva puede ocuparse del registrador erróneo para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el registrador principal, los usuarios pueden llegar a tener un uso restringido de las funciones.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217161"
---
# <a name="registrar-settings-expander"></a>Expansor de configuración de registrador
 
La opción Resistencia brinda alta disponibilidad al grupo de registrador. Al proporcionar un registrador de reserva en caso de error en el registrador principal, el de reserva puede ocuparse del registrador erróneo para que los usuarios puedan iniciar sesión y comunicarse. Según los sistemas que fallen con el registrador principal, los usuarios pueden llegar a tener un uso restringido de las funciones.
  
En la sección **Resistencia** del cuadro de diálogo **Editar propiedades**  de la aplicación o el servidor de sucursal con funciones de supervivencia, puede cambiar las opciones siguientes:
  
- **Servicio de usuario asociado y grupo de registrador de reserva** En la lista desplegable, seleccione el grupo de servidores front-end Enterprise Edition o el servidor front-end Standard Edition que va a actuar como registrador de reserva de la aplicación de sucursal con funciones de supervivencia o del servidor de sucursal con funciones de supervivencia.
    
- **Habilitar la conmutación por error y la conmutación por recuperación** Seleccione esta opción para permitir la detección automática de un registrador erróneo y la determinación automática de que el registrador principal vuelve a estar preparado para reanudar el proceso de registrador.
    
- **Intervalo de detección de errores (s)** Escriba el número de segundos que deben transcurrir antes de que se determine que el registrador principal ha generado un error. El valor predeterminado es 120 segundos. Este campo es obligatorio si se selecciona **Habilitar conmutación por error y conmutación por recuperación**.
    
- **Intervalo de detección de reserva (s)** Escriba el número de segundos que deben transcurrir antes de que se determine que se realiza una copia de seguridad del registrador principal. El valor predeterminado es 240 segundos. Este campo es obligatorio si se selecciona **Habilitar conmutación por error y conmutación por recuperación**.
    
> [!IMPORTANT]
> Al definir el intervalo de detección de errores y el de detección de reserva, procure no especificar un intervalo que active la conmutación por error y la reserva si durante un periodo de tiempo breve el registrador no responde. Es posible que el registrador principal no responda durante periodos breves, según la carga de los servidores o el grupo de servidores. 
  

