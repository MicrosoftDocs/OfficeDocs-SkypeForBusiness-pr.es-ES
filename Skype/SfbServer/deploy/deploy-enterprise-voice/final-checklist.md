---
title: Lista de comprobación final de implementación de control de admisión de llamadas para Skype Empresarial Server
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
description: Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830840"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implementación del control de admisión de llamadas: lista de comprobación final para Skype Empresarial Server
 
Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype Empresarial Server Telefonía IP empresarial. 
  
Use la siguiente lista de comprobación para comprobar que ha completado todas las tareas de configuración necesarias para implementar el Control de admisión de llamadas (CAC).
  
- Si implementa uno o más servidores perimetrales, debe agregar cada dirección IP de interfaz externa a la lista de subredes de los parámetros de configuración de red, con una máscara de bits de 32. También debe asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    
    > [!NOTE]
    > Los servidores perimetrales no son necesarios para implementar el CAC. 
  
- Asegúrese de que el CAC está habilitado, como se especifica en Habilitar el control de admisión de [llamadas en Skype Empresarial Server.](enable-call-admission-control.md)
    
- Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Esto se puede hacer a través del Generador de topologías. Si se genera una advertencia al publicarla,  *no la*  ignore.
    
- Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es esencial que todas las subredes se asocie a un sitio de red, como se explica en Implementar regiones de red, sitios y subredes [en Skype Empresarial.](deploy-network.md)
    
- Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.
    

