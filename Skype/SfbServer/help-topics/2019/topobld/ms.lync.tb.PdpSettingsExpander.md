---
title: Expansor de configuración de control de admisión de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Después de configurar la red para el control de admisión de llamadas, deberá habilitarlo para forzar las limitaciones de ancho de banda.
ms.openlocfilehash: 62d77de88a6bf0f0195e1c54eef4e5cac6d2a409
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701775"
---
# <a name="call-admission-control-settings-expander"></a>Expansor de configuración de control de admisión de llamadas
 
El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Después de configurar la red para el control de admisión de llamadas, deberá habilitarlo para forzar las limitaciones de ancho de banda. 
  
> [!NOTE]
> También puede usar el panel de control o los cmdlets del Shell de administración para habilitar CAC. 
  
En la sección **Configuración del control de admisión de llamadas** del cuadro de diálogo **Editar propiedades** del sitio, puede cambiar las siguientes opciones:
  
- **Habilitar control de admisión de llamadas** Seleccione esta opción para habilitar CAC. No la seleccione la opción para deshabilitar el control de admisión de llamadas en toda la red. Para habilitarlo, debe tener la red convenientemente configurada para ello. Para obtener más información, consulte [implementar el control de admisión de llamadas en Skype empresarial Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) en la documentación de implementación.
    
- **Grupo de servidores front-end para ejecutar el control de admisión de llamadas** Si ha habilitado CAC, puede cambiar el grupo que lo ejecuta. Seleccione el grupo en la lista desplegable.
    

