---
title: Vista FileTransfers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTransfer almacena información acerca de las sesiones de transferencia de archivos de punto a punto. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 97bc5f957192c8a2c6d888f81fce0891aa2b4f75
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531222"
---
# <a name="filetransfers-view"></a>Vista FileTransfers
 
La vista FileTransfer almacena información acerca de las sesiones de transferencia de archivos de punto a punto. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista FileTransfers contiene todos los de las columnas de la [SessionDetails view](sessiondetails-0.md) además las columnas enumeradas a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nombre del archivo transferido.  <br/> |
|**Galleta** <br/> |nvarchar (128)  <br/> |Se usa para identificar todos los mensajes de seguimiento que están asociadas con éste.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificador único para distinguir entre las transferencias de archivos que implican el mismo nombre de archivo.  <br/> |
|**Aceptar** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, a continuación, rechazar y cancelar será NULL.  <br/> |
|**Rechazar** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y cancelar será NULL.  <br/> |
|**Cancelar** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y rechazar será NULL.  <br/> |
   

