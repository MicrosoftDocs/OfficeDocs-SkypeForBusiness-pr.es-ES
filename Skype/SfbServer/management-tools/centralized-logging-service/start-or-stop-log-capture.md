---
title: Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Resumen: Conozca cómo iniciar o detener una sesión de captura de registro de servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: 81db8c521f96306e118ebe5fe8053ff6e849dd54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a iniciar o detener una sesión de captura de registro de servicio de registro centralizado en Skype para Business Server 2015.
  
Para capturar los registros de seguimiento mediante el servicio de registro centralizado, emite un comando para empezar a registrar en uno o más equipos y grupos. También emite los parámetros que definen qué equipos o grupos, ¿qué escenarios para ejecutar (por ejemplo, AlwaysOn, otro escenario predefinido o una situación que ha creado), ¿qué Skype para componentes Business Server (por ejemplo, S4, SipStack) y hacer un seguimiento.
  
Para capturar la información correcta, asegúrese de que utiliza el escenario correcto para recopilar información relevante al problema. En el servicio centralizado de registro, un escenario es el concepto de activar el registro en función de un conjunto de componentes de servidor, los niveles de registro y los indicadores, que es mucho más eficaz y útil que tener que definir estos elementos en por servidor. Es preciso definir y especificar un escenario para que se ejecute de forma homogénea en todos los servidores y grupos de servidores de la infraestructura.
  
El escenario predeterminado se denomina **AlwaysOn**. El propósito de este escenario es ejecutarse constantemente, tal como su nombre lo indica. El escenario AlwaysOn recopila datos de información (tenga en cuenta que el nivel de registro de información incluye los errores irrecuperables, los errores y las advertencias, además de los mensajes de información) para muchos de los componentes de servidores más comunes. AlwaysOn recopila información antes, durante y después de que se produzca un problema. Esto supone una diferencia significativa con respecto al comportamiento típico de las herramientas de registro anteriores como, por ejemplo, OCSLogger. OCSLogger se ejecutaba después de que se hubiera producido el problema, lo que dificultaba la tarea de solución de problemas, ya que los datos con los que se trabajaba eran reactivos y no proactivos. En caso de que AlwaysOn no contenga la información que busca para identificar el componente que presenta el problema e indicar la acción que necesita llevar a cabo para corregirlo (cosa poco probable dada la amplitud y la profundidad que caracterizan a los proveedores de AlwaysOn), siempre mostrará información razonable para determinar qué acción necesita llevar a cabo como, por ejemplo, crear un escenario, recopilar más datos, ejecutar una búsqueda diferente para recopilar detalles más específicos, etc.
  
El servicio de registro centralizado proporciona dos formas de ejecutar comandos. Una serie de temas se han centrado en ángulo recto sobre el uso de Windows PowerShell a través del Skype para el Shell de administración de servidor empresarial. La capacidad para utilizar un número de configuraciones complejas y comandos favorece a Windows PowerShell para uso del servicio de registro centralizado. Dado que Windows PowerShell mediante el Skype para el Shell de administración de servidor empresarial es casi omnipresente para todas las funciones de Skype para Business Server, se describen sólo los comandos de Windows PowerShell. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Ejecutar CsClsLogging de inicio con Windows PowerShell con comandos básicos

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Iniciar un escenario de registro con el servicio de registro centralizado escribiendo lo siguiente:
    
  ```
  Start-CsClsLogging -Scenario <name of scenario>
  ```

    Por ejemplo, para iniciar el escenario **AlwaysOn**, escriba:
    
  ```
  Start-CsClsLogging -Scenario AlwaysOn
  ```

    > [!NOTE]
    > El escenario AlwaysOn no tiene duración predeterminada. Este escenario se ejecutará hasta que se detiene explícitamente con el cmdlet **Stop-CsClsLogging** . Para obtener más información, consulte [CsClsLogging de detención](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Para el resto de los escenarios, la duración predeterminada es de 4 horas. 
  
3. Presione Entrar para ejecutar el comando. 
    
    > [!NOTE]
    > La ejecución de los comandos y la recepción de datos de estado de los equipos de su implementación pueden llevar algo de tiempo (de 30 a 60 segundos). 
  
     ![Ejecutar Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Para iniciar otro escenario, utilice el cmdlet **Start-CsClsLogging** con el nombre del escenario adicional para ejecutar como sigue (por ejemplo, el escenario de **autenticación**):
    
  ```
  Start-CsClsLogging -Scenario Authentication
  ```

    > [!IMPORTANT]
    > Puede tener un total de hasta dos escenarios en ejecución a la vez en un mismo equipo. Si el comando tiene un ámbito global, todos los equipos de su implementación ejecutarán el escenario o los escenarios. Para iniciar un tercer escenario, es preciso detener el registro en el equipo, en el grupo, en el sitio o en el ámbito global en el que desee ejecutar el nuevo escenario. En caso de que haya iniciado un ámbito global, detenga el registro de uno o ambos escenarios en uno o varios de los equipos o grupos. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Ejecutar CsClsLogging de inicio con Windows PowerShell con comandos avanzados

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Puede utilizar parámetros adicionales para administrar los comandos de registro. Puede utilizar - duración para ajustar el intervalo de tiempo para el escenario para que se ejecute. También puede definir - equipos, una lista de nombres de dominio de equipo totalmente cualificado (FQDN) separados por una coma, o - Pools, una coma separan de la lista de nombres de dominio completos para los grupos que desea ejecutar la sesión de.
    
    Inicie una sesión de registro para el escenario de UserReplicator en la piscina "pool01.contoso.net". Defina también la duración de la sesión de registro en 8 horas. Para ello, escriba lo siguiente:
    
  ```
  Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"

  ```

    La correcta ejecución de este escenario devuelve un resultado similar al siguiente:
    
     ![Ejecutar Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Tenga en cuenta que en este ejemplo, el escenario AlwaysOn está en ejecución junto con el escenario UserReplicator. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Detener la captura de registros del servicio de registro centralizado
<a name="stop"> </a>

Puede detener una sesión de registro que se esté ejecutando actualmente con el cmdlet Stop-CsClsLogging. Por lo general, no hay muchas situaciones en las que necesite detener una sesión de registro. Por ejemplo, puede buscar en registros y cambiar configuraciones sin tener que detener primero el registro. Si tiene dos escenarios en ejecución, por ejemplo, AlwaysOn y UserReplicator, y tiene que recopilar información relacionada con la autenticación, tendrá que detener uno de los demás escenarios (en un ámbito global, de sitio, de grupo o de equipo) antes de poder empezar a ejecutar en el escenario de autenticación. Para obtener más información, consulte [CsClsLogging de detención](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Al determinar qué escenarios puede ejecutar en una implementación, grupo o equipo determinado, tiene que recordar que está limitado a ejecutar dos escenarios **por equipo**: AlwaysOn y un escenario personalizado. Si está registrando actividad en un grupo, dicho grupo necesita considerarse como una entidad única. En la mayoría de los casos, no tendría sentido ejecutar diferentes escenarios en cada equipo de un grupo. Parece lógico mirar el problema sobre el que está recopilando datos y considerar qué escenario tiene más sentido en un equipo determinado en la implementación global. Por ejemplo, si se considera el escenario UserReplicator, habría muy poco valor en ejecución UserReplicator en un servidor perimetral o un grupo de servidores de borde. 
  
Tras comprender el problema y el ámbito del impacto, es preciso realizar elecciones cuidadosas sobre qué escenarios ejecutar en qué equipos y grupos. A pesar de que el escenario AlwaysOn tiene sentido para una aplicación de amplio ámbito porque recopila información en una gran variedad de proveedores, los escenarios específicos solo tienen valor de aplicación en grupos o equipos específicos. Además, necesita tener cuidado al iniciar de manera aleatoria una sesión de registro sin comprender primero el valor de un escenario determinado. Si usa el escenario incorrecto, o si usa un escenario que es adecuado para la tarea y aplica el escenario en el ámbito equivocado (ya sea global, de sitio, de grupo o de equipo), puede obtener datos cuestionables que no son muy útiles, como si no ejecutara el escenario en absoluto.
  
Para controlar las funciones del servicio de registro centralizado utilizando el Skype para negocios de Shell de administración de servidor, debe ser miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) de control o una función personalizada de RBAC que contiene cualquiera de estos dos grupos. Para devolver una lista de todas las funciones RBAC que se ha asignado este cmdlet en (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para el Shell de administración de servidor de negocios o el símbolo del sistema de Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para detener una sesión de servicio de registro centralizado está actualmente en ejecución

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Consulta el servicio de registro centralizado para averiguar qué escenarios se están ejecutando actualmente escribiendo lo siguiente:
    
  ```
  Show-CsClsLogging
  ```

  ![Consola Windows PowerShell después de llamar Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
  El resultado de Show-CsClsLogging es un resumen de los escenarios que se están ejecutando y en qué ámbito se están ejecutando. Para obtener información detallada, vea [Mostrar CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Para detener una sesión de registro actualmente en ejecución con un escenario específico, escriba:
    
  ```
  Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
  ```
  Por ejemplo:
    
  ```
  Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
  ```

  Este comando detendrá el registro con el escenario de UserReplicatior en pool01.contoso.net.
    
    > [!NOTE]
    > No se eliminan los registros creados durante esta sesión de registro con el escenario de UserReplicator. El registro todavía está disponible para que ejecute las búsquedas con el comando Search-CsClsLogging. Para obtener más información, consulte [CsClsLogging de búsqueda](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Al actuar como el comando complementario para Start-CsClsLogging, el cmdlet Stop-CsClsLogging finaliza la sesión de registro, definida por los escenarios, y conserva los registros creados por la sesión de registro. Puede ejecutar dos escenarios en un equipo determinado en cualquier momento. El método de detener un escenario para recopilar información usando otro escenario es una tarea común que puede llevar a cabo durante la mayor parte de la solución de problemas de cargas de trabajo.
## <a name="see-also"></a>Vea también
<a name="stop"> </a>

#### 

[Servicio de registro centralizado en Skype para negocios 2015](centralized-logging-service.md)

