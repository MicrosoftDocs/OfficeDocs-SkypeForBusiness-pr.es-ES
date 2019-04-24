---
title: Vista FileTransfers
ms.reviewer: ''
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
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213091"
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
|**Cancelar.** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y rechazar será NULL.  <br/> |
   

