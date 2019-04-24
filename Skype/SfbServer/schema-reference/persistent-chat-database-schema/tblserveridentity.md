---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212421"
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
   

