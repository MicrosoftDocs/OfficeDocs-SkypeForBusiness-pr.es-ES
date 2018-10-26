---
title: Descripción general del servicio de registro centralizado
TOCTitle: Descripción general del servicio de registro centralizado
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49889394
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Descripción general del servicio de registro centralizado

 

_**Última modificación del tema:** 2016-12-08_

El Servicio de registro centralizado está diseñado para proporcionar un medio para la recopilación controlada de datos, con un ámbito amplio o limitado. Puede recopilar datos de todos los servidores de la implementación simultáneamente, definir elementos específicos para seguimiento, establecer indicadores de seguimiento y devolver resultados de búsqueda de un solo equipo o una agregación de todos los datos de todos los servidores. El Servicio de registro centralizado se ejecuta en todos los servidores de su implementación. La arquitectura del Servicio de registro centralizado está compuesta por los siguientes agentes y servicios:

  - *Agente del servicio de registro centralizado*   ClsAgent.exe es el archivo ejecutable del servicio que se comunica con el controlador y recibe los comandos que el administrador ejecuta para el controlador. El agente se ejecuta como un servicio en cada equipo de Lync Server. Cuando el agente recibe un comando, lo ejecuta, envía mensajes a los componentes definidos para seguimiento y escribe los registros de seguimiento en el disco. También lee los registros de seguimiento de su equipo y envía los datos de seguimiento de nuevo al controlador cuando se solicitan. ClsAgent escucha los comandos en los siguientes puertos: **TCP 50001**, **TCP 50002** y **TCP 50003**.

  - *Controlador del servicio de registro centralizado*   ClsControllerLib.dll es el motor de ejecución de comandos del Shell de administración de Lync Server y de ClsController.exe. CLSControllerLib.dll envía los comandos Start, Stop, Flush y Search a ClsAgent. Cuando se envían comandos de búsqueda, los registros resultantes se devuelven a ClsControllerLib.dll y se agregan. El controlador es responsable de enviar comandos al agente, de recibir el estado de dichos comandos y de administrar los datos del archivo de registro que devuelven todos los agentes sobre cualquier equipo del ámbito de búsqueda, y de agregar los datos de registro en un conjunto de resultados significativo y ordenado. La información de los temas siguientes se centra en el uso del Shell de administración de Lync Server. ClsController.exe se limita a un subconjunto de las características y funciones que están disponibles en el Shell de administración de Lync Server. Puede obtener ayuda para ClsController.exe en la línea de comandos; para ello, escriba `ClsController` en el directorio predeterminado C:\\Archivos de programa\\Archivos comunes\\Microsoft Lync Server 2013\\ClsAgent

**Comunicaciones de ClsController con ClsAgent**

![Relación entre CLSController y CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relación entre CLSController y CLSAgent.")

Los comandos se ejecutan mediante la interfaz de línea de comandos de Windows Server o mediante Shell de administración de Lync Server. Los comandos se ejecutan en el equipo donde haya iniciado sesión y se envían a ClsAgent localmente o a los demás equipos y grupos de su implementación.

ClsAgent mantiene un archivo de índice de todos los archivos .CACHE disponibles en el equipo local. ClsAgent los asigna de manera que se distribuyan uniformemente entre todos los volúmenes definidos por la opción CacheFileLocalFolders, sin consumir nunca más del 80% de cada volumen (la ubicación de la caché local y el porcentaje se pueden configurar mediante el cmdlet **Set-CsClsConfiguration**). ClsAgent también es responsable de limpiar los archivos de registro de seguimiento de eventos (.etl) del equipo local. Después de dos semanas (el período de tiempo se puede configurar mediante el cmdlet **Set-CsClsConfiguration**), estos archivos se copian a un recurso compartido de archivos y se eliminan del equipo local. Para obtener más información, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration). Cuando se recibe una solicitud de búsqueda, se usan los criterios de búsqueda para seleccionar el conjunto de archivos .etl en caché para realizar la búsqueda en función de los valores del índice que mantiene el agente.


> [!NOTE]
> ClsAgent puede buscar en los archivos que se trasladan al recurso compartido de archivos desde el equipo local. Después de que ClsAgent mueve los archivos al recurso compartido de archivos, ClsAgent no realiza el mantenimiento de limpieza y eliminación de archivos. Debe definir una tarea administrativa para supervisar el tamaño de los archivos en el recurso compartido de archivos y eliminarlos o archivarlos.



Los archivos de registro resultantes se pueden leer y analizar usando diferentes herramientas, incluida **Snooper.exe** y otras herramientas que puedan leer un archivo de texto, como **Notepad.exe**. Snooper.exe forma parte de las herramientas de depuración de Lync Server 2013 y está disponible para su descarga en Internet.

Al igual que OCSLogger, el Servicio de registro centralizado tiene varios componentes con los que realizar el seguimiento, y dispone de opciones para seleccionar indicadores, como TF\_COMPONENT y TF\_DIAG. El Servicio de registro centralizado también conserva las opciones del nivel de registro de OCSLogger.

La principal ventaja de usar Windows PowerShell frente a ClsController en la línea de comandos es que puede configurar y definir nuevos escenarios usando los proveedores seleccionados orientados al espacio de problemas, a los indicadores personalizados y a los niveles de registro. Los escenarios disponibles para ClsController se limitan a los que están definidos para el archivo ejecutable.

En versiones anteriores, OCSLogger.exe se proporcionaba para que los administradores y el personal de soporte pudiera recopilar archivos de seguimiento de los equipos de la implementación. A pesar de sus ventajas, OCSLogger tenía una limitación. Solo se podían recopilar los registros de un equipo al mismo tiempo. Podía realizar el registro de varios equipos usando copias diferentes de OCSLogger, pero al final obtenía varios registros y ninguna manera sencilla de agregar los resultados.

Cuando un usuario solicita una búsqueda de registros, ClsController determina a qué equipos se enviará la solicitud (en función de los escenarios seleccionados). También determina si es necesario enviar la búsqueda al recurso compartido de archivos donde se encuentran los archivos .etl guardados. Cuando los resultados de búsqueda se devuelven a ClsController, el controlador combina los resultados en un único conjunto de resultados ordenados por tiempo, que se presenta al usuario. Los usuarios pueden guardar los resultados de búsqueda en su equipo local para su posterior análisis.

Cuando inicia una sesión de registro, especifica los escenarios relativos al problema que está intentando resolver. Puede tener dos escenarios en ejecución al mismo tiempo. Uno de los dos debe ser el escenario AlwaysOn. Como su nombre indica, siempre debe estar en ejecución en su implementación, recopilando información sobre todos los equipos, grupos y componentes.

> [!IMPORTANT]  
> De forma predeterminada, el escenario AlwaysOn no se ejecuta en su implementación. Debe iniciarlo explícitamente. Una vez iniciado, continuará ejecutándose hasta que se detenga explícitamente, y el estado en ejecución persistirá aunque se reinicien los equipos. Para obtener más información sobre cómo iniciar y detener escenarios, consulte <a href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Uso de Inicio para el servicio de registro centralizado para los registros de captura</a> y <a href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Uso de Detener en el servicio de registro centralizado</a>.



Cuando se produce un problema, inicia un segundo escenario relacionado con el problema notificado. Reproduce el problema y detiene el registro del segundo escenario. Comienza las búsquedas de registros relativas al problema notificado. La colección agregada de registros produce un archivo de registro que contiene mensajes de seguimiento de todos los equipos del ámbito de sitio o global de su implementación. Si la búsqueda devuelve más datos de los que es razonable analizar (lo que normalmente se conoce como relación señal-ruido, en la que el ruido es demasiado alto), ejecuta otra búsqueda con parámetros más limitados. En este punto, puede comenzar a observar que aparecen patrones que le ayudarán a centrarse en el problema. Por último, después de realizar un par de búsquedas más refinadas, podrá encontrar los datos relativos al problema y averiguar la causa originaria.

> [!TIP]  
> Cuando se le presente un escenario de problemas en Lync Server, comience por preguntarse “¿Qué sé realmente ya acerca del problema?”. Si cuantifica los límites del problema, podrá eliminar gran parte de las entidades operativas de Lync Server.<br />
> Considere un escenario de ejemplo en el que sabe que los usuarios no están obteniendo resultados actualizados cuando buscan un contacto. No tiene sentido buscar problemas en los componentes de medios, Telefonía IP empresarial, conferencias y algunos otros componentes. Lo que quizás no sepa es dónde está realmente el problema: ¿en el cliente o es un problema del lado del servidor? El replicador de usuarios recopila los contactos de Active Directory y los envía al cliente mediante el servidor de libreta de direcciones (ABServer). ABServer obtiene sus actualizaciones de la base de datos de RTC (donde el replicador de usuarios las escribió) y las recopila en archivos de libreta de direcciones a la 1:30 a.m de forma predeterminada. Los clientes de Lync Server recuperan la nueva libreta de direcciones según una programación aleatoria. Como conoce el funcionamiento del proceso, puede reducir la búsqueda de la posible causa a un problema relativo a los datos que el replicador de usuarios recopila de Active Directory, a que ABServer no está recuperando o creando los archivos de libretas de direcciones o a que los clientes no están descargando el archivo de libreta de direcciones.

