---
title: Eliminar una colección existente de opciones de configuración de CDR en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumen: Obtenga información sobre cómo quitar las opciones de configuración de CDR en Skype para Business Server.'
ms.openlocfilehash: ed8f729d78ea64b230d91d9142d0ba7dae743b0e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003702"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Eliminar una colección existente de opciones de configuración de CDR en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo quitar las opciones de configuración de CDR en Skype para Business Server.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.
  
Al instalar Skype para Business Server, una única colección global de opciones de configuración de CDR se crea para usted. Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales. Por diseño, las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Si elimina la configuración con ámbito en el sitio, el CDR se puede administrar en dicho sitio utilizando la configuración global.
  
Tenga en cuenta que también puede "eliminar" la configuración global. Pero, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, la purga está habilitada de forma predeterminada en una colección de opciones de configuración de CDR. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.
  
Puede quitar la configuración de CDR mediante el Skype para Panel de Control de servidor empresarial o el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Para quitar las opciones de configuración de CDR con Skype para el Panel de Control de servidor empresarial

1. Skype para el Panel de Control de servidor empresarial, haga clic en **supervisión y archivado**. 
    
2. En la pestaña **Registro detallado de llamadas**, seleccione la colección o colecciones de opciones de CDR que se van a quitar. Para seleccionar varias colecciones, haga clic en la primera colección, mantenga presionada la tecla Control y haga clic en otras colecciones.
    
3. Haga clic en **Editar** y después en **Eliminar**.
    
4. Skype para el cuadro de diálogo Panel de Control de servidor empresarial, haga clic en **Aceptar**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de CDR mediante el uso de Cmdlets de Windows PowerShell

Puede eliminar de detalles de llamadas de opciones de configuración mediante el uso de Windows PowerShell y el cmdlet **Remove-CsCdrConfiguration** . Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Para quitar una colección especificada de opciones de configuración de CDR

 Este comando quita las opciones de configuración de CDR que se aplican al sitio Redmond:
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de CDR que se aplican al ámbito del sitio

 Este comando quita todas las opciones de configuración de CDR que se aplican al ámbito del sitio:
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para quitar todas las opciones de configuración de CDR que deshabilitan el registro detallado de llamadas

 Este comando quita todas las opciones de configuración de CDR en las que se ha deshabilitado el registro detallado de llamadas:
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Vea también

[Purgar manualmente los detalles de las llamadas y las bases de datos de calidad de la experiencia en Skype para Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

