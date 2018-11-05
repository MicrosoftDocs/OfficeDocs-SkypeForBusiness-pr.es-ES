---
title: "Lync Server 2013 : Import. des cas de test de routage des comm. voc."
TOCTitle: Importar casos de prueba de enrutamiento de voz
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48275486
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importar casos de prueba de enrutamiento de voz en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Los casos de prueba constituyen un modo de comprobar las rutas de voz de la organización: primero se definen aspectos como el número que se va a marcar y el plan de marcado y la directiva de voz que se van a usar, y luego Lync Server 2013 comprueba si, dadas dichas condiciones, el número especificado se puede enrutar sin problemas a la red RTC.

Los casos de prueba, que se pueden crear en el Panel de control de Lync Server, se suelen guardar únicamente en el servidor donde el caso se creó y ejecutó inicialmente. Pese a ello, se pueden exportar como archivos XML (con la extensión .vtest) y, luego, importar a otros servidores para que puedan ejecutarse en otros equipos ubicados en distintos puntos de la topología.

## Para importar un caso de prueba de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  En el menú **Acciones**, haga clic en **Importar casos de prueba**.

5.  Busque el archivo del caso de prueba (.vtest) que desee importar y, a continuación, haga clic en **Abrir**.

6.  Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que importe un archivo .vtest, deberá ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el caso de prueba. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.



## Vea también

#### Tareas

[Exportar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)

