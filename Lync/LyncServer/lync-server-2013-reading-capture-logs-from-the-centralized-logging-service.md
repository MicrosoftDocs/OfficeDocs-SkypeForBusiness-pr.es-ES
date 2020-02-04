---
title: 'Lync Server 2013: lectura de registros de captura del servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2713c9a1209aad4a96fcb3a76afaf7c2bc61c0dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lectura de registros de captura del servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-28_

Usted se da cuenta de la ventaja real del servicio de registro centralizado después de ejecutar la búsqueda y tiene un archivo que puede usar para realizar un seguimiento de un problema que se ha notificado. Hay varias formas de leer el archivo. El archivo de salida tiene un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que permita abrir y leer un archivo de texto. En el caso de archivos más grandes y problemas más complejos, puede usar una herramienta como Snoop. exe, que está diseñada para leer y analizar los resultados del registro desde el servicio de registro centralizado. El Snoop se incluye con las herramientas de depuración de Lync Server 2013 que están disponibles como una descarga independiente. Puede descargar las herramientas de depuración de Lync Server [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)2013:. Al instalar las herramientas de depuración de Lync Server 2013, no se crean los puntos cortos ni los elementos de menú. Después de instalar las herramientas de depuración de Lync Server 2013, abra el explorador de Windows, una ventana de línea de comandos o un shell de administración de Lync Server y vaya\\al directorio\\(ubicación predeterminada)\\C: archivos de programa herramientas de depuración de Microsoft Lync Server 2013. Haga doble clic en Snoop. exe o escriba Snoop. exe y, a continuación, presione Entrar si está usando la línea de comandos o el shell de administración de Lync Server.

<div>


> [!IMPORTANT]  
> La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas. La solución de problemas y los procesos relacionados con esta son un tema muy complejo. Para obtener detalles sobre la solución de problemas básicos y la solución de problemas de cargas de trabajo específicas, consulte el libro del <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>kit de recursos de 2010 de Microsoft Lync Server en. Los procesos y procedimientos siguen aplicándose a Lync Server 2013.



</div>

Lync Server 2013 introduce una versión actualizada del Snoop que incluye algunas características nuevas. La siguiente captura de pantalla muestra la versión del Snoop de Office Communications Server 2007.

![Office Communications 2007 versión del Snoop.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 versión del Snoop.")

La siguiente captura de pantalla muestra la nueva versión de Snoop, que se incluye en las herramientas de depuración de Lync Server 2013.

![Lync Server 2013 versión del Snoop.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 versión del Snoop.")

La siguiente captura de pantalla muestra la barra de herramientas con funciones usadas con frecuencia.

![Barra de herramientas del 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de herramientas del 2013.")

Y la característica más reciente que agrega valor es la vista de diagrama de diagrama de flujo (flujo de llamadas). Selecciona un flujo de mensajes en la pestaña **mensaje** y haz clic en el botón **flujo de llamadas** . A medida que avance por los mensajes, el diagrama de flujo de llamadas se actualizará con datos nuevos.

![Diagrama de flujo de llamadas del Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de flujo de llamadas del Snooper 2013.")

Puede desplazar el puntero sobre la vista de diagrama y obtener detalles sobre los mensajes y el contenido de los flujos y mensajes, así como los elementos del servidor. Haga clic en cualquier flecha de flujo de llamadas para ir al mensaje en la vista mensajes.

![Detalles del mensaje del diagrama de flujo de llamadas.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalles del mensaje del diagrama de flujo de llamadas.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Para abrir un archivo de registro en Snooper

1.  Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro tiene que ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.

2.  Después de la instalación de las herramientas de depuración de Lync Server (LyncDebugTools. msi), cambie el directorio a la ubicación de Snoop. exe con el explorador de Windows o desde la línea de comandos. De forma predeterminada, las herramientas de depuración se encuentran\\en C\\: archivos de programa\\herramientas de depuración de Microsoft Lync Server 2013. Haga doble clic en Snooper.exe o ejecútelo.

3.  Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.

4.  Los mensajes de **Seguimiento** del archivo de registro se muestran en la pestaña **Seguimiento**. Haga clic en la pestaña **Mensajes** para ver el contenido de los mensajes de los seguimientos recopilados.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>Para mostrar un diagrama de flujo de llamada

1.  Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro es preciso ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.

2.  Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.

3.  Haga clic en **Flujo de llamada**.
    
    <div>
    

    > [!NOTE]  
    > Si hace clic en un mensaje o seguimiento que no forma parte de un flujo de llamada, el diagrama no aparecerá y un mensaje de estado en la parte inferior de Snooper indicará que "Este mensaje no es apto para el flujo de llamada". Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada.

    
    </div>

4.  Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.

5.  Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

