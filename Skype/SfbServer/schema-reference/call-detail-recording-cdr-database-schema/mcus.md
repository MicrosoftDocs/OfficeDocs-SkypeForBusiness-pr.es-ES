---
title: Tabla Mcus en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabla Mcus es una tabla de apoyo. Cada registro almacena información sobre un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end), y el servicio de conferencia web y el servicio de conferencia A/V.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821430"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabla Mcus en Skype Empresarial Server 2015
 
La tabla Mcus es una tabla de apoyo. Cada registro almacena información sobre un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end), y el servicio de conferencia web y el servicio de conferencia A/V. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica este servidor de conferencias.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Externo <br/> |Tipo de servidor de conferencia, como conf:chat (para IMs) o conf:audio-video. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

