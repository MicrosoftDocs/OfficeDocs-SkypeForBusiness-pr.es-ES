---
title: Vista FileTransfers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos de punto a punto. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296241"
---
# <a name="filetransfers-view"></a>Vista FileTransfers
 
La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos de punto a punto. Esta vista se presentó en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista FileTransfers contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las columnas que se muestran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nombre del archivo transferido.  <br/> |
|**Ésta** <br/> |nvarchar(128  <br/> |Se usa para identificar cada mensaje de seguimiento como asociado con este.  <br/> |
|**FileIdentity** <br/> |identificador  <br/> |Identificador único para distinguir entre transferencias de archivos que impliquen el mismo nombre de archivo.  <br/> |
|**Aceptable** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es verdadero, rechazar y cancelar será nulo.  <br/> |
|**Rechace** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es verdadero, aceptar y cancelar será nulo.  <br/> |
|**Cancelar.** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es verdadero, aceptar y rechazar serán NULOs.  <br/> |
   

