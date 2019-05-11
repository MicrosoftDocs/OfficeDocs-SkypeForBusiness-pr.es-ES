---
title: Tabla PurgeSettings
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La tabla PurgeSettings contiene información que especifica si (y cuando) registros de detalles de llamadas no actualizada se eliminarán automáticamente de la base de datos de CDR. Tenga en cuenta que la información relacionada con la depuración también puede obtenerse desde dentro de la Skype para Business Server 2015, ejecute el comando siguiente:'
ms.openlocfilehash: f1e982d50ab029ec2756e8fb4a92f5c01dc327b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930724"
---
# <a name="purgesettings-table"></a>Tabla PurgeSettings
 
La tabla PurgeSettings contiene información que especifica si (y cuando) registros de detalles de llamadas no actualizada se eliminarán automáticamente de la base de datos de CDR. Tenga en cuenta que la información relacionada con la depuración también puede obtenerse desde dentro de la Skype para Business Server 2015, ejecute el comando siguiente:
  
```
Get-CsCdrConfiguration
```

Los administradores deben tratar la tabla PurgeSettings como de solo lectura: los cambios realizados en la configuración de depuración de todos los detalles de llamada solo deben hacerse con los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Id.** <br/> |int  <br/> |Primary  <br/> |Identificador único para la colección de CDR valores de depuración.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando se establece en True (1) Skype para Business Server 2015 periódicamente depurará obsoletos los registros de la base de datos de CDR. Depuración se llevará a cabo cada día a la tomo especificado por la configuración de PurgeHour. Si se establece en False (0), a continuación, registros no se purgarán automáticamente desde la base de datos. El valor predeterminado es True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Especifica la antigüedad de los registros de CDR (en días) que se purgarán desde la base de datos: si está habilitada la depuración, se eliminarán los registros de CDR anteriores a este valor de la base de datos. El valor predeterminado es 60 días.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Especifica la antigüedad de los registros de informe de errores (en días) que se purgarán desde la base de datos: si está habilitada la depuración, se eliminarán los registros de informe de error anteriores a este valor de la base de datos. El valor predeterminado es 60 días.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica la hora local del día cuando la depuración de base de datos llevará a cabo. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 AM), pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 2 (2:00 AM).  <br/> |
   

