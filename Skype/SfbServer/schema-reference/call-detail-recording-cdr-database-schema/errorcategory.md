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
description: 'La tabla ErrorCategory contiene el nombre descriptivo de cada Skype Empresarial Server clasificación de diagnóstico de 2015. De forma predeterminada, Skype Empresarial Server 2015 usa las siguientes clasificaciones:'
ms.openlocfilehash: 68114e96e04ca8e2cb45fbb2b9ba0b3934df4e363700f8a872f05cb1aa0e8a37
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347775"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabla ErrorCategory en Skype Empresarial Server 2015
 
La tabla ErrorCategory contiene el nombre descriptivo de cada Skype Empresarial Server clasificación de diagnóstico de 2015. De forma predeterminada, Skype Empresarial Server 2015 usa las siguientes clasificaciones:
  
- 0 -- Éxito
    
- 1: Error esperado
    
- 2: error inesperado
    
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Principal  <br/> |Identificador único de la clasificación.  <br/> |
|**Nombre** <br/> |nvarchar(256)  <br/> || Valor y nombre descriptivo asignados a la clasificación. Los valores permitidos son: <br/>  0 -- Éxito <br/>  1: Error esperado <br/>  2: error inesperado <br/> |
   

