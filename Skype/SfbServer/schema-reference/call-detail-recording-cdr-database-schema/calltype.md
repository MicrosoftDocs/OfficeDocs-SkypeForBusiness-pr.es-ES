---
title: Tabla CallType en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabla CallType es una tabla estática donde se almacena la lista de posibles tipos de llamada.
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813370"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabla CallType en Skype Empresarial Server 2015
 
La tabla CallType es una tabla estática donde se almacena la lista de posibles tipos de llamada.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |entero  <br/> |Principal  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0 -- Desconocido <br/>  1- Mensajería instantánea <br/>  2-- Uso compartido de aplicaciones <br/>  3 -- Audio <br/>  4- Audio y vídeo <br/>  5- Transferencia de archivos <br/> |
   

