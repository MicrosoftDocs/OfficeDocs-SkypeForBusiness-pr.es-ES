---
title: Tabla de categoría de error de Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'En la tabla de la categoría de error contiene el nombre descriptivo para cada Skype para la clasificación de diagnóstico Business Server 2015. De forma predeterminada, Skype para Business Server 2015 usa las siguientes clasificaciones:'
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213119"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabla de categoría de error de Skype para Business Server 2015
 
En la tabla de la categoría de error contiene el nombre descriptivo para cada Skype para la clasificación de diagnóstico Business Server 2015. De forma predeterminada, Skype para Business Server 2015 usa las siguientes clasificaciones:
  
- 0--correcto
    
- 1--error esperado
    
- 2 - Error inesperado
    
En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único para la clasificación.  <br/> |
|**Nombre.** <br/> |nvarchar(256)  <br/> || Valor y nombre descriptivo asignado a la clasificación. Los valores permitidos son: <br/>  0--correcto <br/>  1--error esperado <br/>  2 - Error inesperado <br/> |
   

