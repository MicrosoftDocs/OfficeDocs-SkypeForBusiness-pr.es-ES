---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contiene testigos temporales para fines de transferencia de archivos.
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contiene testigos temporales para fines de transferencia de archivos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), no nulo  <br/> |Token único (GUID).  <br/> |
|fileTokenUserID  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que transfiere el archivo.  <br/> |
|fileTokenChannelID  <br/> |GUID, no nulo  <br/> |GUID del nodo de salón de chat.  <br/> |
|fileTokenExpireDate  <br/> |fecha y hora, no nulo  <br/> |Fecha de caducidad. (Tokens caducan después de 30 minutos, a menos que fija (consulte las siguientes descripciones en esta columna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |Dirección URL del archivo transferido (para el uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |Dirección URL de la miniatura para el archivo transferido (para el uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Marca de tiempo para la operación de transferencia de archivo real (para el uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True si cargar; False si descarga (para uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenCompliancePinned  <br/> |bits, no nulo  <br/> |True si el token está anclado. Sirve para mantener el token en la tabla hasta que el servicio de cumplimiento de normas tenga la oportunidad de recuperar los campos pertinentes del mismo.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|fileToken  <br/> |Clave principal.  <br/> |
|fileTokenChannelID  <br/> |Clave externa con la búsqueda en la tabla tblNode.nodeGuid.  <br/> |
   

