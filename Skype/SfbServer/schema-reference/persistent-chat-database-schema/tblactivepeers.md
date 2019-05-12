---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929878"
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
   

