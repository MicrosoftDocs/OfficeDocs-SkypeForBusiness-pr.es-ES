---
title: Tabla MCU en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabla MCU es una tabla de soporte. Cada registro almacena información acerca de un servicio de conferencia. Estos pueden incluir el servicio de conferencias de mensajería instantánea y el servicio de conferencias de telefonía (que se ejecutan como procesos en servidores de aplicaciones para el usuario), así como el servicio de conferencias por Internet y el servicio de conferencias A/V.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296045"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabla MCU en Skype empresarial Server 2015
 
La tabla MCU es una tabla de soporte. Cada registro almacena información acerca de un servicio de conferencia. Estos pueden incluir el servicio de conferencias de mensajería instantánea y el servicio de conferencias de telefonía (que se ejecutan como procesos en servidores de aplicaciones para el usuario), así como el servicio de conferencias por Internet y el servicio de conferencias A/V. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este servidor de conferencia.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Extranjero <br/> |Tipo de servidor de conferencia, como conf: chat (para mensajes instantáneos) o conf: audio-video. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
   

