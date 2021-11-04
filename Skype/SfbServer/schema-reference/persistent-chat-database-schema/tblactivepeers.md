---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: d2d28c70cbb1bc35acdeca4739a667a5e991e52f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756310"
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
   

