---
title: Expansor de configuración de control de admisión de llamadas
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 'El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red para CAC, el control de admisión de llamadas debe habilitarse para que se puedan aplicar las limitaciones de ancho de banda.'
---

# <a name="call-admission-control-settings-expander"></a>Expansor de configuración de control de admisión de llamadas
 
El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red para CAC, el control de admisión de llamadas debe habilitarse para que se puedan aplicar las limitaciones de ancho de banda. 
  
> [!NOTE]
> También puede usar el panel de control o los cmdlets del shell de administración para habilitar cac. 
  
En la sección **Configuración del control de admisión de llamadas** del cuadro de diálogo **Editar propiedades** del sitio, puede cambiar las opciones siguientes:
  
- **Habilitar control de admisión de llamadas** Seleccione esta opción para habilitar el CAC. Anule la selección de esta opción para deshabilitar el control de admisión de llamadas en toda la red. Para habilitar el control de admisión de llamadas, la red debe haberse configurado para CAC. Para obtener más información, consulte [Deploy call admission control in Skype Empresarial Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) en la documentación sobre implementación.
    
- **Grupo de servidores front-end para ejecutar el control de admisión de llamadas** Si ha habilitado cac, puede cambiar el grupo que lo ejecuta. Seleccione el grupo de servidores en la lista desplegable.
    

