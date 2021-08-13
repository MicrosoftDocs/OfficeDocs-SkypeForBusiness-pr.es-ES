---
title: Lista de comprobación final de implementación del control de admisión de llamadas Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de comprobación final para implementar el Control de admisión de llamadas (CAC) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 89893e846d37a2a10cbf33de53b8426a0b9d3d642846455e1415991903b0f3e3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338738"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implementación del control de admisión de llamadas: lista de comprobación final Skype Empresarial Server
 
Lista de comprobación final para implementar el Control de admisión de llamadas (CAC) en Skype Empresarial Server Telefonía IP empresarial. 
  
Use la siguiente lista de comprobación para comprobar que ha completado todas las tareas de configuración necesarias para implementar el Control de admisión de llamadas (CAC).
  
- Si implementa uno o más servidores perimetrales, debe agregar cada dirección IP de interfaz externa a la lista de subredes de los parámetros de configuración de red, con una máscara de bits de 32. También debe asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    
    > [!NOTE]
    > Los servidores perimetrales no son necesarios para implementar cac. 
  
- Asegúrese de que cac está habilitado, como se especifica en Habilitar control de admisión de llamadas [en Skype Empresarial Server](enable-call-admission-control.md).
    
- Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Esto se puede hacer a través del Generador de topologías. Si se genera una advertencia al publicar, *no la ignore.*
    
- Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es esencial que todas las subredes se asocie a un sitio de red, como se explica en [Deploy network regions, sites and subnets in Skype Empresarial](deploy-network.md).
    
- Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.
    

