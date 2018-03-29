---
title: Tabla DeRegisterType en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de usuario posible anular registra tipos como 'cliente inicia', 'registro ha caducado' o 'cliente dejado de responder'.
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabla DeRegisterType en Skype para Business Server 2015
 
La tabla DeRegisterType es una tabla estática que almacena la lista de usuario posible anular registra tipos como 'cliente inicia', 'registro ha caducado' o 'cliente dejado de responder'.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0--desconocido <br/>  1: el cliente inicia la anulación de registro <br/>  2--registro caducado <br/>  3 - cliente bloqueado <br/>  4--atributos de usuario cambiados <br/>  5 - preferido registrador cambiado <br/>  6--Cliente heredado en modo de supervivencia <br/> |
   

