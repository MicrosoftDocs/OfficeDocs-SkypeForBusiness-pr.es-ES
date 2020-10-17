---
title: Administración de la configuración del servicio de registro centralizado de equipo, sitio y global
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8b7dfb9d96e452fc18dc5a7a962a18802388410
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505857"
---
# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Administración de equipos, sitios y configuración del servicio de registro centralizado global en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

El servicio de registro centralizado se puede ejecutar en un ámbito que incluya un solo equipo, un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido, como el sitio Redmond, que contiene una colección de equipos y grupos de servidores de la implementación) o en un ámbito global (es decir, todos los equipos y grupos de servidores de la implementación).

Para configurar el ámbito del servicio de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell proporciona más opciones y opciones de configuración adicionales que no están disponibles mediante el uso de CLSController.exe. CLSController ofrece un método rápido y conciso de ejecutar comandos, pero está limitado al conjunto de comandos disponible para CLSController. Windows PowerShell no está limitado solo al comando disponible para el procesador de comandos de la CLSController y proporciona un conjunto más amplio de comandos y un conjunto más amplio de opciones. Por ejemplo, CLSController.exe proporciona las opciones de ámbito -computers y -pools. Con Windows PowerShell, puede indicar equipos o grupos en la mayoría de los comandos y, cuando define nuevos escenarios (CLSController tiene un número finito de escenarios que no son modificables por el usuario), puede definir un ámbito global o de sitio. Esta eficaz característica de Windows PowerShell permite definir un escenario de un sitio o un ámbito global, pero limita el registro real a un equipo o grupo de servidores.<BR>Existen diferencias fundamentales entre los comandos de la línea de comandos que se pueden ejecutar en Windows PowerShell o CLSController. Windows PowerShell proporciona un método enriquecido para configurar y definir escenarios y reutilizarlos de forma significativa para los escenarios de solución de problemas. Aunque CLSController ofrece una manera rápida y eficaz de ejecutar comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos. A diferencia de los cmdlets de Windows PowerShell, CLSController no puede definir nuevos escenarios, administrar ámbitos en un sitio o nivel global, y muchas otras limitaciones de un conjunto de comandos finito que no se pueden configurar dinámicamente. Aunque CLSController proporciona un medio para una ejecución rápida, Windows PowerShell ofrece un medio para extender la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController.



</div>

Se puede definir un ámbito de un solo equipo durante la ejecución de un comando [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) y [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) mediante el parámetro – Computers. El parámetro –Computers acepta una lista separada por comas de nombres de dominio completos (FQDN) del equipo de destino.

<div>


> [!TIP]
> También puede especificar –Pools y una lista separada por comas de los grupos donde quiera ejecutar los comandos de registro.



</div>

Los ámbitos de sitio y global se definen en los cmdlets del servicio de registro **nuevo-**, **set-** y **Remove-** centralizados. En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.

<div>


> [!IMPORTANT]
> Los comandos mostrados pueden contener parámetros y conceptos tratados en otras secciones. Los comandos de ejemplo pretenden mostrar el uso del parámetro <STRONG>–Identity</STRONG> para definir el ámbito, y los demás parámetros se incluyen para completar la información y para especificar el ámbito. Para obtener más información sobre los cmdlets de <STRONG>Set-CsClsConfiguration</STRONG>, consulte <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> en la documentación sobre operaciones.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar la configuración actual del servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Get-CsClsConfiguration

Use los cmdlets **New-CsClsConfiguration** y **Set-CsClsConfiguration** para crear una nueva configuración o para actualizar una configuración existente.

Al ejecutar **Get-CsClsConfiguration**, se muestra información similar a la siguiente captura de pantalla, en la que la implementación tiene actualmente la configuración global predeterminada, pero no hay ninguna configuración de sitio definida:

![Resultado de ejemplo de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Resultado de ejemplo de Get-CsClsConfiguration.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar la configuración actual del servicio de registro centralizado desde el almacén local del equipo

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Get-CsClsConfiguration -LocalStore

Cuando se usa el primer ejemplo en el que **Get-CsClsConfiguration** no especifica ningún parámetro, el comando hace referencia al almacén de administración central para los datos. Si especifica el parámetro – LocalStore, el comando hace referencia al equipo LocalStore en lugar del almacén de administración central.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar la lista de los escenarios actualmente definidos

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Por ejemplo, para recuperar los escenarios definidos en el ámbito global:
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado. En la mayoría de los casos, no se muestran todos los escenarios y están truncados. El comando usado aquí enumera todos los escenarios e información parcial acerca de los proveedores, la configuración y los indicadores que se utilizan.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito global para el servicio de registro centralizado mediante Windows PowerShell

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Por ejemplo:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento en 40 megabytes.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para actualizar un ámbito de sitio para el servicio de registro centralizado mediante Windows PowerShell

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Por ejemplo:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Sin embargo, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

    
    </div>

El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para crear una nueva configuración del servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-CsClsConfiguration proporciona acceso a un gran número de opciones de configuración opcionales. Para obtener más información sobre las opciones de configuración, consulte <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> y <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding centralizated Logging Services Configuration Settings in Lync Server 2013</A>.

    
    </div>
    
    Por ejemplo, para crear una nueva configuración que define una carpeta de red para archivos de caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado. Debe tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas. Debe realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para quitar una configuración del servicio de registro centralizado existente

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en el símbolo del sistema:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Por ejemplo, para quitar la configuración del servicio de registro centralizado que ha creado para aumentar el tiempo de sustitución del archivo de registro, aumente el tamaño del archivo de registro de sustitución y establezca la ubicación de la caché del archivo de registro en un recurso compartido de red de la siguiente manera:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Esta es la nueva configuración que se creó en el procedimiento "para crear una nueva configuración del servicio de registro centralizado".

    
    </div>

Si decide quitar una configuración en el nivel de sitio, el sitio usará la configuración global.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Administración de las opciones de configuración del servicio de registro centralizado en Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

