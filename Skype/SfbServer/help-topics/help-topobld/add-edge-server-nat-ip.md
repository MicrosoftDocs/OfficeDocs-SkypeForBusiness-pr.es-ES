---
title: Agregar IP de NAT de servidor perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: La dirección IP pública es la dirección IP que utiliza traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque ha seleccionado la dirección IP externa de este borde pool se traduce por opción de NAT en la página Seleccionar características de este asistente.
ms.openlocfilehash: 4bfbcb7d8859dc928c78c8e32b21604ef473317b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-nat-ip"></a>Agregar IP de NAT de servidor perimetral
 
La dirección IP pública es la dirección IP que utiliza traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque se seleccionó la opción **NAT traduce la dirección IP externa de este grupo de borde** en la página **Seleccionar características** de este asistente.
  
> [!NOTE]
> Traducción de direcciones de red (NAT) permite a los clientes o servidores en una red privada (por ejemplo, el 192.168.0.0 intervalo) para comunicarse con sistemas en redes remotas a través de las redes públicas de Internet. NAT funciona mediante una única dirección IP pública en una interfaz externa y asociar las direcciones IP internas con las direcciones IP públicas. NAT asigna una dirección interna a la dirección IP pública externa. El sistema remoto ve sólo la dirección pública de la fuente. El sistema remoto responde a la fuente y el origen se refiere a la asignación NAT para determinar qué dirección IP interna a que debe devolverse la respuesta. 
  
La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante. Para obtener más información sobre cómo agregar servidores de borde a una topología existente, vea [Definir su topología de borde](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación de servidor de borde.
  

