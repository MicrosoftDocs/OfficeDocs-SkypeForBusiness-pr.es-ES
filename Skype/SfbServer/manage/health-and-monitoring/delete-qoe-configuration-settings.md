---
title: Eliminar las opciones de configuración de calidad de la experiencia en Skype Empresarial Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Summary: Learn how to delete Quality of Experience (QoE) settings in Skype Empresarial Server.'
---

# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Eliminar las opciones de configuración de calidad de la experiencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo eliminar la configuración de calidad de la experiencia (QoE) en Skype Empresarial Server.
  
Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.
  
Al instalar Skype Empresarial Server, se crea una única colección global de opciones de configuración de QoE. Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales. De forma predeterminada, las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones de ámbito global. Si se elimina la configuración de sitio, la QoE se gestionará en ese sitio mediante la configuración global.
  
Tenga en cuenta que también puede "eliminar" la configuración global. Sin embargo, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, la depuración predeterminada está habilitada en una colección de opciones de configuración de QoE. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.
  
Puede quitar las opciones de configuración de QoE mediante el Panel de control Skype Empresarial Server o mediante el cmdlet [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para eliminar las opciones de configuración de QoE mediante Skype Empresarial Server Panel de control

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol CsVoiceAdministrator, CsServerAdministrator, o CsAdministrator. Para obtener información detallada, consulte **Delegación de permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.  
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.
    
4. En la página **Datos de calidad de experiencia**, haga clic en la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.
    
5. Haga clic en **Aceptar**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar la configuración de QoE Configuración mediante Windows PowerShell cmdlets

Puede eliminar las opciones de configuración de QoE mediante Windows PowerShell y el cmdlet **Remove-CsQoEConfiguration**. Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea [Administración remota de PowerShell de Microsoft Lync](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). El proceso es el mismo en Skype Empresarial Server.
  
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

Para obtener más información, [vea Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Vea también

[Purgar manualmente el registro detallado de llamadas y las bases de datos de calidad de la experiencia en Skype Empresarial Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)