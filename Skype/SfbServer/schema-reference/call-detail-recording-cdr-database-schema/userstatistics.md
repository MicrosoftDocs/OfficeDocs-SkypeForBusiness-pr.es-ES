---
title: Tabla UserStatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: En la tabla UserStatistics es una tabla de apoyo. Cada registro en la tabla almacena información sobre el uso de un usuario concreto del sistema. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213042"
---
# <a name="userstatistics-table"></a>Tabla UserStatistics
 
En la tabla UserStatistics es una tabla de apoyo. Cada registro en la tabla almacena información sobre el uso de un usuario concreto del sistema. En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este usuario.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Modificó por última vez el usuario iniciado sesión.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez que el usuario organizó una conferencia.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario tuvo un error de llamada.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario tuvo un error de llamada como un organizador de la conferencia.  <br/> |
   

