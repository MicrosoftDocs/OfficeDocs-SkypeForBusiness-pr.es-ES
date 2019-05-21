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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene todos los servidores que procesaron un evento de cumplimiento.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295506"
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
   

