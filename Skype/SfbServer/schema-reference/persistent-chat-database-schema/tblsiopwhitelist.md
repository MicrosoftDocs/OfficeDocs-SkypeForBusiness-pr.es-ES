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
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que es posible asociar con nodos.
ms.openlocfilehash: 78cc98f584f20d3a08e9ed750ed9ac406f7e5780
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613830"
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
   

