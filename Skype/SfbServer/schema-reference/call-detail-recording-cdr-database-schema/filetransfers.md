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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos de punto a punto. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815208"
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
   

