---
title: "Lync Server 2013 : Imp. d’un fichier de conf. d’itinéraire de comm. vocales"
TOCTitle: Importar un archivo de configuración de enrutamiento de voz
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48275207
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importar un archivo de configuración de enrutamiento de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Si desea guardar la configuración del enrutamiento de voz sin publicarla, siga los pasos de este tema para usar los comandos de exportación e importación de la configuración de Panel de control de Lync Server con el fin de guardar y recuperar una instantánea de la configuración del enrutamiento de voz. Cuando se importa un archivo de configuración de enrutamiento de voz (.vcfg), mientras se realizan cambios en la configuración del enrutamiento de voz en el servidor, las páginas en el grupo **Enrutamiento de voz** de Panel de control de Lync Server indicarán que existen cambios sin confirmar en el enrutamiento de voz. Estos cambios sin confirmar son distintos entre dos configuraciones que requieren reconciliación.

Si ha realizado cambios sin confirmar en la configuración en cualquier página en el grupo, los cambios se guardan en el archivo de configuración de voz exportado (.vcfg). De esta forma, puede realizar cambios en la configuración del enrutamiento de voz durante varias sesiones de antes de publicar los cambios.

## Para importar una configuración de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  En el menú **Acciones**, haga clic en **Importar configuración**.

5.  Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.

6.  Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que importe un archivo de configuración de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.



## Vea también

#### Tareas

[Exportar un archivo de configuración de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

