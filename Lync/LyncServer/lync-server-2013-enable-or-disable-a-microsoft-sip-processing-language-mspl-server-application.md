---
title: "Habilitar/deshabilitar aplic. leng. procesam. protocolo inicio de sesión de MS (MSPL)"
TOCTitle: "Act. ou dés une app. de serveur MSPL (Microsoft SIP Processing Language)"
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48276388
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar una aplicación de servidor de lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL)

 

_**Última modificación del tema:** 2012-09-21_

Puede usar el Panel de control de Lync Server para habilitar o deshabilitar las aplicaciones de servidor de lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL) que se ejecuten en su entorno de Lync Server 2013. Estas aplicaciones son solo de script y usan lenguaje de scripting en lugar de la API de Microsoft Lync 2013 Preview.

No todos los scripts se pueden habilitar o deshabilitar. Por ejemplo, el script DefaultRouting está habilitado y esta opción no se puede cambiar para DefaultRouting.

## Para habilitar o deshabilitar una aplicación de servidor de MSPL

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Aplicación de servidor**.

4.  En la página **Aplicación de servidor**, haga clic en un encabezado de columna para ordenar las aplicaciones, si fuera necesario, y, a continuación, haga clic en la aplicación de servidor que desee modificar.

5.  Haga clic en **Acción**.

6.  Haga clic en **Habilitar aplicación** o en **Deshabilitar aplicación** (es decir, si el script admite esta opción).

## Vea también

#### Tareas

[Marcar una aplicación de lenguaje de procesamiento de protocolo de inicio de sesión de Microsoft (MSPL) como crítica o no crítica](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  

#### Conceptos

[Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### Otros recursos

[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

