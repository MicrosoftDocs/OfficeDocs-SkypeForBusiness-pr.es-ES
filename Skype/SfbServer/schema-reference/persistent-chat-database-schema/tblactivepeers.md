---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones punto a punto actuales entre servicios de chat.
ms.openlocfilehash: 21623df3acf8ec8077fa4f2f490f28d2e8482907
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622102"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contiene las conexiones punto a punto actuales entre servicios de chat.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, no NULL  <br/> |Id. del servidor que publicó la entrada.  <br/> |
|aplPeerID  <br/> |int, no NULL  <br/> |Id. del mismo nivel al que está conectado el servidor de publicación.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clave principal.  <br/> |
|aplServerID  <br/> |Clave externa con búsqueda en la tabla tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Clave externa con búsqueda en la tabla tblServerIdentity.serverID.  <br/> |
   

