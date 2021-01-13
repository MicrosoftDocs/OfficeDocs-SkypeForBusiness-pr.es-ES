---
title: Tabla IPAddress
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802780"
---
# <a name="ipaddress-table"></a>Tabla IPAddress
 
La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |entero  <br/> |Principal  <br/> |Identificador único de la dirección IP especificada.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Única  <br/> |Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a IpAddressKey. Puede ser una dirección IPv4 o IPv6.  <br/> |
   

