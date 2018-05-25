---
title: Agregar RTC de aplicación de sucursal con funciones de supervivencia
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Para definir la puerta de enlace de telefónica conmutada (RTC) para una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, especifique lo siguiente:'
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a>Agregar RTC de aplicación de sucursal con funciones de supervivencia
 
Para definir la puerta de enlace de telefónica conmutada (RTC) para una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, especifique lo siguiente: 
  
- Un nombre de dominio completo (FQDN) o la dirección IP para el mismo nivel de puerta de enlace que la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia está asociado con para el enrutamiento de entrada y salida llamadas RTC.
    
    > [!IMPORTANT]
    > Si está definiendo una aplicación de sucursal con funciones de supervivencia, esta es la puerta de enlace al que se conectará el servidor de mediación dentro de la aplicación de sucursal con funciones de supervivencia para la conectividad de RTC. 
  
- El puerto de escucha que debe usarse para los mensajes del Protocolo de inicio de sesión (SIP). De forma predeterminada, los puertos son 5066 para el protocolo de control de transmisión (TCP) y 5067 para seguridad de la capa de transporte (TLS) en una puerta de enlace, central de conmutación (PBX) o controlador del borde de sesión (SBC). En una aplicación de sucursal con funciones de supervivencia de una sucursal, los puertos predeterminados son 5081 para TCP y 5082 para Seguridad de la capa de transporte (TLS).
    
- Por motivos de seguridad, se recomienda encarecidamente usar TLS. Si está definiendo una aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor de aplicación de sucursal con funciones de supervivencia para comprobar que la aplicación de sucursal con funciones de supervivencia admite el protocolo TLS.
    
    > [!IMPORTANT]
    > Por motivos de seguridad, se recomienda encarecidamente implementar una puerta de enlace que pueda usar TLS. 
  
> [!NOTE]
> Si desea agregar una puerta de enlace de RTC, puede configurarla posteriormente; sin embargo, no estará plenamente operativa hasta que se haya definido y configurado la puerta de enlace de red telefónica conmutada (RTC). 
  

