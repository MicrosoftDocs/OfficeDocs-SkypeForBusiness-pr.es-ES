---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924811"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|serverID  <br/> |int, no es nulo  <br/> |Identificador de servidor. Se corresponde con un identificador de instancia de almacén de Administración Central.  <br/> |
|serverAddress  <br/> |nvarchar (256), no es nulo  <br/> |Dirección de servidor con la dirección de Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |La última vez que el servidor de canal actualizó esta fila para probar que se está ejecutando.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|serverID  <br/> |Clave principal.  <br/> |
   

