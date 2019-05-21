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
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Las vistas cubren los escenarios más comunes para devolver datos desde la base de datos SQL de calidad. Se recomienda usar vistas para crear informes personalizados en lugar de obtener acceso directamente a las tablas de la base de datos; Esto se debe a que las vistas tienen más probabilidades de mantener la compatibilidad con versiones futuras.
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294757"
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
   

