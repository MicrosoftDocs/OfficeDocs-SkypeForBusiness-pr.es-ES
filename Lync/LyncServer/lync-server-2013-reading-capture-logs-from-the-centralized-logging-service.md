---
title: "Lecture des journ. de capt. à partir du service de journalisation centralisée"
TOCTitle: "Lecture des journ. de capt. à partir du service de journalisation centralisée"
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49889677
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lectura de registros de captura desde el servicio de registro centralizado

 

_**Última modificación del tema:** 2016-12-28_

Las auténticas ventajas de Servicio de registro centralizado pueden apreciarse al realizar una búsqueda y obtener un archivo con el que se puede realizar un seguimiento de un problema resuelto. Hay varias formas de leer el archivo. El archivo de salida tiene el formato de texto estándar y puede usar Notepad. exe o cualquier otro programa que permita abrir y leer archivos de texto. Para los archivos de mayor tamaño y problemas más complejos, puede usar una herramienta como Snooper.exe, que está diseñada para leer y analizar la salida del registro de Servicio de registro centralizado. Snooper forma parte de las herramientas de depuración de Lync Server 2013 disponibles en una descarga independiente. No hay accesos directos ni opciones de menú para las herramientas de depuración de Lync Server 2013. Una vez que las haya instalado, abra el explorador de Windows, una ventana de línea de comandos o Shell de administración de Lync Server, y vaya directamente al directorio (ubicación predeterminada) C:\\Archivos de programa\\Microsoft Lync Server 2013\\Debugging Tools. Haga doble clic en Snooper.exe o escriba Snooper.exe y presione Entrar si está usando la línea de comandos o Shell de administración de Lync Server.

> [!IMPORTANT]  
> La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas. La solución de problemas y los procesos relacionados con esta son un tema muy complejo. Para más información sobre los conceptos básicos de la solución de problemas y sus cargas de trabajo específicas, consulte el manual del kit de recursos de Microsoft Lync Server 2010 en <a href="http://go.microsoft.com/fwlink/?linkid=211003%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=211003&amp;clcid=0xC0A</a>. Los procesos y procedimientos también pueden aplicarse a Lync Server 2013.



Lync Server 2013 incorpora una versión actualizada de Snooper que incluye nuevas características. En la captura de pantalla siguiente se muestra la versión de Snooper de Office Communications Server 2007.

![Office Communications 2007 versión de Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 versión de Snooper.")

La captura de pantalla siguiente muestra la nueva versión de Snooper que se incluye en las herramientas de depuración de Lync Server 2013.

![Versión Lync Server 2013 de Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Versión Lync Server 2013 de Snooper.")

La captura de pantalla siguiente muestra la barra de herramientas con las funciones que se usan con mayor frecuencia.

![Barra de herramientas de Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de herramientas de Snooper 2013.")

La característica más reciente que agrega valor es la vista de Diagrama de flujo (flujo de llamada). Se selecciona un flujo de mensaje en la pestaña **Mensaje** y se hace clic en el botón **Flujo de llamada**. A medida que avanza por los mensajes, el diagrama de flujo de llamada se actualiza con nuevos datos.

![Diagrama de flujo de llamadas de Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de flujo de llamadas de Snooper 2013.")

Puede pasar el mouse por encima de la vista de diagrama y obtener detalles sobre los mensajes y el contenido de los flujos y los mensajes, así como de los elementos del servidor. Haga clic en una flecha del flujo de llamada y vaya al mensaje en la vista Mensaje.

![Detalles de mensaje del diagrama de flujo de llamadas.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalles de mensaje del diagrama de flujo de llamadas.")

## Para abrir un archivo de registro en Snooper:

1.  Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.

2.  Tras la instalación de las herramientas de depuración de Lync Server (LyncDebugTools.msi), sitúese en el directorio donde se encuentra Snooper.exe con el explorador de Windows o desde la línea de comandos. De forma predeterminada, las herramientas de depuración se encuentran en C:\\Archivos de programa\\Microsoft Lync Server 2013\\Debugging Tools. Haga doble clic en Snooper.exe o ejecútelo.

3.  Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.

4.  Los mensajes de **Seguimiento** del archivo de registro se muestran en la pestaña **Seguimiento**. Haga clic en la pestaña **Mensajes** para ver el contenido de los mensajes de los seguimientos recabados.

## Para mostrar un diagrama de flujo de llamada:

1.  Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.

2.  Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.

3.  Haga clic en **Flujo de llamada**.
    

    > [!NOTE]
    > Si hace clic en un mensaje o seguimiento que no forma parte de un flujo de llamada, el diagrama no aparecerá y un mensaje de estado en la parte inferior de Snooper indicará que "Este mensaje no es apto para el flujo de llamada". Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada.



4.  Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.

5.  Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.

