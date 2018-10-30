---
title: Configurar las directivas globales para el archivado
TOCTitle: Configurar las directivas globales para el archivado
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48275320
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar las directivas globales para el archivado

 

_**Última modificación del tema:** 2012-10-09_

Al implementar el Servidores front-end, Lync Server crea una directiva global para el archivado. De forma predeterminada, el archivado se deshabilita en la directiva global. La directiva global controla si el archivado está habilitado para las comunicaciones externas e internas en toda la implementación, a menos que se instalen directivas de sitio o de usuario, las cuales anularán la directiva global o si usa la integración de Microsoft Exchange para algunos o todos sus usuarios. Si usa la integración de Microsoft Exchange, la directiva global no se aplica a los usuarios que se alojan enExchange 2013 han colocado buzones en Conservación local. .

Para obtener información detallada sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, del sitio y del usuario, consulte la documentación referente a la planificación [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md), la documentación referente a la implementación o la documentación referente a las operaciones.


> [!NOTE]
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Conservación local de Exchange controlan si el archivado está habilitado para los usuarios que están alojados en Exchange 2013 y que tienen sus buzones de correo colocados en Conservación local. Para información detallada, vea <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación referente a la implementación.<BR>Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado. Para información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">Configurar opciones de archivado</A> en la documentación referente a la implementación.



## Configurar la directiva global de archivado al usar bases de datos de archivado de Lync Server

1.  Desde una cuenta de usuario que se asigne a la función CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y escriba la URL del administrador para abrir el Panel de control de Lync Server 2013. Para información detallada sobre los diferentes métodos que puede usar para abrir Panel de control de Lync Server 2013, vea [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  En la página **Directiva de archivado**, haga clic en **Global**, **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar directiva de archivado - Global**, haga lo siguiente:
    
      - En **Nombre**, si no desea usar el nombre predeterminado Global, especifique un nombre nuevo para la directiva global.
    
      - En **Descripción**, proporcione información sobre la directiva (por ejemplo, Directiva global para *divisionName*).
    
      - Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente mediante una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas** .
    
      - Para controlar el archivado de las comunicaciones externas de todos los usuarios y sitios que no se controlan específicamente mediante una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones externas** .

6.  Haga clic en **Confirmar** .

