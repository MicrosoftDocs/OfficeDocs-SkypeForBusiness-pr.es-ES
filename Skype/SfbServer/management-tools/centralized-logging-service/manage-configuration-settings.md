---
title: Administración de las opciones de configuración del servicio de registro centralizado en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumen: Obtenga información sobre cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221180"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Administración de las opciones de configuración del servicio de registro centralizado en Skype empresarial Server 2015

**Resumen:** Obtenga información sobre cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype empresarial Server 2015.

El servicio de registro centralizado está controlado y configurado por la configuración y los parámetros que crea y usa el controlador del servicio de registro centralizado (CLSController) para enviar comandos al agente del servicio de registro centralizado (CLSAgent) del equipo individual. El agente procesa los comandos que se envían a él y (en el caso de un comando de inicio) usa la configuración de los escenarios, proveedores, duración del seguimiento e indicadores para empezar a recopilar registros de seguimiento de acuerdo con la información de configuración proporcionada.

> [!IMPORTANT]
>  No todos los cmdlets de Windows PowerShell enumerados para el servicio de registro centralizado están pensados para su uso con implementaciones locales de Skype empresarial Server 2015. Aunque puede parecer que funcionen, los siguientes cmdlets no están diseñados para funcionar con las implementaciones locales de Skype empresarial Server 2015:

-  **Cmdlets de CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)y [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets de CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) y [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlets de CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)y [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

La configuración definida en estos cmdlets no obstaculizará ni provocará ningún comportamiento adverso, pero está diseñado para usarse con Microsoft 365 u Office 365 y no dará como resultado los resultados esperados en implementaciones locales. Lo cual no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.

El servicio de registro centralizado se puede ejecutar en un ámbito que incluya un solo equipo o un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido, como el sitio Redmond, que contiene una colección de equipos y grupos de servidores de la implementación) o en un ámbito global (es decir, todos los equipos y grupos de servidores de la implementación).

Para configurar el ámbito del servicio de registro centralizado mediante el shell de administración de Skype empresarial Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando desde el shell de administración de Skype empresarial Server o el símbolo del sistema de Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Por ejemplo:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Existen diferencias fundamentales entre los comandos de la línea de comandos que se pueden ejecutar en Windows PowerShell o CLSController. Windows PowerShell proporciona un método enriquecido para configurar y definir escenarios y reutilizarlos de forma significativa para los escenarios de solución de problemas. Aunque CLSController ofrece una manera rápida y eficaz de ejecutar comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos. A diferencia de los cmdlets de Windows PowerShell, CLSController no puede definir nuevos escenarios, administrar ámbitos en un sitio o nivel global, y muchas otras limitaciones de un conjunto de comandos finito que no se pueden configurar dinámicamente. Aunque CLSController proporciona un medio para una ejecución rápida, Windows PowerShell ofrece un medio para extender la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController.

Se puede definir un ámbito de un solo equipo durante la ejecución de un comando [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) y [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) mediante el parámetro-Computers. El parámetro-Computers acepta una lista separada por comas de nombres de dominio completos (FQDN) para el equipo de destino.

> [!TIP]
> También puede definir-pools y una lista separada por comas de los grupos en los que desea ejecutar los comandos de registro.

Los ámbitos de sitio y global se definen en los cmdlets del servicio de registro **nuevo-**, **set-** y **Remove-** centralizados. En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.

> [!IMPORTANT]
> Los comandos mostrados pueden contener parámetros y conceptos tratados en otras secciones. Los comandos de ejemplo pretenden demostrar el uso del parámetro **-Identity** para definir el ámbito y los otros parámetros se incluyen para completar y especificar el ámbito. Para obtener más información sobre los cmdlets de **Set-CsClsConfiguration**, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) en la documentación sobre operaciones.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar la configuración actual del servicio de registro centralizado

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Escriba lo siguiente en el símbolo del sistema:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Use los cmdlets **New-CsClsConfiguration** y **set-CsClsConfiguration** para crear una nueva configuración o para actualizar una configuración existente. Al ejecutar **Get-CsClsConfiguration**, se muestra información similar a la siguiente captura de pantalla, en la que la implementación tiene actualmente la configuración global predeterminada, pero no hay ninguna configuración de sitio definida:

![Resultado de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar la configuración actual del servicio de registro centralizado desde el almacén local del equipo

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Escriba lo siguiente en el símbolo del sistema:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Cuando se usa el primer ejemplo en el que **Get-CsClsConfiguration** no especifica ningún parámetro, el comando hace referencia al almacén de administración central para los datos. Si especifica el parámetro-LocalStore, el comando hace referencia al equipo LocalStore en lugar del almacén de administración central.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar la lista de los escenarios actualmente definidos

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Escriba lo siguiente en el símbolo del sistema:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Por ejemplo, para recuperar los escenarios definidos en el ámbito global:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado. En la mayoría de los casos, no se muestran todos los escenarios y están truncados. El comando usado aquí enumera todos los escenarios e información parcial acerca de los proveedores, la configuración y los indicadores que se utilizan.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito global para el servicio de registro centralizado mediante Windows PowerShell

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Escriba lo siguiente en el símbolo del sistema:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Por ejemplo:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento en 40 megabytes.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito de sitio para el servicio de registro centralizado mediante Windows PowerShell

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Escriba lo siguiente en el símbolo del sistema:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Por ejemplo:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Sin embargo, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para crear una nueva configuración del servicio de registro centralizado

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Escriba lo siguiente en el símbolo del sistema:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration proporciona acceso a un gran número de opciones de configuración opcionales. Para obtener más información acerca de las opciones de configuración, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) y [Understanding Centralizated Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Por ejemplo, para crear una nueva configuración que define una carpeta de red para archivos de caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado. Debe tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas. Debe realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para quitar una configuración del servicio de registro centralizado existente

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Escriba lo siguiente en el símbolo del sistema:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Por ejemplo, para quitar la configuración del servicio de registro centralizado que ha creado para aumentar el tiempo de sustitución del archivo de registro, aumente el tamaño del archivo de registro de sustitución y establezca la ubicación de la caché del archivo de registro en un recurso compartido de red de la siguiente manera:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Esta es la nueva configuración que se creó en el procedimiento "para crear una nueva configuración del servicio de registro centralizado".

Si decide quitar una configuración en el nivel de sitio, el sitio usará la configuración global.
## <a name="see-also"></a>Vea también

[Configurar proveedores para el servicio de registro centralizado en Skype empresarial Server 2015](configure-providers.md)

[Configurar escenarios para el servicio de registro centralizado en Skype empresarial Server 2015](configure-scenarios.md)

[Servicio de registro centralizado en Skype empresarial 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
