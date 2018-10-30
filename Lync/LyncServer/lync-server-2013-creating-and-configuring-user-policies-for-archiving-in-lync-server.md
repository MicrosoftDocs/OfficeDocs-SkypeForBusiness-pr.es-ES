---
title: "Créa. et conf. des stratégies d’utilisateur pour l’archivage dans Lync Server"
TOCTitle: "Créa. et conf. des stratégies d’utilisateur pour l’archivage dans Lync Server"
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48275386
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear y configurar las directivas de usuarios para el archivado en Lync Server

 

_**Última modificación del tema:** 2012-10-09_

Para habilitar o deshabilitar el archivado para usuarios específicos hospedados en Lync Server, primero debe crear una directiva de usuario y después aplicarla a uno o varios usuarios o grupos de usuarios. Para obtener información sobre la aplicación de directivas de usuario a usuarios y grupos de usuarios específicos, consulte [Aplicación de una directiva de archivado de Lync Server a un usuario](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) en la documentación de implementación.

Para obtener información sobre cómo funcionan las directivas de archivado, incluida la jerarquía para directivas globales, de sitio y de usuario, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planificación, sobre implementación o sobre operaciones.


> [!NOTE]
> Si ha habilitado la integración con Microsoft Exchange en su implementación, las directivas de conservación local de Exchange controlan si el archivado está habilitado para los usuarios hospedados en Exchange 2013 y que tienen sus buzones en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación de implementación.<BR>Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado. Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configurar opciones de archivado</A> en la documentación de implementación.



## Para configurar una directiva de archivado para los usuarios hospedados en Lync Server

1.  Desde una cuenta de usuario que esté asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la implementación interna.

2.  Abra una ventana del explorador y escriba la dirección URL de administración para abrir el Panel de control de Lync Server 2013. Para obtener información sobre los diferentes métodos que se pueden usar para iniciar el Panel de control de Lync Server 2013, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  Haga clic en **Nuevo** y después en **Directiva de usuario**.

5.  En **Nueva directiva de archivado**, haga lo siguiente:
    
      - En **Nombre**, escriba el nombre de la directiva de usuario.
    
      - En **Descripción**, proporcione información sobre cuál es la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).
    
      - Para controlar el archivado de las comunicaciones internas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones internas**.
    
      - Para controlar el archivado de las comunicaciones externas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones externas**.

6.  Haga clic en **Confirmar**.

Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva. Para obtener información sobre la aplicación de una directiva de usuario a usuarios específicos, consulte [Aplicación de una directiva de archivado de Lync Server a un usuario](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) en la documentación sobre implementación.

