---
title: 'Lync Server 2013: Publicar la topología'
TOCTitle: Publicar la topología
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48274997
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publicar la topología en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-01_

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, es necesario haber iniciado sesión como usuario miembro de los grupos Admins del dominio y RTCUniversalServerAdmins. También se pueden delegar los permisos y derechos de administrador adecuados. Para información detallada, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Para otros cambios de configuración, únicamente se necesita ser miembro del grupo RTCUniversalServerAdmins.

Después de definir la topología en Generador de topologías, es necesario publicarla en el Almacén de administración central. El Almacén de administración central proporciona un almacenamiento sólido y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, describir y trabajar en una implementación de Lync Server 2013. También valida los datos para ayudar a garantizar la coherencia de la configuración. Todos los cambios realizados en los datos de la configuración se llevan a cabo en el Almacén de administración central, con lo que desaparecen los problemas de sincronización. Las copias de solo lectura de los datos se replican a todos los servidores de la topología, incluidos los servidores perimetrales.


> [!NOTE]
> SQL Server necesita un mínimo de 20 GB de espacio libre en disco para publicar la topología inicial y crear el servidor de administración central correctamente.




> [!NOTE]
> Solo para Enterprise Edition: Para publicar la topología, el servidor back-end basado en SQL Server debe estar conectado y ser accesible, y haber especificado excepciones de firewall. Para más información sobre cómo especificar excepciones de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Descripción de los requisitos de firewall para SQL Server con Lync Server 2013</A>. Para información detallada sobre cómo configurar SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configurar SQL Server para Lync Server 2013</A>.



## Para publicar una topología

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  Seleccione abrir la topología desde un archivo local. Si se encuentra en el equipo en el que definió la topología, esta estará en la ubicación en la que la guardó en pasos anteriores. Normalmente, será la carpeta de documentos del usuario que configuró la topología.

3.  Haga clic con el botón secundario en el nodo **Lync Server 2013** y después haga clic en **Publicar topología**.

4.  En la página **Publicar la topología**, haga clic en **Siguiente**.

5.  En la página **Crear bases de datos**, seleccione las bases de datos que desea publicar.
    

    > [!NOTE]
    > Si no dispone de los derechos adecuados para crear las bases de datos, puede desactivar las casillas situadas junto a dichas bases de datos y, posteriormente, alguien con los derechos adecuados podrá crearlas. Para más información, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Permisos de implementación para SQL Server en Lync Server 2013</A>.



6.  Opcionalmente, haga clic en **Avanzadas**. Las opciones avanzadas de colocación de archivos de datos de SQL Server permiten seleccionar las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base de datos**: esta opción determinará el mejor rendimiento operativo a partir de la configuración de disco del servidor basado en SQL Server con la distribución de los archivos de datos y de registro en la mejor ubicación.
    
      - **Usar valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server con el uso de la configuración de la instancia. No usa la funcionalidad operativa del servidor basado en SQL Server para determinar las ubicaciones óptimas de registros y datos. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que sean adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar** y después en **Siguiente**.

7.  En la página **Seleccionar servidor de administración central**, seleccione un Grupo de servidores front-end.

8.  Opcionalmente, haga clic en **Avanzadas**. Las opciones avanzadas de colocación de archivos de datos de SQL Server permiten seleccionar las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base de datos**: esta opción determinará el mejor rendimiento operativo a partir de la configuración de disco del servidor basado en SQL Server con la distribución de los archivos de datos y de registro en la mejor ubicación.
    
      - **Usar valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server con el uso de la configuración de la instancia. No usa la funcionalidad operativa del servidor basado en SQL Server para determinar las ubicaciones óptimas de registros y datos. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que sean adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar**.

9.  Haga clic en **Siguiente** para completar el proceso de publicación.

10. Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.
    
    Cuando se haya publicado correctamente la topología, puede empezar a instalar una réplica local del Almacén de administración central en cada servidor de la topología en el que se ejecute Lync Server 2013. Se recomienda comenzar por el primer Grupo de servidores front-end.

## Vea también

#### Otros recursos

[Configurar servidores front-end y grupos de servidores front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)

