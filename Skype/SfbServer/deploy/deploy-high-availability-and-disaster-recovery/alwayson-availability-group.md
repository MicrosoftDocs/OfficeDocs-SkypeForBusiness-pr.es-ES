---
title: Implementar un grupo de disponibilidad siempre en un servidor Back-End de Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implementar (instalar) un siempre en grupo de disponibilidad en su Skype para Business Server implementación.
ms.openlocfilehash: eaf0c935f246cfdd00aa0707475442c88dc89b8a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374375"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Implementar un grupo de disponibilidad siempre en un servidor Back-End de Skype para Business Server
 
Implementar (instalar) una siempre en disponibilidad grupo (AG) en su Skype para Business Server implementación.
  
Cómo implementar un AG depende de si se implementa en un nuevo grupo de servidores, un grupo de servidores existente que usa la creación de reflejos o un grupo de servidores existente que tiene actualmente no hay una alta disponibilidad para la base de datos back-End.
  
> [!NOTE]
> No se admite el uso de un AG con un rol de servidor de Chat persistente. 
  
- [Implementar un siempre en grupo de disponibilidad en un nuevo grupo de servidores Front-End](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que usa la creación de reflejo de base de datos](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que no se utiliza la creación de reflejo de base de datos](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Implementar un siempre en grupo de disponibilidad en un nuevo grupo de servidores Front-End
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Habilitar la característica de agrupación en clústeres de conmutación por error en todos los servidores de base de datos que formarán parte de la AG. En cada uno de los servidores, haga lo siguiente
    
   - Abra Administrador de servidores y haga clic en **Agregar roles y características**.
    
   - Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.
    
   - En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.
    
   - Haga clic en **Instalar**.
    
2. Valide la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.
    
   - En el cuadro**Resumen** , compruebe los errores que el Asistente para informes. Luego haga clic en **Finalizar** para completar la validación.
    
     Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.
    
3. Crear el clúster de conmutación por error de Windows Server (WSFC).
    
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
    
5. En cada servidor del clúster, habilitar la característica de AG en el Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server.  
    
   - En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.
    
6. Cree el grupo de disponibilidad.
    
   - Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.
    
   - En el Explorador de objetos, expanda la carpeta **Siempre en alta disponibilidad** . Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.
    
   - Si aparece la página **Introducción**, haga clic en **Siguiente**.
    
   - En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
   - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn. Then click **Next**.
    
     No incluya el **ReportServer**, **ReportServerTempDB**o bases de datos de Chat persistente en el grupo de disponibilidad AlwaysOn, como no se admiten en este escenario. Puede incluir todos los demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.
    
   - En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.
    
   - Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.
    
   - Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.
    
   - Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).
    
   - Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.
    
   - En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.
    
     Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.
    
   - En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.
    
   - En la página**Resumen** , compruebe todas las opciones y haga clic en Finalizar.
    
7. Usar el generador de topología para crear el grupo de servidores Front-End, como se explica en [crear y publicar la nueva topología de Skype para Business Server](../../deploy/install/create-and-publish-new-topology.md). Cuando lo hace, especifique el AG como el almacén de SQL para el grupo de servidores.
    
8. Después de que el grupo de servidores y el AG se implementan, realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn. 
    
   - Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.
    
   - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga clic en el almacén de SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
     - En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , cambie el valor para el FQDN del agente de escucha de la AG.
    
   - Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.
    
   - Abra SQL Server Management Studio y navegue a la AG. Conmútelo por error a una réplica secundaria.
    
   - Abra Skype para Shell de administración de servidor empresarial y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:
    
   ```
   Install-CsDatabase -Update
   ```

   - Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria, a continuación, usar `Install-CsDatabase -Update`) para cada réplica en el grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que usa la creación de reflejo de base de datos
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si el grupo que se va a actualizar a una AG hospeda el almacén de Administración Central para su organización, primero debe mover el CMS a otro grupo de servidores antes de actualizar este grupo de servidores. Use el cmdlet Move-CsManagementServer para mover el grupo de servidores. Si no tiene otro grupo de servidores en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo de servidores a la AG. 
  
1. Conmutación por error todos los datos desde el reflejo para el nodo de entidad de seguridad abriendo Skype para Shell de administración de servidor empresarial y escribiendo el siguiente cmdlet.
    
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
    
   - Repita este paso para todas las bases de datos en el grupo de servidores que se convertirá a un AG.
    
5. Configurar la característica de agrupación en clústeres de conmutación por error en todos los servidores de base de datos que formarán parte de la AG. En cada uno de los servidores, haga lo siguiente
    
   - Abra Administrador de servidores y haga clic en **Agregar roles y características**.
    
   - Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.
    
   - En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.
    
   - Haga clic en **Instalar**.
    
6. Valide la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.
    
   - En el cuadro**Resumen** , compruebe los errores que el Asistente para informes. Luego haga clic en **Finalizar** para completar la validación.
    
     Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.
    
7. Crear el clúster de conmutación por error de Windows Server.
    
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
    
9. En cada servidor del clúster, habilitar la característica de AG en el Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server.  
    
   - En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.
    
10. Cree el grupo de disponibilidad.
    
    - Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.
    
    - En el Explorador de objetos, expanda la carpeta **Siempre en alta disponibilidad** . Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.
    
    - Si aparece la página **Introducción**, haga clic en **Siguiente**.
    
    - En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
    - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn. Then click **Next**.
    
    No incluya el **ReportServer**, **ReportServerTempDB**o bases de datos de Chat persistente en el grupo de disponibilidad AlwaysOn, como no se admiten en este escenario. Puede incluir todos los demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.
    
    - En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.
    
    - Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.
    
    - Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.
    
      - Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).
    
    - Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.
    
    - En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.
    
    Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.
    
    - En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.
    
    - En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.
    
11. Crear un nuevo almacén especificando el agente de escucha AG y especificando la entidad de seguridad del reflejo antiguo como el nodo principal de la AG.
    
    - Abra el generador de topología. En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.
    
    - En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.
    
    - En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.
    
    - En el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal de la AG y, a continuación, haga clic en **Aceptar**. Esto debería ser la entidad de seguridad del reflejo antiguo de este almacén.
    
12. Asociar el nuevo AG con el grupo de servidores Front-End.
    
    - En el generador, haga clic en el grupo que se va a asociar con el AG y haga clic en **Editar propiedades**.
    
    - En **asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el AG. Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover a la AG.
    
    - Cuando esté seguro de que todas las bases de datos necesarias se establecen en el AG, haga clic en **Aceptar**.
    
13. Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.
    
14. Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.
    
    - Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.
    
    - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga clic en el almacén de SQL de la nueva AG y haga clic en **Editar propiedades**.
    
    - En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , cambie el valor para el FQDN del agente de escucha de la AG.
    
    - Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.
    
    - Abra SQL Server Management Studio y navegue a la AG. Conmútelo por error a una réplica secundaria.
    
    - Abra Skype para Shell de administración de servidor empresarial y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:
    
    ```
    Install-CsDatabase -Update
    ```

    - Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria, a continuación, usar `Install-CsDatabase -Update`) para cada réplica en el grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que no se utiliza la creación de reflejo de base de datos
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si el grupo que se va a actualizar a una AG hospeda el almacén de Administración Central para su organización, primero debe mover el CMS a otro grupo de servidores antes de actualizar este grupo de servidores. Use el cmdlet Move-CsManagementServer para mover el grupo de servidores. Si no tiene otro grupo de servidores en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo de servidores a la AG. 
  
1. Configurar la característica de agrupación en clústeres de conmutación por error en todos los servidores de base de datos que formarán parte de la AG. En cada uno de los servidores, haga lo siguiente
    
   - Abra Administrador de servidores y haga clic en **Agregar roles y características**.
    
   - Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.
    
   - En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.
    
   - Haga clic en **Instalar**.
    
2. Valide la configuración del clúster.
    
   - En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.
    
   - En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.
    
   - En la página **Antes de empezar**, haga clic en **Siguiente**.
    
   - Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.
    
   - En el cuadro**Resumen** , compruebe los errores que el Asistente para informes. Luego haga clic en **Finalizar** para completar la validación.
    
     Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.
    
3. Crear el clúster de conmutación por error de Windows Server (WSFC).
    
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
    
5. En cada servidor del clúster, habilitar AG en el Administrador de configuración de SQL Server.
    
   - Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server.  
    
   - En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.
    
6. Cree el grupo de disponibilidad.
    
   - Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.
    
   - En el Explorador de objetos, expanda la carpeta **Siempre en alta disponibilidad** . Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.
    
   - Si aparece la página **Introducción**, haga clic en **Siguiente**.
    
   - En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.
    
   - En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el AG. Then click **Next**.
    
     No incluir la **ReportServer**, **ReportServerTempDB**o bases de datos de Chat persistente en el AG, como no se admiten en este escenario. Puede incluir todos los demás Skype para bases de datos de Business Server en el AG.
    
   - En la página **Especificar réplicas** , haga clic en la ficha **réplicas** . A continuación, haga clic en el botón **Agregar réplicas** y conectarse a las instancias SQL que se ha unido a como nodos de la WSFC.
    
   - Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.
    
   - Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.
    
   - Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).
    
   - Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.
    
   - En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.
    
     Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.
    
     - En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.
    
   - En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.
    
7. Crear un nuevo almacén de especificación de la escucha de AG.
    
   - Abra el generador de topología. En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.
    
   - En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.
    
   - En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.
    
   - En el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal de la AG y, a continuación, haga clic en **Aceptar**.
    
8. Asociar el nuevo siempre en grupo de disponibilidad con el grupo de servidores Front-End.
    
   - En el generador, haga clic en el grupo que se va a asociar con el AG y haga clic en **Editar propiedades**.
    
   - En **asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el AG. Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover a la AG.
    
   - Cuando esté seguro de que todas las bases de datos necesarias se establecen en el AG, haga clic en **Aceptar**.
    
9. Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.
    
10. Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el AG.
    
    - Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.
    
    - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga clic en el almacén de SQL de la nueva AG y haga clic en **Editar propiedades**.
    
    - En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , cambie el valor para el FQDN del agente de escucha de la AG.
    
    - Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.
    
    - Abra SQL Server Management Studio y navegue a la AG. Conmútelo por error a una réplica secundaria.
    
    - Abra Skype para Shell de administración de servidor empresarial y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:
    
      ```
      Install-CsDatabase -Update
      ```

      - Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria, a continuación, usar `Install-CsDatabase -Update`) para cada réplica en el grupo.