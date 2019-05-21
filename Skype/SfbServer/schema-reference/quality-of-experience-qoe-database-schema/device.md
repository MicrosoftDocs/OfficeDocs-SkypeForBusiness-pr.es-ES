---
title: Tabla Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabla de dispositivos es una tabla de soporte que almacena información sobre los diversos dispositivos de captura o de representación. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295009"
---
# <a name="device-table"></a>Tabla Device
 
La tabla de dispositivos es una tabla de soporte que almacena información sobre los diversos dispositivos de captura o de representación. Cada registro de la tabla representa un dispositivo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType es único  <br/> |Nombre del dispositivo.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType es único  <br/> |Tipo de dispositivo. 1 es un dispositivo de captura, 0 es un dispositivo de representación.  <br/> |
   

