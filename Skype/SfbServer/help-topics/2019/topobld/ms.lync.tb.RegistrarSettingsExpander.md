---
title: Expansor de configuración de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La resistencia proporciona una alta disponibilidad y una recuperación ante desastres para el grupo de servidores de registro. Al proporcionar un registrador de copias de seguridad en caso de que se produzca un error en el registrador principal, el registrador de la copia de seguridad puede tomar el control del registrador incorrecto, lo que permite a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar la funcionalidad reducida en función de los sistemas que hayan fallado con el registrador principal.
ms.openlocfilehash: cc025bdd09026ac3c3b15d2408d0c99b3494a04f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688043"
---
# <a name="registrar-settings-expander"></a>Expansor de configuración de registrador
 
La resistencia proporciona una alta disponibilidad y una recuperación ante desastres para el grupo de servidores de registro. Al proporcionar un registrador de copias de seguridad en caso de que se produzca un error en el registrador principal, el registrador de la copia de seguridad puede tomar el control del registrador incorrecto, lo que permite a los usuarios iniciar sesión y comunicarse. Los usuarios pueden experimentar la funcionalidad reducida en función de los sistemas que hayan fallado con el registrador principal.
  
En la sección **resistencia** del cuadro de diálogo **Editar propiedades** del equipo de sucursal o servidor de sucursal supervivientes que se pueda modificar, haga lo siguiente:
  
- **Servicio de usuario asociado y grupo de registro de la copia de seguridad** En la lista desplegable, seleccione el grupo de servidores front-end de Enterprise Edition o el servidor front-end Standard Edition que actuará como registrador de copias de seguridad de la aplicación de sucursales que es modificable o el servidor de sucursal con la supervivencia.
    
- **Habilitar la conmutación por error y la conmutación por recuperación** Seleccione esta opción para permitir la detección automática de una entidad de registro fallida y la determinación automática de que el registrador principal está en la copia de seguridad y listo para reanudar el proceso de registro.
    
- **Intervalo de detección de errores (s)** Escriba el número de segundos que deben transcurrir antes de determinar que el registrador principal ha fallado. El valor predeterminado es 120 segundos. Este campo es obligatorio si selecciona **Habilitar conmutación por error y conmutación por recuperación**.
    
- **Intervalo de detección de reserva (s)** Escriba el número de segundos que deben transcurrir antes de determinar que se hace una copia de seguridad del registrador principal. El valor predeterminado es 240 segundos. Este campo es obligatorio si selecciona **Habilitar conmutación por error y retrasar**.
    
> [!IMPORTANT]
> Cuando defina el intervalo de detección de errores y el intervalo de detección de reserva, tenga cuidado de no introducir un intervalo que hará que la conmutación por error y la reserva se produzcan si el registrador no responde durante un breve período de tiempo. Es posible que el registrador principal no responda por breves períodos de tiempo en función de la carga del grupo de servidores o los servidores. 
  

