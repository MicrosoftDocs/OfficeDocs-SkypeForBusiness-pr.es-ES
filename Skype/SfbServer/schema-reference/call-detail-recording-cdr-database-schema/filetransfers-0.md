---
title: Tabla FileTransfers en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Cada registro representa una sesión de transferencia de archivo.
ms.openlocfilehash: 2d249cb303bca7726a8c666bc8b906841be5ce1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901062"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabla FileTransfers en Skype para Business Server 2015
 
Cada registro representa una sesión de transferencia de archivo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**Nombre de archivo** <br/> |nvarchar(256)  <br/> ||Nombre del archivo.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificador único para distinguir entre las transferencias de archivos que implican el mismo nombre de archivo.  <br/> |
|**Galleta** <br/> |nvarchar (128)  <br/> |Primary  <br/> |Se usa para identificar todos los mensajes de seguimiento que están asociadas con éste.  <br/> |
|**Aceptar** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, a continuación, rechazar y cancelar será NULL.  <br/> |
|**Rechazar** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y cancelar será NULL.  <br/> |
|**Cancelar.** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y rechazar será NULL.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

