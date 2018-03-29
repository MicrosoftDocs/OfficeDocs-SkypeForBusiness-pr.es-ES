---
title: tblServerIdentity
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene los servidores de chat activo en el grupo de servidor de charla persistente.
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contiene los servidores de chat activo en el grupo de servidor de charla persistente.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|serverID  <br/> |int, no nulo  <br/> |Identificador de servidor. Corresponde a la ID de instancia de almacén de Administración Central.  <br/> |
|serverAddress  <br/> |nvarchar (256), no nulo  <br/> |Dirección del servidor mediante la dirección de Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |La última hora en la que el servidor de canal actualizar esta fila para proporcionar evidencia de que se está ejecutando.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|serverID  <br/> |Clave principal.  <br/> |
   

