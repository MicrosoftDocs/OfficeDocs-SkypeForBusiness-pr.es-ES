---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 0207871100904af348b4c1a51ed2c6f4574249d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398614"
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
   

