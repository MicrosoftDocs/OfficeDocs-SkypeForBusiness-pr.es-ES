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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815298"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabla DeRegisterType en Skype empresarial Server 2015
 
La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0--desconocido <br/>  1: deregistro Iniciado por el cliente <br/>  2--registro expirado <br/>  3-cliente bloqueado <br/>  4: atributos de usuario modificados <br/>  5: el registrador preferido ha cambiado <br/>  6--cliente heredado en modo de supervivencia <br/> |
   

