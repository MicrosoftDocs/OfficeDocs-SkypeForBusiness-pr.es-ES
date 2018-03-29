---
title: Tabla NetworkConnectionDetail
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red utilizados en la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a>Tabla NetworkConnectionDetail
 
La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red utilizados en la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único para el tipo de conexión de red.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Único  <br/> |Tipo de conexión de red que corresponde a la NetworkConnectionDetailKey. Los valores permitidos son:  <br/> 0--con cable  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--los demás  <br/> 5: túnel  <br/> |
   

