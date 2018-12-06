---
title: Implementar el grupo piloto de Lync Server 2013
TOCTitle: Implementar el grupo piloto de Lync Server 2013
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48276290
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar el grupo piloto de Lync Server 2013

 

_**Última modificación del tema:** 2013-11-22_

Uno de los primeros pasos de una implementación escalonada es implementar un grupo piloto de Lync Server 2013. En el grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Lync Server 2010. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y grupos de servidores a Lync Server 2013.

Debe implementar las mismas características y cargas de trabajo en el grupo piloto Lync Server 2013 que tiene en el grupo Lync Server 2010. Si implementó Servidor de archivado, Servidor de supervisión, o System Center Operations Manager para el archivado o supervisión de su entorno Lync Server 2010 y desea continuar realizando el archivado y supervisión durante la migración, necesita implementar también estas características en su entorno piloto. La versión que implemente para archivar o supervisar su entorno Lync Server 2010 no capturará datos en su entorno Lync Server 2013.


> [!NOTE]
> En el siguiente procedimiento se describen las características y las configuraciones que debe tener en cuenta como parte del proceso general de implementación de un grupo piloto. En esta sección solo se destacan los puntos clave que se deben tener en cuenta en dicho proceso. Para saber cuáles son los pasos detallados, consulte la guía de implementación <A href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</A>.



**Para implementar un grupo piloto de Lync Server 2013**

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Expanda el árbol hasta llegar a **Grupos de servidores front-end Enterprise Edition** de **Lync Server 2013**.

3.  Haga clic con el botón derecho en **Grupos de servidores front-end Enterprise Edition** y seleccione **Nuevo grupo de servidores front-end**
    
    ![Submenú de selección de grupo de servidores en el Generador de topologías](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenú de selección de grupo de servidores en el Generador de topologías")

4.  Escriba el FQDN del grupo. Cuando defina el grupo piloto, podrá elegir si desea implementar un Grupo de servidores front-end Enterprise Edition o un Servidor Standard Edition. En Lync Server 2013, no es necesario que el grupo piloto coincida con lo implementado en el grupo heredado.
    
    > [!WARNING]  
	> El nombre de dominio completo (FQDN) del grupo o del servidor que defina para el piloto debe ser único. No puede coincidir con el nombre del grupo Lync Server 2010 implementado actualmente o con otros servidores implementados actualmente.
    
    ![Página FQDN del asistente para nuevo grupo de servidores front end](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Página FQDN del asistente para nuevo grupo de servidores front end")

5.  En la página **Seleccionar características** , seleccione las casillas con las características que desea en este grupo de servidores front-end. Por ejemplo, si está implementando únicamente las características de presencia y de mensajería instantánea (MI), deberá activar la casilla Conferencia para habilitar la mensajería instantánea para varios participantes, pero no deberá activar las casillas Conferencia de acceso telefónico local (RTC), Telefonía IP empresarial o Control de admisión de llamadas, ya que representan características de voz, vídeo y de colaboración. Para obtener información adicional acerca de la selección de características, consulte el tema [Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación relativa a la implementación.
    
    ![Página del grupo de servidores front end para seleccionar características](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página del grupo de servidores front end para seleccionar características")

6.  En la página **Seleccionar roles de servidor instalados** , se recomienda que instale el Servidor de mediación en Lync Server 2013. Cuando se combina una topología heredada con Lync Server 2013, se necesita que, en primer lugar, instale el Lync Server 2010Servidor de mediación. Después de combinar las topologías y de configurar el Lync Server 2013  Servidor de mediación, podrá decidir mantener el Servidor de mediación instalados o cambiarlo a un servidor independiente al mover el rol de Servidor de mediación a Lync Server 2013 más adelante, en el proceso de implementación.
    
    ![Página del grupo de servidores front end para seleccionar roles de servidor combinados](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página del grupo de servidores front end para seleccionar roles de servidor combinados")

7.  En la página **Asociar funciones de servidor con este grupo Front-End** durante la implementación de un grupo piloto, no seleccione la opción **Habilitar el uso de un servidor perimetral por parte del componente multimedia de este grupo front-end**. Esta característica se habilitará y se pondrá en línea en una fase posterior de la migración. No seleccione esta opción por el momento.
    
    ![Pagina Asociar roles de servidor con grupos de servidores front end](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Pagina Asociar roles de servidor con grupos de servidores front end")

8.  En la página **Seleccionar un servidor de aplicaciones web de Office**, haga clic en **Nuevo** y especifique el nombre de dominio completo (FQDN) del servidor de la aplicación.
    
    ![Propiedades de Definir FQDN para nuevo servidor de Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Propiedades de Definir FQDN para nuevo servidor de Office Web Apps")

9.  En la página **Definición del almacén de SQL Server para el archivado** , al definir el almacén de SQL Server para el archivado y la supervisión de Lync Server, seleccione la instancia del servidor SQL Server creado previamente para Lync Server 2013.
    
    ![Página Definir almacén SQL Server de archivado](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página Definir almacén SQL Server de archivado")

10. Para publicar la topología, haga clic con el botón secundario sobre el nodo **Lync Server** y, a continuación, haga clic en **Publicar topología**.
    
    ![Generador de topologías mostrando una topología configurada](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Generador de topologías mostrando una topología configurada")

11. Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar** .

Para instalar una copia local de la base de datos de configuración e iniciar los servicios requeridos, consulte [Configurar servidores front-end y grupos de servidores front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación relativa a la implementación.


