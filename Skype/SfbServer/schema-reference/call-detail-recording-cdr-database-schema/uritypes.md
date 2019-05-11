---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.
ms.openlocfilehash: 72704715ff5e5fd3a354b75b0aa6baff45ecea54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930272"
---
# <a name="uritypes-table"></a>Tabla UriTypes
 
En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.

Cuando se crea la CDR DB, se crean dos registros para representar PhoneUri y UserUri, y los registros se crean después de se asignan dinámicamente UriTypeId. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único asignado a un tipo de URI.  <br/> Valores posibles: de 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descripciones de los distintos tipos URI. Los siguientes valores son asignados previamente: <br/>  1: URI del teléfono <br/>  0 - URI del usuario <br/> <br/>  Otros tipos posibles son: <br/>conferencia:uso compartido de aplicaciones <br/> conferencia:audio-vídeo<br/> conf:chat<br/>    conferencia:foco<br/>   MRAS<br/>
