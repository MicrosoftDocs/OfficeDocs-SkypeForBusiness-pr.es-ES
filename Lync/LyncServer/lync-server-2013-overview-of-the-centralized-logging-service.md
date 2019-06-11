---
title: 'Lync Server 2013: información general sobre el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647e6b1e5797b3936dc1fef6023c85ce4baf68b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Información general sobre el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

El servicio de registro centralizado está diseñado para proporcionar un medio para la recopilación de datos controlada, con un ámbito amplio o estrecho. Puede recopilar datos de todos los servidores de la implementación de forma simultánea, definir elementos específicos para rastrear, establecer indicadores de seguimiento y devolver resultados de búsqueda de un único equipo o una agregación de todos los datos de todos los servidores. El servicio de registro centralizado se ejecuta en todos los servidores de la implementación. La arquitectura del servicio de registro centralizado consta de los siguientes agentes y servicios:

  - *Agente de servicio de registro centralizado*   ClsAgent. exe es el ejecutable de servicio que se comunica con el controlador y recibe los comandos que el administrador emite. El agente se ejecuta como un servicio en cada equipo de Lync Server. Cuando el agente recibe un comando, ejecuta el comando, envía mensajes a los componentes definidos para su seguimiento y escribe los registros de seguimiento en el disco. También lee los registros de seguimiento de su equipo y envía los datos de seguimiento al controlador cuando lo solicitan. El ClsAgent escucha los comandos en los siguientes puertos: **tcp 50001**, **TCP 50002**y **TCP 50003**.

  - *Controlador de servicio de registro centralizado*   ClsControllerLib. dll es el motor de ejecución de comandos para el shell de administración de Lync Server y ClsController. exe. CLSControllerLib. dll envía los comandos iniciar, detener, vaciar y buscar a la ClsAgent. Cuando se envían los comandos de búsqueda, los registros de resultados se devuelven a ClsControllerLib.dll y se agregan. El controlador es responsable de enviar comandos al agente, de recibir el estado de esos comandos y de administrar los datos del archivo de registro de búsqueda a medida que se devuelven de todos los agentes en un equipo en el ámbito de búsqueda, y de agregar los datos de registro en un sentido y se ordenan conjunto de salida. La información de los temas siguientes se centra en el uso del shell de administración de Lync Server. ClsController. exe está limitado a un subconjunto de las características y funciones que están disponibles en el shell de administración de Lync Server. La ayuda de ClsController. exe está disponible en la línea de comandos `ClsController` escribiendo el directorio predeterminado C:\\archivos\\comunes de programa\\archivos de Microsoft Lync\\Server 2013 ClsAgent.

**Comunicaciones de ClsController con ClsAgent**

![Relación entre CLSController y CLSAgent.] (images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relación entre CLSController y CLSAgent.")

Los comandos se emiten con la interfaz de línea de comandos de Windows Server o mediante el shell de administración de Lync Server. Los comandos se ejecutan en el equipo donde haya iniciado sesión y se envían a ClsAgent de forma local o a los demás equipos y grupos de la implementación.

ClsAgent mantiene un archivo de índice de todos los archivos .CACHE disponibles en la máquina local. ClsAgent los asigna de manera que se distribuyan uniformemente entre todos los volúmenes definidos por la opción CacheFileLocalFolders, sin consumir nunca más del 80 % de cada volumen (es decir, la ubicación de la memoria caché local y el porcentaje se pueden configurar con el cmdlet **Set-CsClsConfiguration**). ClsAgent también es responsable de limpiar los archivos de registro de seguimiento de eventos (.etl) antiguos almacenados en la memoria caché de la máquina local. Después de dos semanas (que es el período de tiempo que se puede configurar con el cmdlet **Set-CsClsConfiguration**), estos archivos se copian a un recurso compartido de archivos y se eliminan del equipo local. Para más detalles, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Cuando se recibe una solicitud de búsqueda, se usan los criterios de búsqueda para seleccionar el conjunto de archivos .etl en la memoria caché a fin de realizar la búsqueda en función de los valores del índice que mantiene el agente.

<div>


> [!NOTE]  
> ClsAgent puede buscar en los archivos que se trasladan al recurso compartido de archivos desde el equipo local. Después de que ClsAgent mueve los archivos al recurso compartido de archivos, ClsAgent no realiza el mantenimiento de limpieza y eliminación de archivos. Es necesario definir una tarea administrativa para supervisar el tamaño de los archivos en el recurso compartido de archivos y eliminarlos o archivarlos.



</div>

Los archivos de registro resultantes se pueden leer y analizar con distintas herramientas, incluyendo **Snooper.exe** y cualquier herramienta que pueda leer un archivo de texto, como **Notepad.exe**. Snoop. exe forma parte de las herramientas de depuración de Lync Server 2013 y se puede descargar desde [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)la Web.

Al igual que OCSLogger, el servicio de registro centralizado cuenta con varios componentes para realizar el seguimiento y proporciona opciones para seleccionar marcas\_, como TF\_Component y TF diag. El servicio de registro centralizado también conserva las opciones de nivel de registro de OCSLogger.

La ventaja más importante para usar el shell de administración de Lync Server en el ClsController de la línea de comandos es que puede configurar y definir nuevos escenarios con los proveedores seleccionados orientados al espacio de problemas, los indicadores personalizados y los niveles de registro. Los escenarios disponibles para ClsController se limitan a los que están definidos para el archivo ejecutable.

En versiones anteriores, OCSLogger.exe se proporcionaba para que los administradores y el personal de soporte pudieran recopilar archivos de seguimiento de los equipos de la implementación. A pesar de sus ventajas, OCSLogger tenía una limitación. Solo se podían recopilar los registros de un equipo al mismo tiempo. Podía realizar el registro de varios equipos usando copias diferentes de OCSLogger, pero al final obtenía varios registros y ninguna manera sencilla de agregar los resultados.

Cuando un usuario solicita una búsqueda de registros, ClsController determina a qué máquinas se enviará la solicitud (en función de los escenarios seleccionados). También determina si es necesario enviar la búsqueda al recurso compartido de archivos donde se encuentran los archivos .etl guardados. Cuando los resultados de búsqueda se devuelven a ClsController, el controlador combina los resultados en un único conjunto de resultados ordenados por tiempo, que se presenta al usuario. Los usuarios pueden guardar los resultados de búsqueda en la máquina local para su posterior análisis.

Cuando inicia una sesión de registro, especifica los escenarios relativos al problema que está intentando resolver. Puede tener dos escenarios en ejecución al mismo tiempo. Uno de los dos tiene que ser el escenario AlwaysOn. Como su nombre indica, siempre necesita estar en ejecución en la implementación, recopilando información sobre todos los equipos, grupos y componentes.

<div>


> [!IMPORTANT]  
> De forma predeterminada, el escenario AlwaysOn no se ejecuta en la implementación. Es preciso iniciarlo explícitamente. Una vez iniciado, continuará ejecutándose hasta que se detenga explícitamente, y el estado en ejecución persistirá aunque se reinicien los equipos. Para obtener más información sobre cómo iniciar y detener escenarios, consulte <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Usar inicio para el servicio de registro centralizado para capturar registros en Lync server 2013</A> y <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">usar detener para el servicio de registro centralizado en Lync Server 2013</A>.



</div>

Cuando se produce un problema, inicie un segundo escenario relacionado con el problema notificado. Reproduzca el problema y detenga el registro del segundo escenario. Empiece las búsquedas de registros relativas al problema notificado. La colección agregada de registros produce un archivo de registro que contiene mensajes de seguimiento de todos los equipos del ámbito de sitio o global de la implementación. Si la búsqueda devuelve más datos de los que es razonable analizar (lo que normalmente se conoce como relación señal-ruido, en la que el ruido es demasiado alto), ejecute otra búsqueda con parámetros más limitados. En este punto, puede empezar a observar que aparecen patrones que le ayudarán a centrarse mejor en el problema. Por último, después de realizar un par de búsquedas más refinadas, podrá encontrar los datos relativos al problema y averiguar la causa principal.

<div>


> [!TIP]  
> Cuando se le presenta un escenario con problemas de Lync Server, empiece por preguntar "¿qué ya conozco el problema?". Si cuantifica los límites del problema, puede eliminar una gran parte de las entidades operativas de Lync Server.<BR>Considere un escenario de ejemplo en el que sabe que los usuarios no están obteniendo resultados actualizados cuando buscan un contacto. No hay puntos para buscar problemas en los componentes multimedia, la telefonía IP empresarial, la Conferencia y otros muchos componentes. Lo que quizás no sepa es dónde está realmente el problema: ¿en el cliente o es un problema del lado del servidor? El replicador recopila los contactos de Active Directory y los envía al cliente mediante el servidor de la libreta de direcciones (ABserver). ABServer obtiene sus actualizaciones de la base de datos de RTC (donde el replicador de usuarios las escribió) y las recopila en archivos de la libreta de direcciones a la 1:30 de forma predeterminada. Los clientes de Lync Server recuperan la nueva libreta de direcciones con una programación aleatoria. Dado que sabe cómo funciona el proceso, puede reducir la búsqueda de la causa potencial de un problema relacionado con los datos que el replicador de usuarios recopila en Active Directory, si el equipo no puede recuperar y crear los archivos de la libreta de direcciones, o no Descargando el archivo de la libreta de direcciones.



</div>

</div>

<span> </span>

</div>

</div>

</div>

