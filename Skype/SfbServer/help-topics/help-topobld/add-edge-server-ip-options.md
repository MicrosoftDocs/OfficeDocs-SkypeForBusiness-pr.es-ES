---
title: Agregar opciones de IP del servidor de borde
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: '2013 de Microsoft Lync Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz del servidor de borde y fondo de borde. Para ello, siga este procedimiento:'
ms.openlocfilehash: a6f4dd60355a4e241c70ec28c72fa86d91c66a9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-ip-options"></a>Agregar opciones de IP del servidor de borde
 
2013 de Microsoft Lync Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz del servidor de borde y fondo de borde. Para ello, siga este procedimiento:
  
- **Habilitar IPv4 en la interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz interna del grupo de borde
    
- **Habilitar IPv6 en la interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz interna del grupo de borde
    
- **Habilitar IPv4 en la interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz externa del grupo de borde
    
- **Habilitar IPv6 en la interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz externa del grupo de borde
    
También puede configurar el servidor perimetral o un grupo de servidores de borde para utilizar una dirección de traducción de direcciones de red para las direcciones IP externas. Para ello, activando la casilla de verificación **NAT traduce la dirección IP externa de este grupo de borde**.
  
Compatibilidad con NAT. Traducción de direcciones de red (NAT) no se admite cuando se utiliza hardware equilibrio de carga, por lo que no se seleccione la opción NAT si va a implementar una agrupación de servidor perimetral con equilibrio de carga de hardware.
  

