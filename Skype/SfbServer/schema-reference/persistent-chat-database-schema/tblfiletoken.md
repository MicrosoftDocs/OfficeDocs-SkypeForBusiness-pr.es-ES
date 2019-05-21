---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contiene tokens temporales para la transferencia de archivos.
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295408"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contiene tokens temporales para la transferencia de archivos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), not null  <br/> |Identificador exclusivo (un GUID).  <br/> |
|fileTokenUserID  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que está transfiriendo el archivo.  <br/> |
|fileTokenChannelID  <br/> |GUID, not null  <br/> |GUID del nodo del salón de chat.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, not null  <br/> |Fecha de expiración. (Los tokens vencen después de 30 minutos, a menos que se hayan anclado (vea las siguientes descripciones en esta columna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |Dirección URL del archivo transferido (para el uso del servicio de cumplimiento).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |Dirección URL de la miniatura del archivo transferido (para el uso del servicio de cumplimiento).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Marca de hora para la operación de transferencia de archivos real (para el uso del servicio de cumplimiento).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |Es verdadero si se carga; Falso si descargar (para uso del servicio de cumplimiento).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, not null  <br/> |True si el símbolo está anclado. Se usa para mantener el token en la tabla hasta que el servicio de cumplimiento tiene la posibilidad de recuperar los campos correspondientes de él.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|fileToken  <br/> |Clave principal.  <br/> |
|fileTokenChannelID  <br/> |Clave externa con la búsqueda en la tabla tblNode. nodeGuid.  <br/> |
   

