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
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene alguna configuración no admitida del servidor de chat persistente, en una fila.
ms.openlocfilehash: 8cf1fc53087d3fc786ac47e848a21dbd2a8f5549
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595312"
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
   

