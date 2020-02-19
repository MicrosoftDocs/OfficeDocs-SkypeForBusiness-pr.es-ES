---
title: Uso de inicio para el servicio de registro centralizado para capturar registros
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ef2900d66796ec261e7abd9c8c6d910eb6c0e81
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Uso de inicio para el servicio de registro centralizado para capturar registros en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Para capturar registros de seguimiento mediante el servicio de registro centralizado, se emite un comando para iniciar el registro en uno o más equipos y grupos de servidores. También se emiten parámetros que definen qué equipos o grupos de servidores, qué escenarios se deben ejecutar (por ejemplo, AlwaysOn, otro escenario predefinido o un escenario creado), qué componentes de Lync Server (por ejemplo, S4, SipStack) se trazarán.

Para capturar la información correcta, asegúrese de que utiliza el escenario correcto para recopilar información relevante al problema. En el servicio de registro centralizado, un escenario es el concepto de activar el registro en función de una colección de componentes de servidor, niveles de registro e indicadores, que es mucho más eficiente y útil que tener que definir estos elementos por cada servidor. Debe definir y especificar un escenario para que se ejecute de forma homogénea en todos los servidores y grupos de servidores de la infraestructura.

El escenario predeterminado se denomina **AlwaysOn**. El propósito de este escenario es ejecutarse constantemente, tal como el nombre indica. El escenario AlwaysOn recopila datos de nivel de información (tenga en cuenta que el nivel de registro de información incluye los errores irrecuperables, los errores y las advertencias, además de los mensajes de información) para muchos de los componentes de servidores más comunes. AlwaysOn recopila información antes, durante y después de que se produzca un problema. Esto supone una drástica diferencia con respecto al comportamiento típico de las herramientas de registro anteriores como, por ejemplo, OCSLogger. OCSLogger se ejecutaba después de que se hubiera producido el problema, lo que dificultaba la tarea de resolución de problemas, ya que los datos con los que se trabajaba eran reactivos y no proactivos. En caso de que AlwaysOn no contenga la información que busca para identificar el componente que presenta el problema e indicar la acción que debe llevar a cabo para corregirlo (cosa poco probable dada la amplitud y la profundidad que caracterizan a los proveedores de AlwaysOn), siempre mostrará información razonable que le ayude a determinar qué acción debe llevar a cabo como, por ejemplo, crear un nuevo escenario, recopilar más datos, ejecutar una búsqueda diferente para recopilar detalles más específicos, etc.

El servicio de registro centralizado ofrece dos maneras de emitir comandos. Una cantidad de temas se ha centrado en el uso de Windows PowerShell a través del shell de administración de Lync Server. La capacidad de usar varias configuraciones y comandos complejos favorece el uso del servicio de registro centralizado de Windows PowerShell. Como Windows PowerShell a través del shell de administración de Lync Server es casi omnipresente para todas las funciones de Lync Server, solo se analizan los comandos de Windows PowerShell.

<div>


> [!NOTE]
> Si decide usar el conjunto de comandos limitado disponible en la línea de comandos, puede obtener ayuda con CLSController. exe escribiendo <CODE>ClsController.exe</CODE>. De forma predeterminada, <STRONG>ClsController. exe</STRONG> se instala en el directorio C:\Archivos de Programa\microsoft Lync Server 2013 \ ClsAgent.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para ejecutar Start-CsClsLogging con Windows PowerShell usando comandos básicos

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Inicie un escenario de registro con el servicio de registro centralizado; para ello, escriba lo siguiente:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Por ejemplo, para iniciar el escenario **AlwaysOn**, escriba:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > El escenario AlwaysOn no tiene duración predeterminada. Este escenario permanecerá en ejecución hasta que lo detenga explícitamente con el cmdlet <STRONG>Stop-CsClsLogging</STRONG>. Para obtener más detalles, vea <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Para el resto de escenarios, la duración predeterminada es de 4 horas.

    
    </div>

3.  Presione Entrar para ejecutar el comando.
    
    <div>
    

    > [!NOTE]
    > La ejecución de los comandos y la recepción de datos de estado de los equipos de su implementación pueden llevar algo de tiempo (de 30 a 60 segundos).

    
    </div>
    
    ![Ejecutar Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Ejecutar Start-CsClsLogging.")

4.  Para iniciar otro escenario, use el cmdlet **Start-CsClsLogging** con el nombre del escenario adicional que desee ejecutar tal como se muestra a continuación (por ejemplo, el escenario **Authentication**):
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > Puede tener un total de hasta dos escenarios en ejecución a la vez en un mismo equipo. Si el comando tiene un ámbito global, todos los equipos de su implementación ejecutarán el escenario o los escenarios. Para iniciar un tercer escenario, deberá detener el registro en el equipo, grupo de equipos, sitio o ámbito global en el que desee ejecutar el nuevo escenario. En caso de que haya iniciado un ámbito global, detenga el registro de uno o ambos escenarios en uno o varios de los equipos o grupos de equipos. Para obtener más información sobre cómo administrar los escenarios que se están ejecutando, consulte <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">uso de STOP para el servicio de registro centralizado en Lync Server 2013</A> y <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Para ejecutar Start-CsClsLogging con Windows PowerShell mediante comandos avanzados

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Puede utilizar parámetros adicionales para administrar los comandos de registro. Use el parámetro –Duration para ajustar el tiempo que se ejecutará el escenario. También puede definir el parámetro –Computers, que representa una lista de nombres de dominio completo (FQDN) de equipos separados por coma o el parámetros, o el parámetro –Pools, que representa una lista de FQDN separada por comas de grupos de equipos para los que desea ejecutar el registro.
    
    Inicia una sesión de registro para el escenario de *UserReplicator* en el grupo de servidores "pool01.contoso.net". Defina también la duración de la sesión de registro en 8 horas. Para ello, escriba lo siguiente:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    La correcta ejecución de este escenario devuelve un resultado similar al siguiente:
    
    ![Ejecutar Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Ejecutar Start-CsClsLogging.")
    
    Tenga en cuenta que en este ejemplo, el escenario AlwaysOn está en ejecución junto con el escenario UserReplicator.

</div>

<div>

## <a name="see-also"></a>Vea también


[Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

