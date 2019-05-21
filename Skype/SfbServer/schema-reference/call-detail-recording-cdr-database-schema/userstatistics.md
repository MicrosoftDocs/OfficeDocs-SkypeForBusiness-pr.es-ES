---
title: Tabla UserStatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es una tabla de soporte. Cada registro de la tabla almacena información sobre el uso del sistema por un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295695"
---
# <a name="userstatistics-table"></a>Tabla UserStatistics
 
La tabla UserStatistics es una tabla de soporte. Cada registro de la tabla almacena información sobre el uso del sistema por un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Iddeusuario** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este usuario.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||La última vez que el usuario inició sesión.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||La última vez que el usuario organizó una conferencia.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||La última vez que el usuario experimentó un error de llamada.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||La última vez que el usuario experimentó un error de llamada como organizador de la Conferencia.  <br/> |
   

