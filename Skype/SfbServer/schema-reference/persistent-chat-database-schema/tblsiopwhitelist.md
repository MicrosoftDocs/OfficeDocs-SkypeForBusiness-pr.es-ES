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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812118"
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
   

