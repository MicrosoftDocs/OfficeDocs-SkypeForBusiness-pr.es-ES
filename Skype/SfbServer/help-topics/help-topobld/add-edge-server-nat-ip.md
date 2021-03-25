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
ms.openlocfilehash: cf5cb61dce8d71e97ba3977e241df4480c30a403
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119819"
---
# <a name="add-edge-server-nat-ip"></a>Agregar IP de NAT del servidor perimetral

La dirección IP pública es la dirección IP que utiliza la traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque ha seleccionado la opción **La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT** en la página **Seleccionar características** de este asistente.

> [!NOTE]
> La traducción de direcciones de red (NAT) permite a los clientes o servidores de una red pública (por ejemplo, el intervalo 192.168.0.0) comunicarse con sistemas de redes remotas a través de redes públicas de Internet. La NAT funciona mediante el uso de una única dirección IP pública en una interfaz externa y la asociación de direcciones IP internas con esa dirección IP pública. La asignación de NAT asigna una dirección interna a la dirección IP pública externa. El sistema remoto solamente ve la dirección pública de origen. El sistema remoto responde al origen y éste consulta la asignación de NAT para determinar a qué dirección IP interna se debería mandar la respuesta.

Puede permitir que los usuarios externos tengan acceso al implementar la topología inicial o después. Para obtener más información sobre cómo agregar servidores perimetrales a una topología ya creada, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) en la documentación sobre implementación de servidores perimetrales.