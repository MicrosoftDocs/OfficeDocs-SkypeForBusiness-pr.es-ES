---
title: Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumen: Aprenda a recuperar, actualizar y crear parámetros de configuración para el servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: 20f62a5568bef6f11eab35e13fa4e4f7adf8102e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991465"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015

**Resumen:** Obtenga información sobre cómo recuperar, actualizar y crear parámetros de configuración para el servicio de registro centralizado en Skype empresarial Server 2015.

El servicio de registro centralizado es controlado y configurado por la configuración y los parámetros creados y usados por el controlador de servicio de registro centralizado (CLSController) para enviar comandos al agente del servicio de registro centralizado ( CLSAgent). El agente procesa los comandos que le envían y (en el caso del comando Start) usa la configuración de los escenarios, los proveedores, la duración del seguimiento y las marcas para empezar a recopilar registros de seguimiento de acuerdo con la información de configuración facilitada.

> [!IMPORTANT]
>  No todos los cmdlets de Windows PowerShell enumerados para el servicio de registro centralizado están pensados para usarlos con las implementaciones locales de Skype empresarial Server 2015. Aunque parezca que funcionen, los siguientes cmdlets no están diseñados para funcionar con las implementaciones locales de Skype empresarial Server 2015:

-  **Cmdlets de CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)y [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets de CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) y [set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlets de CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)y [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

La configuración definida en estos cmdlets no obstaculizará ni provocará ningún comportamiento adverso, pero estará diseñado para usarse con Microsoft Office 365 y no producirá los resultados esperados en las implementaciones locales. Esto no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.

El servicio de registro centralizado se puede ejecutar en un ámbito que incluya un solo equipo o un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido, como el sitio Redmond, que contiene una colección de equipos y grupos en su implementación), o en un ámbito global (es decir, , todos los equipos y grupos de su implementación).

Para configurar el ámbito del servicio de registro centralizado mediante el shell de administración de Skype empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contiene alguno de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Skype empresarial Server o el símbolo del sistema de Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Por ejemplo:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Existen diferencias fundamentales entre los comandos de la línea de comandos que puede ejecutar en Windows PowerShell o CLSController. Windows PowerShell ofrece un método avanzado para configurar y definir escenarios, y para volver a usarlos de forma significativa para los escenarios de solución de problemas. Aunque CLSController ofrece una manera rápida y eficaz de emitir comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos. A diferencia de los cmdlets de Windows PowerShell, CLSController no puede definir nuevos escenarios, administrar el ámbito a nivel global o de sitio, y muchas otras limitaciones de un conjunto de comandos finito que no se pueden configurar dinámicamente. Si bien CLSController ofrece un medio para realizar una ejecución rápida, Windows PowerShell ofrece un medio para ampliar la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController.

Se puede definir un solo ámbito de equipo durante la ejecución de un comando de [búsqueda-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) y [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) mediante el parámetro-Computers. El parámetro-Computers acepta una lista separada por comas de nombres de dominio completos (FQDN) para el equipo de destino.

> [!TIP]
> También puede definir-pools y una lista separada por comas de las agrupaciones en las que desea ejecutar los comandos de registro.

Los ámbitos globales y de sitio se definen en los cmdlets del servicio de registro **nuevo**, **set**y **Remove-** centralizados. En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.

> [!IMPORTANT]
> Los comandos que se muestran pueden contener parámetros y conceptos tratados en otras secciones. Los comandos de ejemplo pretenden demostrar el uso del parámetro **-Identity** para definir el ámbito, y los otros parámetros se incluyen para completar y especificar el ámbito. Para más información sobre los cmdlets de **Set-CsClsConfiguration**, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) en la documentación sobre operaciones.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar la configuración del servicio de registro centralizado actual

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Escriba lo siguiente en el símbolo de la línea de comandos:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Use los cmdlets **New-CsClsConfiguration** y **set-CsClsConfiguration** para crear una nueva configuración o para actualizar una existente. Al ejecutar **Get-CsClsConfiguration**, se muestra información similar a la siguiente captura de pantalla, en la que la implementación tiene actualmente la configuración global predeterminada, pero no hay configuraciones de sitios definidas:

![Salida de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar la configuración del servicio de registro centralizado actual del almacén local del equipo

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Escriba lo siguiente en el símbolo de la línea de comandos:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Al usar el primer ejemplo, si **Get-CsClsConfiguration** no especifica ningún parámetro, el comando hace referencia al almacén de administración central de los datos. Si especifica el parámetro-LocalStore, el comando hace referencia al equipo LocalStore en lugar del almacén de administración central.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar la lista de los escenarios actualmente definidos

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Escriba lo siguiente en el símbolo de la línea de comandos:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Por ejemplo, para recuperar los escenarios definidos en el ámbito global:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado. En la mayoría de los casos, no se muestran todos los escenarios y están truncados. El comando usado aquí enumera todos los escenarios e información parcial sobre los proveedores, la configuración y las marcas que se utilizan.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito global para el servicio de registro centralizado mediante Windows PowerShell

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Escriba lo siguiente en el símbolo de la línea de comandos:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Por ejemplo:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento configurado en 40 megabytes.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito de sitio para el servicio de registro centralizado mediante Windows PowerShell

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Escriba lo siguiente en el símbolo de la línea de comandos:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Por ejemplo:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Pero, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento configurado definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para crear una nueva configuración de servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Escriba lo siguiente en el símbolo de la línea de comandos:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration proporciona acceso a una gran cantidad de opciones de configuración opcionales. Para obtener más información sobre las opciones de configuración, vea [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) y [comprender los parámetros de configuración del servicio de registro centralizado](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Por ejemplo, para crear una configuración que define una carpeta de red para archivos caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado. Hay que tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas. Es necesario realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para quitar una configuración del servicio de registro centralizado existente

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Escriba lo siguiente en el símbolo de la línea de comandos:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Por ejemplo, para quitar una configuración centralizada del servicio de registro que ha creado para aumentar el tiempo de sustitución del archivo de registro, aumente el tamaño del archivo de registro de sustitución y establezca la ubicación de la caché del archivo de registro en un recurso compartido de red de la siguiente manera:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Esta es la nueva configuración que se creó en el procedimiento "para crear una nueva configuración de servicio de registro centralizado".

Si decide quitar una configuración de sitio, el sitio usará la configuración global.
## <a name="see-also"></a>Vea también

[Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015](configure-providers.md)

[Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
