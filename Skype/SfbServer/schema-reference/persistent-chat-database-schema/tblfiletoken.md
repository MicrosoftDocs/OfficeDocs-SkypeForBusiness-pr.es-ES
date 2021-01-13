---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: La tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivos.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816020"
---
# <a name="tblfiletoken"></a>tblFileToken
 
La tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivos.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), no NULL  <br/> |Símbolo único (un GUID).  <br/> |
|fileTokenUserID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad que está transfiriendo el archivo.  <br/> |
|fileTokenChannelID  <br/> |GUID, no NULL  <br/> |GUID del nodo de la sala de chat.  <br/> |
|fileTokenExpireDate  <br/> |datetime, no NULL  <br/> |Tiempo de expiración; los tokens caducan después de 30 minutos, a menos que esté anclado (vea las siguientes descripciones en esta columna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL del archivo transferido (para el uso del Servicio de cumplimiento).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL de la miniatura del archivo transferido (para el uso del Servicio de cumplimiento).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Marca de tiempo para la operación de transferencia de archivo real (para el uso del Servicio de cumplimiento).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True si se carga; False si se descarga (para el uso del Servicio de cumplimiento).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, no NULL  <br/> |True si el token está anclado. Se usa para mantener el token en la tabla hasta que el servicio de cumplimiento tenga la oportunidad de recuperar los campos relevantes de él.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|fileToken  <br/> |Clave principal.  <br/> |
|fileTokenChannelID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeGuid.  <br/> |
   

