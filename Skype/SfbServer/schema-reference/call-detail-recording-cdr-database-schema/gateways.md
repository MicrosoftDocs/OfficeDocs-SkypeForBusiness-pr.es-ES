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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabla puertas de enlace es una tabla de soporte. Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815168"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabla de puertas de enlace en Skype empresarial Server 2015
 
La tabla puertas de enlace es una tabla de soporte. Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta puerta de enlace.  <br/> |
|**Puerta** <br/> |nvarchar(256)  <br/> | <br/> |Nombre de la puerta de enlace.  <br/> |
   

