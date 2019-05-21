---
title: Tabla PurgeSettings
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de detalles de llamadas obsoletas se eliminarán automáticamente de la base de datos de CDR. Tenga en cuenta que la información relacionada con la purga también puede obtenerse desde el servidor de Skype para empresas 2015 ejecutando el siguiente comando:'
ms.openlocfilehash: 6aac92555dda6875f23a177bb09384f453369846
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295926"
---
# <a name="purgesettings-table"></a>Tabla PurgeSettings
 
La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de detalles de llamadas obsoletas se eliminarán automáticamente de la base de datos de CDR. Tenga en cuenta que la información relacionada con la purga también puede obtenerse desde el servidor de Skype para empresas 2015 ejecutando el siguiente comando:
  
```
Get-CsCdrConfiguration
```

Los administradores deben tratar la tabla PurgeSettings como de solo lectura: los cambios en la configuración de depuración de detalles de llamada solo deben realizarse con los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Identificar** <br/> |int  <br/> |Primary  <br/> |Identificador único de la colección de configuración de purga de CDR.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando se establece en true (1), Skype empresarial Server 2015 purgará periódicamente los registros obsoletos de la base de datos de CDR. La purga se realizará cada día a la tomé especificada por el valor PurgeHour. Si se establece en false (0), los registros no se purgarán automáticamente de la base de datos. El valor predeterminado es True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Especifica la antigüedad de los registros de CDR (en días) que se purgarán de la base de datos: Si la purga está habilitada, los registros CDR anteriores a este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Especifica los registros de informe de antigüedad de errores (en días) que se purgarán de la base de datos: Si la purga está habilitada, los registros de informe de errores anteriores a este valor se quitarán de la base de datos. El valor predeterminado es 60 días.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se puede especificar la hora del día: un valor de 10 (indicando 10:00 A.M.), pero no se permite un valor de 10:30 de 10,5 (que indica 10:30 A.M.). El valor predeterminado es 2 (2:00 AM).  <br/> |
   

