---
title: Tabla UserStatistics
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es una tabla auxiliar. Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 4dcd7c8d14bdaf3c8a9844aab3057d356a53fc91
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857217"
---
# <a name="userstatistics-table"></a>Tabla UserStatistics
 
La tabla UserStatistics es una tabla auxiliar. Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica a este usuario.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Hora de la última vez que el usuario inició sesión.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez que el usuario organizó una conferencia.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario tuvo un error de llamada.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario tuvo un error de llamada como organizador de conferencia.  <br/> |
   

