---
title: "Administrar config. servicio registro centralizado en ámbito equipo, sitio y global"
TOCTitle: "Gest. conf. du serv. de journ. Centr. au niv. d’un ordi., site ou au niv. gl."
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49889388
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de la configuración del servicio de registro centralizado en el ámbito de equipo, sitio y global

 

_**Última modificación del tema:** 2014-02-04_

El Servicio de registro centralizado se puede ejecutar en un ámbito que incluye un único equipo o un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido como el sitio Redmond que contiene una colección de equipos y grupos en su implementación) o en un ámbito global (es decir, en todos los equipos y grupos de su implementación).

Para configurar el ámbito del Servicio de registro centralizado mediante el Shell de administración de Lync Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga alguno de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado personalmente), ejecute el siguiente comando desde el Shell de administración de Lync Server o desde el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}


> [!NOTE]
> Windows PowerShell proporciona más opciones y opciones de configuración adicionales que no están disponibles cuando se usa CLSController.exe. CLSController ofrece un método rápido y conciso de ejecutar comandos, pero está limitado al conjunto de comandos disponible para CLSController. Windows PowerShell no se limita solo a los comandos disponibles para el procesador de comandos de CLSController, y ofrece un conjunto de comandos y de opciones más amplio. Por ejemplo, CLSController.exe proporciona las opciones de ámbito -computers y -pools. Con Windows PowerShell, puede especificar equipos o grupos en la mayoría de los comandos y, cuando defina nuevos escenarios (CLSController tiene un número finito de escenarios que el usuario no puede modificar), puede definir un ámbito de sitio o global. Esta eficaz característica de Windows PowerShell permite definir un escenario con ámbito de sitio o global, pero limita el registro real a un equipo o grupo.<BR>Existen diferencias fundamentales entre los comandos de línea de comandos que puede ejecutar en Windows PowerShell o en CLSController. Windows PowerShell es un método más completo para configurar y definir escenarios, y para reutilizar esos escenarios de una manera significativa en escenarios de resolución de problemas. Aunque CLSController ofrece una manera rápida y eficaz de ejecutar comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos. A diferencia de los cmdlets de Windows PowerShell, CLSController no puede definir nuevos escenarios ni administrar un ámbito en un sitio o globalmente, además de las otras muchas limitaciones de un conjunto finito de comandos que no se puede configurar dinámicamente. Aunque CLSController permite ejecuciones rápidas, Windows PowerShell permite ampliar la funcionalidad de Servicio de registro centralizado más allá de lo que es posible con CLSController.



Se puede definir un ámbito de un único equipo durante la ejecución de un comando de [Search-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging), [Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging), [Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging), [Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging), [Sync-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Sync-CsClsLogging) y [Update-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsClsLogging) usando el parámetro –Computers. Este parámetro acepta una lista separada por comas de nombres de dominio completos (FQDN) para el equipo de destino.

> [!TIP]  
> También puede especificar –Pools y una lista separada por comas de los grupos donde quiera ejecutar los comandos de registro.



Los ámbitos de sitio y global se definen en los cmdlets **New-**, **Set-** y **Remove-**Servicio de registro centralizado. En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.

> [!IMPORTANT]  
> Los comandos mostrados pueden contener parámetros y conceptos tratados en otras secciones. Los comandos de ejemplo pretenden mostrar el uso del parámetro <strong>–Identity</strong> para definir el ámbito, y los demás parámetros se incluyen para completar la información y para especificar el ámbito. Para obtener más información sobre los cmdlets de <strong>Set-CsClsConfiguration</strong>, consulte <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration">Set-CsClsConfiguration</a> en la documentación sobre operaciones.



## Para recuperar la configuración actual del Servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Get-CsClsConfiguration

Use los cmdlets **New-CsClsConfiguration** y **Set-CsClsConfiguration** para crear una nueva configuración o para actualizar una configuración existente.

Al ejecutar **Get-CsClsConfiguration**, se muestra información similar a la siguiente captura de pantalla, en la que la implementación tiene actualmente la configuración Global sin configuraciones de sitios definidas:

![Salida de ejemplo de Get-CsClsConfiguration.](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Salida de ejemplo de Get-CsClsConfiguration.")

## Para recuperar la configuración actual del Servicio de registro centralizado desde el almacén local del equipo

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Get-CsClsConfiguration -LocalStore

Cuando se usa el primer ejemplo en el que **Get-CsClsConfiguration** no especifica ningún parámetro, el comando hace referencia a Almacén de administración central para obtener los datos. Si especifica el parámetro –LocalStore, el comando hace referencia al almacén local del equipo en lugar de a Almacén de administración central.

## Para recuperar la lista de los escenarios actualmente definidos

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Por ejemplo, para recuperar los escenarios definidos en el ámbito global:
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado. En la mayoría de los casos, no se muestran todos los escenarios y están truncados. El comando usado aquí enumera todos los escenarios e información parcial acerca de los proveedores, la configuración y los indicadores que se utilizan.

## Para actualizar un ámbito global para el Servicio de registro centralizado mediante Windows PowerShell

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Por ejemplo:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento en 40 megabytes.

## Para actualizar un ámbito de sitio para el Servicio de registro centralizado mediante Windows PowerShell

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Por ejemplo:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    

    > [!NOTE]
    > Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Sin embargo, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.



El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.

## Para crear una nueva configuración del Servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    

    > [!NOTE]
    > New-CsClsConfiguration proporciona acceso a un gran número de opciones de configuración opcionales. Para obtener más información sobre las opciones de configuración, consulte <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration">Get-CsClsConfiguration</A> y <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Introducción a las opciones de configuración del servicio de registro centralizado</A>.

    
    Por ejemplo, para crear una nueva configuración que define una carpeta de red para archivos de caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Debe planear cuidadosamente la creación de nuevas configuraciones y la manera de definir las nuevas propiedades del Servicio de registro centralizado. Debe tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas. Debe realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.

## Para quitar una configuración existente del Servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Por ejemplo, para quitar una configuración del Servicio de registro centralizado que ha creado para aumentar el tiempo de sustitución del archivo de registro, aumente el tamaño del archivo de registro de sustitución y establezca la ubicación de la caché del archivo de registro en un recurso de red compartido de la siguiente manera:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    

    > [!NOTE]
    > Esta es la nueva configuración que se creó en el procedimiento "Para crear una nueva configuración del Servicio de registro centralizado".



Si decide quitar una configuración en el nivel de sitio, el sitio usará la configuración global.

## Vea también

#### Conceptos

[Descripción general del servicio de registro centralizado](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Otros recursos

[Administración de las opciones de configuración del servicio de registro centralizado con PowerShell](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)

