---
title: Uso de registro enriquecido para transacciones sintéticas
TOCTitle: Uso de registro enriquecido para transacciones sintéticas
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48274859
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de registro enriquecido para transacciones sintéticas

 

_**Última modificación del tema:** 2012-10-22_

Las transacciones sintéticas (introducidas en Microsoft Lync Server 2010) permiten a los administradores comprobar si los usuarios pueden completar correctamente tareas comunes como, por ejemplo, iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a teléfonos de la red telefónica conmutada (RTC). Los administradores pueden llevar a cabo estas pruebas (empaquetadas como un conjunto de cmdlets de Windows PowerShell de Lync Server) de forma manual o pueden ejecutarse de forma automática mediante aplicaciones como, por ejemplo, System Center Operations Manager.

En Lync Server 2010, las transacciones sintéticas han sido de gran utilidad para los administradores en la identificación de problemas. Por ejemplo, el cmdlet **Test-CsRegistration** avisaba a los administradores del hecho de que determinados usuarios estaban teniendo problemas para registrarse en Lync Server. No obstante, las transacciones sintéticas resultaban de poca utilidad para los administradores a la hora de determinar por qué estaban experimentando dificultades estos usuarios para registrarse en Lync Server. Esto se debía al hecho de que las transacciones sintéticas no proporcionaban información de registro detallada que sirviera de ayuda a los administradores para resolver problemas con Lync Server. En el mejor de los casos, los resultados detallados de las transacciones sintéticas proporcionaban información detallada que podían ayudar al administrador a suponer dónde se podía encontrar el problema.

En Microsoft Lync Server 2013, la arquitectura de las transacciones sintéticas se ha rediseñado para proporcionar registros enriquecidos. El concepto "registro enriquecido" implica que se registra información detallada para cada una de las transacciones sintéticas llevadas a cabo:

  - La hora a la que se inició la actividad

  - La hora a la que finalizó la actividad

  - La acción realizada (por ejemplo, la creación de conferencias, las incorporaciones o los abandonos, así como los inicios de sesión en Lync Server los envíos de mensajes instantáneos, etc.)

  - Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad

  - Mensajes de registro SIP

  - Códigos de diagnóstico o registros de excepción generados cuando se ejecutó la actividad

  - Resultado neto de la ejecución de la actividad

Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética. Sin embargo, la información no se muestra automáticamente ni se guarda en un archivo de registro. En su lugar, los administradores que ejecuten transacciones sintéticas de forma manual pueden utilizar el parámetro OutLoggerVariable para especificar una variable de Windows PowerShell en la que se va a almacenar la información. Desde ahí, los administradores pueden usar un par de métodos que permiten guardar y ver los registros enriquecidos en formato XML o HTML.

Por ejemplo, los administradores de Lync Server 2010 pueden ejecutar el cmdlet **Test-CsRegistration** usando un comando similar al siguiente:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Los administradores tienen la opción de incluir el parámetro OutLoggerVariable seguido de un nombre de variable de su elección:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest


> [!NOTE]
> Asegúrese de no anteponer el carácter $ al nombre de la variable. Utilice el nombre de variable RegistrationTest y no $RegistrationTest.



El comando anterior muestra un contenido similar al siguiente:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Sin embargo, existe información más detallada para este error que el mensaje mostrado anteriormente. Para tener acceso a dicha información en formato HTML, utilice un comando similar al siguiente. Este comando permite guardar la información almacenada en la variable RegistrationTest en un archivo HTML:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Estos archivos pueden verse mediante Internet Explorer, Visual Studio o con cualquier otra aplicación capaz de abrir archivos HTML/XML.

Las transacciones sintéticas ejecutadas desde System Center Operations Manager generarán automáticamente estos archivos de registro de error. Sin embargo, estos registros no se generarán si se produce un error en la ejecución antes de que Windows PowerShell pueda cargar y ejecutar la transacción sintética.

> [!IMPORTANT]  
> De forma predeterminada, Lync Server 2013 guarda los archivos de registro en una carpeta no compartida. Para que estos registros estén disponibles, deberá compartir esta carpeta (por ejemplo, \\atl-watcher-001.litwareinc.com\WatcherNode.


