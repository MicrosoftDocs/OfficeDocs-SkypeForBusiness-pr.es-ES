---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295548"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, not null  <br/> |IDENTIFICADOR del servidor que ha publicado la entrada.  <br/> |
|aplPeerID  <br/> |int, not null  <br/> |IDENTIFICADOR del elemento del mismo nivel al que está conectado el servidor de publicación.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clave principal.  <br/> |
|aplServerID  <br/> |Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.  <br/> |
|aplPeerID  <br/> |Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.  <br/> |
   

