---
title: Tabla DeRegisterType en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posible usuario desaprovisionamiento registra tipos, como 'iniciado por cliente', 'registro expirado' o 'cliente interrumpida'.
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901176"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabla DeRegisterType en Skype para Business Server 2015
 
La tabla DeRegisterType es una tabla estática que almacena la lista de posible usuario desaprovisionamiento registra tipos, como 'iniciado por cliente', 'registro expirado' o 'cliente interrumpida'.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0--Unknown (desconocido) <br/>  1--anulación del registro iniciada por el cliente <br/>  2--registro expirado <br/>  3 - cliente bloqueado <br/>  4--atributos de usuario ha cambiado <br/>  5 - registrador preferido modificado <br/>  6--El cliente heredado en modo de supervivencia <br/> |
   

