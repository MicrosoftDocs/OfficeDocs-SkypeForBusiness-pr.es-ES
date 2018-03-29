---
title: Tabla Bloqueandote en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Cada registro representa una sesión de transferencia de archivos.
ms.openlocfilehash: 07ab898246efbac623910886000e97037f43ead2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabla Bloqueandote en Skype para Business Server 2015
 
Cada registro representa una sesión de transferencia de archivos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**Nombre de archivo** <br/> |nvarchar(256)  <br/> ||Nombre del archivo.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificador único para distinguir entre las transferencias de archivos con el mismo nombre de archivo.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Primary  <br/> |Se utiliza para identificar cada mensaje de seguimiento que están asociadas con éste.  <br/> |
|**Aceptar** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, a continuación, rechazar y cancelar será NULL.  <br/> |
|**Rechazar** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y cancelar será NULL.  <br/> |
|**Cancelar** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y rechazar será NULL.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

