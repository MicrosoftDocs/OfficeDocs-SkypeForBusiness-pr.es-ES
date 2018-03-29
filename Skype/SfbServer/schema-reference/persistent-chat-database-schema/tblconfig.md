---
title: tblConfig
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene una configuración no compatible persistente Chat Server, en una fila.
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contiene una configuración no compatible persistente Chat Server, en una fila.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), no nulo  <br/> |Contiene "grupo".  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenido de configuración.  <br/> |
|configPoolID  <br/> |GUID, no nulo  <br/> |Identificador exclusivo de la instancia de base de datos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|configLabel  <br/> |Clave principal.  <br/> |
   

