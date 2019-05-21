---
title: Tabla de puertas de enlace en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabla puertas de enlace es una tabla de soporte. Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296185"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabla de puertas de enlace en Skype empresarial Server 2015
 
La tabla puertas de enlace es una tabla de soporte. Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta puerta de enlace.  <br/> |
|**Puerta** <br/> |nvarchar(256)  <br/> | <br/> |Nombre de la puerta de enlace.  <br/> |
   

