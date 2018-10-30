---
title: Implementación de un grupo piloto de Lync Server 2013
TOCTitle: Implementación de un grupo piloto de Lync Server 2013
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48274579
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de un grupo piloto de Lync Server 2013

 

_**Última modificación del tema:** 2013-11-22_

Uno de los primeros pasos de una implementación escalonada es implementar un grupo piloto de Lync Server 2013. En el grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Office Communications Server 2007 R2. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y grupos de servidores a Lync Server 2013.

Al implementar un grupo de servidores piloto, usa el Asistente para definir nuevo grupo de servidores front-end. Debe implementar en el grupo piloto las mismas características y cargas de trabajo que tiene Lync Server 2013 en el grupo Office Communications Server 2007 R2. Si implementó el servidor de archivado, el servidor de supervisión o el System Center Operations Manager para archivar o supervisar su entorno de Office Communications Server 2007 R2, y desea continuar archivando o supervisando durante la migración, necesita implementar también estas funciones en su entorno piloto. La versión que implementó para archivar o supervisar su entorno de Office Communications Server 2007 R2 no capturará los datos en su entorno de Lync Server 2013.


> [!NOTE]
> En el siguiente procedimiento se describen las características y las configuraciones que debe tener en cuenta como parte del proceso general de implementación de un grupo piloto. En esta sección solo se destacan los puntos clave que se deben tener en cuenta en dicho proceso. Para saber cuáles son los pasos detallados, consulte la guía de implementación <A href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</A>.



**Para implementar un grupo piloto de Lync Server 2013**

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Abra el Generador de topologías y elija para crear una nueva topología.

3.  Especifique el dominio SIP principal.
    
    ![Crear nueva topología, página Definir dominio principal](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Crear nueva topología, página Definir dominio principal")

4.  Continúe completando el asistente hasta llegar al asistente **Definir el nuevo grupo de servidores front-end**. Haga clic en Siguiente.

5.  Escriba el FQDN del grupo. Cuando defina el grupo piloto, podrá elegir si desea implementar un Grupo de servidores front-end Enterprise Edition o un Servidor Standard Edition. En Lync Server 2013, no es necesario que el grupo piloto coincida con lo implementado en el grupo heredado.
    
    > [!WARNING]  
	> El nombre de dominio completo (FQDN) del grupo o del servidor que defina para el piloto debe ser único. No puede coincidir con el nombre del grupo Office Communications Server 2007 R2 implementado actualmente o con otros servidores implementados actualmente.
    
    ![Página Definir el FQDN del grupo front-end](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Página Definir el FQDN del grupo front-end")

6.  Defina el equipo que se agregará al grupo de servidores.
    
    ![Cuadro de diálogo Definir nuevo grupo de servidores front end](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Cuadro de diálogo Definir nuevo grupo de servidores front end")

7.  En la página **Seleccionar características**, seleccione las casillas con las características que desea en este grupo de servidores front-end. Por ejemplo, si está implementando únicamente las características de presencia y de mensajería instantánea (MI), deberá activar la casilla Conferencia para habilitar la mensajería instantánea para varios participantes, pero no deberá activar las casillas Conferencia de acceso telefónico local (RTC), Telefonía IP empresarial o Control de admisión de llamadas, ya que representan características de voz, vídeo y de colaboración. Para obtener información adicional acerca de la selección de características, consulte el tema [Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación relativa a la implementación.
    
    ![Página del grupo de servidores front end para seleccionar características](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página del grupo de servidores front end para seleccionar características")

8.  En la página **Seleccionar roles de servidor instalados**, se recomienda que instale el Servidor de mediación en Lync Server 2013. Cuando se combina una topología heredada con Lync Server 2013, se necesita que, en primer lugar, instale el Office Communications Server 2007 R2Servidor de mediación. Después de combinar las topologías y de configurar el Lync Server 2013Servidor de mediación, podrá decidir mantener el Servidor de mediación instalado o cambiarlo a un servidor independiente al mover el rol de Servidor de mediación a Lync Server 2013 más adelante, en el proceso de implementación.
    
    ![Página del grupo de servidores front end para seleccionar roles de servidor combinados](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página del grupo de servidores front end para seleccionar roles de servidor combinados")

9.  En la página **Asociar funciones de servidor con este grupo Front-End** durante la implementación de un grupo piloto, no seleccione la opción **Habilitar el uso de un servidor perimetral por parte del componente multimedia de este grupo front-end**. Esta característica se habilitará y se pondrá en línea en una fase posterior de la migración. No seleccione esta opción por el momento.
    
    ![Pagina Asociar roles de servidor con grupos de servidores front end](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Pagina Asociar roles de servidor con grupos de servidores front end")

10. En la página **Seleccionar un servidor de aplicaciones web de Office**, haga clic en **Nuevo** y especifique el nombre de dominio completo (FQDN) del servidor de la aplicación.
    
    ![Propiedades de Definir FQDN para nuevo servidor de Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Propiedades de Definir FQDN para nuevo servidor de Office Web Apps")

11. En la página **Definir el almacén de SQL Server de archivado**, seleccione la instancia de SQL Server creada anteriormente para Lync Server 2013.
    
    ![Página Definir almacén SQL Server de archivado](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página Definir almacén SQL Server de archivado")

12. En la página **Definir el almacén de SQL Server de supervisión**, seleccione la instancia del servidor SQL creado previamente para Lync Server 2013. Haga clic en **Finalizar**.

13. Desde el nodo principal del Generador de topologías, haga clic con el botón secundario en **Lync Server** y haga clic en **Editar propiedades.** Haga clic en **Direcciones URL simples**.

14. Actualice la **Dirección URL de acceso administrativo**.
    
    ![Editar propiedades, página direcciones URL sencillas](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propiedades, página direcciones URL sencillas")
    
    Para obtener información adicional sobre direcciones URL sencillas, vea el tema [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación de implementación.

15. En **Editar propiedades**, haga clic en **Servidor de administración central**.

16. En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.
    
    ![Editar propiedades, página Servidor de administración central](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Editar propiedades, página Servidor de administración central")

17. Haga clic en Aceptar para cerrar la página **Editar propiedades**.

18. En el menú **Acción**, seleccione **Publicar topología**.

19. Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.

20. Devuelta en el Asistente para implementación de Lync Server 2013, haga clic en **Instalar o actualizar el sistema Lync Server**.
    
    ![Asistente para la implementación de Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Asistente para la implementación de Lync Server 2013")

Para instalar una copia local de la base de datos de configuración e iniciar los servicios requeridos, consulte [Configurar servidores front-end y grupos de servidores front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación relativa a la implementación.


