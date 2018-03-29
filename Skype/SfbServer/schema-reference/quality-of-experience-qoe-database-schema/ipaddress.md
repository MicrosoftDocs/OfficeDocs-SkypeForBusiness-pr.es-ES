---
title: Tabla de dirección IP
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabla dirección IP asigna direcciones IP a los identificadores únicos de dirección IP utilizados en la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a>Tabla de dirección IP
 
La tabla dirección IP asigna direcciones IP a los identificadores únicos de dirección IP utilizados en la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |Identificador único de la dirección IP especificada.  <br/> |
|**Dirección IP** <br/> |varchar(50)  <br/> |Único  <br/> |Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a la IpAddressKey. Esto puede ser tanto una dirección IPv4 o IPv6.  <br/> |
   

