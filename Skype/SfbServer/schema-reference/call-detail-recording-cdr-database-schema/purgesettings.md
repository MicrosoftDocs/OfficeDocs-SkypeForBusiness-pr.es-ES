---
title: Tabla PurgeSettings
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La tabla PurgeSettings contiene información que especifica si (y cuándo) llamada anticuados registros de detalle se eliminarán automáticamente de la base de datos de CDR. Tenga en cuenta que información relacionada con la purga también puede obtenerse desde dentro el Skype para Business Server 2015 ejecutando el comando siguiente:'
ms.openlocfilehash: a28ac592fb1d5d2001e7f297f37fdc1938f25643
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table"></a>Tabla PurgeSettings
 
La tabla PurgeSettings contiene información que especifica si (y cuándo) llamada anticuados registros de detalle se eliminarán automáticamente de la base de datos de CDR. Tenga en cuenta que información relacionada con la purga también puede obtenerse desde dentro el Skype para Business Server 2015 ejecutando el comando siguiente:
  
```
Get-CsCdrConfiguration
```

Los administradores deben tratar la tabla PurgeSettings como de sólo lectura: cambios en la configuración de depuración de detalle llamada sólo deberá hacerse uso de los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [CsCdrConfiguration del conjunto](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Id.** <br/> |int  <br/> |Primary  <br/> |Identificador único de la colección de CDR purgar la configuración.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando se establece en True (1) Skype para Business Server 2015 periódicamente purgará anticuados los registros de la base de datos de CDR. Purga se realizará cada día en la Tomé especificada por el valor de PurgeHour. Si se establece en False (0), a continuación, registros no se purgará automáticamente desde la base de datos. El valor predeterminado es True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Especifica la antigüedad de los registros de CDR (en días) que se purgan desde la base de datos: si está habilitada la depuración, se eliminarán los registros de CDR anteriores a este valor de la base de datos. El valor predeterminado es de 60 días.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Especifica la antigüedad de los registros de informe de errores (en días) que se purgan desde la base de datos: si está habilitada la depuración, se eliminarán los registros de informe de error anteriores a este valor de la base de datos. El valor predeterminado es de 60 días.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica la hora local del día cuando la depuración de base de datos llevará a cabo. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Nota sólo se puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 A.M.), pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 2 (2:00 AM).  <br/> |
   

