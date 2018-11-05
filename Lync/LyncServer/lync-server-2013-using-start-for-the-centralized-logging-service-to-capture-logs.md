---
title: "Uso de Inicio para el servicio de registro centralizado para los registros de captura"
TOCTitle: "Ut. comm. Start pour capture des journaux par le serv. de journ. centralisée"
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49888793
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de Inicio para el servicio de registro centralizado para los registros de captura

 

_**Última modificación del tema:** 2013-02-21_

Para capturar registros de seguimiento con Servicio de registro centralizado, debe ejecutar un comando para iniciar el registro en uno o varios PC y grupos. También debe ejecutar parámetros que definan los PC, grupos y escenarios que se van a ejecutar (por ejemplo, AlwaysOn, otro escenario predefinido o un escenario de su propia creación), así como los componentes de Lync Server (por ejemplo, S4, SipStack) de los que se va a realizar el seguimiento.

Para capturar la información correcta, asegúrese de que utiliza el escenario correcto para recopilar información relevante al problema. En el Servicio de registro centralizado, el escenario representa la activación del registro basada en una recopilación de componentes de servidor, niveles de registro e indicadores, lo que resulta más eficaz y útil que la definición de estos elementos por cada servidor. Debe definir y especificar un escenario para que se ejecute de forma homogénea en todos los servidores y grupos de servidores de la infraestructura.

El escenario predeterminado se denomina **AlwaysOn**. El propósito de este escenario es ejecutarse constantemente, tal como el nombre indica. El escenario AlwaysOn recopila datos de nivel de información (tenga en cuenta que el nivel de registro de información incluye los errores irrecuperables, los errores y las advertencias, además de los mensajes de información) para muchos de los componentes de servidores más comunes. AlwaysOn recopila información antes, durante y después de que se produzca un problema. Esto supone una drástica diferencia con respecto al comportamiento típico de las herramientas de registro anteriores como, por ejemplo, OCSLogger. OCSLogger se ejecutaba después de que se hubiera producido el problema, lo que dificultaba la tarea de resolución de problemas, ya que los datos con los que se trabajaba eran reactivos y no proactivos. En caso de que AlwaysOn no contenga la información que busca para identificar el componente que presenta el problema e indicar la acción que debe llevar a cabo para corregirlo (cosa poco probable dada la amplitud y la profundidad que caracterizan a los proveedores de AlwaysOn), siempre mostrará información razonable que le ayude a determinar qué acción debe llevar a cabo como, por ejemplo, crear un nuevo escenario, recopilar más datos, ejecutar una búsqueda diferente para recopilar detalles más específicos, etc.

El Servicio de registro centralizado ofrece dos formas de ejecutar comandos. Varios temas se han dedicado al uso de Windows PowerShell mediante la Shell de administración de Lync Server. La capacidad para usar varias configuraciones complejas y varios comandos inclina la balanza en favor del uso de Windows PowerShell para el Servicio de registro centralizado. Puesto que el uso de Windows PowerShell mediante el Shell de administración de Lync Server es posible en prácticamente todas las funciones de Lync Server, solo se abordarán los comandos de Windows PowerShell.


> [!NOTE]
> Si decide usar el conjunto de comandos limitado disponible desde la línea de comandos, puede obtener ayuda relacionada con el archivo CLSController.exe escribiendo <CODE>ClsController.exe</CODE>. De forma predeterminada, <STRONG>ClsController.exe</STRONG> se instala en el directorio C:\Archivos de programa\Microsoft Lync Server 2013\ClsAgent.



## Para ejecutar Start-CsClsLogging con el Windows PowerShell mediante comandos básicos

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Inicie un escenario de registro con el Servicio de registro centralizado. Para ello, escriba lo siguiente:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Por ejemplo, para iniciar el escenario **AlwaysOn**, escriba:
    
        Start-CsClsLogging -Scenario AlwaysOn
    

    > [!NOTE]
    > El escenario AlwaysOn no tiene duración predeterminada. Este escenario permanecerá en ejecución hasta que lo detenga explícitamente con el cmdlet <STRONG>Stop-CsClsLogging</STRONG>. Para obtener más detalles, vea <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</A>. Para el resto de escenarios, la duración predeterminada es de 4 horas.



3.  Presione Entrar para ejecutar el comando.
    

    > [!NOTE]
    > La ejecución de los comandos y la recepción de datos de estado de los equipos de su implementación pueden llevar algo de tiempo (de 30 a 60 segundos).

    
    ![Ejecutando Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Ejecutando Start-CsClsLogging.")

4.  Para iniciar otro escenario, use el cmdlet **Start-CsClsLogging** con el nombre del escenario adicional que desee ejecutar tal como se muestra a continuación (por ejemplo, el escenario **Authentication**):
    
        Start-CsClsLogging -Scenario Authentication
    
    > [!IMPORTANT]  
    > Puede tener un total de hasta dos escenarios en ejecución a la vez en un mismo equipo. Si el comando tiene un ámbito global, todos los equipos de su implementación ejecutarán el escenario o los escenarios. Para iniciar un tercer escenario, deberá detener el registro en el equipo, grupo de equipos, sitio o ámbito global en el que desee ejecutar el nuevo escenario. En caso de que haya iniciado un ámbito global, detenga el registro de uno o ambos escenarios en uno o varios de los equipos o grupos de equipos. Para obtener más detalles sobre la administración de los escenarios en ejecución, vea <a href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Uso de Detener en el servicio de registro centralizado</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</a>.
    


## Para ejecutar Start-CsClsLogging con el Windows PowerShell mediante comandos avanzados

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Puede utilizar parámetros adicionales para administrar los comandos de registro. Use el parámetro –Duration para ajustar el tiempo que se ejecutará el escenario. También puede definir el parámetro –Computers, que representa una lista de nombres de dominio completos (FQDN) de equipos separados por coma, o el parámetro –Pools, que representa una lista de FQDN separados por coma, para los grupos en los que desea ejecutar el registro.
    
    Inicie una sesión de registro para el escenario *UserReplicator* en el grupo "pool01.contoso.net". Defina también la duración de la sesión de registro en 8 horas. Para ello, escriba lo siguiente:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    La correcta ejecución de este escenario devuelve un resultado similar al siguiente:
    
    ![Ejecutando Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Ejecutando Start-CsClsLogging.")
    
    Tenga en cuenta que en este ejemplo, el escenario AlwaysOn está en ejecución junto con el escenario UserReplicator.

## Vea también

#### Conceptos

[Descripción general del servicio de registro centralizado](lync-server-2013-overview-of-the-centralized-logging-service.md)

