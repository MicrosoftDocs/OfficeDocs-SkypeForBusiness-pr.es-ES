---
title: Lista de comprobación final de implementación del control de admisión de llamadas Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de comprobación final para implementar el Control de admisión de llamadas (CAC) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 11bf5a69b273f1311399090cc893bee1f4732443
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759082"
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
    

