---
title: "Lync Server 2013: Marcar una aplicación MSPL como crítica o no crítica"
TOCTitle: "Marquer une app. serv. MSPL comme critique ou non critique"
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48276934
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Marcar una aplicación de lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL) como crítica o no crítica

 

_**Última modificación del tema:** 2012-11-01_

Las aplicaciones de servidor del Lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL) son aplicaciones de solo script que usan el lenguaje de scripting MSPL, en lugar del Microsoft Lync 2010 API. Algunas aplicaciones de servidor de MSPL se consideran críticas. Si un script es crítico, es necesario que se inicie al arrancar el sistema para que se inicie Lync Server 2013. Si se produce un error en el script mientras se está ejecutando Lync Server, el servidor no se apagará, pero dejará de enviar tráfico al script y escribirá los errores en el registro de eventos.

Puede usar Panel de control de Lync Server para marcar o desmarcar como críticas las aplicaciones de servidor del Lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL).

No todos los scripts son compatibles con esta opción. Por ejemplo, el script DefaultRouting está marcado como crítico y esta opción no se puede cambiar.

## Para marcar o desmarcar una aplicación de servidor de MSPL como crítica

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Aplicación de servidor**.

4.  En la página **Aplicación de servidor**, haga clic en un encabezado de columna para ordenar las aplicaciones, si fuera necesario, y, a continuación, haga clic en la aplicación de servidor que desee modificar.

5.  Haga clic en **Acción**.

6.  Haga clic en **Marcar como crítico** o **Anular selección como crítico** (si el script admite esta opción).

## Vea también

#### Tareas

[Habilitar o deshabilitar una aplicación de servidor de lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL)](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  

#### Conceptos

[Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### Otros recursos

[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

