---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que es posible asociar con nodos.
ms.openlocfilehash: 7a84170ccf79e3cb84c876a1bc1828c4eabf4e78
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743106"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList es la lista de complementos registrados que es posible asociar con nodos.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, no NULL  <br/> |GUID del complemento.  <br/> |
|siopName  <br/> |nvarchar (50), no NULL  <br/> |Nombre para mostrar del complemento.  <br/> |
|siopUrl  <br/> |nvarchar (255), no NULL  <br/> |URL del complemento.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|siopID  <br/> |Clave principal.  <br/> |
   

