---
title: Tabla FileTransfers en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Cada registro representa una sesión de transferencia de archivos.
ms.openlocfilehash: 59a8346bb000af9c556306d1314c93e45feb28ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593424"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabla FileTransfers en Skype Empresarial Server 2015
 
Cada registro representa una sesión de transferencia de archivos.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**Nombre de archivo** <br/> |nvarchar(256)  <br/> ||Nombre del archivo.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificador único para distinguir entre las transferencias de archivos con el mismo nombre de archivo.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Principal  <br/> |Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.  <br/> |
|**Accept** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.  <br/> |
|**Reject** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

