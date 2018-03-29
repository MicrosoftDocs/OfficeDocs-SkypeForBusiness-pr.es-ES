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
description: 'Para definir la puerta de enlace de telefónica pública conmutada (PSTN) de red de un dispositivo de la rama que sobreviven en un sitio de sucursal, especifique lo siguiente:'
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a>Agregar RTC de aplicación de sucursal con funciones de supervivencia
 
Para definir la puerta de enlace de telefónica pública conmutada (PSTN) de red de un dispositivo de la rama que sobreviven en un sitio de sucursal, especifique lo siguiente: 
  
- Un nombre de dominio completo (FQDN) o dirección IP para el interlocutor de puerta de enlace que el dispositivo de sucursal que sobreviven o el servidor de sucursal que sobreviven está asociado para el enrutamiento entrante y saliente se llama PSTN.
    
    > [!IMPORTANT]
    > Si va a definir un dispositivo de la rama que sobreviven, ésta es la puerta de enlace al que se conectará el servidor de mediación ubicado dentro del dispositivo de la rama que sobreviven para conectividad PSTN. 
  
- El puerto de escucha que debe usarse para los mensajes del Protocolo de inicio de sesión (SIP). De forma predeterminada, los puertos son 5066 para el protocolo de control de transmisión (TCP) y 5067 para seguridad de la capa de transporte (TLS) en una puerta de enlace, central de conmutación (PBX) o controlador del borde de sesión (SBC). En una aplicación de sucursal con funciones de supervivencia de una sucursal, los puertos predeterminados son 5081 para TCP y 5082 para Seguridad de la capa de transporte (TLS).
    
- Por motivos de seguridad, se recomienda encarecidamente usar TLS. Si va a definir un dispositivo de la rama que sobreviven, consulte la documentación del proveedor de dispositivo de sucursal que sobreviven para comprobar que el dispositivo de la rama que sobreviven admite el protocolo TLS.
    
    > [!IMPORTANT]
    > Por motivos de seguridad, se recomienda encarecidamente implementar una puerta de enlace que pueda usar TLS. 
  
> [!NOTE]
> Si desea agregar una puerta de enlace de RTC, puede configurarla posteriormente; sin embargo, no estará plenamente operativa hasta que se haya definido y configurado la puerta de enlace de red telefónica conmutada (RTC). 
  

