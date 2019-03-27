---
title: Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades en configuración externa, configure lo siguiente:'
ms.openlocfilehash: 3ebd98c17f7b32af72809375bd17e55514684e6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882351"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
 
Para definir las propiedades en **configuración externa**, configure lo siguiente:
  
Seleccione el **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** casilla de verificación si desea definir distintos IP y FQDN del grupo de direcciones para conferencias web y audio/vídeo.
  
> [!NOTE]
> Si opta por no active la casilla de verificación para separe las direcciones IP y FQDN, debe proporcionar los puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral. El nombre de dominio completo sólo que consiste en configurar es el FQDN asociado con el servicio de servidor perimetral de acceso. 
  
Seleccione el **A / servicio perimetral A/v está habilitado para NAT** casilla de verificación si desea que el / servicio perimetral A/v para usar una red dirección dirección IP de traducción (NAT) y la configuración.
  
Para los Servicios perimetrales habilitados, se escribe un **FQDN del grupo de servidores** y un puerto en **puertos**
  
- Definir el FQDN del grupo de **servicio de servidor perimetral de acceso** y un puerto que identifica el servicio.
    
- Definir el FQDN del grupo de servidores de **servicio perimetral de conferencia Web** (si habilitar separar el FQDN y la dirección IP para la conferencia web y / V no está seleccionada) y un puerto que identifica el servicio.
    
- Definir la **A / servicio perimetral A/v** FQDN del grupo de servidores (si habilitar separar el FQDN y la dirección IP para la conferencia web y / V no está seleccionada) y un puerto que identifica el servicio.
    
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

