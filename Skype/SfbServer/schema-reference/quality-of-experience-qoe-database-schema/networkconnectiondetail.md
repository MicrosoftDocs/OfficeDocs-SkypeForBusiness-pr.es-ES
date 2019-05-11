---
title: Tabla NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: En la tabla NetworkConnectionDetail asigna tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de calidad de la experiencia. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: a7095000cc996f2a6430ffcaf8411a2891872938
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919994"
---
# <a name="networkconnectiondetail-table"></a>Tabla NetworkConnectionDetail
 
En la tabla NetworkConnectionDetail asigna tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de calidad de la experiencia. En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único para el tipo de conexión de red.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Único  <br/> |Tipo de conexión de red que corresponde a la NetworkConnectionDetailKey. Los valores permitidos son:  <br/> 0--con cable  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--otros  <br/> 5--túnel  <br/> |
   

