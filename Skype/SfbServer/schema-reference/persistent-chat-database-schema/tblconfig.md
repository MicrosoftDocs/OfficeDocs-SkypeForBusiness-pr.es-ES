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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295457"
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
   

