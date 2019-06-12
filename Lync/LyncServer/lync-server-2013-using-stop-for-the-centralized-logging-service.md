---
title: 'Lync Server 2013: usar detener para el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521328b688f90ca591abddb3e59e7d49ae771b15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Usar detener para el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede detener una sesión de registro que se esté ejecutando actualmente con el cmdlet Stop-CsClsLogging. Por lo general, no hay muchas situaciones en las que tenga que detener una sesión de registro. Por ejemplo, puede buscar en registros y cambiar configuraciones sin tener que detener primero el registro. Si tiene dos escenarios en ejecución, por ejemplo, AlwaysOn y UserReplicator, y tiene que recopilar información relacionada con la autenticación, tendrá que detener uno de los demás escenarios (en un ámbito global, de sitio, de grupo o de equipo) antes de poder empezar a ejecutar en el escenario de autenticación. Para más detalles, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> Al determinar qué escenarios puede ejecutar en una implementación, grupo de servidores o equipo determinado, debe recordar que está limitado a ejecutar dos escenarios <STRONG>por equipo</STRONG>. Si está registrando actividad en un grupo, dicho grupo necesita considerarse como una entidad única. En la mayoría de los casos, no tendría sentido ejecutar diferentes escenarios en cada equipo de un grupo. Parece lógico mirar el problema sobre el que está recopilando datos y considerar qué escenario tiene más sentido en un equipo determinado en la implementación global. Por ejemplo, si consideras el escenario UserReplicator, sería muy poco probable que se estuviera ejecutando UserReplicator en un servidor perimetral o un grupo perimetral.<BR>Tras comprender el problema y el ámbito del impacto, es preciso realizar elecciones cuidadosas sobre qué escenarios ejecutar en qué equipos y grupos. A pesar de que el escenario AlwaysOn tiene sentido para una aplicación de amplio ámbito porque recopila información en una gran variedad de proveedores, los escenarios específicos solo tienen valor de aplicación en grupos o equipos específicos. Además, necesita tener cuidado al iniciar de manera aleatoria una sesión de registro sin comprender primero el valor de un escenario determinado. Si usa el escenario incorrecto, o si usa un escenario que es adecuado para la tarea y aplica el escenario en el ámbito equivocado (ya sea global, de sitio, de grupo o de equipo), puede obtener datos cuestionables que no son muy útiles, como si no ejecutara el escenario en absoluto.



</div>

Para controlar las funciones de los servicios de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para detener una sesión del servicio de registro centralizado que se está ejecutando

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Consulte el servicio de registro centralizado para averiguar qué escenarios se están ejecutando actualmente escribiendo lo siguiente:
    
        Show-CsClsLogging
    
    ![Consola de Windows PowerShell después de llamar a show-CSCL] (images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Consola de Windows PowerShell después de llamar a show-CSCL")
    
    El resultado de Show-CsClsLogging es un resumen de los escenarios que se están ejecutando y en qué ámbito se están ejecutando. Para más detalles, consulte [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Para detener una sesión de registro actualmente en ejecución con un escenario específico, escriba:
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Por ejemplo:
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Este comando detendrá el registro con el escenario de UserReplicatior en pool01.contoso.net.
    
    <div>
    

    > [!NOTE]  
    > No se eliminan los registros creados durante esta sesión de registro con el escenario de UserReplicator. El registro todavía está disponible para que ejecute las búsquedas con el comando Search-CsClsLogging. Para más detalles, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.

    
    </div>

Al actuar como el comando complementario para Start-CsClsLogging, el cmdlet Stop-CsClsLogging finaliza la sesión de registro, definida por los escenarios, y conserva los registros creados por la sesión de registro. Puede ejecutar dos escenarios en un equipo determinado en cualquier momento. El método de detener un escenario para recopilar información usando otro escenario es una tarea común que puede llevar a cabo durante la mayor parte de la solución de problemas de cargas de trabajo.

</div>

<div>

## <a name="see-also"></a>Vea también


[Uso de iniciar para el servicio de registro centralizado para capturar registros en Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

