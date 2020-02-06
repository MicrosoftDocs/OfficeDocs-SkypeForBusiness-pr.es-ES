---
title: Eliminar la calidad de la configuración de la experiencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumen: Aprenda a eliminar la configuración de la calidad de la experiencia (QoE) en Skype empresarial Server.'
ms.openlocfilehash: 08c002b45db7e8dd9617f2314c49d3d43057d545
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818020"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Eliminar la calidad de la configuración de la experiencia en Skype empresarial Server
 
**Resumen:** Aprenda a eliminar la configuración de la calidad de la experiencia (QoE) en Skype empresarial Server.
  
Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.
  
Al instalar Skype empresarial Server, se crea una única colección global de parámetros de configuración de QoE para usted. Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales. De forma predeterminada, las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones de ámbito global. Si se elimina la configuración de sitio, la QoE se gestionará en ese sitio por medio de la configuración global.
  
Tenga en cuenta que también puede "eliminar" la configuración global. Pero, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, de forma predeterminada, la purga está habilitada en una colección de parámetros de configuración de QoE. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.
  
Puede quitar las opciones de configuración de la calidad de servicio con el panel de control de Skype empresarial o mediante el cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para eliminar la configuración de QoE con el panel de control de Skype empresarial Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.
    
4. En la página **Datos de calidad de la experiencia**, haga clic en la directiva que desee, haga clic en **Editar** y, luego, en **Eliminar**.
    
5. Haga clic en **Aceptar**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de QoE mediante cmdlets de Windows PowerShell

Puede eliminar la configuración de la configuración de la calidad de usuario mediante Windows PowerShell y el cmdlet **Remove-CsQoEConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Para quitar un conjunto concreto de configuraciones de QoE

 Este comando quita la configuración de QoE aplicada al sitio Redmond:
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de QoE aplicadas al ámbito de sitio

 Este comando quita todas las opciones de configuración de QoE aplicadas al ámbito de sitio:
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para quitar todas las opciones de configuración de QoE en las que se ha deshabilitado la supervisión de QoE

 Este comando quita todas las opciones de configuración de QoE donde se ha deshabilitado la supervisión de QoE:
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Para obtener más información, consulte [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Vea también

[Purgar manualmente las bases de datos de grabación de detalles de llamadas y de calidad de la experiencia en Skype empresarial Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

