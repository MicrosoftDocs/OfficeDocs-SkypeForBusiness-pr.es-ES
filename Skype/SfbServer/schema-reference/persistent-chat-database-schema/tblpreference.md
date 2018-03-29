---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias del cliente de los usuarios. Generalmente se utiliza por los clientes anteriores a Lync de 2013.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a>tblPreference
 
tblPreference contiene las preferencias del cliente de los usuarios. Generalmente se utiliza por los clientes anteriores a Lync de 2013.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prefLabel  <br/> |nvarchar (255), no nulo  <br/> |Etiquetar con un formato como: \<uri de sip del usuario\>|nombre de usuario. \<conjunto de preferencias\>.  <br/> |
|prefSeqID  <br/> |int, no nulo  <br/> |Un número secuencial (por etiqueta) para control de versiones.  <br/> |
|prefContent  <br/> |nvarchar (max)  <br/> |Contenido codificado.  <br/> |
|lastModifiedBy  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que se actualiza la preferencia.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clave principal.  <br/> |
   

