---
title: Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Resumen: Obtenga información sobre cómo iniciar o detener una sesión de captura de registro del servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: 49c36620cd58bf113ad1ce7823fcc438d88d8724
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274390"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Iniciar o detener la captura de registros de CLS en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo iniciar o detener una sesión de captura de registro del servicio de registro centralizado en Skype empresarial Server 2015.
  
Para capturar registros de seguimiento con el servicio de registro centralizado, emita un comando para iniciar el registro en uno o más equipos y grupos de grupos. También puede emitir parámetros que definan qué equipos o grupos, qué escenarios se deben ejecutar (por ejemplo, AlwaysOn, otro escenario predefinido o un escenario que haya creado), qué componentes de Skype empresarial Server (por ejemplo, S4, SipStack) realizar un seguimiento.
  
Para capturar la información correcta, asegúrese de que utiliza el escenario correcto para recopilar información relevante al problema. En el servicio de registro centralizado, un escenario es el concepto de activar el inicio de sesión basado en una colección de componentes de servidor, niveles de registro e indicadores, que es mucho más eficaz y útil que tener que definir estos elementos por servidor. Es preciso definir y especificar un escenario para que se ejecute de forma homogénea en todos los servidores y grupos de servidores de la infraestructura.
  
El escenario predeterminado se denomina **AlwaysOn**. El propósito de este escenario es ejecutarse constantemente, tal como su nombre lo indica. El escenario AlwaysOn recopila datos de información (tenga en cuenta que el nivel de registro de información incluye los errores irrecuperables, los errores y las advertencias, además de los mensajes de información) para muchos de los componentes de servidores más comunes. AlwaysOn recopila información antes, durante y después de que se produzca un problema. Esto supone una diferencia significativa con respecto al comportamiento típico de las herramientas de registro anteriores como, por ejemplo, OCSLogger. OCSLogger se ejecutaba después de que se hubiera producido el problema, lo que dificultaba la tarea de solución de problemas, ya que los datos con los que se trabajaba eran reactivos y no proactivos. En caso de que AlwaysOn no contenga la información que busca para identificar el componente que presenta el problema e indicar la acción que necesita llevar a cabo para corregirlo (cosa poco probable dada la amplitud y la profundidad que caracterizan a los proveedores de AlwaysOn), siempre mostrará información razonable para determinar qué acción necesita llevar a cabo como, por ejemplo, crear un escenario, recopilar más datos, ejecutar una búsqueda diferente para recopilar detalles más específicos, etc.
  
El servicio de registro centralizado ofrece dos maneras de ejecutar comandos. Una cantidad de temas se ha centrado en el uso de Windows PowerShell a través del shell de administración de Skype empresarial Server. La capacidad de usar varias configuraciones y comandos complejos favorece el uso del servicio de registro centralizado de Windows PowerShell. Dado que Windows PowerShell a través del shell de administración de Skype empresarial es casi omnipresente para todas las funciones de Skype empresarial Server, solo se tratan los comandos de Windows PowerShell. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para ejecutar Start-CsClsLogging con Windows PowerShell con comandos básicos

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para iniciar un escenario de registro con el servicio de registro centralizado, escriba lo siguiente:
    
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
    
2. Puede utilizar parámetros adicionales para administrar los comandos de registro. Puede usar-duración para ajustar la cantidad de tiempo que se va a ejecutar el escenario. También puede definir los equipos, una lista de nombres de dominio completos (FQDN) de equipos separados por comas, o-pools, una lista separada por comas de FQDN para los grupos en los que desea iniciar sesión.
    
    Inicie una sesión de registro para el escenario UserReplicator en el grupo "pool01.contoso.net". Defina también la duración de la sesión de registro en 8 horas. Para ello, escriba lo siguiente:
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    La correcta ejecución de este escenario devuelve un resultado similar al siguiente:
    
     ![Ejecutar Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Tenga en cuenta que en este ejemplo, el escenario AlwaysOn está en ejecución junto con el escenario UserReplicator. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Detener la captura de registros del servicio de registro centralizado
<a name="stop"> </a>

Puede detener una sesión de registro que se esté ejecutando actualmente con el cmdlet Stop-CsClsLogging. Por lo general, no hay muchas situaciones en las que necesite detener una sesión de registro. Por ejemplo, puede buscar en registros y cambiar configuraciones sin tener que detener primero el registro. Si tiene dos escenarios en ejecución, por ejemplo, AlwaysOn y UserReplicator, y tiene que recopilar información relacionada con la autenticación, tendrá que detener uno de los demás escenarios (en un ámbito global, de sitio, de grupo o de equipo) antes de poder empezar a ejecutar en el escenario de autenticación. Para más detalles, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Al determinar qué escenarios puede ejecutar en una implementación, grupo o equipo determinado, tiene que recordar que está limitado a ejecutar dos escenarios **por equipo**: AlwaysOn y un escenario personalizado. Si está registrando actividad en un grupo, dicho grupo necesita considerarse como una entidad única. En la mayoría de los casos, no tendría sentido ejecutar diferentes escenarios en cada equipo de un grupo. Parece lógico mirar el problema sobre el que está recopilando datos y considerar qué escenario tiene más sentido en un equipo determinado en la implementación global. Por ejemplo, si consideras el escenario UserReplicator, sería muy poco probable que se estuviera ejecutando UserReplicator en un servidor perimetral o un grupo perimetral. 
  
Tras comprender el problema y el ámbito del impacto, es preciso realizar elecciones cuidadosas sobre qué escenarios ejecutar en qué equipos y grupos. A pesar de que el escenario AlwaysOn tiene sentido para una aplicación de amplio ámbito porque recopila información en una gran variedad de proveedores, los escenarios específicos solo tienen valor de aplicación en grupos o equipos específicos. Además, necesita tener cuidado al iniciar de manera aleatoria una sesión de registro sin comprender primero el valor de un escenario determinado. Si usa el escenario incorrecto, o si usa un escenario que es adecuado para la tarea y aplica el escenario en el ámbito equivocado (ya sea global, de sitio, de grupo o de equipo), puede obtener datos cuestionables que no son muy útiles, como si no ejecutara el escenario en absoluto.
  
Para controlar las funciones de los servicios de registro centralizado mediante el shell de administración de Skype empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o de un rol de RBAC personalizado. que contiene cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Skype empresarial Server o el símbolo del sistema de Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Por lo tanto, es posible que se pregunte: ahora que ha habilitado el registro, ¿dónde se conservan los registros? Dado que tendrá acceso a la información almacenada en los registros mediante las consultas de Shell de administración enviadas a los agentes de CLS, y puede enviar los resultados a varios formatos de archivo posibles, en los que un agente de CLS mantiene sus registros no es importante saber.  Los archivos de registro pueden guardarse en una ubicación que especifique y leerse y analizarse con una gran variedad de herramientas, entre las que se incluyen el programa **Snoop. exe** y cualquier herramienta que pueda leer un archivo de texto, como **Notepad. exe**. Snoop. exe forma parte de las herramientas de depuración de Skype empresarial Server 2015 y está disponible como una [descarga de Internet](https://go.microsoft.com/fwlink/p/?LinkId=285257).

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para detener una sesión del servicio de registro centralizado que se está ejecutando

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Consulte el servicio de registro centralizado para averiguar qué escenarios se están ejecutando actualmente escribiendo lo siguiente:
    
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
## <a name="see-also"></a>Vea también
<a name="stop"> </a>

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)
