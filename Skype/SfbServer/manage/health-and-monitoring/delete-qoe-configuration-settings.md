---
title: Eliminar opciones de configuración de la calidad de la experiencia en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumen: Conozca cómo eliminar la configuración de calidad de la experiencia (QoE) en Skype para Business Server 2015.'
ms.openlocfilehash: 52008e14ca7a7b2a7a26726a2749f6d4dd083bbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server-2015"></a>Eliminar opciones de configuración de la calidad de la experiencia en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a eliminar la configuración de calidad de la experiencia (QoE) en Skype para Business Server 2015.
  
Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.
  
Al instalar Skype para Business Server 2015, una única colección global de la configuración de calidad se crea para usted. Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales. De forma predeterminada, las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones de ámbito global. Si se elimina la configuración de sitio, la QoE se gestionará en ese sitio por medio de la configuración global.
  
Tenga en cuenta que también puede "eliminar" la configuración global. Pero, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, de forma predeterminada purga está habilitada en una colección de valores de configuración de calidad de la experiencia. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.
  
Puede quitar los valores de configuración de calidad de la experiencia mediante el Skype para el Panel de Control de servidor empresarial o mediante el cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para eliminar los valores de configuración de calidad de la experiencia mediante Skype para Panel de Control de servidor empresarial

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, vea **Delegar permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.
    
4. En la página **Datos de calidad de la experiencia**, haga clic en la directiva que desee, haga clic en **Editar** y, luego, en **Eliminar**.
    
5. Haga clic en **Aceptar**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar valores de configuración de calidad de la experiencia mediante Cmdlets de Windows PowerShell

Puede eliminar los valores de configuración de calidad de la experiencia con Windows PowerShell y el cmdlet **Remove-CsQoEConfiguration** . Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Para quitar un conjunto concreto de configuraciones de QoE

 Este comando quita la configuración de QoE aplicada al sitio Redmond:
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de QoE aplicadas al ámbito de sitio

 Este comando quita todas las opciones de configuración de QoE aplicadas al ámbito de sitio:
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para quitar todas las opciones de configuración de QoE en las que se ha deshabilitado la supervisión de QoE

 Este comando quita todas las opciones de configuración de QoE donde se ha deshabilitado la supervisión de QoE:
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Para obtener más información, vea [Quitar CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Vea también

[Purgar manualmente el registro de detalles de llamadas y las bases de datos de calidad de la experiencia de Skype para Business Server 2015](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

