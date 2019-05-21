---
title: Tabla PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La tabla PurgeSettings contiene información que especifica si (y cuándo) la calidad de los registros de experiencia se eliminará automáticamente de la base de datos de QoE. Tenga en cuenta que la información relacionada con la purga también puede obtenerse en el shell de administración de Skype empresarial Server ejecutando el siguiente comando:'
ms.openlocfilehash: ec957a445c59020e8909beeb8cb3dcd12f662d68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294778"
---
# <a name="purgesettings-table-qoe"></a>Tabla PurgeSettings (QoE)
 
La tabla PurgeSettings contiene información que especifica si (y cuándo) la calidad de los registros de experiencia se eliminará automáticamente de la base de datos de QoE. Tenga en cuenta que la información relacionada con la purga también puede obtenerse en el shell de administración de Skype empresarial Server ejecutando el siguiente comando:
  
```
Get-CsQoEConfiguration
```

Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Identificador único para la recopilación de configuración de purga de QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Cuando se establece en true (1), Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de calidad. La purga se realizará cada día a la tomé especificada por el valor PurgeHour. Si se establece en false (0), los registros no se purgarán automáticamente de la base de datos. El valor predeterminado es True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Especifica los registros de edad de calidad (en días) que se purgarán de la base de datos: Si la purga está habilitada, los registros de QoE anteriores a este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se puede especificar la hora del día: un valor de 10 (indicando 10:00 A.M.), pero no se permite un valor de 10:30 de 10,5 (que indica 10:30 A.M.). El valor predeterminado es 1 (1:00 A.M.). Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se puede especificar la hora del día: un valor de 10 (indicando 10:00 A.M.), pero no se permite un valor de 10:30 de 10,5 (que indica 10:30 A.M.). El valor predeterminado es 1 (1:00 A.M.).  <br/> |
   

