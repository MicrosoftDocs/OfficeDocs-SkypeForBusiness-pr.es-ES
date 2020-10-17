---
title: 'Lync Server 2013: lectura de registros de captura desde el servicio de registro centralizado'
description: 'Lync Server 2013: lectura de registros de captura desde el servicio de registro centralizado.'
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
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559166"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lectura de registros de captura desde el servicio de registro centralizado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-28_

Tiene en cuenta las ventajas reales del servicio de registro centralizado después de ejecutar la búsqueda y tiene un archivo que puede usar para realizar un seguimiento de un problema notificado. Hay varias formas de leer el archivo. El archivo de salida está en un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que le permita abrir y leer un archivo de texto. Para archivos más grandes y problemas más complejos, puede usar una herramienta como Snooper.exe que está diseñada para leer y analizar el resultado del registro del servicio de registro centralizado. Snooper se incluye con las herramientas de depuración de Lync Server 2013 que están disponibles como una descarga independiente. Puede descargar las herramientas de depuración de Lync Server 2013 aquí: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) . Al instalar las herramientas de depuración de Lync Server 2013, los elementos de menú y los cortados no se crean. Después de instalar las herramientas de depuración de Lync Server 2013, abra el explorador de Windows, una ventana de línea de comandos o shell de administración de Lync Server y vaya al directorio (ubicación predeterminada) C: \\ archivos de programa \\ herramientas de depuración de Microsoft Lync Server 2013 \\ . Haga doble clic en Snooper.exe o escriba Snooper.exe y, a continuación, presione Entrar si está usando la línea de comandos o el shell de administración de Lync Server.

<div>


> [!IMPORTANT]  
> La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas. La solución de problemas y los procesos relacionados con esta son un tema muy complejo. Para obtener más información sobre la solución de problemas básicos y la solución de problemas de cargas de trabajo específicas, consulte el manual del kit de recursos de Microsoft Lync Server 2010 en <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> . Los procesos y procedimientos siguen siendo válidos para Lync Server 2013.



</div>

Lync Server 2013 presenta una versión actualizada del Snoop que incluye algunas características nuevas. En la siguiente captura de pantalla se muestra la versión de Snoop de Office Communications Server 2007.

![Office Communications 2007 versión del Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 versión del Snooper.")

En la siguiente captura de pantalla vemos la nueva versión del Snooper que se incluye en las herramientas de depuración de Lync Server 2013.

![Lync Server 2013 versión de Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 versión de Snooper.")

La captura de pantalla siguiente muestra la barra de herramientas con las funciones que se usan con mayor frecuencia.

![Barra de herramientas de Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de herramientas de Snooper 2013.")

La característica más reciente que agrega valor es la vista de Diagrama de flujo (flujo de llamada). Se selecciona un flujo de mensaje en la pestaña **Mensaje** y se hace clic en el botón **Flujo de llamada**. A medida que avanza por los mensajes, el diagrama de flujo de llamada se actualiza con nuevos datos.

![Diagrama de flujo de llamadas de Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de flujo de llamadas de Snooper 2013.")

Puede pasar el mouse por encima de la vista de diagrama y obtener detalles sobre los mensajes y el contenido de los flujos y los mensajes, así como de los elementos del servidor. Haga clic en una flecha del flujo de llamada y vaya al mensaje en la vista Mensaje.

![Detalles del mensaje del diagrama de flujo de llamadas.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalles del mensaje del diagrama de flujo de llamadas.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Para abrir un archivo de registro en Snooper:

1.  Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.

2.  Tras la instalación de las herramientas de depuración de Lync Server (LyncDebugTools.msi), cambie el directorio a la ubicación de Snooper.exe con el explorador de Windows o desde la línea de comandos. De forma predeterminada, las herramientas de depuración se encuentran en C: \\ archivos de programa \\ herramientas de depuración de Microsoft Lync Server 2013 \\ . Haga doble clic en Snooper.exe o ejecútelo.

3.  Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.

4.  Los mensajes de **Seguimiento** del archivo de registro se muestran en la pestaña **Seguimiento**. Haga clic en la pestaña **Mensajes** para ver el contenido de los mensajes de los seguimientos recabados.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>Para mostrar un diagrama de flujo de llamada:

1.  Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.

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

