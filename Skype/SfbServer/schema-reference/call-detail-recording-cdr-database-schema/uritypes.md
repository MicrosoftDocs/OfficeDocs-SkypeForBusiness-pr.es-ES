---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) supervisados en Skype empresarial Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295751"
---
# <a name="uritypes-table"></a>Tabla UriTypes
 
La tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) supervisados en Skype empresarial Server 2015.

Cuando se crea la base de la BD de CDR, se crean dos registros para representar PhoneUri y UserUri, y los registros creados después de que se hayan asignado de forma dinámica UriTypeId. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único asignado a un tipo de URI.  <br/> Valores posibles: 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descripciones de los distintos tipos de URI. Los valores siguientes se han asignado previamente: <br/>  URI de 1 teléfono <br/>  0: URI de usuario <br/> <br/>  Otros tipos posibles son: <br/>conferencia:uso compartido de aplicaciones <br/> conferencia:audio-vídeo<br/> conf: chat<br/>    conferencia:foco<br/>   mras<br/>
