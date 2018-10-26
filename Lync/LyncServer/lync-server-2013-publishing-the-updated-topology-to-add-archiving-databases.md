---
title: "Publicación de la topología actualizada para agregar bases de datos de archivado"
TOCTitle: "Publication de la topologie màj pour l’ajout des bases de données d’archivage"
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48275092
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publicación de la topología actualizada para agregar bases de datos de archivado

 

_**Última modificación del tema:** 2012-10-01_

Después de actualizar su topología en Generador de topologías, debe publicarla en el almacén de administración central para poder configurar y usar el archivado. Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios de topología y de otro tipo.

## Para publicar su topología actualizada

1.  En un PC que ejecute Lync Server 2013 o en el cual estén instaladas las herramientas administrativas de Lync Server, inicie sesión mediante una cuenta que sea miembro del grupo de usuarios locales (o en una cuenta con derechos de usuario equivalentes).
    

    > [!NOTE]
    > Puede definir una topología usando una cuenta que sea miembro del grupo de usuarios locales, pero, para publicar una topología, lo cual es necesario para agregar un servidor a la topología, debe usar una cuenta que sea miembro del grupo <STRONG>Admins. del dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG>, y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Lync Server 2013; es decir, de modo que Generador de topologías pueda configurar las listas de control de acceso discrecional (DACL) necesarias o una cuenta con derechos equivalentes.



2.  Abra la topología que creó en la sección anterior con Generador de topologías.

3.  En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013** y, a continuación, haga clic en **Publicar topología**.

4.  En la página **Publicar la topología**, haga clic en **Siguiente**.

5.  En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y haga clic en **Siguiente**.
    

    > [!NOTE]
    > Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos. Para información sobre los derechos de administrador y permisos requeridos, vea <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Permisos de implementación para SQL Server en Lync Server 2013</A> en la documentación de implementación.<BR>Solo se pueden instalar bases de datos en servidores SQL Server exclusivos usando Generador de topologías. Las bases de datos en servidores SQL Server que se han instalado con otros componentes de servidor deben instalarse ejecutando la configuración local en dicho equipo.



6.  En la página **Asistente para publicación completado**, verifique que se ha publicado correctamente la topología y haga clic en **Finalizar**.
    
    > [!IMPORTANT]  
    > Una vez publicada la topología, debe configurar opciones y directivas para el archivado antes de que se pueda archivar cualquier contenido. Para obtener información, consulte <a href="lync-server-2013-configuring-support-for-archiving.md">Configurar compatibilidad con archivado en Lync Server 2013</a> en la documentación sobre implementación.
    

