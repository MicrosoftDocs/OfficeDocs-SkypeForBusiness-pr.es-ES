---
title: Vista FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos punto a punto. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: e805b770038eb7fae93337c5d6c26d7059e5764436328f6321e65c948e40c88d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349692"
---
# <a name="filetransfers-view"></a>Vista FileTransfers
 
La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos punto a punto. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista FileTransfers contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las columnas que se enumeran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nombre del archivo transferido.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificador único para distinguir entre las transferencias de archivos en las que participa el mismo nombre de archivo.  <br/> |
|**Accept** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.  <br/> |
|**Reject** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> |Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.  <br/> |
   

