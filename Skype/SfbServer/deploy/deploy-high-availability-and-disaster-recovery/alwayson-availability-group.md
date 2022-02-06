---
title: Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implemente (instale) un grupo de disponibilidad AlwaysOn en su Skype Empresarial Server implementación.
---

# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server
 
Implemente (instale) un grupo de disponibilidad AlwaysOn (AG) en su Skype Empresarial Server implementación.
  
La forma de implementar un grupo de disponibilidad depende de si se va a implementar en un nuevo grupo de servidores, en un grupo existente que usa la creación de reflejos o en un grupo existente que actualmente no tiene alta disponibilidad para la base de datos back-end.
  
> [!NOTE]
> No se admite el uso de una AG con un rol de servidor de chat persistente. 
  
- [Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo de servidores front-end](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que usa la creación de reflejo de la base de datos](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que no usa la creación de reflejo de la base de datos](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo de servidores front-end
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Habilite la característica clústeres de conmutación por error en todos los servidores de bases de datos que formarán parte del grupo de disponibilidad. En cada servidor, haga lo siguiente
    
   - Abra el Administrador del servidor y haga clic **en Agregar roles y características**.
    
   - Haga **clic en** Siguiente hasta que llegue al **cuadro Seleccionar** características. Aquí, active la casilla **Clústeres de conmutación** por error.
    
   - En el **cuadro Agregar características necesarias para la** agrupación en clústeres de conmutación por error, haga clic **en Agregar características**.
    
   - Haga clic en **Instalar**.
    
2. Validar la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el **menú Herramientas** y, a continuación, haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en el lado derecho de la pantalla, haga clic **en Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que desea agregar al clúster y, a continuación, haga clic **en Ejecutar todas las pruebas**.
    
   - En la **casilla Resumen** , compruebe los errores que informe el asistente. A **continuación, haga** clic en Finalizar para completar la validación.
    
     Es probable que el asistente informe varias advertencias, especialmente si no está usando el almacenamiento compartido. No es necesario usar el almacenamiento compartido. Sin embargo, si ve algún **mensaje de error** , debe corregir esos problemas antes de continuar.
    
3. Cree el Windows de conmutación por error de servidor (WSFC).
    
   - En el Asistente **para administración de clústeres de** conmutación por error, haga clic con el botón secundario en **Administración** de clústeres de conmutación por error y, a continuación, haga clic **en Crear clúster**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Agregue el nombre del clúster y la dirección IP. Cuando se valide la configuración, haga clic **en Siguiente**.
    
   - En la página Confirmación, haga clic en **Siguiente**.
    
   - Después de crear el clúster, haga clic **en Finalizar**.
    
4. Se recomienda configurar la configuración de quórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:
    
   - Haga clic con el botón secundario en el nombre del clúster, haga clic **en Más** acciones y haga clic en **Configurar quórum de clúster Configuración**.
    
   - En la página **Seleccionar opción de configuración de quórum** , haga **clic en Seleccionar el testigo de quórum**.
    
   - En la página **Seleccionar testigo de quórum** , haga **clic en Configurar un testigo de recurso compartido de archivos**.
    
   - En la **página Configurar testigo de recurso compartido de** archivos, escriba la ruta de acceso del recurso compartido de archivos que desea usar y, a continuación, haga clic en **Siguiente**.
    
   - En la página **Confirmación**, haga clic en **Siguiente**.
    
5. En cada servidor del clúster, habilite la característica AG en Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic **en SQL Server Servicios** y, a continuación, haga doble clic en SQL Server servicio. 
    
   - En el **cuadro Propiedades** , seleccione la **pestaña Alta disponibilidad AlwaysOn** . Active la **casilla Habilitar grupos de disponibilidad AlwaysOn** . Reinicie el SQL Server cuando se le pida.
   
6. Use topology Builder para crear el grupo de servidores front-end, como se explica en [Create and publish new topology in Skype Empresarial Server](../../deploy/install/create-and-publish-new-topology.md). Cuando lo haga, especifique el AG como el SQL almacén para el grupo.
    
7. Cree el grupo de disponibilidad.
    
   - Abra SQL Server Management Studio y conéctese a la SQL Server instancia.
    
   - En el Explorador de objetos, expanda la **carpeta Siempre en alta** disponibilidad. Haga clic con el botón secundario en la carpeta **Grupos de disponibilidad** y haga clic **en Asistente para nuevo grupo de disponibilidad**.
    
   - Si aparece **la página** Introducción, haga clic en **Siguiente**.
    
   - En la **página Especificar nombre del grupo de** disponibilidad, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
   - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn. A continuación, haga clic en **Siguiente**.
    
     No incluya las bases de datos **ReportServer**, **ReportServerTempDB** o Persistent Chat en el grupo de disponibilidad AlwaysOn, ya que no se admiten en este escenario. Puede incluir todas las demás Skype Empresarial Server bases de datos en el grupo de disponibilidad AlwaysOn.
    
   - En la **página Especificar réplicas**, haga clic en **la pestaña Réplicas**. A continuación, haga clic en el botón Agregar **réplicas** y conéctese a las demás instancias SQL que ha unido como nodos del clúster de conmutación por error Windows servidor.
    
   - Para cada instancia, seleccione las **opciones Conmutación por error** automática y **Confirmación sincrónica** . No seleccione la opción **Secundario legible** .
    
   - Haga clic **en la pestaña** Extremos y compruebe que **número** de puerto está establecido en 5022.
    
   - Haga clic **en la pestaña** Escucha y seleccione la **opción Crear una escucha de grupo de** disponibilidad. En esa opción, escriba un nombre para el agente de escucha y establezca **el** puerto en 1433 (no se admiten otros puertos para esta opción).
    
   - Haga **clic en** Agregar y, a continuación, en el cuadro Dirección **IPv4** , proporcione la dirección IP virtual preferida y, a continuación, haga clic en **Aceptar**.
    
   - En la  página Seleccionar sincronización inicial de datos, seleccione Completo y especifique una carpeta accesible para las réplicas y que la cuenta de servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. A continuación, haga clic en **Siguiente**.
    
     Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si está trabajando con bases de datos grandes, se recomienda inicializarlos manualmente en caso de que el ancho de banda de red no pueda adaptarse al tamaño de las copias de seguridad de la base de datos.
    
   - En la página Validación, compruebe que todas las comprobaciones de validación se han realizado correctamente y, a continuación, haga clic **en Siguiente**.
    
   - En la **página Resumen** , compruebe toda la configuración y haga clic en Finalizar.
      
8. Después de implementar el grupo de servidores y el grupo de disponibilidad, realice algunos pasos finales para asegurarse de que los inicios de sesión SQL están en cada una de las réplicas del grupo de disponibilidad AlwaysOn. 
    
   - Abra el Generador de topologías, **seleccione Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
   - Expanda Skype Empresarial Server, expanda la topología y expanda **SQL Server almacenes**. Haga clic con el botón secundario en SQL almacén del nuevo grupo de disponibilidad AlwaysOn y haga clic **en Editar propiedades**.
    
     - En la parte inferior de la página, en el cuadro **SQL Server FQDN**, cambie el valor al FQDN del agente de escucha del GRUPO.
    
   - Publique la topología. En el **menú Acción** , haga **clic en Topología y** , a continuación **, en Publicar**. A continuación, en la página de confirmación, haga clic **en Siguiente**. A continuación, espere unos minutos a que se replique la nueva topología.
    
   - Abra SQL Server Management Studio y vaya al GRUPO. Conmutación por error en una réplica secundaria.
    
   - Abra Skype Empresarial Server Shell de administración y escriba el siguiente cmdlet para crear el SQL inicios de sesión en esta réplica:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria y, a continuación, use  `Install-CsDatabase -Update`) para cada réplica del grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que usa la creación de reflejo de la base de datos
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si el grupo de servidores que va a actualizar a un grupo de servidores hospeda el almacén de administración central de su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo. Use el cmdlet Move-CsManagementServer para mover el grupo. Si no tiene otro grupo de servidores en la organización, puede implementar un servidor de Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo a ag. 
  
1. Para conmutar por error todos los datos del reflejo al nodo principal, abra Skype Empresarial Server Shell de administración y escriba el siguiente cmdlet.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Repita este cmdlet para cada tipo de base de datos del grupo. Puede usar el siguiente cmdlet para buscar todos los tipos de base de datos almacenados en este grupo.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Use el Generador de topologías para quitar la creación de reflejos de la base de datos del grupo.
    
   - Abra el Generador de topologías. En la topología, expanda Enterprise Edition **grupos de servidores front-end**, haga clic con el botón secundario en el nombre del grupo y haga clic **en Editar propiedades**.
    
   - Para cada tipo de SQL en el grupo de servidores, desactive la casilla Habilitar **SQL** creación de reflejos de la tienda.
    
3. Publique la topología modificada. En el **menú Acción** , haga **clic en Topología y** , a continuación **, en Publicar**. A continuación, en la página de confirmación, haga clic **en Siguiente**
    
4. Use SQL Server Management Studio para romper el reflejo.
    
   - Abra SQL Server Management Studio, vaya a las bases de datos, haga clic con el botón secundario en **Tareas** y haga clic en **Reflejo**. A **continuación, haga clic en Quitar creación de reflejo** y haga clic en **Aceptar**.
    
   - Repita esta opción para todas las bases de datos del grupo de servidores que se convertirán en un grupo de disponibilidad.
    
5. Configure la característica clústeres de conmutación por error en todos los servidores de base de datos que formarán parte del GRUPO. En cada servidor, haga lo siguiente
    
   - Abra el Administrador del servidor y haga clic **en Agregar roles y características**.
    
   - Haga **clic en** Siguiente hasta que llegue al **cuadro Seleccionar** características. Aquí, active la casilla **Clústeres de conmutación** por error.
    
   - En el **cuadro Agregar características necesarias para la** agrupación en clústeres de conmutación por error, haga clic **en Agregar características**.
    
   - Haga clic en **Instalar**.
    
6. Validar la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el **menú Herramientas** y, a continuación, haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en el lado derecho de la pantalla, haga clic **en Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que desea agregar al clúster y, a continuación, haga clic **en Ejecutar todas las pruebas**.
    
   - En la **casilla Resumen** , compruebe los errores que informe el asistente. A **continuación, haga** clic en Finalizar para completar la validación.
    
     Es probable que el asistente informe varias advertencias, especialmente si no está usando el almacenamiento compartido. No es necesario usar el almacenamiento compartido. Sin embargo, si ve algún **mensaje de error** , debe corregir esos problemas antes de continuar.
    
7. Cree el clúster Windows de conmutación por error del servidor.
    
   - En el Asistente **para administración de clústeres de** conmutación por error, haga clic con el botón secundario en **Administración** de clústeres de conmutación por error y, a continuación, haga clic **en Crear clúster**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Agregue el nombre del clúster y la dirección IP. Cuando se valide la configuración, haga clic **en Siguiente**.
    
   - En la página Confirmación, haga clic en **Siguiente**.
    
   - Después de crear el clúster, haga clic **en Finalizar**.
    
8. Se recomienda configurar la configuración de quórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:
    
   - Haga clic con el botón secundario en el nombre del clúster, haga clic **en Más** acciones y haga clic en **Configurar quórum de clúster Configuración**.
    
   - En la página **Seleccionar opción de configuración de quórum** , haga **clic en Seleccionar el testigo de quórum**.
    
   - En la página **Seleccionar testigo de quórum** , haga **clic en Configurar un testigo de recurso compartido de archivos**.
    
   - En la **página Configurar testigo de recurso compartido de** archivos, escriba la ruta de acceso del recurso compartido de archivos que desea usar y, a continuación, haga clic en **Siguiente**.
    
   - En la página **Confirmación**, haga clic en **Siguiente**.
    
9. En cada servidor del clúster, habilite la característica AG en Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic **en SQL Server Servicios** y, a continuación, haga doble clic en SQL Server servicio. 
    
   - En el **cuadro Propiedades** , seleccione la **pestaña Alta disponibilidad AlwaysOn** . Active la **casilla Habilitar grupos de disponibilidad AlwaysOn** . Reinicie el SQL Server cuando se le pida.
    
10. Cree el grupo de disponibilidad.
    
    - Abra SQL Server Management Studio y conéctese a la SQL Server instancia.
    
    - En el Explorador de objetos, expanda la **carpeta Siempre en alta** disponibilidad. Haga clic con el botón secundario en la carpeta **Grupos de disponibilidad** y haga clic **en Asistente para nuevo grupo de disponibilidad**.
    
    - Si aparece **la página** Introducción, haga clic en **Siguiente**.
    
    - En la **página Especificar nombre del grupo de** disponibilidad, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
    - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn. A continuación, haga clic en **Siguiente**.
    
    No incluya las bases de datos **ReportServer**, **ReportServerTempDB** o Persistent Chat en el grupo de disponibilidad AlwaysOn, ya que no se admiten en este escenario. Puede incluir todas las demás Skype Empresarial Server bases de datos en el grupo de disponibilidad AlwaysOn.
    
    - En la **página Especificar réplicas**, haga clic en **la pestaña Réplicas**. A continuación, haga clic en el botón Agregar **réplicas** y conéctese a las demás instancias SQL que ha unido como nodos del clúster de conmutación por error Windows servidor.
    
    - Para cada instancia, seleccione las **opciones Conmutación por error** automática y **Confirmación sincrónica** . No seleccione la opción **Secundario legible** .
    
    - Haga clic **en la pestaña** Extremos y compruebe que **número** de puerto está establecido en 5022.
    
      - Haga clic **en la pestaña** Escucha y seleccione la **opción Crear una escucha de grupo de** disponibilidad. En esa opción, escriba un nombre para el agente de escucha y establezca **el** puerto en 1433 (no se admiten otros puertos para esta opción).
    
    - Haga **clic en** Agregar y, a continuación, en el cuadro Dirección **IPv4** , proporcione la dirección IP virtual preferida y, a continuación, haga clic en **Aceptar**.
    
    - En la  página Seleccionar sincronización inicial de datos, seleccione Completo y especifique una carpeta accesible para las réplicas y que la cuenta de servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. A continuación, haga clic en **Siguiente**.
    
    Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si está trabajando con bases de datos grandes, se recomienda inicializarlos manualmente en caso de que el ancho de banda de red no pueda adaptarse al tamaño de las copias de seguridad de la base de datos.
    
    - En la página Validación, compruebe que todas las comprobaciones de validación se han realizado correctamente y, a continuación, haga clic **en Siguiente**.
    
    - En la **página Resumen** , compruebe toda la configuración y haga clic en Finalizar.
    
11. Cree un nuevo almacén que especifique el agente de escucha de AG y especifique la entidad de seguridad del reflejo antiguo como nodo principal del grupo de disponibilidad.
    
    - Abra el Generador de topologías. En la topología, expanda **Componentes compartidos**, haga clic con el botón secundario **en SQL Server y** haga clic en **Nuevo SQL Server almacén**.
    
    - En la página Definir nuevo **almacén de SQL**, active primero la casilla De alta disponibilidad **Configuración** y, a continuación, asegúrese de que SQL grupos de disponibilidad AlwaysOn aparezcan en el cuadro desplegable.
    
    - En el **SQL Server FQDN de escucha de** disponibilidad, escriba el FQDN del agente de escucha que creó al crear el grupo de disponibilidad.
    
    - En el **SQL Server FQDN**, escriba el FQDN del nodo principal del GRUPO y, a continuación, haga clic en **Aceptar**. Debe ser la entidad de seguridad del espejo antiguo de esta tienda.
    
12. Asocie el nuevo grupo de disponibilidad con el grupo de servidores front-end.
    
    - En el Generador de topologías, haga clic con el botón secundario en el grupo de servidores para asociarlo con el grupo de servidores y haga clic **en Editar propiedades**.
    
    - En **Asociaciones**, en el **cuadro SQL Server store**, seleccione ag. Seleccione el mismo grupo para cualquier otra base de datos del grupo que desee mover al grupo de servidores.
    
    - Cuando esté seguro de que todas las bases de datos necesarias están establecidas en ag, haga clic en **Aceptar**.
    
13. Publique la topología. En el **menú Acción** , haga **clic en Topología y** , a continuación **, en Publicar**. A continuación, en la página de confirmación, haga clic **en Siguiente**.
    
14. Realice algunos pasos finales para asegurarse de que los inicios de sesión SQL están en cada una de las réplicas del grupo de disponibilidad AlwaysOn.
    
    - Abra el Generador de topologías, **seleccione Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
    - Expanda Skype Empresarial Server, expanda la topología y expanda **SQL Server almacenes**. Haga clic con el botón secundario en SQL almacén del nuevo grupo de disponibilidad y haga clic **en Editar propiedades**.
    
    - En la parte inferior de la página, en el cuadro **SQL Server FQDN**, cambie el valor al FQDN del agente de escucha del GRUPO.
    
    - Publique la topología. En el **menú Acción** , haga **clic en Topología y** , a continuación **, en Publicar**. A continuación, en la página de confirmación, haga clic **en Siguiente**. A continuación, espere unos minutos a que se replique la nueva topología.
    
    - Abra SQL Server Management Studio y vaya al GRUPO. Conmutación por error en una réplica secundaria.
    
    - Abra Skype Empresarial Server Shell de administración y escriba el siguiente cmdlet para crear el SQL inicios de sesión en esta réplica:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria y, a continuación, use  `Install-CsDatabase -Update`) para cada réplica del grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que no usa la creación de reflejo de la base de datos
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si el grupo de servidores que va a actualizar a un grupo de servidores hospeda el almacén de administración central de su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo. Use el cmdlet Move-CsManagementServer para mover el grupo. Si no tiene otro grupo de servidores en la organización, puede implementar un servidor de Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo a ag. 
  
1. Configure la característica clústeres de conmutación por error en todos los servidores de base de datos que formarán parte del GRUPO. En cada servidor, haga lo siguiente
    
   - Abra el Administrador del servidor y haga clic **en Agregar roles y características**.
    
   - Haga **clic en** Siguiente hasta que llegue al **cuadro Seleccionar** características. Aquí, active la casilla **Clústeres de conmutación** por error.
    
   - En el **cuadro Agregar características necesarias para la** agrupación en clústeres de conmutación por error, haga clic **en Agregar características**.
    
   - Haga clic en **Instalar**.
    
2. Validar la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el **menú Herramientas** y, a continuación, haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en el lado derecho de la pantalla, haga clic **en Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que desea agregar al clúster y, a continuación, haga clic **en Ejecutar todas las pruebas**.
    
   - En la **casilla Resumen** , compruebe los errores que informe el asistente. A **continuación, haga** clic en Finalizar para completar la validación.
    
     Es probable que el asistente informe varias advertencias, especialmente si no está usando el almacenamiento compartido. No es necesario usar el almacenamiento compartido. Sin embargo, si ve algún **mensaje de error** , debe corregir esos problemas antes de continuar.
    
3. Cree el Windows de conmutación por error de servidor (WSFC).
    
   - En el Asistente **para administración de clústeres de** conmutación por error, haga clic con el botón secundario en **Administración** de clústeres de conmutación por error y, a continuación, haga clic **en Crear clúster**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Agregue el nombre del clúster y la dirección IP. Cuando se valide la configuración, haga clic **en Siguiente**.
    
   - En la página Confirmación, haga clic en **Siguiente**.
    
   - Después de crear el clúster, haga clic **en Finalizar**.
    
4. Se recomienda configurar la configuración de quórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:
    
   - Haga clic con el botón secundario en el nombre del clúster, haga clic **en Más** acciones y haga clic en **Configurar quórum de clúster Configuración**.
    
   - En la página **Seleccionar opción de configuración de quórum** , haga **clic en Seleccionar el testigo de quórum**.
    
   - En la página **Seleccionar testigo de quórum** , haga **clic en Configurar un testigo de recurso compartido de archivos**.
    
   - En la **página Configurar testigo de recurso compartido de** archivos, escriba la ruta de acceso del recurso compartido de archivos que desea usar y, a continuación, haga clic en **Siguiente**.
    
   - En la página **Confirmación**, haga clic en **Siguiente**.
    
5. En cada servidor del clúster, habilite AG en Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic **en SQL Server Servicios** y, a continuación, haga doble clic en SQL Server servicio. 
    
   - En el **cuadro Propiedades** , seleccione la **pestaña Alta disponibilidad AlwaysOn** . Active la **casilla Habilitar grupos de disponibilidad AlwaysOn** . Reinicie el SQL Server cuando se le pida.
    
6. Cree el grupo de disponibilidad.
    
   - Abra SQL Server Management Studio y conéctese a la SQL Server instancia.
    
   - En el Explorador de objetos, expanda la **carpeta Siempre en alta** disponibilidad. Haga clic con el botón secundario en la carpeta **Grupos de disponibilidad** y haga clic **en Asistente para nuevo grupo de disponibilidad**.
    
   - Si aparece **la página** Introducción, haga clic en **Siguiente**.
    
   - En la **página Especificar nombre del grupo de** disponibilidad, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
   - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad. A continuación, haga clic en **Siguiente**.
    
     No incluya las bases **de datos ReportServer**, **ReportServerTempDB** o Persistent Chat en la AG, ya que no se admiten en este escenario. Puede incluir todas las demás Skype Empresarial Server bases de datos en la AG.
    
   - En la **página Especificar réplicas**, haga clic en **la pestaña Réplicas**. A continuación, haga clic en el botón Agregar **réplicas** y conéctese a las demás instancias SQL que ha unido como nodos del WSFC.
    
   - Para cada instancia, seleccione las **opciones Conmutación por error** automática y **Confirmación sincrónica** . No seleccione la opción **Secundario legible** .
    
   - Haga clic **en la pestaña** Extremos y compruebe que **número** de puerto está establecido en 5022.
    
   - Haga clic **en la pestaña** Escucha y seleccione la **opción Crear una escucha de grupo de** disponibilidad. En esa opción, escriba un nombre para el agente de escucha y establezca **el** puerto en 1433 (no se admiten otros puertos para esta opción).
    
   - Haga **clic en** Agregar y, a continuación, en el cuadro Dirección **IPv4** , proporcione la dirección IP virtual preferida y, a continuación, haga clic en **Aceptar**.
    
   - En la  página Seleccionar sincronización inicial de datos, seleccione Completo y especifique una carpeta accesible para las réplicas y que la cuenta de servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. A continuación, haga clic en **Siguiente**.
    
     Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si está trabajando con bases de datos grandes, se recomienda inicializarlos manualmente en caso de que el ancho de banda de red no pueda adaptarse al tamaño de las copias de seguridad de la base de datos.
    
     - En la página Validación, compruebe que todas las comprobaciones de validación se han realizado correctamente y, a continuación, haga clic **en Siguiente**.
    
   - En la **página Resumen** , compruebe toda la configuración y haga clic en Finalizar.
    
7. Cree un nuevo almacén que especifique el agente de escucha de AG.
    
   - Abra el Generador de topologías. En la topología, expanda **Componentes compartidos**, haga clic con el botón secundario **en SQL Server y** haga clic en **Nuevo SQL Server almacén**.
    
   - En la página Definir nuevo **almacén de SQL**, active primero la casilla De alta disponibilidad **Configuración** y, a continuación, asegúrese de que SQL grupos de disponibilidad AlwaysOn aparezcan en el cuadro desplegable.
    
   - En el **SQL Server FQDN de escucha de** disponibilidad, escriba el FQDN del agente de escucha que creó al crear el grupo de disponibilidad.
    
   - En el **SQL Server FQDN**, escriba el FQDN del nodo principal del GRUPO y, a continuación, haga clic en **Aceptar**.
    
8. Asocie el nuevo grupo de disponibilidad AlwaysOn con el grupo front-end.
    
   - En el Generador de topologías, haga clic con el botón secundario en el grupo de servidores para asociarlo con el grupo de servidores y haga clic **en Editar propiedades**.
    
   - En **Asociaciones**, en el **cuadro SQL Server store**, seleccione ag. Seleccione el mismo grupo para cualquier otra base de datos del grupo que desee mover al grupo de servidores.
    
   - Cuando esté seguro de que todas las bases de datos necesarias están establecidas en ag, haga clic en **Aceptar**.
    
9. Publique la topología. En el **menú Acción** , haga **clic en Topología y** , a continuación **, en Publicar**. A continuación, en la página de confirmación, haga clic **en Siguiente**.
    
10. Realice algunos pasos finales para asegurarse de que SQL inicios de sesión están en cada una de las réplicas del grupo de disponibilidad.
    
    - Abra el Generador de topologías, **seleccione Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
    - Expanda Skype Empresarial Server, expanda la topología y expanda **SQL Server almacenes**. Haga clic con el botón secundario en SQL almacén del nuevo grupo de disponibilidad y haga clic **en Editar propiedades**.
    
    - En la parte inferior de la página, en el cuadro **SQL Server FQDN**, cambie el valor al FQDN del agente de escucha del GRUPO.
    
    - Publique la topología. En el **menú Acción** , haga **clic en Topología y** , a continuación **, en Publicar**. A continuación, en la página de confirmación, haga clic **en Siguiente**. A continuación, espere unos minutos a que se replique la nueva topología.
    
    - Abra SQL Server Management Studio y vaya al GRUPO. Conmutación por error en una réplica secundaria.
    
    - Abra Skype Empresarial Server Shell de administración y escriba el siguiente cmdlet para crear el SQL inicios de sesión en esta réplica:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria y, a continuación, use  `Install-CsDatabase -Update`) para cada réplica del grupo.
