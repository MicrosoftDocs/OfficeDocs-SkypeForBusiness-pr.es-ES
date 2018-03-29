---
title: Tabla de MCU en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabla de la MCU es una tabla de soporte. Cada registro almacena información acerca de un servicio de conferencias. Éstos pueden incluir el servicio Conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end) y el servicio de conferencias Web y A / servicio de conferencias audiovisuales.
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabla de MCU en Skype para Business Server 2015
 
La tabla de la MCU es una tabla de soporte. Cada registro almacena información acerca de un servicio de conferencias. Éstos pueden incluir el servicio Conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end) y el servicio de conferencias Web y A / servicio de conferencias audiovisuales. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este servidor de conferencia.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Externa <br/> |Tipo de servidor de conferencias, como conf:chat (para IMs) o conf:audio-vídeo. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
   

