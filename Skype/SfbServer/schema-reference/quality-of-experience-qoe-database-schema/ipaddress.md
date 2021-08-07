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
ms.openlocfilehash: db9405a05335974456f77d8117f9e3f64e9832750c3d2c23441a5a587ca91d7a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305102"
---
# <a name="ipaddress-table"></a>Tabla IPAddress
 
La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |Entero  <br/> |Principal  <br/> |Identificador único de la dirección IP especificada.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Única  <br/> |Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a IpAddressKey. Puede ser una dirección IPv4 o IPv6.  <br/> |
   

