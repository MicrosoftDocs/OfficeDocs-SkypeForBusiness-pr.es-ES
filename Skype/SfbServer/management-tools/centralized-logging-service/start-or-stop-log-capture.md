---
title: Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
ms.reviewer: ''
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
description: 'Resumen: Obtenga información sobre cómo iniciar o detener una sesión de captura del registro de servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: 982aecf9da4e8ca08d734a4adb35d8a34a3bb816
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887333"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo iniciar o detener una sesión de captura del registro de servicio de registro centralizado en Skype para Business Server 2015.
  
Para capturar los registros de seguimiento mediante el servicio de registro centralizado, emitir un comando que se va a iniciar sesión en uno o varios equipos y grupos de servidores. También emitir los parámetros que definen qué equipos o grupos, qué escenarios para ejecutar (por ejemplo, AlwaysOn, otro escenario predefinido o un escenario que haya creado), ¿qué Skype para los componentes de Business Server (por ejemplo, S4, SipStack) para realizar un seguimiento.
  
Para capturar la información correcta, asegúrese de que utiliza el escenario correcto para recopilar información relevante al problema. En el servicio de registro con centralizado, un escenario es el concepto de activar el registro en función de una colección de componentes de servidor, los niveles de registro y los indicadores, que es mucho más eficaz y útil que tener que volver a definir estos elementos en un servidor a la vez. Es preciso definir y especificar un escenario para que se ejecute de forma homogénea en todos los servidores y grupos de servidores de la infraestructura.
  
El escenario predeterminado se denomina **AlwaysOn**. El propósito de este escenario es ejecutarse constantemente, tal como su nombre lo indica. El escenario AlwaysOn recopila datos de información (tenga en cuenta que el nivel de registro de información incluye los errores irrecuperables, los errores y las advertencias, además de los mensajes de información) para muchos de los componentes de servidores más comunes. AlwaysOn recopila información antes, durante y después de que se produzca un problema. Esto supone una diferencia significativa con respecto al comportamiento típico de las herramientas de registro anteriores como, por ejemplo, OCSLogger. OCSLogger se ejecutaba después de que se hubiera producido el problema, lo que dificultaba la tarea de solución de problemas, ya que los datos con los que se trabajaba eran reactivos y no proactivos. En caso de que AlwaysOn no contenga la información que busca para identificar el componente que presenta el problema e indicar la acción que necesita llevar a cabo para corregirlo (cosa poco probable dada la amplitud y la profundidad que caracterizan a los proveedores de AlwaysOn), siempre mostrará información razonable para determinar qué acción necesita llevar a cabo como, por ejemplo, crear un escenario, recopilar más datos, ejecutar una búsqueda diferente para recopilar detalles más específicos, etc.
  
El servicio de registro centralizado proporciona dos formas para emitir comandos. Se han centrado directamente un número de temas sobre el uso de Windows PowerShell a través de la Skype para Shell de administración de servidor empresarial. La capacidad para usar un número de configuraciones complejas y comandos favorezca Windows PowerShell para su uso del servicio de registro centralizado. Dado que Windows PowerShell a través de la Skype para Shell de administración de servidor empresarial es casi ubicuo para todas las funciones de Skype para Business Server, se analizan únicamente los comandos de Windows PowerShell. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para ejecutar Start-CsClsLogging con Windows PowerShell mediante comandos básicos

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
    > El escenario AlwaysOn no tiene duración predeterminada. Este escenario permanecerá en ejecución hasta que lo detenga explícitamente con el cmdlet **Stop-CsClsLogging**. Para más detalles, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Para el resto de los escenarios, la duración predeterminada es de 4 horas. 
  
3. Presione Entrar para ejecutar el comando. 
    
    > [!NOTE]
    > La ejecución de los comandos y la recepción de datos de estado de los equipos de su implementación pueden llevar algo de tiempo (de 30 a 60 segundos). 
  
     ![Ejecutar Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Para iniciar otro escenario, use el cmdlet **Start-CsClsLogging** con el nombre del escenario adicional que desee ejecutar tal como se muestra a continuación (por ejemplo, el escenario **Authentication**):
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > Puede tener un total de hasta dos escenarios en ejecución a la vez en un mismo equipo. Si el comando tiene un ámbito global, todos los equipos de su implementación ejecutarán el escenario o los escenarios. Para iniciar un tercer escenario, es preciso detener el registro en el equipo, en el grupo, en el sitio o en el ámbito global en el que desee ejecutar el nuevo escenario. En caso de que haya iniciado un ámbito global, detenga el registro de uno o ambos escenarios en uno o varios de los equipos o grupos. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Para ejecutar Start-CsClsLogging con Windows PowerShell mediante comandos avanzados

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Puede utilizar parámetros adicionales para administrar los comandos de registro. Puede usar - duración que se va a ajustar el período de tiempo para el escenario para que se ejecute. También puede definir - equipos, una lista de nombres de dominio de equipo completo (FQDN) separadas por comas, o - grupos de servidores, una coma separados por la lista de nombres de dominio completos de los grupos de servidores que desee que ejecute el inicio de sesión.
    
    Inicie una sesión de registro para el escenario UserReplicator en el grupo "pool01.contoso.net". Defina también la duración de la sesión de registro en 8 horas. Para ello, escriba lo siguiente:
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    La correcta ejecución de este escenario devuelve un resultado similar al siguiente:
    
     ![Ejecutar Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Tenga en cuenta que en este ejemplo, el escenario AlwaysOn está en ejecución junto con el escenario UserReplicator. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Detener la captura de registros del servicio de registro centralizado
<a name="stop"> </a>

Puede detener una sesión de registro que se esté ejecutando actualmente con el cmdlet Stop-CsClsLogging. Por lo general, no hay muchas situaciones en las que sería necesario detener una sesión de registro. Por ejemplo, puede buscar en registros y cambiar configuraciones sin tener que detener primero el registro. Si tiene dos escenarios en ejecución, por ejemplo, AlwaysOn y UserReplicator, y tiene que recopilar información relacionada con la autenticación, tendrá que detener uno de los demás escenarios (en un ámbito global, de sitio, de grupo o de equipo) antes de poder empezar a ejecutar en el escenario de autenticación. Para más detalles, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Al determinar qué escenarios puede ejecutar en una implementación, grupo o equipo determinado, tiene que recordar que está limitado a ejecutar dos escenarios **por equipo**: AlwaysOn y un escenario personalizado. Si está registrando actividad en un grupo, dicho grupo necesita considerarse como una entidad única. En la mayoría de los casos, no tendría sentido ejecutar diferentes escenarios en cada equipo de un grupo. Parece lógico mirar el problema sobre el que está recopilando datos y considerar qué escenario tiene más sentido en un equipo determinado en la implementación global. Por ejemplo, si tiene en cuenta el escenario UserReplicator, habrá muy poco valor en la ejecución de UserReplicator en un servidor perimetral o grupo de servidores perimetrales. 
  
Tras comprender el problema y el ámbito del impacto, es preciso realizar elecciones cuidadosas sobre qué escenarios ejecutar en qué equipos y grupos. A pesar de que el escenario AlwaysOn tiene sentido para una aplicación de amplio ámbito porque recopila información en una gran variedad de proveedores, los escenarios específicos solo tienen valor de aplicación en grupos o equipos específicos. Además, necesita tener cuidado al iniciar de manera aleatoria una sesión de registro sin comprender primero el valor de un escenario determinado. Si usa el escenario incorrecto, o si usa un escenario que es adecuado para la tarea y aplica el escenario en el ámbito equivocado (ya sea global, de sitio, de grupo o de equipo), puede obtener datos cuestionables que no son muy útiles, como si no ejecutara el escenario en absoluto.
  
Para controlar las funciones de servicio de registro centralizado mediante el uso de la Skype para Shell de administración de servidor empresarial, debe ser un miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) del control o un rol RBAC personalizado que contiene cualquiera de estos dos grupos. Para devolver una lista de todas las funciones RBAC que se ha asignado este cmdlet para (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para Business Server Management Shell o el símbolo del sistema de Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> ¿Por lo que puede que se pregunte: ahora que se ha habilitado el registro, donde se guardan los registros? Dado que tendrá acceso a la información almacenada en los registros de uso de consultas de shell de administración enviadas a los agentes de CLS, y puede generar resultados en varios formatos de archivo posibles, donde en cada servidor de un agente de CLS mantiene sus registros no es realmente importante que debe conocer.  Los archivos de registro se pueden guardar en una ubicación que especifique y lee y analiza utilizando una gran variedad de herramientas, como **Snooper.exe** y cualquier otra herramienta que puede leer un archivo de texto, como **Notepad.exe**. Snooper.exe forma parte de la Skype para las herramientas de depuración de Business Server 2015 y está disponible como una [descarga de Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para detener una sesión de servicio de registro centralizado actualmente en ejecución

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Consultar el servicio de registro centralizado para averiguar qué escenarios se están ejecutando escribiendo lo siguiente:
    
   ```
   Show-CsClsLogging
   ```

   ![Consola Windows PowerShell después de llamar Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   El resultado de Show-CsClsLogging es un resumen de los escenarios que se están ejecutando y en qué ámbito se están ejecutando. Para más detalles, consulte [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
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
    > No se eliminan los registros creados durante esta sesión de registro con el escenario de UserReplicator. El registro todavía está disponible para que ejecute las búsquedas con el comando Search-CsClsLogging. Para más detalles, consulte [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Al actuar como el comando complementario para Start-CsClsLogging, el cmdlet Stop-CsClsLogging finaliza la sesión de registro, definida por los escenarios, y conserva los registros creados por la sesión de registro. Puede ejecutar dos escenarios en un equipo determinado en cualquier momento. El método de detener un escenario para recopilar información usando otro escenario es una tarea común que puede llevar a cabo durante la mayor parte de la solución de problemas de cargas de trabajo.
## <a name="see-also"></a>Consulte también
<a name="stop"> </a>

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)
