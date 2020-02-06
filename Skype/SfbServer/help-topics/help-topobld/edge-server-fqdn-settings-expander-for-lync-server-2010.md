---
title: Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades en configuración externa, configure lo siguiente:'
ms.openlocfilehash: 95e55625ec698d8762832e812a79547daf4d2bcf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820062"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
 
Para definir las propiedades en **configuración externa**, configure lo siguiente:
  
Seleccione las casillas de verificación **Habilitar FQDN e dirección IP para las conferencias web y a/V** si desea definir distintas direcciones IP y FQDN de grupo para conferencias web y audio/vídeo.
  
> [!NOTE]
> Si decide no activar la casilla de verificación de direcciones FQDN e IP separadas, debe proporcionar puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral. El único nombre de dominio completo que debe configurarse es el FQDN asociado con el servicio perimetral de acceso. 
  
Active la casilla de verificación el **servicio de borde a/v es NAT habilitado** si quiere que el servicio perimetral a/v use una configuración y una dirección IP de traducción de direcciones de red (NAT).
  
Para los servicios perimetrales habilitados, escriba un **FQDN de grupo** y un puerto en **puertos**
  
- Defina el FQDN del grupo de **servicio perimetral de Access** y un puerto que identifique de forma única el servicio.
    
- Defina el FQDN del grupo de **servicios perimetrales de conferencia web** (si habilitar la dirección IP y el FQDN separados para conferencias web, y a/V no está seleccionada) y un puerto que identifique de manera única el servicio.
    
- Defina el FQDN del grupo de **servicios perimetrales a/V** (si habilitar el FQDN y la dirección IP separados para las conferencias web y no se selecciona a/V) y un puerto que identifique de forma única el servicio.
    
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

