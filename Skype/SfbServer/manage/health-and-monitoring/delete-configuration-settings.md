---
title: Eliminar una colección existente de opciones de configuración de CDR en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumen: Conozca cómo quitar valores de configuración de CDR en Skype para Business Server 2015.'
ms.openlocfilehash: d7379817b808ac800694c01014469fe0d159d68f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server-2015"></a>Eliminar una colección existente de opciones de configuración de CDR en Skype Empresarial Server 2015
 
**Resumen:** Aprenda cómo quitar valores de configuración de CDR de Skype para Business Server 2015.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.
  
Al instalar Skype para Business Server 2015, una única colección global CDR de opciones de configuración se crea para usted. Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales. Por diseño, las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Si elimina la configuración con ámbito en el sitio, el CDR se puede administrar en dicho sitio utilizando la configuración global.
  
Tenga en cuenta que también puede "eliminar" la configuración global. Pero, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, la purga está habilitada de forma predeterminada en una colección de opciones de configuración de CDR. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.
  
Puede quitar los valores de configuración de CDR mediante el Skype para Panel de Control de servidor de negocios o el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Para quitar valores de configuración de CDR con Skype para Panel de Control de servidor empresarial

1. En Skype para Business Server Control Panel, haga clic en **supervisión y archivado**. 
    
2. En la pestaña **Registro detallado de llamadas**, seleccione la colección o colecciones de opciones de CDR que se van a quitar. Para seleccionar varias colecciones, haga clic en la primera colección, mantenga presionada la tecla Control y haga clic en otras colecciones.
    
3. Haga clic en **Editar** y después en **Eliminar**.
    
4. En Skype para el cuadro de diálogo Panel de Control del servidor de empresa, haga clic en **Aceptar**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar configuración de CDR mediante Cmdlets de Windows PowerShell

Puede eliminar detalle de llamada configuración de grabación mediante Windows PowerShell y el cmdlet **Remove-CsCdrConfiguration** . Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
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

[Purgar manualmente el registro de detalles de llamadas y las bases de datos de calidad de la experiencia de Skype para Business Server 2015](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

