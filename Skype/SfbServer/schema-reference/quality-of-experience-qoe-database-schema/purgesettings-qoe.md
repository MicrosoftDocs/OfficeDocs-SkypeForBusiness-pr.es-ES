---
title: Tabla PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La tabla PurgeSettings contiene información que especifica si (y cuando) los registros de calidad de la experiencia no actualizados se eliminarán automáticamente de la base de datos de QoE. Tenga en cuenta que información relacionada con la depuración también puede obtenerse desde dentro de la Skype para Shell de administración de Business Server, ejecute el comando siguiente:'
ms.openlocfilehash: 2b78f066907d6d0763fab7faa9d378e51f3715fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924790"
---
# <a name="purgesettings-table-qoe"></a>Tabla PurgeSettings (QoE)
 
La tabla PurgeSettings contiene información que especifica si (y cuando) los registros de calidad de la experiencia no actualizados se eliminarán automáticamente de la base de datos de QoE. Tenga en cuenta que información relacionada con la depuración también puede obtenerse desde dentro de la Skype para Shell de administración de Business Server, ejecute el comando siguiente:
  
```
Get-CsQoEConfiguration
```

En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Identificador único para la colección de QoE valores de depuración.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando establece en True (1) Microsoft Lync Server 2013 periódicamente depurará registros obsoletos de la base de datos de QoE. Depuración se llevará a cabo cada día a la tomo especificado por la configuración de PurgeHour. Si se establece en False (0), a continuación, registros no se purgarán automáticamente desde la base de datos. El valor predeterminado es True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Especifica la antigüedad de los registros de QoE (en días) que se purgarán desde la base de datos: si está habilitada la depuración, se quitarán los registros de QoE anteriores a este valor desde la base de datos. El valor predeterminado es 60 días.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica la hora local del día cuando la depuración de base de datos llevará a cabo. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 AM), pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 AM). Especifica la hora local del día cuando la depuración de base de datos llevará a cabo. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 AM), pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 AM).  <br/> |
   

