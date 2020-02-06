---
title: Tabla ErrorCategory en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabla ErrorCategory contiene el nombre descriptivo de cada clasificación de diagnóstico de Skype empresarial Server 2015. De forma predeterminada, Skype empresarial Server 2015 usa las siguientes clasificaciones:'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815258"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabla ErrorCategory en Skype empresarial Server 2015
 
La tabla ErrorCategory contiene el nombre descriptivo de cada clasificación de diagnóstico de Skype empresarial Server 2015. De forma predeterminada, Skype empresarial Server 2015 usa las siguientes clasificaciones:
  
- 0---correcto
    
- 1: error esperado
    
- 2-Error inesperado
    
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**IdCategoría** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único de la clasificación.  <br/> |
|**Nombre.** <br/> |nvarchar(256)  <br/> || Valor y nombre descriptivo asignados a la clasificación. Los valores permitidos son: <br/>  0---correcto <br/>  1: error esperado <br/>  2-Error inesperado <br/> |
   

