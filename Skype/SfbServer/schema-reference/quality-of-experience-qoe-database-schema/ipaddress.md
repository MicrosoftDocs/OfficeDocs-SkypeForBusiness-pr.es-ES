---
title: Tabla IPAddress
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 004bdbbe652a275788293bb42cda2e779b698d65
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756179"
---
# <a name="ipaddress-table"></a>Tabla IPAddress
 
La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |Entero  <br/> |Principal  <br/> |Identificador único de la dirección IP especificada.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Única  <br/> |Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a IpAddressKey. Puede ser una dirección IPv4 o IPv6.  <br/> |
   

