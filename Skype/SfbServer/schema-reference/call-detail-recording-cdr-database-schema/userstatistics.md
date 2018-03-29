---
title: Tabla UserStatistics
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es un auxiliar. Cada registro de la tabla almacena información acerca del uso de un usuario individual del sistema. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a>Tabla UserStatistics
 
La tabla UserStatistics es un auxiliar. Cada registro de la tabla almacena información acerca del uso de un usuario individual del sistema. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ID de usuario** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este usuario.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Última vez que el usuario conectado.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez que el usuario organizó una conferencia.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario error de llamada.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que el usuario presentó un error de llamada como un organizador de la conferencia.  <br/> |
   

