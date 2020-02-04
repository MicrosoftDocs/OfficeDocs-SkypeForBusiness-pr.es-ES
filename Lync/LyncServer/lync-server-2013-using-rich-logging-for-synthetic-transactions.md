---
title: 'Lync Server 2013: uso del registro completo para transacciones sintéticas'
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
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Usar el registro avanzado para transacciones sintéticas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Las transacciones sintéticas (presentadas en Microsoft Lync Server 2010) permiten a los administradores comprobar que los usuarios pueden completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono ubicado en la red de telefonía pública conmutada (RTC). Estas pruebas (que se empaquetan como un conjunto de cmdlets de Windows PowerShell de Lync Server) pueden realizarse manualmente por un administrador o una aplicación, como System Center Operations Manager, las puede ejecutar automáticamente.

En Lync Server 2010, las transacciones sintéticas se demostraron muy útiles para ayudar a los administradores a identificar problemas con el sistema. Por ejemplo, el cmdlet **Test-CsRegistration** puede avisar a los administradores de que algunos usuarios tienen problemas para registrarse en Lync Server. Sin embargo, las transacciones sintéticas eran menos útiles para ayudar a los administradores a determinar por qué estos usuarios tenían problemas para registrarse en Lync Server. Esto se debía a que las transacciones sintéticas no proporcionaban información de registro detallada que pudiera ayudar a los administradores a solucionar problemas con Lync Server. En el mejor de los casos, la salida detallada de una transacción sintética proporcionaba información paso a paso que podría permitir a un administrador hacer una estimación educada sobre dónde se produjo un problema.

En Microsoft Lync Server 2013, las transacciones sintéticas se han diseñado para proporcionar un registro enriquecido. "Registro enriquecido" significa que, para cada actividad que se compromete con una transacción sintética, se registrará información como esta:

  - El momento en que comenzó la actividad

  - El momento en que terminó la actividad

  - La acción que se realizó (por ejemplo, crear, unirse o salir de una conferencia; iniciar sesión en Lync Server; enviar un mensaje instantáneo, etc.)

  - Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad.

  - Mensajes de registro SIP

  - Registros de excepciones o códigos de diagnóstico generados cuando se ejecutó la actividad

  - El resultado neto de la ejecución de la actividad

Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética. Sin embargo, la información no se muestra o se guarda automáticamente en un archivo de registro. En su lugar, los administradores que ejecutan manualmente una transacción sintética pueden usar el parámetro OutLoggerVariable para especificar una variable de Windows PowerShell en la que se almacenará la información. Desde allí, los administradores pueden usar un par de métodos que les permitan guardar o ver el registro enriquecido en formato XML o HTML.

Por ejemplo, los administradores de Lync Server 2010 pueden ejecutar el cmdlet **Test-CsRegistration** con un comando similar al siguiente:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Los administradores tienen la opción de incluir el parámetro OutLoggerVariable seguido de un nombre de variable de su elección:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> No anteponga el carácter $ al nombre de la variable. Use un nombre de variable como RegistrationTest y no $RegistrationTest.

El comando anterior genera contenido similar al siguiente:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Sin embargo, hay mucha más información detallada para este error que solo el mensaje de error que se muestra arriba. Para tener acceso a esa información en formato HTML, use un comando similar a este para guardar la información almacenada en la variable RegistrationTest en un archivo HTML:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Estos archivos se pueden ver con Internet Explorer, Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML o XML.

Las transacciones sintéticas ejecutadas desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro por si se producen errores. Sin embargo, estos registros no se generarán si se produce un error en la ejecución antes de que Windows PowerShell pueda cargar y ejecutar la transacción sintética.

> [!IMPORTANT]  
> De forma predeterminada, Lync Server 2013 guarda los archivos de registro en una carpeta que no está compartida. Para que estos registros sean accesibles fácilmente, debe compartir esta carpeta (por ejemplo, \\ \\ATL-Watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

