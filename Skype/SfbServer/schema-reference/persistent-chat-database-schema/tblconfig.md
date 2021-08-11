---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene alguna configuración no admitida del servidor de chat persistente, en una fila.
ms.openlocfilehash: 0e9cc0a0c4686432032591aa0c380b303fc5251a56a6c983a1e10b009e0eb28a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278358"
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
   

