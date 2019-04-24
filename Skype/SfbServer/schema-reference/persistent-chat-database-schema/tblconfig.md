---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213070"
---
# <a name="tblconfig"></a>tblConfig
 
la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), no es nulo  <br/> |Contiene "grupo".  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenido de configuración.  <br/> |
|configPoolID  <br/> |GUID, no es nulo  <br/> |Identificador único de la instancia de base de datos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|configLabel  <br/> |Clave principal.  <br/> |
   

