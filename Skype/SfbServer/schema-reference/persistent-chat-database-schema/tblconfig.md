---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930025"
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
   

