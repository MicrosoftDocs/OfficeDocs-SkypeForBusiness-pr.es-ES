---
title: Agregar RTC de aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Para definir la puerta de enlace de la red telefónica conmutada (RTC) de una aplicación de sucursal con funciones de supervivencia en una sucursal, especifique los elementos siguientes:'
ms.openlocfilehash: 65731fe7227f0aaba485ecf27c1493df120379e2ae8224eaf471c2f557e61479
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307221"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Agregar RTC de aplicación de sucursal con funciones de supervivencia
 
Para definir la puerta de enlace de la red telefónica conmutada (RTC) de una aplicación de sucursal con funciones de supervivencia en una sucursal, especifique los elementos siguientes: 
  
- Un nombre de dominio completo o una dirección IP para la puerta de enlace del mismo nivel con el que esté asociado la aplicación o el servidor de sucursal con funciones de supervivencia para llamadas de red telefónica conmutada (RTC) de enrutamiento de entrada y de salida.
    
    > [!IMPORTANT]
    > Si está definiendo una aplicación de sucursal con funciones de supervivencia, esta es la puerta de enlace a la que se conectará el servidor de mediación de dicha aplicación para conectividad de red telefónica conmutada (RTC). 
  
- El puerto de escucha que debe usarse para los mensajes del Protocolo de inicio de sesión (SIP). De forma predeterminada, los puertos son 5066 para el protocolo de control de transmisión (TCP) y 5067 para seguridad de la capa de transporte (TLS) en una puerta de enlace, central de conmutación (PBX) o controlador del borde de sesión (SBC). En una aplicación de sucursal con funciones de supervivencia de una sucursal, los puertos predeterminados son 5081 para TCP y 5082 para Seguridad de la capa de transporte (TLS).
    
- Por motivos de seguridad, se recomienda usar Seguridad de la capa de transporte (TLS). Si está definiendo una aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor para verificar que dicha aplicación admita el protocolo de Seguridad de la capa de transporte (TLS).
    
    > [!IMPORTANT]
    > Por motivos de seguridad, se recomienda encarecidamente implementar una puerta de enlace que pueda usar TLS. 
  
> [!NOTE]
> Si desea agregar una puerta de enlace de RTC, puede configurarla posteriormente; sin embargo, no estará plenamente operativa hasta que se haya definido y configurado la puerta de enlace de red telefónica conmutada (RTC). 
  

