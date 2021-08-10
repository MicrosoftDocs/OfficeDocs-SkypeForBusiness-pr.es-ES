---
title: Tabla NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d1aa430f821233fcbf89f166bf76d3d8fadf76a9f7401ce5c9009629fccea70a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306701"
---
# <a name="networkconnectiondetail-table"></a>Tabla NetworkConnectionDetail
 
La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principal  <br/> |Identificador único del tipo de conexión de red.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Única  <br/> |Tipo de conexión de red que se corresponde con NetworkConnectionDetailKey. Los valores permitidos son:  <br/> 0: cableada  <br/> 1: Wi-Fi  <br/> 2: Ethernet  <br/> 3: MobileBB  <br/> 4 -- Otros  <br/> 5-- Tunnel  <br/> |
   

