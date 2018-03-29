---
title: Vista de Bloqueandote
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTranfer almacena información acerca de las sesiones de transferencia de archivos de igual a igual. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a>Vista de Bloqueandote
 
La vista FileTranfer almacena información acerca de las sesiones de transferencia de archivos de igual a igual. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista Bloqueandote contiene todas las columnas en la [vista SessionDetails](sessiondetails-0.md) además las columnas enumeradas a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**Nombre de archivo** <br/> |nvarchar(256)  <br/> |Nombre del archivo transferido.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Se utiliza para identificar cada mensaje de seguimiento que están asociadas con éste.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificador único para distinguir entre las transferencias de archivos con el mismo nombre de archivo.  <br/> |
|**Aceptar** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, a continuación, rechazar y cancelar será NULL.  <br/> |
|**Rechazar** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y cancelar será NULL.  <br/> |
|**Cancelar** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, a continuación, Aceptar y rechazar será NULL.  <br/> |
   

