---
title: Tabla NetworkConnectionDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d41b89ce85ee365d883c2224f2da29fca3cab926
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394712"
---
# <a name="networkconnectiondetail-table"></a>Tabla NetworkConnectionDetail
 
La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principal  <br/> |Identificador único del tipo de conexión de red.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Única  <br/> |Tipo de conexión de red que se corresponde con NetworkConnectionDetailKey. Los valores permitidos son:  <br/> 0: cableada  <br/> 1: Wi-Fi  <br/> 2: Ethernet  <br/> 3: MobileBB  <br/> 4 -- Otros  <br/> 5-- Tunnel  <br/> |
   

