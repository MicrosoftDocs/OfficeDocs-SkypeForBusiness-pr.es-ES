---
title: Detalles de la vista QoE
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Las vistas abarcan la mayoría de los escenarios en los que se recuperan datos de la base de datos de SQL de calidad de la experiencia. Se recomienda usar vistas para crear informes personalizados en lugar de tener acceso directamente a las tablas de base de datos; esto se debe a que es más probable que las vistas mantengan la compatibilidad con versiones anteriores con versiones futuras.
ms.openlocfilehash: d812af701a0073b8be4188b98cd94a66d50c68d3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385388"
---
# <a name="qoe-view-details"></a>Detalles de la vista QoE
 
Las vistas abarcan la mayoría de los escenarios en los que se recuperan datos de la base de datos de SQL de calidad de la experiencia. Se recomienda usar vistas para crear informes personalizados en lugar de tener acceso directamente a las tablas de base de datos; esto se debe a que es más probable que las vistas mantengan la compatibilidad con versiones anteriores con versiones futuras.
  
|**Nombre de vista**|**Descripción**|
|:-----|:-----|
|[Vista AudioStreamDetail](audiostreamdetail.md) <br/> |Almacena información sobre cada transmisión de audio en la base de datos.  <br/> |
|[Vista MediaLine](medialine.md) <br/> |Almacena información sobre cada línea multimedia de la base de datos. Una sesión de audio normalmente contiene una línea de medios de audio. Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería.  <br/> |
|[Vista NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Almacena información sobre la configuración de red.  <br/> |
|[Vista de sesión](session-0.md) <br/> |Almacena información sobre las sesiones que tienen registros en la base de datos.  <br/> |
|[Vista UserAgent](useragent-0.md) <br/> |Almacena información sobre los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.  <br/> |
|[Vista VideoStreamDetail](videostreamdetail.md) <br/> |Almacena información sobre cada transmisión de vídeo en la base de datos.  <br/> |
   

