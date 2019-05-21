---
title: Tabla CallType en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamadas.
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296563"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabla CallType en Skype empresarial Server 2015
 
La tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamadas.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--desconocido <br/>  1-mensajería instantánea <br/>  2: uso compartido de aplicaciones <br/>  3: audio <br/>  4-audio y vídeo <br/>  5-transferencia de archivos <br/> |
   

