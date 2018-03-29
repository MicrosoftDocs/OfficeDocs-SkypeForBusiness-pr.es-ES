---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las actuales conexiones peer-to-peer entre servicios de charla.
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contiene las actuales conexiones peer-to-peer entre servicios de charla.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, no nulo  <br/> |Id. del servidor que se registró el movimiento.  <br/> |
|aplPeerID  <br/> |int, no nulo  <br/> |Id. del interlocutor que está conectado el servidor de registro.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clave principal.  <br/> |
|aplServerID  <br/> |Clave externa con la búsqueda en la tabla tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Clave externa con la búsqueda en la tabla tblServerIdentity.serverID.  <br/> |
   

