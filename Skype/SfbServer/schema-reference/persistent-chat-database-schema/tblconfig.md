---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814628"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), not null  <br/> |Contiene "pool".  <br/> |
|configContent  <br/> |nvarchar (Max)  <br/> |Contenido de configuración.  <br/> |
|configPoolID  <br/> |GUID, not null  <br/> |IDENTIFICADOR único de la instancia de la base de datos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|configLabel  <br/> |Clave principal.  <br/> |
   

