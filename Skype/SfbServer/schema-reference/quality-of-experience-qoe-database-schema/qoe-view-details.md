---
title: Detalles de la vista QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Las vistas tratan los escenarios más comunes para devolver los datos de la base de datos SQL QoE. Se recomienda vistas usadas para generación de informes personalizados en lugar de obteniendo acceso directamente a las tablas de base de datos; Esto es debido a que las vistas son más probables mantener la compatibilidad con versiones futuras con versiones anteriores.
ms.openlocfilehash: 2726900a1fc31c6e69571123c87137b3291a507e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924867"
---
# <a name="qoe-view-details"></a>Detalles de la vista QoE
 
Las vistas tratan los escenarios más comunes para devolver los datos de la base de datos SQL QoE. Se recomienda vistas usadas para generación de informes personalizados en lugar de obteniendo acceso directamente a las tablas de base de datos; Esto es debido a que las vistas son más probables mantener la compatibilidad con versiones futuras con versiones anteriores.
  
|**Nombre de la vista**|**Descripción**|
|:-----|:-----|
|[Vista AudioStreamDetail](audiostreamdetail.md) <br/> |Almacena información acerca de cada secuencia de audio en la base de datos.  <br/> |
|[Vista MediaLine](medialine.md) <br/> |Almacena información acerca de cada línea de medios en la base de datos. Normalmente, una sesión de audio contiene una línea de medios de audio. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de medios de audio y una única línea de medios de vídeo. Sin embargo, la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo para conferencias o si se usa la vista de galería.  <br/> |
|[Vista NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Almacena información acerca de la configuración de red.  <br/> |
|[Vista de sesión](session-0.md) <br/> |Almacena información acerca de las sesiones que tienen registros en la base de datos.  <br/> |
|[Vista UserAgent](useragent-0.md) <br/> |Almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.  <br/> |
|[Vista VideoStreamDetail](videostreamdetail.md) <br/> |Almacena información acerca de cada secuencia de vídeo en la base de datos.  <br/> |
   

