---
title: Tabla dirección IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabla direcciónIP asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de la calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294925"
---
# <a name="ipaddress-table"></a>Tabla dirección IP
 
La tabla direcciónIP asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de la calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |Identificador único de la dirección IP especificada.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Solo  <br/> |Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a la IpAddressKey. Puede ser una dirección IPv4 o IPv6.  <br/> |
   

