---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295177"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, not null  <br/> |GUID del complemento.  <br/> |
|siopName  <br/> |nvarchar (50), not null  <br/> |Display: nombre del complemento.  <br/> |
|siopUrl  <br/> |nvarchar (255), not null  <br/> |Dirección URL del complemento.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|siopID  <br/> |Clave principal.  <br/> |
   

