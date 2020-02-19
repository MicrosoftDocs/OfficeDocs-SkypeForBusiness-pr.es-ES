---
title: 'Lync Server 2013: usar el registro enriquecido para transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc43a38a1c6060827755c958ac071fa63608556f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Uso del registro enriquecido para transacciones sintéticas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Las transacciones sintéticas (incluidas en Microsoft Lync Server 2010) proporcionan una manera para que los administradores comprueben que los usuarios pueden completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC). Estas pruebas (que se empaquetan como un conjunto de cmdlets de Windows PowerShell de Lync Server) pueden ser realizadas manualmente por un administrador o pueden ser ejecutadas automáticamente por una aplicación como System Center Operations Manager.

En Lync Server 2010, las transacciones sintéticas resultaban muy útiles para ayudar a los administradores a identificar problemas en el sistema. Por ejemplo, el cmdlet **Test-CsRegistration** podría avisar a los administradores del hecho de que algunos usuarios tenían problemas para registrarse en Lync Server. Sin embargo, las transacciones sintéticas eran algo menos útiles para ayudar a los administradores a determinar por qué estos usuarios tenían problemas para registrarse con Lync Server. Esto se debe a que las transacciones sintéticas no proporcionaban información de registro detallada que podría ayudar a los administradores a solucionar problemas con Lync Server. En el mejor de los casos, los resultados detallados de las transacciones sintéticas proporcionaban información detallada que podían ayudar al administrador a suponer dónde se podía encontrar el problema.

En Microsoft Lync Server 2013, las transacciones sintéticas se han vuelto a diseñar para proporcionar un registro enriquecido. El concepto "registro enriquecido" implica que se registra información detallada para cada una de las transacciones sintéticas llevadas a cabo:

  - La hora a la que se inició la actividad

  - La hora a la que finalizó la actividad

  - La acción que se ha realizado (por ejemplo, crear, unirse o abandonar una conferencia; iniciar sesión en Lync Server; enviar un mensaje instantáneo, etc.)

  - Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad

  - Mensajes de registro SIP

  - Códigos de diagnóstico o registros de excepción generados cuando se ejecutó la actividad

  - Resultado neto de la ejecución de la actividad

Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética. Sin embargo, la información no se muestra automáticamente ni se guarda en un archivo de registro. En su lugar, los administradores que ejecutan manualmente una transacción sintética pueden usar el parámetro OutLoggerVariable para especificar una variable de Windows PowerShell en la que se almacenará la información. Desde ahí, los administradores pueden usar un par de métodos que permiten guardar y ver los registros enriquecidos en formato XML o HTML.

Por ejemplo, los administradores de Lync Server 2010 pueden ejecutar el cmdlet **Test-CsRegistration** con un comando similar al siguiente:

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

A continuación, estos archivos se pueden ver con Internet Explorer, Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML/XML.

Las transacciones sintéticas que se ejecutan desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro para los errores. Sin embargo, estos registros no se generarán si se produce un error en la ejecución antes de que Windows PowerShell pueda cargar y ejecutar la transacción sintética.

> [!IMPORTANT]  
> De forma predeterminada, Lync Server 2013 guarda los archivos de registro en una carpeta que no está compartida. Para que estos registros sean accesibles fácilmente, debe compartir esta carpeta (por ejemplo, \\ \\ATL-monitor-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

