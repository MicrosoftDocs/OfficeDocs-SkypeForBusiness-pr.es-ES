---
title: Expansor de configuración de control de admisión de llamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red para CAC, el control de admisión de llamadas debe habilitarse para que se puedan aplicar las limitaciones de ancho de banda.
ms.openlocfilehash: 1278cb19e4c8df047d97e5f391ca940255f094cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833120"
---
# <a name="call-admission-control-settings-expander"></a>Expansor de configuración de control de admisión de llamadas
 
El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red para CAC, el control de admisión de llamadas debe habilitarse para que se puedan aplicar las limitaciones de ancho de banda. 
  
> [!NOTE]
> También puede usar el panel de control o los cmdlets del Shell de administración para habilitar el CAC. 
  
En la sección **Configuración del control de admisión de llamadas** del cuadro de diálogo **Editar propiedades** del sitio, puede cambiar las opciones siguientes:
  
- **Habilitar el control de admisión de llamadas** Seleccione esta opción para habilitar el CAC. Anule la selección de esta opción para deshabilitar el control de admisión de llamadas en toda la red. Para habilitar el control de admisión de llamadas, la red debe haberse configurado para CAC. Para obtener más información, consulte [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) en la documentación sobre implementación.
    
- **Grupo de servidores front-end para ejecutar el control de admisión de llamadas** Si habilitó el CAC, puede cambiar el grupo de servidores que lo ejecuta. Seleccione el grupo de servidores en la lista desplegable.
    

