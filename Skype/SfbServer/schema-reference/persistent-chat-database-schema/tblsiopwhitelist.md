---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que es posible asociar con nodos.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831490"
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
   

