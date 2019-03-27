---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884170"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, no es nulo  <br/> |Identificador del servidor que publicó la entrada.  <br/> |
|aplPeerID  <br/> |int, no es nulo  <br/> |Identificador del punto al que está conectado el servidor de registro.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clave principal.  <br/> |
|aplServerID  <br/> |Clave externa con búsqueda en la tabla tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Clave externa con búsqueda en la tabla tblServerIdentity.serverID.  <br/> |
   

