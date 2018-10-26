---
title: Configurar directivas de sitio para el archivado
TOCTitle: Configurar directivas de sitio para el archivado
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48276876
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar directivas de sitio para el archivado

 

_**Última modificación del tema:** 2012-10-09_

Puede habilitar o deshabilitar el archivado de sitios específicos al crear y configurar una directiva de archivado para cada uno de esos sitios. Las directiva de sitio anulan la directiva global pero las directivas de usuario anulan las directivas de sitio. El archivado de directivas solo se aplica si no usa una integración de Microsoft Exchange o bien si usa la integración de Microsoft Exchange pero algunos de sus usuarios no están alojados en Exchange 2013 y tienen sus buzones en Conservación local.

Para obtener información detallada sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, del sitio y del usuario, consulte la documentación referente a la planificación [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md), la documentación referente a la implementación o la documentación referente a las operaciones.


> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Conservación local de Exchange controlan si el archivado está habilitado para los usuarios que están alojados en Exchange 2013 y que tienen sus buzones de correo en Conservación local. Para obtener información detallada, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación referente a la implementación.<BR>Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado. Para obtener información detallada, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configurar opciones de archivado</A> en la documentación referente a la implementación.



## Para crear una directiva de archivado para un sitio

1.  Desde una cuenta de usuario que se asigne a la función CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y escriba la URL del administrador para abrir el Panel de control de Lync Server 2013.

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
    Para obtener información detallada sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, del sitio y del usuario, consulte la documentación referente a la planificación [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md), la documentación referente a la implementación o la documentación referente a las operaciones.

4.  Haga clic en **Nuevo** y en **Directiva de sitio** .

5.  En **Seleccionar un sitio** , haga clic en el sitio al que se va a aplicar la directiva.

6.  En **Directiva de archivado nueva** , haga lo siguiente:
    
      - En **Nombre** , especifique el nombre para la directiva de sitio.
    
      - En **Descripción**, proporcione información sobre la función de la directiva de sitio (por ejemplo, directiva de archivado de usuarios externos para Redmond).
    
      - Para controlar el archivado de comunicaciones internas para los sitios especificados, active o desactive la casilla **Archivar comunicaciones internas** .
    
      - Para controlar el archivado de comunicaciones externas para los usuarios especificados, active o desactive la casilla **Archivar comunicaciones externas** .

7.  Haga clic en **Confirmar** .

