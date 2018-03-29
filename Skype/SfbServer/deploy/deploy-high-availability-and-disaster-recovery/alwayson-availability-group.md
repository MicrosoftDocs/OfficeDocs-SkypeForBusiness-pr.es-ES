---
title: Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implementar implementación (instalación) un grupo de disponibilidad AlwaysOn en su Skype para Business Server.
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a>Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server 2015
 
Implementar implementación (instalación) un grupo de disponibilidad AlwaysOn en su Skype para Business Server.
  
Cómo implementar un grupo de disponibilidad AlwaysOn depende de si se está implementando en un nuevo grupo, un grupo existente que utiliza espejado o un grupo existente que actualmente no tiene alta disponibilidad para la base de datos Back End.
  
> [!NOTE]
> No se admite el uso de un grupo de disponibilidad AlwaysOn con un rol de servidor de charla persistente. 
  
> [!IMPORTANT]
> Nombres de instancia para varias instancias del grupo de disponibilidad AlwaysOn deben ser el mismo. 
  
- [Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo front-end](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que use reflejos de bases de datos](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que no use reflejos de bases de datos](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a>Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo front-end
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Configurar clústeres de conmutación por error de Windows Server en todos los servidores de base de datos que formarán parte del grupo de disponibilidad AlwaysOn. En cada uno de los servidores, haga lo siguiente
    
   - Abra Administrador de servidores y haga clic en **Agregar roles y características**.
    
   - Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.
    
   - En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.
    
   - Haga clic en **Instalar**.
    
2. Valide la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.
    
   - En el cuadro**Resumen** , revise los errores que el Asistente para informes. Luego haga clic en **Finalizar** para completar la validación.
    
    Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.
    
3. Cree el clúster.
    
   - En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.
    
   - En la página Confirmación, haga clic en **Siguiente**.
    
   - Una vez que se cree el clúster, haga clic en **Finalizar**.
    
4. Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:
    
   - Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.
    
   - En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.
    
   - En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.
    
   - En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.
    
   - En la página **Confirmación**, haga clic en **Siguiente**.
    
5. En cada uno de los servidores en el clúster, habilite Always On en el Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server.  
    
   - En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.
    
6. Cree el grupo de disponibilidad.
    
   - Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.
    
   - En Explorador de objetos, expanda la carpeta **AlwaysOn alta disponibilidad**. Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.
    
   - Si aparece la página **Introducción**, haga clic en **Siguiente**.
    
   - En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
   - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn. Then click **Next**.
    
    No incluya el **ReportServer**, **ReportServerTempDB**o charla persistente de bases de datos en el grupo de disponibilidad AlwaysOn, ya no se admiten en este escenario. Puede incluir todas las demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.
    
   - En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.
    
   - Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.
    
   - Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.
    
   - Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).
    
   - Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.
    
   - En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.
    
    Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.
    
   - En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.
    
   - En la página**Resumen** , compruebe todas las configuraciones y haga clic en Finalizar.
    
7. Utilice el generador de topología para crear la agrupación de Front-End, como se explica en [crear y publicar la nueva topología en Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md). Cuando lo haga, especifique el grupo de disponibilidad AlwaysOn como almacén de SQL para el grupo.
    
8. Después de implementan la agrupación y el grupo de disponibilidad AlwaysOn, realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn. 
    
   - Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.
    
   - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y ** editar propiedades **.
    
    - En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , cambie el valor para el nombre completo del agente de escucha del grupo disponibilidad AlwaysOn.
    
   - Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.
    
   - Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn. Conmútelo por error a una réplica secundaria.
    
   - Abre Skype para negocios de Shell de administración de servidor y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:
    
   ```
   Install-CsDatabase -Update
   ```

   - Repita los dos pasos anteriores (error en el grupo a una segunda réplica, luego use `Install-CsDatabase -Update`) para cada réplica en el grupo.
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que use reflejos de bases de datos
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si el grupo que se va a actualizar a los hosts de un grupo de disponibilidad AlwaysOn la Administración Central se almacena para su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo. Use el cmdlet Move-CsManagementServer para mover el grupo de servidores. Si no tiene otro grupo en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo para el grupo de disponibilidad AlwaysOn. 
  
1. Todos los datos desde el espejo al nodo principal por error abriendo Skype para el Shell de administración de servidor empresarial y escribiendo el siguiente cmdlet.
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Repita este cmdlet para cada tipo de base de datos en el grupo de servidores. Puede usar el siguiente cmdlet para buscar todos los tipos de base de datos almacenados en este grupo de servidores.
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Usar el Generador de topologías para quitar el reflejo de bases de datos del grupo
    
   - Abra el generador de topología. En su topología, expanda **Grupos de servidores front-end Enterprise Edition**, haga clic derecho en el nombre del grupo de servidores y haga clic en **Editar propiedades**.
    
   - Para cada tipo de almacén SQL en el grupo, desactive la casilla **Habilitar la creación de reflejos de almacén SQL**.
    
3. Publique la nueva topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.
    
4. Use SQL Server Management Studio para separar el reflejo.
    
   - Abra SQL Server Management Studio, vaya a las bases de datos, haga clic con el botón derecho en **Tareas** y haga clic en **Reflejo**. Luego, haga clic en **Quitar la creación de reflejos** y haga clic en **Aceptar**.
    
   - Repita este paso para todas las bases de datos en el grupo que se convertirá en un grupo de disponibilidad AlwaysOn.
    
5. Configurar clústeres de conmutación por error de Windows Server en todos los servidores de base de datos que formarán parte del grupo de disponibilidad AlwaysOn. En cada uno de los servidores, haga lo siguiente
    
   - Abra Administrador de servidores y haga clic en **Agregar roles y características**.
    
   - Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.
    
   - En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.
    
   - Haga clic en **Instalar**.
    
6. Valide la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.
    
   - En el cuadro**Resumen** , revise los errores que el Asistente para informes. Luego haga clic en **Finalizar** para completar la validación.
    
    Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.
    
7. Cree el clúster.
    
   - En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.
    
   - En la página Confirmación, haga clic en **Siguiente**.
    
   - Una vez que se cree el clúster, haga clic en **Finalizar**.
    
8. Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:
    
   - Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.
    
   - En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.
    
   - En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.
    
   - En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.
    
   - En la página **Confirmación**, haga clic en **Siguiente**.
    
9. En cada uno de los servidores en el clúster, habilite Always On en el Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server.  
    
   - En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.
    
10. Cree el grupo de disponibilidad.
    
    - Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.
    
    - En Explorador de objetos, expanda la carpeta **AlwaysOn alta disponibilidad**. Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.
    
    - Si aparece la página **Introducción**, haga clic en **Siguiente**.
    
    - En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
    - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn. Then click **Next**.
    
    No incluya el **ReportServer**, **ReportServerTempDB**o charla persistente de bases de datos en el grupo de disponibilidad AlwaysOn, ya no se admiten en este escenario. Puede incluir todas las demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.
    
    - En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.
    
    - Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.
    
    - Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.
    
     - Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).
    
    - Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.
    
    - En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.
    
    Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.
    
    - En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.
    
    - En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.
    
11. Crear un nuevo almacén especificando la escucha del grupo de disponibilidad AlwaysOn y especificando la entidad de seguridad del espejo antiguo como el nodo principal del grupo de disponibilidad AlwaysOn.
    
    - Abra el generador de topología. En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.
    
    - En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.
    
    - En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.
    
    - En el cuadro **Nombre de dominio completo de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn y, a continuación, haga clic en **Aceptar**. Esto debería ser la entidad de seguridad del reflejo antiguo de este almacén.
    
12. Asociar el nuevo grupo de disponibilidad AlwaysOn con el grupo de servidores Front-End.
    
    - Generador de topología, haga clic en el grupo que desee asociar al grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
    - En **las asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el grupo de disponibilidad AlwaysOn. Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover al grupo de disponibilidad AlwaysOn.
    
    - Cuando esté seguro de que todas las bases de datos necesarias se establecen en el grupo de disponibilidad AlwaysOn, haga clic en **Aceptar**.
    
13. Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.
    
14. Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.
    
    - Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.
    
    - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. (Ratón) en el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
    - En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , cambie el valor para el nombre completo del agente de escucha del grupo disponibilidad AlwaysOn.
    
    - Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.
    
    - Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn. Conmútelo por error a una réplica secundaria.
    
    - Abre Skype para negocios de Shell de administración de servidor y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:
    
    ```
    Install-CsDatabase -Update
    ```

    - Repita los dos pasos anteriores (error en el grupo a una segunda réplica, luego use `Install-CsDatabase -Update`) para cada réplica en el grupo.
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que no use reflejos de bases de datos
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si el grupo que se va a actualizar a los hosts de un grupo de disponibilidad AlwaysOn la Administración Central se almacena para su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo. Use el cmdlet Move-CsManagementServer para mover el grupo de servidores. Si no tiene otro grupo en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo para el grupo de disponibilidad AlwaysOn. 
  
1. Configurar clústeres de conmutación por error de Windows Server en todos los servidores de base de datos que formarán parte del grupo de disponibilidad AlwaysOn. En cada uno de los servidores, haga lo siguiente
    
   - Abra Administrador de servidores y haga clic en **Agregar roles y características**.
    
   - Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.
    
   - En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.
    
   - Haga clic en **Instalar**.
    
2. Valide la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.
    
   - En el cuadro**Resumen** , revise los errores que el Asistente para informes. Luego haga clic en **Finalizar** para completar la validación.
    
    Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.
    
3. Cree el clúster.
    
   - En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.
    
   - En la página Confirmación, haga clic en **Siguiente**.
    
   - Una vez que se cree el clúster, haga clic en **Finalizar**.
    
4. Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:
    
   - Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.
    
   - En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.
    
   - En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.
    
   - En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.
    
   - En la página **Confirmación**, haga clic en **Siguiente**.
    
5. En cada uno de los servidores en el clúster, habilite Always On en el Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server.  
    
   - En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.
    
6. Cree el grupo de disponibilidad.
    
   - Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.
    
   - En Explorador de objetos, expanda la carpeta **AlwaysOn alta disponibilidad**. Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.
    
   - Si aparece la página **Introducción**, haga clic en **Siguiente**.
    
   - En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
   - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn. Then click **Next**.
    
    No incluya el **ReportServer**, **ReportServerTempDB**o charla persistente de bases de datos en el grupo de disponibilidad AlwaysOn, ya no se admiten en este escenario. Puede incluir todas las demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.
    
   - En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.
    
   - Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.
    
   - Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.
    
   - Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).
    
   - Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.
    
   - En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.
    
    Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.
    
    - En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.
    
   - En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.
    
7. Crear un nuevo almacén especificando la escucha del grupo de disponibilidad AlwaysOn.
    
   - Abra el generador de topología. En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.
    
   - En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.
    
   - En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.
    
   - En el cuadro **Nombre de dominio completo de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn y, a continuación, haga clic en **Aceptar**.
    
8. Asociar el nuevo grupo de disponibilidad AlwaysOn con el grupo de servidores Front-End.
    
   - Generador de topología, haga clic en el grupo que desee asociar al grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
   - En **las asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el grupo de disponibilidad AlwaysOn. Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover al grupo de disponibilidad AlwaysOn.
    
   - Cuando esté seguro de que todas las bases de datos necesarias se establecen en el grupo de disponibilidad AlwaysOn, haga clic en **Aceptar**.
    
9. Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.
    
10. Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.
    
    - Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.
    
    - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y ** editar propiedades **.
    
    - En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , cambie el valor para el nombre completo del agente de escucha del grupo disponibilidad AlwaysOn.
    
    - Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.
    
    - Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn. Conmútelo por error a una réplica secundaria.
    
    - Abre Skype para negocios de Shell de administración de servidor y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:
    
     ```
     Install-CsDatabase -Update
     ```

     - Repita los dos pasos anteriores (error en el grupo a una segunda réplica, luego use `Install-CsDatabase -Update`) para cada réplica en el grupo.
    

