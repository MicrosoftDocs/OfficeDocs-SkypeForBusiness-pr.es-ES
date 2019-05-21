---
title: Agregar IP de NAT del servidor perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: La dirección IP pública es la dirección IP que usa la traducción de direcciones de red (NAT). La dirección IP debe ser públicamente enrutable. Esto es necesario porque la opción NAT ha traducido la dirección IP externa de este grupo de límites de la página seleccionar características de este asistente.
ms.openlocfilehash: 55200991a0674c6372de9f44c2511e700166bebf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293948"
---
# <a name="add-edge-server-nat-ip"></a>Agregar IP de NAT del servidor perimetral

La dirección IP pública es la dirección IP que usa la traducción de direcciones de red (NAT). La dirección IP debe ser públicamente enrutable. Esto es necesario porque la opción **NAT ha traducido la dirección IP externa de este grupo de límites** de la página **seleccionar características** de este asistente.

> [!NOTE]
> La traducción de direcciones de red (NAT) permite que los clientes o servidores de una red privada (por ejemplo, el intervalo 192.168.0.0) se comuniquen con sistemas de redes remotas a través de redes públicas de Internet. NAT funciona con una única dirección IP pública en una interfaz externa y asocia las direcciones IP internas a la dirección IP pública. La asignación NAT asigna una dirección interna a la dirección IP pública externa. El sistema remoto solo ve la dirección pública del origen. El sistema remoto responde al origen y el origen hace referencia al mapa NAT para determinar la dirección IP interna a la que se debe devolver la respuesta.

La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante. Para más detalles sobre cómo agregar servidores perimetrales a una topología existente, mire [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación de servidores perimetrales.


