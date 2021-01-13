---
title: Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Resumen: obtenga información sobre cómo iniciar o detener una sesión de captura de registros del Servicio de registro centralizado en Skype Empresarial Server 2015.'
ms.openlocfilehash: cd6864b0d4d16e952f93fe321b49522028d76e5b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835140"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo iniciar o detener una sesión de captura de registro del Servicio de registro centralizado en Skype Empresarial Server 2015.
  
Para capturar registros de seguimiento mediante el servicio de registro centralizado, emita un comando para iniciar el registro en uno o más equipos y grupos de servidores. También emite parámetros que definen qué equipos o grupos de servidores, qué escenarios ejecutar (por ejemplo, AlwaysOn, otro escenario predefinido o un escenario que ha creado), qué componentes de Skype Empresarial Server (por ejemplo, S4, SipStack) se deben seguir.
  
Para capturar la información correcta, asegúrese de que utiliza el escenario correcto para recopilar información relevante al problema. En el servicio de registro centralizado, un escenario es el concepto de activar el registro basado en una colección de componentes de servidor, niveles de registro y marcas, que es mucho más eficaz y útil que tener que definir estos elementos por servidor. Debe definir y especificar un escenario para que se ejecute de forma homogénea en todos los servidores y grupos de servidores de la infraestructura.
  
El escenario predeterminado se denomina **AlwaysOn**. El propósito de este escenario es ejecutarse constantemente, tal como el nombre indica. El escenario AlwaysOn recopila datos de nivel de información (tenga en cuenta que el nivel de registro de información incluye los errores irrecuperables, los errores y las advertencias, además de los mensajes de información) para muchos de los componentes de servidores más comunes. AlwaysOn recopila información antes, durante y después de que se produzca un problema. Esto supone una drástica diferencia con respecto al comportamiento típico de las herramientas de registro anteriores como, por ejemplo, OCSLogger. OCSLogger se ejecutaba después de que se hubiera producido el problema, lo que dificultaba la tarea de resolución de problemas, ya que los datos con los que se trabajaba eran reactivos y no proactivos. En caso de que AlwaysOn no contenga la información que busca para identificar el componente que presenta el problema e indicar la acción que debe llevar a cabo para corregirlo (cosa poco probable dada la amplitud y la profundidad que caracterizan a los proveedores de AlwaysOn), siempre mostrará información razonable que le ayude a determinar qué acción debe llevar a cabo como, por ejemplo, crear un nuevo escenario, recopilar más datos, ejecutar una búsqueda diferente para recopilar detalles más específicos, etc.
  
El servicio de registro centralizado proporciona dos formas de emitir comandos. Varios temas se han centrado en el uso de Windows PowerShell a través del Shell de administración de Skype Empresarial Server. La capacidad de usar una serie de configuraciones complejas y comandos favorece Windows PowerShell uso del servicio de registro centralizado. Dado Windows PowerShell a través del Shell de administración de Skype Empresarial Server es casi ubicuo para todas las funciones de Skype Empresarial Server, solo se analizan los Windows PowerShell comandos. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para ejecutar Start-CsClsLogging con Windows PowerShell comandos básicos

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Inicie un escenario de registro con el servicio de registro centralizado escribiendo lo siguiente:
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Por ejemplo, para iniciar el escenario **AlwaysOn**, escriba:
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > El escenario AlwaysOn no tiene duración predeterminada. Este escenario permanecerá en ejecución hasta que lo detenga explícitamente con el cmdlet **Stop-CsClsLogging**. Para obtener más detalles, vea [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Para el resto de escenarios, la duración predeterminada es de 4 horas. 
  
3. Presione Entrar para ejecutar el comando. 
    
    > [!NOTE]
    > La ejecución de los comandos y la recepción de datos de estado de los equipos de su implementación pueden llevar algo de tiempo (de 30 a 60 segundos). 
  
     ![Ejecución de Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Para iniciar otro escenario, use el cmdlet **Start-CsClsLogging** con el nombre del escenario adicional que desee ejecutar tal como se muestra a continuación (por ejemplo, el escenario **Authentication**):
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > Puede tener un total de hasta dos escenarios en ejecución a la vez en un mismo equipo. Si el comando tiene un ámbito global, todos los equipos de su implementación ejecutarán el escenario o los escenarios. Para iniciar un tercer escenario, deberá detener el registro en el equipo, grupo de equipos, sitio o ámbito global en el que desee ejecutar el nuevo escenario. En caso de que haya iniciado un ámbito global, detenga el registro de uno o ambos escenarios en uno o varios de los equipos o grupos de equipos. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Para ejecutar Start-CsClsLogging con Windows PowerShell comandos avanzados

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Puede utilizar parámetros adicionales para administrar los comandos de registro. Puede usar -Duration para ajustar el período de tiempo durante el que se ejecutará el escenario. También puede definir -Computers, una lista de nombres de dominio completos (FQDN) de equipos separados por una coma, o -Pools, una lista separada por comas de FQDN para los grupos en los que desea ejecutar el inicio de sesión.
    
    Inicie una sesión de registro para el escenario UserReplicator en el grupo de servidores "pool01.contoso.net". Defina también la duración de la sesión de registro en 8 horas. Para ello, escriba lo siguiente:
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    La correcta ejecución de este escenario devuelve un resultado similar al siguiente:
    
     ![Ejecución de Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Tenga en cuenta que en este ejemplo, el escenario AlwaysOn está en ejecución junto con el escenario UserReplicator. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Detener la captura de registro del Servicio de registro centralizado
<a name="stop"> </a>

Puede detener una sesión de inicio que se esté ejecutando actualmente con el cmdlet Stop-CsClsLogging. Por lo general, no hay muchas situaciones en las que tendría que detener una sesión de registro. Por ejemplo, puede buscar en registros y cambiar configuraciones sin tener que detener primero el registro. Si tiene dos escenarios en ejecución, por ejemplo, AlwaysOn y UserReplicator, y tiene que recopilar información relacionada con la autenticación, tendrá que detener uno de los demás escenarios (en un ámbito global, de sitio, de grupo de servidores o equipo) antes de poder empezar a ejecutar en el escenario de autenticación. Para obtener detalles, vea [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Al determinar qué escenarios se pueden ejecutar en una implementación, grupo o equipo determinados, debe recordar que está limitado a ejecutar dos **escenarios** por equipo: AlwaysOn y un escenario personalizado. Si está registrando actividad en un grupo de servidores, debe tratar un grupo de servidores como una entidad única. En la mayoría de los casos, no tendría sentido ejecutar diferentes escenarios en cada equipo de un grupo de servidores. Parece lógico mirar el problema sobre el que está recopilando datos y pensar acerca de qué escenario tiene más sentido en un equipo determinado en la implementación global. Por ejemplo, si tiene en cuenta el escenario UserReplicator, no tendría mucho valor ejecutar UserReplicator en un servidor perimetral o un grupo de servidores perimetrales. 
  
Tras comprender el problema y el ámbito del impacto, debería realizar elecciones cuidadosas acerca de qué escenarios ejecutar en qué equipos y grupos de servidores. Mientras que el AlwaysOn tiene sentido para una aplicación de amplio ámbito porque recopila información en una amplia variedad de proveedores, los escenarios específicos solo tienen valor de aplicación en grupos de servidores o equipos específicos. Además, debería tener cuidado al iniciar de manera aleatoria una sesión de registro sin comprender primero el valor de un escenario determinado. Si usa el escenario incorrecto, o si usa un escenario que es adecuado para la tarea y aplica el escenario en el ámbito equivocado (ya sea global, de sitio, de grupo de servidores o equipo), puede obtener datos cuestionables que no son muy útiles) como si no ejecutara el escenario en absoluto.
  
Para controlar las funciones del servicio de registro centralizado mediante el Shell de administración de Skype Empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o un rol RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado usted mismo), ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server o desde el símbolo del sistema Windows PowerShell voz:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Por lo tanto, puede que se pregunte: Ahora que ha habilitado el registro, ¿dónde se guardan los registros? Dado que tendrá acceso a la información almacenada en los registros mediante consultas del Shell de administración enviadas a los agentes de CLS, y puede enviar los resultados a varios formatos de archivo posibles, donde en cada servidor no es importante que un agente de CLS mantenga sus registros.  Los archivos de registro se pueden guardar en una ubicación que especifique, leer y analizar con una variedad de herramientas, como **Snooper.exe** y cualquier herramienta que pueda leer un archivo de texto, como **Notepad.exe**. Snooper.exe forma parte de las herramientas de depuración de Skype Empresarial Server 2015 y está disponible como [descarga web.](https://go.microsoft.com/fwlink/p/?LinkId=285257)

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para detener una sesión del servicio de registro centralizado que se está ejecutando actualmente

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Consulte el servicio de registro centralizado para averiguar qué escenarios se están ejecutando actualmente escribiendo lo siguiente:
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell consola después de llamar Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   El resultado de Show-CsClsLogging es un resumen de los escenarios que se están ejecutando y en qué ámbito se está ejecutando. Para obtener detalles, vea [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Para detener una sesión de registro actualmente en ejecución con un escenario específico, escriba:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Por ejemplo:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Este comando detendrá el registro con el escenario de UserReplicatior en pool01.contoso.net.
    
    > [!NOTE]
    > No se eliminan los registros creados durante esta sesión de registro con el escenario de UserReplicator. El registro todavía está disponible para que ejecute las búsquedas con el comando Search-CsClsLogging. Para obtener detalles, vea [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Actuando como el comando complementario para Start-CsClsLogging, el cmdlet Stop-CsClsLogging termina la sesión de registro, definida por los escenarios, y conserva los registros creados por la sesión de registro. Puede ejecutar dos escenarios en un equipo determinado en cualquier momento. El método de detener un escenario para recopilar información usando otro escenario es una tarea común que puede llevar a cabo durante la mayor parte de la solución de problemas de carga de trabajo.
## <a name="see-also"></a>Ver también
<a name="stop"> </a>

[Servicio de registro centralizado en Skype Empresarial 2015](centralized-logging-service.md)
