---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: la tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivo de.
ms.openlocfilehash: 46553a4b8752e2a95691dc2042a2632845166fc7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212603"
---
# <a name="tblfiletoken"></a>tblFileToken
 
la tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivo de.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), no es nulo  <br/> |Símbolo único (GUID).  <br/> |
|fileTokenUserID  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que va a transferir el archivo.  <br/> |
|fileTokenChannelID  <br/> |GUID, no es nulo  <br/> |GUID del nodo del salón de chat.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, no es nulo  <br/> |Tiempo de expiración. (Los tokens caducan después de 30 minutos, a menos que anclados (vea las siguientes descripciones en esta columna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |Dirección URL del archivo transferido (para el uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |Dirección URL de la imagen en miniatura del archivo transferido (para el uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Marca de tiempo para la operación de transferencia de archivo real (para el uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True si la carga; False si descarga (para el uso del servicio de cumplimiento de normas).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, no es nulo  <br/> |True si se fija el símbolo (token). Se utiliza para mantener el token en la tabla hasta que el servicio de cumplimiento tiene una oportunidad para recuperar los campos correspondientes de él.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|fileToken  <br/> |Clave principal.  <br/> |
|fileTokenChannelID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeGuid.  <br/> |
   

