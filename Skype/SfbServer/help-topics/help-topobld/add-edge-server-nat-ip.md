---
title: Agregar IP de NAT del servidor perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: La dirección IP pública es la dirección IP que utiliza la traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque ha seleccionado la opción La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT en la página Seleccionar características de este asistente.
ms.openlocfilehash: c4f49f9677ff6f636ae165dc72280828a63e30d5281b40adc2a0abdbab0027a9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335220"
---
# <a name="add-edge-server-nat-ip"></a>Agregar IP de NAT del servidor perimetral

La dirección IP pública es la dirección IP que utiliza la traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque ha seleccionado la opción **La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT** en la página **Seleccionar características** de este asistente.

> [!NOTE]
> La traducción de direcciones de red (NAT) permite a los clientes o servidores de una red pública (por ejemplo, el intervalo 192.168.0.0) comunicarse con sistemas de redes remotas a través de redes públicas de Internet. La NAT funciona mediante el uso de una única dirección IP pública en una interfaz externa y la asociación de direcciones IP internas con esa dirección IP pública. La asignación de NAT asigna una dirección interna a la dirección IP pública externa. El sistema remoto solamente ve la dirección pública de origen. El sistema remoto responde al origen y éste consulta la asignación de NAT para determinar a qué dirección IP interna se debería mandar la respuesta.

Puede agregar compatibilidad de acceso de usuarios externos al implementar la topología inicial o más adelante. Para más detalles sobre cómo agregar servidores perimetrales a una topología existente, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) en la documentación sobre implementación de servidores perimetrales.