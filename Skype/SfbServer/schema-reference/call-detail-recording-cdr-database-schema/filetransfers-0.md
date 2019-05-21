---
title: Tabla FileTransfers en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Cada registro representa una sesión de transferencia de archivos.
ms.openlocfilehash: ada437eacfa9a532a4875c3ce1837ccd9d8aed17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296255"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabla FileTransfers en Skype empresarial Server 2015
 
Cada registro representa una sesión de transferencia de archivos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**Nombre de archivo** <br/> |nvarchar(256)  <br/> ||Nombre del archivo.  <br/> |
|**FileIdentity** <br/> |identificador  <br/> ||Identificador único para distinguir entre transferencias de archivos que impliquen el mismo nombre de archivo.  <br/> |
|**Ésta** <br/> |nvarchar(128  <br/> |Primary  <br/> |Se usa para identificar cada mensaje de seguimiento como asociado con este.  <br/> |
|**Aceptable** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es verdadero, rechazar y cancelar será nulo.  <br/> |
|**Rechace** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es verdadero, aceptar y cancelar será nulo.  <br/> |
|**Cancelar.** <br/> |bit  <br/> ||Puede ser TRUE o NULL. Si es verdadero, aceptar y rechazar serán NULOs.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   

