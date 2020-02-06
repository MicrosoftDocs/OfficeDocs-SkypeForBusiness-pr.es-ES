---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene todos los servidores que procesaron un evento de cumplimiento.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814658"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout contiene todos los servidores que procesaron un evento de cumplimiento.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |IDENTIFICADOR de evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identidad del servidor (correspondiente a la tabla tblServerIdentity. serverID).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|fanoutEventID  <br/> |Clave externa con la búsqueda en la tabla tblComplianceData. cmplEventID.  <br/> |
   

