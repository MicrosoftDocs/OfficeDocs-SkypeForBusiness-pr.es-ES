---
title: Tabla ContentTypes en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabla ContentTypes es una tabla de soporte que almacena una lista de los tipos de contenido que se usan en sesiones de punto a punto y en sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296374"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabla ContentTypes en Skype empresarial Server 2015
 
La tabla ContentTypes es una tabla de soporte que almacena una lista de los tipos de contenido que se usan en sesiones de punto a punto y en sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el tipo de contenido.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nombre del tipo de contenido.  <br/> |
   

