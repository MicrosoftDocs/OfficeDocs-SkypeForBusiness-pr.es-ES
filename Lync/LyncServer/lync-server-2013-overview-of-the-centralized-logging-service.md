---
title: 'Lync Server 2013: información general sobre el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f2589e6c30a6ca928230dde2deb32f23e91967
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Información general sobre el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

El servicio de registro centralizado está diseñado para proporcionar un medio para la recopilación de datos controlada, con un ámbito amplio o estrecho. Puede recopilar datos de todos los servidores de la implementación a la vez, definir elementos específicos para realizar un seguimiento, establecer marcas de seguimiento y devolver resultados de búsqueda de un único equipo o una agregación de todos los datos de todos los servidores. El servicio de registro centralizado se ejecuta en todos los servidores de la implementación. La arquitectura del servicio de registro centralizado consta de los siguientes agentes y servicios:

  - *Agente de servicio de registro centralizado*   ClsAgent. exe es el ejecutable de servicio que se comunica con el controlador y recibe los comandos que el administrador emite el controlador. El agente se ejecuta como un servicio en cada equipo de Lync Server. Cuando el agente recibe un comando, ejecuta el comando, envía mensajes a los componentes definidos para el seguimiento y escribe los registros de seguimiento en el disco. También lee los registros de seguimiento de su equipo y envía los datos de seguimiento de vuelta al controlador cuando se solicitan. El ClsAgent escucha los comandos en los siguientes puertos: **tcp 50001**, **TCP 50002**y **TCP 50003**.

  - *Controlador del servicio de registro centralizado*   ClsControllerLib. dll es el motor de ejecución del comando para el shell de administración de Lync Server y para ClsController. exe. CLSControllerLib. dll envía los comandos iniciar, detener, vaciar y buscar a la ClsAgent. Cuando se envían los comandos de búsqueda, los registros resultantes se devuelven a ClsControllerLib. dll y se agregan. El controlador es responsable de enviar comandos al agente, recibir el estado de dichos comandos y administrar los datos del archivo de registro de búsqueda a medida que se devuelven de todos los agentes en un equipo en el ámbito de búsqueda y de agregar los datos de registro en un sentido y ordenados. conjunto de resultados. La información de los temas siguientes se centra en el uso del shell de administración de Lync Server. ClsController. exe se limita a un subconjunto de las características y funciones que están disponibles en el shell de administración de Lync Server. La ayuda para ClsController. exe está disponible en la línea de comandos `ClsController` escribiendo en el directorio predeterminado C\\: archivos\\de programa\\archivos comunes Microsoft Lync\\Server 2013 ClsAgent.

**ClsController Communications a ClsAgent**

![Relación entre CLSController y CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relación entre CLSController y CLSAgent.")

Puede emitir comandos mediante la interfaz de línea de comandos de Windows Server o mediante el shell de administración de Lync Server. Los comandos se ejecutan en el equipo en el que ha iniciado sesión y se envían a ClsAgent localmente o en los otros equipos y grupos de la implementación.

ClsAgent mantiene un archivo de índice de ALL. Archivos de caché que tiene en el equipo local. ClsAgent los asigna para que se distribuyan uniformemente entre los volúmenes definidos por la opción CacheFileLocalFolders, y nunca consumen más del 80% de cada volumen (es decir, la ubicación de la memoria caché local y el porcentaje se pueden configurar mediante el cmdlet **set-CsClsConfiguration** ). ClsAgent también es responsable de la caducidad de los archivos de registro de seguimiento de eventos (. ETL) almacenados en caché antiguos del equipo local. Después de dos semanas (es decir, el período de tiempo se puede configurar mediante el cmdlet **set-CsClsConfiguration** ) estos archivos se copian en un recurso compartido de archivos y se eliminan del equipo local. Para obtener más información, consulte [set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Cuando se recibe una solicitud de búsqueda, los criterios de búsqueda se usan para seleccionar el conjunto de archivos. ETL en caché para realizar la búsqueda en función de los valores del índice mantenido por el agente.

<div>


> [!NOTE]  
> Los archivos que se mueven al recurso compartido de archivos desde el equipo local pueden ser buscados por ClsAgent. Una vez que ClsAgent mueve los archivos al recurso compartido de archivos, ClsAgent no mantiene la caducidad y la eliminación de los archivos. Debe definir una tarea administrativa para supervisar el tamaño de los archivos en el recurso compartido de archivos y eliminarlos o archivarlos.



</div>

Los archivos de registro resultantes se pueden leer y analizar con una amplia variedad de herramientas, entre las que se incluyen **Snooper. exe** y cualquier otra herramienta que pueda leer un archivo de texto, como **Notepad. exe**. Snooper. exe forma parte de las herramientas de depuración de Lync Server 2013 y está disponible como [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)descarga desde el Web.

Al igual que OCSLogger, el servicio de registro centralizado tiene varios componentes de los que se realiza el seguimiento y proporciona opciones para\_seleccionar marcas,\_como TF Component y TF diag. El servicio de registro centralizado también conserva las opciones de nivel de registro de OCSLogger.

La ventaja más importante para usar el shell de administración de Lync Server a través de la línea de comandos ClsController es que puede configurar y definir escenarios nuevos con los proveedores seleccionados destinados al espacio de problemas, los indicadores personalizados y los niveles de registro. Los escenarios disponibles para ClsController se limitan a los que se definen para el archivo ejecutable.

En versiones anteriores, se proporcionaba OCSLogger. exe para permitir que los administradores y el personal de soporte técnico recopilaran archivos de seguimiento de los equipos de la implementación. OCSLogger, para todos sus puntos fuertes ha tenido una deficiencia. Solo se podían recopilar registros en un equipo en un momento dado. Puede iniciar sesión en varios equipos con copias independientes de OCSLogger, pero ha terminado con varios registros y no tiene una forma sencilla de agregar los resultados.

Cuando un usuario solicita una búsqueda de registros, el ClsController determina a qué máquinas se debe enviar la solicitud (es decir, en función de los escenarios seleccionados). También determina si es necesario enviar la búsqueda al recurso compartido de archivos donde se encuentran los archivos. ETL guardados. Cuando los resultados de la búsqueda se devuelven a ClsController, el controlador combina los resultados en un único conjunto de resultados ordenado por tiempo que se presenta al usuario. Los usuarios pueden guardar los resultados de la búsqueda en su equipo local para analizarlos más detalladamente.

Cuando se inicia una sesión de registro, se especifican escenarios relacionados con el problema que se intenta resolver. Puede tener dos escenarios en ejecución en cualquier momento. Uno de estos dos escenarios debe ser el escenario AlwaysOn. Como su nombre implica, siempre debe estar en ejecución en la implementación, recopilando información en todos los equipos, grupos de servidores y componentes.

<div>


> [!IMPORTANT]  
> De forma predeterminada, el escenario AlwaysOn no se está ejecutando en su implementación. Debe iniciar explícitamente el escenario. Una vez iniciado, continuará ejecutándose hasta que se detenga explícitamente y el estado en ejecución persistirá a lo largo de los reinicios de los equipos. Para obtener más información sobre cómo iniciar y detener escenarios, consulte <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Inicio para el servicio de registro centralizado para capturar registros en Lync server 2013</A> y <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">usar detener para el servicio de registro centralizado en Lync Server 2013</A>.



</div>

Cuando se produzca un problema, inicie un segundo escenario relacionado con el problema notificado. Reproduzca el problema y detenga el registro para el segundo escenario. Comience las búsquedas de registros relativas al problema del que se informa. La colección agregada de registros genera un archivo de registro que contiene mensajes de seguimiento de todos los equipos de su sitio o ámbito global de la implementación. Si la búsqueda devuelve más datos de los que puede analizar de manera factible (lo que se conoce normalmente como una relación señal-ruido, en la que el ruido es demasiado alto), se ejecuta otra búsqueda con parámetros más estrechos. En este momento, puede empezar a ver patrones que se muestran y puede ayudarle a tener un enfoque más claro sobre el problema. Por último, después de realizar un par de búsquedas refinadas, puede encontrar datos relevantes para el problema y averiguar la causa raíz.

<div>


> [!TIP]  
> Cuando aparezca un escenario con problemas en Lync Server, empiece a preguntarse "¿Qué es lo que ya sé sobre el problema?". Si cuantifica los límites del problema, puede eliminar una gran parte de las entidades operativas en Lync Server.<BR>Considere un escenario de ejemplo en el que sabe que los usuarios no obtienen los resultados actuales al buscar un contacto. No tiene sentido buscar problemas en los componentes multimedia, la telefonía IP empresarial, la Conferencia y varios otros componentes. Lo que quizás no sepa es dónde se encuentra realmente el problema: ¿en el cliente o es un problema del servidor? El replicador de usuarios recopila los contactos de Active Directory y los entrega al cliente mediante el servidor de libreta de direcciones (ABserver). El abcargador obtiene sus actualizaciones de la base de datos RTC (donde el replicador de usuarios las escribió) y las recopila en archivos de la libreta de direcciones, de manera predeterminada – 1:30 A.M. Los clientes de Lync Server recuperan la nueva libreta de direcciones con una programación aleatoria. Como sabe cómo funciona el proceso, puede reducir la búsqueda por la posible causa de un problema relacionado con los datos recopilados desde Active Directory por el replicador de usuarios, el que no puede recuperar y crear los archivos de la libreta de direcciones o los clientes no descargar el archivo de la libreta de direcciones.



</div>

</div>

<span> </span>

</div>

</div>

</div>

