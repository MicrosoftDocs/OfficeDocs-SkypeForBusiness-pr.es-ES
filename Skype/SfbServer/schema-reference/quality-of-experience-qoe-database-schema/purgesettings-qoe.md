---
title: Tabla PurgeSettings (QoE)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros obsoletos de calidad de la experiencia se eliminarán automáticamente de la base de datos de calidad. Tenga en cuenta que información relacionada con la purga también puede obtenerse desde dentro el Skype para el Shell de administración de servidor empresarial ejecutando el comando siguiente:'
ms.openlocfilehash: 1acccbd796e20f099df895260cb34f9597718cdd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table-qoe"></a>Tabla PurgeSettings (QoE)
 
La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros obsoletos de calidad de la experiencia se eliminarán automáticamente de la base de datos de calidad. Tenga en cuenta que información relacionada con la purga también puede obtenerse desde dentro el Skype para el Shell de administración de servidor empresarial ejecutando el comando siguiente:
  
```
Get-CsQoEConfiguration
```

Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ID.** <br/> |int  <br/> |Primary  <br/> |Identificador único de la colección de QoE purgar la configuración.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando establecida en True (1) Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de calidad de la experiencia. Purga se realizará cada día en la Tomé especificada por el valor de PurgeHour. Si se establece en False (0), a continuación, registros no se purgará automáticamente desde la base de datos. El valor predeterminado es True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Especifica la antigüedad de los registros de calidad (en días) que se purgan desde la base de datos: si está habilitada la depuración, se eliminarán los registros de calidad de la experiencia anteriores a este valor de la base de datos. El valor predeterminado es de 60 días.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica la hora local del día cuando la depuración de base de datos llevará a cabo. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Nota sólo se puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 A.M.), pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 A.M.). Especifica la hora local del día cuando la depuración de base de datos llevará a cabo. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Nota sólo se puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 A.M.), pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 A.M.).  <br/> |
   

