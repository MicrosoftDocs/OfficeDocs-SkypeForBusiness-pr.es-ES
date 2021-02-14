---
title: Tabla PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de calidad de experiencia obsoletos se eliminarán automáticamente de la base de datos de QoE. Tenga en cuenta que la información relacionada con la depuración también se puede obtener desde el Shell de administración de Skype Empresarial Server ejecutando el siguiente comando:'
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815810"
---
# <a name="purgesettings-table-qoe"></a>Tabla PurgeSettings (QoE)
 
La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de calidad de experiencia obsoletos se eliminarán automáticamente de la base de datos de QoE. Tenga en cuenta que la información relacionada con la depuración también se puede obtener desde el Shell de administración de Skype Empresarial Server ejecutando el siguiente comando:
  
```PowerShell
Get-CsQoEConfiguration
```

Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Id.** <br/> |entero  <br/> |Principal  <br/> |Identificador único para la colección de valores de depuración de QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando se establece en True (1), Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de QoE. La depuración tendrá lugar todos los días en el tomo especificado por la configuración PurgeHour. Si se establece en False (0), los registros no se depurarán automáticamente desde la base de datos. El valor predeterminado es True.  <br/> |
|**KeepQoEDataForDays** <br/> |entero  <br/> ||Especifica la antigüedad de los registros de QoE (en días) que se depurarán desde la base de datos: si la depuración está habilitada, se eliminarán de la base de datos los registros de QoE anteriores a este valor. El valor predeterminado es 60 días.  <br/> |
|**PurgeHour** <br/> |entero  <br/> ||Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (indicando 10:00 *AM) pero no se permite un valor de 10:30 de 10.5 (indicando 10:30 AM). El valor predeterminado es 1 (1:00 AM). Especifica la hora local del día en que tendrá lugar la depuración de la base de datos. La hora del día se especifica mediante un reloj de 24 horas, representando el 0 la medianoche (12:00 AM) y el 23, las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 AM) pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 AM).  <br/> |
   

