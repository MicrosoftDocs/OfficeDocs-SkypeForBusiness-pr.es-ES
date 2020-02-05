---
title: Lista de comprobación de la implementación de control de admisión de llamada final para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 5d5e4f6f40143bfec2a215e6bc9a54817d53da1b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767233"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implementación de control de admisión de llamadas: lista de comprobación final para Skype empresarial Server
 
Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype empresarial Server Enterprise Voice. 
  
Use la siguiente lista de comprobación para comprobar si ha completado todas las tareas de configuración necesarias para implementar el Servicio de control de admisión de llamadas (CAC).
  
- Si se implementan uno o varios servidores perimetrales, cada dirección IP de la interfaz externa debe agregarse a la lista de subred en la configuración de red, con una máscara de bits de 32. También tiene que asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    
    > [!NOTE]
    > No es necesario que los servidores perimetrales implementen CAC. 
  
- Asegúrese de que CAC está habilitado, como se especifica en [Habilitar control de admisión de llamadas en Skype empresarial Server](enable-call-admission-control.md).
    
- Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Esto se puede hacer a través del generador de topología. Si se genera una advertencia al publicarla, *no* la pase por alto.
    
- Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es esencial que cada subred esté asociada a un sitio de red, como se explica en [implementar regiones, sitios y subredes de red en Skype empresarial](deploy-network.md).
    
- Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.
    

