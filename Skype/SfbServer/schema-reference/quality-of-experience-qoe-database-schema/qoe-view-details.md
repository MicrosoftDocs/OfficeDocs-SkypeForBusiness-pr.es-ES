---
title: Ver detalles de la calidad de la experiencia
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Vistas de cubren los escenarios más comunes para devolver los datos de la base de datos SQL QoE. Se recomienda vistas utilizadas para generar informes personalizados en lugar de obtener acceso directo a las tablas de la base de datos; eso es porque las vistas son más propensos a mantener la compatibilidad con versiones futuras al revés.
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a>Ver detalles de la calidad de la experiencia
 
Vistas de cubren los escenarios más comunes para devolver los datos de la base de datos SQL QoE. Se recomienda vistas utilizadas para generar informes personalizados en lugar de obtener acceso directo a las tablas de la base de datos; eso es porque las vistas son más propensos a mantener la compatibilidad con versiones futuras al revés.
  
|**Nombre de la vista**|**Descripción**|
|:-----|:-----|
|[Vista de AudioStreamDetail](audiostreamdetail.md) <br/> |Almacena información acerca de cada secuencia de audio en la base de datos.  <br/> |
|[Vista de MediaLine](medialine.md) <br/> |Almacena información acerca de cada línea de medios en la base de datos. Una sesión de audio normalmente contiene una línea de audio multimedia. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de media audio y una línea de vídeo; Sin embargo, la sesión puede contener dos líneas de vídeo si se utiliza un dispositivo de conferencias o si se utiliza la vista Galería.  <br/> |
|[Vista de NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Almacena información acerca de la configuración de red.  <br/> |
|[Vista de sesión](session-0.md) <br/> |Almacena información acerca de las sesiones que tengan registros en la base de datos.  <br/> |
|[UserAgent vista](useragent-0.md) <br/> |Almacena información acerca de los agentes de usuario que han participado en sesiones que tengan registros en la base de datos.  <br/> |
|[Vista de VideoStreamDetail](videostreamdetail.md) <br/> |Almacena información acerca de cada secuencia de vídeo en la base de datos.  <br/> |
   

