---
title: Tabla NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabla NetworkConnectionDetail se asigna a los identificadores de conexión de red que se usan en otras partes de la base de datos de la calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807508"
---
# <a name="networkconnectiondetail-table"></a>Tabla NetworkConnectionDetail
 
La tabla NetworkConnectionDetail se asigna a los identificadores de conexión de red que se usan en otras partes de la base de datos de la calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único del tipo de conexión de red.  <br/> |
|**NetworkConnectionDetail** <br/> |VARCHAR (256)  <br/> |Solo  <br/> |Tipo de conexión de red que corresponde a la NetworkConnectionDetailKey. Los valores permitidos son:  <br/> 0: conectado  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--otros  <br/> 5--túnel  <br/> |
   

