---
title: tblConfig
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene alguna configuración no admitida del servidor de chat persistente, en una fila.
ms.openlocfilehash: 344922f4ffb1cf172c154117c95491558f8e8905
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767368"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contiene alguna configuración no admitida del servidor de chat persistente, en una fila.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), no NULL  <br/> |Contiene "grupo".  <br/> |
|configContent  <br/> |nvarchar (máx.)  <br/> |Contenido de la configuración.  <br/> |
|configPoolID  <br/> |GUID, no NULL  <br/> |Identificador único de la instancia de base de datos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|configLabel  <br/> |Clave principal.  <br/> |
   

