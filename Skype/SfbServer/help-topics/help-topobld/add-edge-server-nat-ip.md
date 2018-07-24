---
title: Agregar IP de NAT de servidor perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: La dirección IP pública es la dirección IP que se usa en la traducción de direcciones de red (NAT). La dirección IP debe ser públicamente enrutable. Esto es necesario porque ha seleccionado la dirección IP externa de este borde se traduce el grupo de servidores mediante la opción de NAT en la página Seleccionar características de este asistente.
ms.openlocfilehash: be14b49a0d5ccac83dbee483d45aef91f1182621
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003120"
---
# <a name="add-edge-server-nat-ip"></a>Agregar IP de NAT de servidor perimetral
 
La dirección IP pública es la dirección IP que se usa en la traducción de direcciones de red (NAT). La dirección IP debe ser públicamente enrutable. Esto es necesario porque seleccionó la opción de **la dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT** en la página **Seleccionar características** de este asistente.
  
> [!NOTE]
> Traducción de direcciones de red (NAT) permite a los clientes o servidores en una red privada (por ejemplo, la 192.168.0.0 intervalo) para comunicarse con sistemas en redes remotas a través de las redes públicas de Internet. NAT funciona con una sola dirección IP pública en una interfaz externa y asociar las direcciones IP internas a la dirección IP pública uno. NAT asigna una dirección interna a la dirección IP pública externa. El sistema remoto ve sólo la dirección pública del origen. El sistema remoto responde a la fuente y el origen hace referencia a la asignación NAT para determinar qué dirección IP interna de que la respuesta se debe devolver al. 
  
La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante. Para obtener información detallada sobre la adición de servidores perimetrales a una topología existente, consulte [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación del servidor perimetral.
  

