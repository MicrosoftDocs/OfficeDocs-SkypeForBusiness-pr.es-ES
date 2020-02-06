---
title: Detalles de la vista QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Las vistas cubren los escenarios más comunes para devolver datos desde la base de datos SQL de calidad. Se recomienda usar vistas para crear informes personalizados en lugar de obtener acceso directamente a las tablas de la base de datos; Esto se debe a que las vistas tienen más probabilidades de mantener la compatibilidad con versiones futuras.
ms.openlocfilehash: d207c2cff86c398fed62023b30d193e974cbca7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807178"
---
# <a name="qoe-view-details"></a>Detalles de la vista QoE
 
Las vistas cubren los escenarios más comunes para devolver datos desde la base de datos SQL de calidad. Se recomienda usar vistas para crear informes personalizados en lugar de obtener acceso directamente a las tablas de la base de datos; Esto se debe a que las vistas tienen más probabilidades de mantener la compatibilidad con versiones futuras.
  
|**Nombre de la vista**|**Descripción**|
|:-----|:-----|
|[Vista AudioStreamDetail](audiostreamdetail.md) <br/> |Almacena información sobre cada secuencia de audio de la base de datos.  <br/> |
|[Vista MediaLine](medialine.md) <br/> |Almacena información sobre cada línea de medios de la base de datos. Una sesión de audio normalmente contiene una línea multimedia de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo; sin embargo, la sesión podría contener dos líneas multimedia de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.  <br/> |
|[Vista NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Almacena información sobre la configuración de red.  <br/> |
|[Vista de sesión](session-0.md) <br/> |Almacena información sobre las sesiones que tienen registros en la base de datos.  <br/> |
|[Vista UserAgent](useragent-0.md) <br/> |Almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos.  <br/> |
|[Vista VideoStreamDetail](videostreamdetail.md) <br/> |Almacena información sobre cada secuencia de vídeo de la base de datos.  <br/> |
   

