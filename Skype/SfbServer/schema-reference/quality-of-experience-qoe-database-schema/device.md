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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabla de dispositivos es una tabla de soporte que almacena información sobre los diversos dispositivos de captura o de representación. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810158"
---
# <a name="device-table"></a>Tabla Device
 
La tabla de dispositivos es una tabla de soporte que almacena información sobre los diversos dispositivos de captura o de representación. Cada registro de la tabla representa un dispositivo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType es único  <br/> |Nombre del dispositivo.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType es único  <br/> |Tipo de dispositivo. 1 es un dispositivo de captura, 0 es un dispositivo de representación.  <br/> |
   

