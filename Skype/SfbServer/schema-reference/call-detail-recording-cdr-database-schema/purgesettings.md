---
title: Tabla PurgeSettings
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La tabla PurgeSettings contiene información que especifica si los registros de detalles de llamadas obsoletos se eliminarán automáticamente de la base de datos de CDR (y, en caso de que sí, cuándo). Tenga en cuenta que la información relacionada con la depuración también se puede obtener desde Skype Empresarial Server 2015 ejecutando el siguiente comando:'
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823170"
---
# <a name="purgesettings-table"></a>Tabla PurgeSettings
 
La tabla PurgeSettings contiene información que especifica si los registros de detalles de llamadas obsoletos se eliminarán automáticamente de la base de datos de CDR (y, en caso de que sí, cuándo). Tenga en cuenta que la información relacionada con la depuración también se puede obtener desde Skype Empresarial Server 2015 ejecutando el siguiente comando:
  
```PowerShell
Get-CsCdrConfiguration
```

Los administradores deben tratar la tabla PurgeSettings como de solo lectura: los cambios en la configuración de depuración de detalles de llamadas solo deben realizarse con los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |entero  <br/> |Principal  <br/> |Identificador único de la recopilación de opciones de configuración para depuración de CDR.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando se establece en True (1), Skype Empresarial Server 2015 purgará periódicamente los registros obsoletos de la base de datos de CDR. La depuración tendrá lugar todos los días en el tomo especificado por la configuración PurgeHour. Si se establece en False (0), los registros no se depurarán automáticamente desde la base de datos. El valor predeterminado es True.  <br/> |
|**KeepCallDetailForDays** <br/> |entero  <br/> ||Especifica la antigüedad de los registros de CDR (en días) que se depurarán de la base de datos: si se habilita la depuración, los registros de CDR cuya antigüedad sea mayor que este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.  <br/> |
|**KeepErrorReportForDays** <br/> |entero  <br/> ||Especifica la antigüedad de los registros de informe de errores (en días) que se depurarán de la base de datos: si se habilita la depuración, los registros de informe de errores cuya antigüedad sea mayor que este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.  <br/> |
|**PurgeHour** <br/> |entero  <br/> ||Especifica la hora local del día a la que se realizará la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se pueden especificar horas en formato convencional: se permite un valor 10 (que indicaría las 10:00 a.m.), pero no un valor 10:30 o 10.5 (que indicaría las 10:30 a.m.). El valor predeterminado es 2 (2:00 AM).  <br/> |
   

