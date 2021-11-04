---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabla UriTypes contiene los distintos tipos de URI (identificador uniforme de recursos) supervisados en Skype Empresarial Server 2015.
ms.openlocfilehash: ee7a2d79458640eff2695ce253792e154d36dee4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767448"
---
# <a name="uritypes-table"></a>Tabla UriTypes
 
La tabla UriTypes contiene los distintos tipos de URI (identificador uniforme de recursos) supervisados en Skype Empresarial Server 2015.

Cuando se crea la base de datos de CDR, se crean dos registros para representar PhoneUri y UserUri, y los registros creados después se asignan dinámicamente UriTypeId. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principal  <br/> |Identificador único asignado a un tipo de URI.  <br/> Valores posibles: de 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descripciones de diferentes tipos de URI. Los siguientes valores están asignados previamente: <br/>  1: uri Teléfono uri <br/>  0: Uri de usuario <br/> <br/>  Otros tipos posibles son: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
