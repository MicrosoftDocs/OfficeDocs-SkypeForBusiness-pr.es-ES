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
description: 'Resumen: Conozca cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: 0c4d03119a61fccd062e650c38815bee069852f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.
  
El servicio de registro centralizado está controlado y configurado por la configuración y los parámetros que se crean y utilizan el centralizado registro controlador del servicio (CLSController) para enviar comandos a (agente de servicio de registro centralizado) del equipo individuales CLSAgent). El agente procesa los comandos que le envían y (en el caso del comando Start) usa la configuración de los escenarios, los proveedores, la duración del seguimiento y las marcas para empezar a recopilar registros de seguimiento de acuerdo con la información de configuración facilitada.
  
> [!IMPORTANT]
>  No todos los cmdlets de Windows PowerShell para el servicio de registro centralizado está destinados con Skype para las implementaciones locales de Business Server 2015. Aunque parecen funcionar, los cmdlets siguientes no están diseñados para funcionar con Skype para las implementaciones locales de Business Server 2015:

-  **CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [Nueva CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)y [CsClsRegion de quitar](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps). 
-  **CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) y [CsClsSearchTerm del conjunto](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).  
-  **CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [Nueva CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)y [CsClsSecurityGroup de quitar](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps). 

La configuración definida en estos cmdlets no obstaculizar ni provocar cualquier comportamiento adverso, pero están diseñadas para su uso con Microsoft Office 365 y no producirá los resultados esperados en las implementaciones locales. Esto no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.
  
Se puede ejecutar el servicio de registro centralizado en un ámbito que incluye un único equipo o un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido como el sitio Redmond que contiene una colección de equipo y grupos en la implementación) o en un ámbito global (es decir todos los equipos y grupos en la implementación).
  
Para configurar el ámbito del servicio de registro centralizado mediante el Skype para negocios de Shell de administración de servidor, debe ser miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) de control o una función personalizada de RBAC que contiene cualquiera de estos dos grupos. Para devolver una lista de todas las funciones RBAC que se ha asignado este cmdlet en (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para el Shell de administración de servidor de negocios o el símbolo del sistema de Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Hay diferencias fundamentales entre los comandos de línea de comandos que puede ejecutar en Windows PowerShell o CLSController. Windows PowerShell proporciona un método completo para configurar y definir los escenarios y volver a los escenarios en forma significativa para los escenarios de solución de problemas. Aunque CLSController ofrece una manera rápida y eficaz de emitir comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos. A diferencia de los cmdlets de Windows PowerShell, CLSController no se puede definir nuevos escenarios, administrar el ámbito en un sitio o nivel global y muchas otras limitaciones de un conjunto de comandos limitado que no se puede configurar dinámicamente. Mientras CLSController proporciona un medio de ejecución rápida, Windows PowerShell proporciona un medio para ampliar la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController. 
  
Puede definirse un ámbito único equipo durante la ejecución de [Búsqueda CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Mostrar CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [CsClsLogging de inicio](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Parada CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) y [CsClsLogging de actualización](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) uso del comando-parámetro de equipos. -Equipos parámetro acepta una lista separada por comas de nombres de dominio completo (FQDN) del equipo de destino.
  
> [!TIP]
> También puede definir - grupos y una lista separada por comas de grupos que desea ejecutar los comandos de registro en. 
  
Ámbitos de sitio y Global se definen en los cmdlets **Nuevo**, **Set**y **Remove -** centralizada de servicio de registro. En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.
  
> [!IMPORTANT]
> Los comandos que se muestran pueden contener parámetros y conceptos tratados en otras secciones. Los comandos de ejemplo se pretenden demostrar el uso de la **-identidad** parámetro para definir el ámbito y los demás parámetros se incluyen su integridad y para especificar el ámbito. Para obtener más información acerca de los cmdlets **Set-CsClsConfiguration** , consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) en la documentación de las operaciones.
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar la configuración actual del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Get-CsClsConfiguration
  ```

Usar los cmdlets de **Nuevo CsClsConfiguration** y **CsClsConfiguration de conjunto** para crear una nueva configuración o para actualizar una configuración existente. Al ejecutar **Get-CsClsConfiguration**, se muestra información similar a la siguiente pantalla, donde la implementación tiene actualmente la configuración Global predeterminada, pero no hay configuraciones de sitio definidos:
  
![Salida de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar la configuración actual del servicio de registro centralizado desde el almacén del equipo local

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

Cuando utilizas el primer ejemplo donde **Get CsClsConfiguration** no especifica ningún parámetro, las referencias de comandos el almacén de Administración Central para los datos. Si se especifica el parámetro - almacénLocal, el comando hace referencia a la almacénLocal de equipo en lugar del almacén de Administración Central.
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
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito global para el servicio de registro centralizado mediante Windows PowerShell

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para crear una nueva configuración del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > New-CsClsConfiguration proporciona acceso a una gran cantidad de opciones de configuración opcionales. Para obtener más información acerca de las opciones de configuración, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) y [Entendimiento centralizada de registro de configuración de servicio](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx). 
  
Por ejemplo, para crear una configuración que define una carpeta de red para archivos caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado. Hay que tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas. Es necesario realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para eliminar una configuración existente del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente en el símbolo de la línea de comandos:
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

Por ejemplo, para quitar una configuración de servicio de registro centralizado que creó para aumentar la hora de conversión del archivo de registro, aumente el tamaño de archivo de registro de conversión y establecer la ubicación de caché de archivo de registro a un recurso compartido de red de la siguiente manera:
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Ésta es la configuración nueva que creó en el procedimiento "para"crear una nueva configuración del servicio de registro centralizado. 
  
Si decide quitar una configuración de sitio, el sitio usará la configuración global.
## <a name="see-also"></a>Vea también

#### 

[Configurar los proveedores de servicio de registro centralizado en Skype para Business Server 2015](configure-providers.md)
  
[Configurar escenarios para el servicio de registro centralizado en Skype para Business Server 2015](configure-scenarios.md)
#### 

[Servicio de registro centralizado en Skype para negocios 2015](centralized-logging-service.md)
#### 

[Conjunto de CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[Nueva CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[Quitar CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

