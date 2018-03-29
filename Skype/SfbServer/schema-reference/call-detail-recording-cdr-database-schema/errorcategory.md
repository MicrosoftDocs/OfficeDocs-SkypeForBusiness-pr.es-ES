---
title: Tabla ErrorCategory en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabla ErrorCategory contiene el nombre descriptivo de cada Skype para clasificación diagnóstico Business Server 2015. De forma predeterminada, Skype para el año 2015 de Business Server utiliza las siguientes clasificaciones:'
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabla ErrorCategory en Skype para Business Server 2015
 
La tabla ErrorCategory contiene el nombre descriptivo de cada Skype para clasificación diagnóstico Business Server 2015. De forma predeterminada, Skype para el año 2015 de Business Server utiliza las siguientes clasificaciones:
  
- 0--correcto
    
- 1--error
    
- 2 - Error inesperado
    
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**IdCategoría** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único para la clasificación.  <br/> |
|**Nombre.** <br/> |nvarchar(256)  <br/> || Valor y nombre descriptivo asignado a la clasificación. Los valores permitidos son: <br/>  0--correcto <br/>  1--error <br/>  2 - Error inesperado <br/> |
   

