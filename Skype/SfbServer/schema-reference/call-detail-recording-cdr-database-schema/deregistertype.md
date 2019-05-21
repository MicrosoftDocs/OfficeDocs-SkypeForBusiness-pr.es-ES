---
title: Tabla DeRegisterType en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296353"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabla DeRegisterType en Skype empresarial Server 2015
 
La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0--desconocido <br/>  1: deregistro Iniciado por el cliente <br/>  2--registro expirado <br/>  3-cliente bloqueado <br/>  4: atributos de usuario modificados <br/>  5: el registrador preferido ha cambiado <br/>  6--cliente heredado en modo de supervivencia <br/> |
   

