---
title: Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades en Configuración externa, configure lo siguiente:'
ms.openlocfilehash: d8c800051dcbc6aa2c1a533940c3d3d558ef86ba8db115e557846dc04a08c795
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307161"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
 
Para definir las propiedades en **Configuración externa**, configure lo siguiente:
  
Marque la casilla de verificación **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V** si desea definir direcciones IP y FQDN del grupo de servidores diferentes para conferencia web y audio/vídeo.
  
> [!NOTE]
> Si decide no activar la casilla para direcciones IP y FQDN independientes, debe proporcionar puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral. El único nombre de dominio completo que se va a configurar es el FQDN asociado al servicio perimetral de acceso. 
  
Active la casilla Servicio perimetral **A/V** está habilitado para NAT si desea que el servicio perimetral A/V use una dirección IP y una configuración de traducción de direcciones de red (NAT).
  
Para los servicios perimetrales habilitados, escriba un **FQDN de grupo de servidores** y un puerto en **Puertos**
  
- Defina el FQDN de grupo de servidores del **Servicio perimetral de acceso** y un puerto que identifique el servicio de forma exclusiva.
    
- Defina el FQDN de grupo de servidores del **Servicio perimetral de conferencia web** (si no está seleccionada la opción Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V) y un puerto que identifique el servicio de forma exclusiva.
    
- Defina el FQDN de grupo de servidores del **Servicio perimetral A/V** (si no está seleccionada la opción Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V) y un puerto que identifique el servicio de forma exclusiva.
    
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

