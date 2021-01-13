---
title: Tabla ErrorCategory en Skype Empresarial Server 2015
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
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabla ErrorCategory contiene el nombre descriptivo de cada clasificación de diagnóstico de Skype Empresarial Server 2015. De forma predeterminada, Skype Empresarial Server 2015 usa las siguientes clasificaciones:'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813150"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabla ErrorCategory en Skype Empresarial Server 2015
 
La tabla ErrorCategory contiene el nombre descriptivo de cada clasificación de diagnóstico de Skype Empresarial Server 2015. De forma predeterminada, Skype Empresarial Server 2015 usa las siguientes clasificaciones:
  
- 0 -- Éxito
    
- 1-- Error esperado
    
- 2- Error inesperado
    
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Principal  <br/> |Identificador único de la clasificación.  <br/> |
|**Nombre** <br/> |nvarchar(256)  <br/> || Valor y nombre descriptivo asignados a la clasificación. Los valores permitidos son: <br/>  0 -- Éxito <br/>  1-- Error esperado <br/>  2- Error inesperado <br/> |
   

