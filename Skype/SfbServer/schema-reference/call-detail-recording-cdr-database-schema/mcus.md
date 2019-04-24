---
title: Tabla de MCU en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: En la tabla de MCU es una tabla de apoyo. Cada registro almacena información acerca de un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencias telefónicas (que se ejecutan como procesos en servidores front-end) y el servicio de conferencia Web y A / servicio de conferencia A/v.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212976"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabla de MCU en Skype para Business Server 2015
 
En la tabla de MCU es una tabla de apoyo. Cada registro almacena información acerca de un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencias telefónicas (que se ejecutan como procesos en servidores front-end) y el servicio de conferencia Web y A / servicio de conferencia A/v. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este servidor de conferencia.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Externa <br/> |Tipo de servidor de conferencia, como conf:chat (para mensajes instantáneos) o conf:audio-vídeo. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

