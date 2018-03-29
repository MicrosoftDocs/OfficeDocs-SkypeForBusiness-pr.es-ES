---
title: Llame a la lista de comprobación de final de implementación de control de admisión de Skype para Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de comprobación final para la implementación de Control de admisión llamar (CAC) en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 9971d59f0b9c3c2c1f9bfd5e8176122715b19d20
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a>Implementar el servicio de control de admisión de llamadas: lista de comprobación final para Skype Empresarial Server 2015
 
Lista de comprobación final para la implementación de Control de admisión llamar (CAC) en Skype para Telefonía IP empresarial de Business Server. 
  
Use la siguiente lista de comprobación para comprobar si ha completado todas las tareas de configuración necesarias para implementar el Servicio de control de admisión de llamadas (CAC).
  
- Si uno o más servidores perimetrales están distribuidos, cada dirección IP de interfaz externa debe agregarse a la lista de subredes en la configuración de red, con una máscara de bits de 32. También tiene que asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    
    > [!NOTE]
    > Servidores de borde no tienen que implementar CAC. 
  
- Asegúrese de que está habilitado CAC, como especificado en [Habilitar control de admisión de llamada en Skype para Business Server 2015](enable-call-admission-control.md).
    
- Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Esto puede hacerse mediante el generador de topología. Si se genera una advertencia cuando se publica, *no* omitirlo.
    
- Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es esencial que todas las subredes estén asociados a un sitio de red, como se explica en [implementar regiones de red, sitios y subredes en Skype para negocios 2015](deploy-network.md).
    
- Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.
    

