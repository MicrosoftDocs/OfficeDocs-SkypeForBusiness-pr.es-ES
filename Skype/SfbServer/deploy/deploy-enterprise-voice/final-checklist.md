---
title: Lista de comprobación final de implementación de control de admisión de llamadas de Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de comprobación final para la implementación de Control de admisión de llamadas (CAC) en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: e5791aa6f3b32e423f36021314bec930fa7f74e5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025677"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implementación de control de admisión de llamadas: lista de comprobación de final de Skype para Business Server
 
Lista de comprobación final para la implementación de Control de admisión de llamadas (CAC) en Skype para Business Server Enterprise Voice. 
  
Use la siguiente lista de comprobación para comprobar si ha completado todas las tareas de configuración necesarias para implementar el Servicio de control de admisión de llamadas (CAC).
  
- Si se implementan uno o más servidores perimetrales, cada dirección IP de interfaz externa debe agregarse a la lista de subred en las opciones de configuración de red, con una máscara de bits de 32. También tiene que asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    
    > [!NOTE]
    > Los servidores perimetrales no son necesarios para implementar CAC. 
  
- Asegúrese de que esté habilitado el CAC, como especificado en [Habilitar control de admisión de llamadas en Skype para Business Server](enable-call-admission-control.md).
    
- Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Esto puede realizarse mediante el generador de topología. Si se genera una advertencia cuando se publica, *de lo contrario* omitirlo.
    
- Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es esencial que cada subred estén asociadas a un sitio de red, como se explica en [Deploy regiones de red, sitios y las subredes de Skype para la empresa](deploy-network.md).
    
- Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.
    

