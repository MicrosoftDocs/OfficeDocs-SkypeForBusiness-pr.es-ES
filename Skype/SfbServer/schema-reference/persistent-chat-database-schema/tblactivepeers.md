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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814718"
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
   

