---
title: Agregar RTC de aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir la puerta de enlace de red de telefonía pública conmutada (RTC) para un equipo de sucursales con la mayoría de las sucursales, especifique lo siguiente:'
ms.openlocfilehash: 133f109c1d076432cd628bccde9e3c49518500c2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689735"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Agregar RTC de aplicación de sucursal con funciones de supervivencia
 
Para definir la puerta de enlace de red de telefonía pública conmutada (RTC) para un equipo de sucursales con la mayoría de las sucursales, especifique lo siguiente: 
  
- Un nombre de dominio completo (FQDN) o una dirección IP para la puerta de enlace del mismo nivel a la que se asocia la aplicación de la sucursal o el servidor de sucursal con la supervivencia para enrutar llamadas RTC entrantes y salientes.
    
    > [!IMPORTANT]
    > Si está definiendo un dispositivo de sucursal que funciona bien, esta es la puerta de enlace a la que se conectará el servidor de mediación de la aplicación de la sucursal con la que se puede obtener conectividad RTC. 
  
- El puerto de escucha que debe usarse para los mensajes del Protocolo de inicio de sesión (SIP). De forma predeterminada, los puertos son 5066 para el protocolo de control de transmisión (TCP) y 5067 para seguridad de la capa de transporte (TLS) en una puerta de enlace, central de conmutación (PBX) o controlador del borde de sesión (SBC). En una aplicación de sucursal con funciones de supervivencia de una sucursal, los puertos predeterminados son 5081 para TCP y 5082 para Seguridad de la capa de transporte (TLS).
    
- Por motivos de seguridad, se recomienda encarecidamente usar TLS. Si está definiendo un dispositivo de sucursal que es reviviente, consulte la documentación del proveedor de su equipo de sucursales que sea superviviente para verificar que su equipo de sucursales con la supervivencia es compatible con el protocolo TLS.
    
    > [!IMPORTANT]
    > Por motivos de seguridad, se recomienda encarecidamente implementar una puerta de enlace que pueda usar TLS. 
  
> [!NOTE]
> Si desea agregar una puerta de enlace de RTC, puede configurarla posteriormente; sin embargo, no estará plenamente operativa hasta que se haya definido y configurado la puerta de enlace de red telefónica conmutada (RTC). 
  

