---
title: Tabla Mcus en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabla Mcus es una tabla de soporte. Cada registro almacena información sobre un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end), y el servicio de conferencia web y el servicio de conferencia A/V.
ms.openlocfilehash: 1394a2f899df47b15a66989aeaed5872f6913912
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765098"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabla Mcus en Skype Empresarial Server 2015
 
La tabla Mcus es una tabla de soporte. Cada registro almacena información sobre un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end), y el servicio de conferencia web y el servicio de conferencia A/V. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este servidor de conferencias.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Externo <br/> |Tipo de servidor de conferencia, como conf:chat (para IMs) o conf:audio-video. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

