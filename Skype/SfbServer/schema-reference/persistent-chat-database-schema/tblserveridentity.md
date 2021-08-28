---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene los servidores de chat activos del grupo de servidores de chat persistente.
ms.openlocfilehash: 1e6e70835865f2ca6ef992a879dad58011a5170c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613840"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contiene los servidores de chat activos del grupo de servidores de chat persistente.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|serverID  <br/> |int, no NULL  <br/> |Id. de servidor. Corresponde al identificador de instancia del almacén de administración central.  <br/> |
|serverAddress  <br/> |nvarchar (256), no NULL  <br/> |Dirección de servidor con la dirección de Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |La última hora en la que el servidor de canal actualizó esta fila para probar que está ejecutándose.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|serverID  <br/> |Clave principal.  <br/> |
   

