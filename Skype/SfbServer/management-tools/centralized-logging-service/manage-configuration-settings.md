---
title: Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumen: Obtenga información sobre cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: e386c22b8e8c1543b553ca1b9f242e9554ee5c85
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504575"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.
  
El servicio de registro centralizado se controla y configurado por la configuración y los parámetros que se crean y utilizan el centralizado registro de controlador del servicio (CLSController) para enviar comandos a (agente de servicio de registro centralizado) del equipo individuales Con CLSAgent). El agente procesa los comandos que le envían y (en el caso del comando Start) usa la configuración de los escenarios, los proveedores, la duración del seguimiento y las marcas para empezar a recopilar registros de seguimiento de acuerdo con la información de configuración facilitada.
  
> [!IMPORTANT]
>  No todos los cmdlets de Windows PowerShell enumerados para el servicio de registro centralizado están diseñados para su uso con Skype para las implementaciones locales de Business Server 2015. Aunque es posible que aparecen para que funcione, los cmdlets siguientes no están diseñados para funcionar con Skype para las implementaciones locales de 2015 de servidor empresarial:

-  **Cmdlets de CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)y [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps). 
-  **Cmdlets de CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) y [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).  
-  **Cmdlets de CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)y [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps). 

La configuración definida en estos cmdlets no obstaculizar ni causar ningún comportamiento adversa, pero están diseñados para su uso con Microsoft Office 365 y no se producirán los resultados esperados en las implementaciones locales. Esto no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.
  
El servicio de registro centralizado se puede ejecutar en un ámbito que incluye un único equipo o un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido como el sitio de Redmond que contiene una colección de equipo y grupos de servidores en la implementación) o en un ámbito global (es decir todos los equipos y grupos de servidores en la implementación).
  
Para configurar el ámbito de servicio de registro centralizado mediante el uso de la Skype para Shell de administración de servidor empresarial, debe ser un miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) del control o un rol RBAC personalizado que contiene cualquiera de estos dos grupos. Para devolver una lista de todas las funciones RBAC que se ha asignado este cmdlet para (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para Business Server Management Shell o el símbolo del sistema de Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Hay diferencias fundamentales entre los comandos de línea de comandos que se pueden ejecutar en Windows PowerShell o CLSController. Windows PowerShell proporciona un método enriquecido para configurar y definir escenarios y para volver a usar dichos escenarios de forma significativa para los escenarios de solución de problemas. Aunque CLSController ofrece una manera rápida y eficaz de emitir comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos. A diferencia de los cmdlets de Windows PowerShell, CLSController no se puede definir nuevos escenarios, administrar ámbito en un sitio o nivel global y muchas otras limitaciones de un conjunto de comandos limitado que no se puede configurar de forma dinámica. Mientras CLSController proporciona un medio para ejecución rápida, Windows PowerShell proporciona un medio para extender la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController. 
  
Ámbito de un único equipo puede definirse durante la ejecución de una [Búsqueda-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) y [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) comando con el - parámetro Computers. -Equipos parámetro acepta una lista separada por comas de nombres de dominio completo (FQDN) para el equipo de destino.
  
> [!TIP]
> También puede definir - grupos de servidores y una lista separada por comas de los grupos de servidores que se desean ejecutar los comandos de registro en. 
  
Los ámbitos de sitio y Global se definen en los cmdlets **New -**, **Set -** y **Remove -** servicio de registro centralizado. En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.
  
> [!IMPORTANT]
> Los comandos que se muestran pueden contener parámetros y conceptos tratados en otras secciones. Los comandos de ejemplo están diseñados para demostrar el uso de la **-Identity** parámetro para definir el ámbito y los demás parámetros se incluyen para más precisión y para especificar el ámbito. Para obtener información detallada acerca de los cmdlets **Set-CsClsConfiguration** , consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) en la documentación sobre operaciones.
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar la configuración actual del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Get-CsClsConfiguration
  ```

Use los cmdlets **New-CsClsConfiguration** y **Set-CsClsConfiguration** para crear una nueva configuración o para actualizar una configuración existente. Cuando se ejecuta **Get-CsClsConfiguration**, muestra información similar a la siguiente pantalla, donde la implementación tiene actualmente la configuración Global de forma predeterminada, pero no las configuraciones de sitios definidas:
  
![Salida de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar la configuración actual del servicio de registro centralizado desde el almacén del equipo local

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

Cuando se use en el primer ejemplo donde **Get-CsClsConfiguration** no se especifica ningún parámetro, las referencias de comando el almacén de Administración Central para los datos. Si se especifica el parámetro - LocalStore, el comando hace referencia a la LocalStore de equipo en lugar del almacén de Administración Central.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar la lista de los escenarios actualmente definidos

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    Por ejemplo, para recuperar los escenarios definidos en el ámbito global:
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado. En la mayoría de los casos, no se muestran todos los escenarios y están truncados. El comando usado aquí enumera todos los escenarios e información parcial sobre los proveedores, la configuración y las marcas que se utilizan.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito global para el servicio de registro centralizado mediante el uso de Windows PowerShell

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Por ejemplo:
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento configurado en 40 megabytes.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito de sitio para el servicio de registro centralizado mediante Windows PowerShell

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Por ejemplo:
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Pero, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. 
  
El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento configurado definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para crear una nueva configuración de servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > New-CsClsConfiguration proporciona acceso a una gran cantidad de opciones de configuración opcionales. Para obtener información detallada acerca de las opciones de configuración, vea [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) y [Descripción centralizada de registro de la configuración del servicio](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx). 
  
Por ejemplo, para crear una configuración que define una carpeta de red para archivos caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado. Hay que tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas. Es necesario realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para quitar una configuración existente del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

Por ejemplo, para quitar una configuración del servicio de registro centralizado que creó para aumentar el tiempo de conversión de archivo de registro, aumente el tamaño de archivo de registro de conversión y establezca la ubicación de memoria caché del archivo de registro en un recurso compartido de red de la siguiente manera:
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Esta es la configuración nueva que se creó en el procedimiento "para"crear una nueva configuración de servicio de registro centralizado. 
  
Si decide quitar una configuración de sitio, el sitio usará la configuración global.
## <a name="see-also"></a>Vea también

[Configurar los proveedores de servicio de registro centralizado en Skype para Business Server 2015](configure-providers.md)
  
[Configurar escenarios para el servicio de registro centralizado en Skype para Business Server 2015](configure-scenarios.md)

[Servicio de registro centralizado en Skype para profesionales de 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)