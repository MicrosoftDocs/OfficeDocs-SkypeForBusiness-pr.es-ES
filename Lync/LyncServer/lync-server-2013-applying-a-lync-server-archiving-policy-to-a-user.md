---
title: Aplicación de una directiva de archivado de Lync Server a un usuario
TOCTitle: Aplicación de una directiva de archivado de Lync Server a un usuario
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48276251
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aplicación de una directiva de archivado de Lync Server a un usuario

 

_**Última modificación del tema:** 2012-10-10_

Después de crear una directiva de usuario de Lync Server, debe aplicarla a los usuarios o grupos de usuarios específicos alojados en Lync Server 2013 antes de que surta efecto. Para obtener información detallada sobre la creación de directivas de usuarios para usuarios específicos, consulte [Crear y configurar las directivas de usuarios para el archivado en Lync Server](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) en documentación referente a la implementación.

Para obtener información detallada sobre cómo funcionan las políticas de archivado, incluida la jerarquía de las directivas globales, del sitio y del usuario, consulte la documentación referente a la planificación [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md), la documentación referente a la implementación o la documentación referente a las operaciones.


> [!NOTE]
> Para configurar y usar el archivado, es necesario que primero implemente el archivado. Para más información, vea <A href="lync-server-2013-deploying-archiving.md">Implementar archivado en Lync Server 2013</A> en la documentación referente a la implementación.<BR>Si habilitó la integración de Microsoft Exchange para su implementación, las directivas en conservación local de Exchange controlan si el archivado está habilitado para los usuarios que están alojados en Exchange 2013 y que tienen sus buzones de correo en conservación local. Para obtener información detallada, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación referente a la implementación.<BR>Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado. Para obtener información detallada, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configurar opciones de archivado</A> en la documentación referente a la implementación.



## Para aplicar una directiva de archivado de Lync Server a un usuario

1.  Desde una cuenta de usuario que se asigne a la función CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y escriba la URL del administrador para abrir el Panel de control de Lync Server 2013. Para obtener más información sobre los diferentes métodos que puede utilizar para iniciar Panel de control de Lync Server 2013, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles** .

5.  En **Editar usuario de Lync Server** en **Directiva de archivado**, seleccione la directiva de usuario de archivado que desea aplicar.
    

    > [!NOTE]
    > En configuración <STRONG>&lt;Automática&gt;</STRONG>, aplique la configuración de la instalación del servidor predeterminada. El servidor aplica automáticamente esta configuración.



6.  Haga clic en **Confirmar** .

