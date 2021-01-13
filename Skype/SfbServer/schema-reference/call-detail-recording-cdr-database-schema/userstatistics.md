---
title: Tabla UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es una tabla auxiliar. Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813110"
---
# <a name="userstatistics-table"></a>Tabla UserStatistics
 
La tabla UserStatistics es una tabla auxiliar. Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica a este usuario.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Hora de la última vez que el usuario inició sesión.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez que el usuario organizó una conferencia.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario tuvo un error de llamada.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario tuvo un error de llamada como organizador de conferencia.  <br/> |
   

