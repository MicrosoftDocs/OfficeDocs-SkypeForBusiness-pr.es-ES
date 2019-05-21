---
title: Implementar el panel de calidad de llamadas para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumen: Obtenga información sobre el proceso de implementación del panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 3cc3b81180453454f8615d31f57911c0958553c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274845"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Implementar el panel de calidad de llamadas para Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el proceso de implementación para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
## <a name="deployment-overview"></a>Información general de la implementación

El panel de calidad de llamadas (CQD) consta de tres componentes principales:
  
- **Archivar la base**de datos, donde se replican y almacenan los datos de la calidad de la experiencia (QoE).
    
- **Cubo**, donde los datos de la base de datos de archivo de QoE se agregan para un acceso rápido y optimizado.
    
- **Portal**, donde los usuarios pueden consultar y visualizar los datos de la calidad del QoE con facilidad.
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
El proceso de configuración para el archivo de QoE incluye la creación de la base de datos de archivo de QoE, la implementación de un procedimiento almacenado de SQL Server que moverá los datos de la base de datos de la QoE de origen a la base de datos de archivo de QoE y la configuración del trabajo del Agente SQL Server para ejecutar el procedimiento a intervalos regulares. 
  
Implementación de cubo obtiene información del usuario en la que se encuentra el archivo de calidad de la calidad, implementa el cubo y configura un trabajo normal del Agente SQL Server que actualizará el cubo a intervalos regulares.
  
Instalación del portal crea una base de datos del depósito que almacena la asignación de los usuarios del CQD a las consultas o los informes de cada usuario. Después, configura una aplicación Web de IIS, que es el panel donde los usuarios pueden ver un conjunto predefinido de informes, así como personalizar y crear sus propias consultas para visualizar los datos del cubo. La instalación del portal crea dos aplicaciones web adicionales que exponen las API para que los usuarios tengan acceso mediante programación al repositorio y al cubo. (El panel también usa internamente estas API).
  

|**Fase**|**Pasos**|**Roles y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|Instalar requisitos previos de hardware y software.  <br/> |Decida la configuración del CQD y seleccione un SQL Server desde el que realizar la instalación.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Sección "requisitos previos a la instalación" de la documentación de implementación.  <br/> |
|Instale el CQD.  <br/> |Ejecute el MSI siguiendo el documento de implementación.  <br/> |Para realizar la configuración, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo de administradores locales y tener acceso de lectura a la base de datos de QoE Metrics en el servidor de supervisión.  <br/> |Secciones "cuentas y pasos de implementación" en la documentación de implementación.  <br/> |
|Conceder acceso al usuario.  <br/> |Para administrar la autorización de usuario para el portal, se recomienda usar la autorización de URL, que se presentó en IIS 7,0. Para obtener más información, vea Descripción de la [autorización de URL de IIS 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Administrar el acceso de los usuarios para la sección del portal en la documentación de implementación.  <br/> |
|Opcional: proporcionar información de asignación de subred.  <br/> |Rellene la red y cree tablas de asignación en la base de datos de archivos de QoE.  <br/> |Una cuenta con acceso de escritura a la base de datos de archivo de calidad.  <br/> |Sección "suministrar información de subred" en la documentación del usuario.  <br/> |
   


La implementación del panel de calidad de llamadas implica la configuración de la infraestructura y la instalación del software. El procedimiento siguiente describe el proceso.
  
## <a name="deployment-steps"></a>Pasos de implementación

1. Copie CallQualityDashboard. msi en el equipo en el que se va a instalar el componente de base de datos de archivo del CQD (este es el equipo que tiene instalado SQL Server). 
    
2. Ejecute el MSI (Windows le pedirá que se ejecute con privilegio de administrador, etc.). 
    
3. Acepte el CLUF.
    
4. Seleccione la carpeta de destino donde se encuentran los archivos relacionados con los componentes del panel de calidad de llamadas o acepte la ubicación predeterminada.
    
5. Seleccione todas las características.
    
6. En la página Configuración del archivo de calidad del archivo, proporcione la siguiente información:
    
   - La QoE de calidad de la **calidad de SQL Server:** Nombre de la instancia de SQL Server para el lugar donde se encuentra la base de datos de la calidad de la QoE (este es el origen de datos).
    
   - **Nombre del servidor SQL del archivo QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local. La base de datos de almacenamiento solo se puede instalar en el equipo local.
    
   - **Archivo de la instancia de SQL Server de archivo QoE:** Un nombre de instancia de SQL Server local para el lugar donde se va a crear la base de datos de archivo. Para usar una instancia de SQL Server predeterminada, deje este campo en blanco. Para usar una instancia de SQL Server con nombre, especifique el nombre de la instancia (por ejemplo,\"el nombre después de ")".
    
   - **Base de datos de archivo de QoE:** De forma predeterminada, esta opción está establecida en "crear nueva base de datos". Como la actualización de la base de datos archivada no es compatible, la única circunstancia en la que se puede usar la opción "usar base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación que se va a instalar.
    
   - **Directorio de archivos de base de datos:** Ruta de acceso donde se deben colocar los archivos de base de datos (. MDF y. ldf) para el archivo BD de archivo. Debe estar en una unidad (HDD2 en la configuración de hardware recomendada) independiente del sistema operativo. Tenga en cuenta que, dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se use un directorio en blanco sin archivos.
    
   - **Usar varias particiones:** El valor predeterminado se establece en "partición múltiple", que requiere Business Intelligence Edition o Enterprise Edition de SQL Server. Para Standard Edition, seleccione la opción "partición única". Tenga en cuenta que el rendimiento del procesamiento del cubo puede verse afectado si se usa una única partición.
    
     > [!NOTE]
     > La opción selección para usar varias particiones no se puede cambiar una vez que se complete la instalación. Para poder cambiarla, la característica de cubo debe desinstalarse primero y volver a instalarse con la opción "cambiar" del panel de control. 
  
   - **Directorio de archivos de partición:** Ruta en la que se deben ubicar las particiones de la base de datos de archivo de calidad. Debe estar en una unidad (HDD3 en la configuración de hardware recomendada) independiente de la unidad del sistema operativo y de los archivos de registro de la base de datos de SQL. Tenga en cuenta que, dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se use un directorio en blanco sin archivos.
    
   - **Trabajo del Agente SQL-contraseña del &amp; nombre de usuario:** Nombre y contraseña de la cuenta de servicio de dominio (enmascarado) que se usarán para ejecutar el paso "información del archivo de calidad del producto de QoE" del trabajo del Agente SQL Server (que ejecutará el procedimiento almacenado para capturar datos de la BD de QoE Metrics a Archive DB, por lo que esta cuenta debe tener acceso de lectura a la BD de la métrica de calidad.  según se indica en la sección cuentas. Esta cuenta también necesita tener un inicio de sesión en la instancia de Archive SQL Server de QoE).
    
     > [!NOTE]
     > La cuenta con la que se ejecuta la instancia de SQL Server, como NT SERVICE\MSSQLSERVER, debe tener acceso/permiso a los directorios mencionados anteriormente para que la instalación se realice correctamente. Para obtener más información, vea [configurar permisos del sistema de archivos para el acceso del motor de base de datos](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Al hacer clic en siguiente, el instalador realizará comprobaciones y notificaciones de requisitos previos si se producen problemas. Cuando se superan todas las comprobaciones de requisitos previos, el instalador irá a la página de configuración del cubo. 
    
    > [!NOTE]
    > Si el instalador muestra un mensaje de advertencia que indica que el servicio del Agente SQL Server para la instancia de Archive SQL Server de QoE no se está ejecutando actualmente, la instalación puede continuar, pero después de la instalación, asegúrese de que el servicio Agente SQL se esté ejecutando y establezca el tipo de inicio en Automático para que se ejecute el trabajo programado. 
  
8. En la página Configuración del cubo, proporcione la siguiente información:
    
   - **Nombre del servidor SQL del archivo QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local. El cubo solo se puede instalar desde la máquina que tiene la base de datos de archivo de calidad. El propio cubo puede instalarse en un equipo remoto. Ver a continuación)
    
   - **Archivo de la instancia de SQL Server de archivo QoE:** Nombre de la instancia de SQL Server en la que se encuentra la QoE Archive DB. Para especificar una instancia de SQL Server predeterminada, deje este campo en blanco. Para especificar una instancia de SQL Server con nombre, escriba el nombre de la instancia (por ejemplo,\"el nombre después de ")". Si se seleccionó el componente de archivo QoE para la instalación, este campo estará previamente rellenado con el valor proporcionado en la página de configuración del archivo de calidad.
    
   - **Servidor de análisis de cubos:** Nombre de instancia de SQL Server Analysis Services para la ubicación donde se va a crear el cubo. Puede ser un equipo diferente, pero el usuario de instalación tiene que ser miembro de los administradores de servidor de la instancia de SQL Server Analysis Services de destino.
    
     > [!NOTE]
     >  Para obtener más información sobre cómo configurar permisos de administrador del servidor de Analysis Services, consulte [conceder permisos de administrador de servidor (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx) .
  
   - **Usar varias particiones:** El valor predeterminado se establece en "partición múltiple", que requiere Business Intelligence Edition o Enterprise Edition de SQL Server. Para Standard Edition, seleccione la opción "partición única". Tenga en cuenta que el rendimiento del procesamiento del cubo puede verse afectado si se usa una única partición.
    
     > [!NOTE]
     >  La opción selección para usar varias particiones no se puede cambiar una vez que se complete la instalación. Para poder cambiarla, la característica de cubo debe desinstalarse primero y volver a instalarse con la opción "cambiar" del panel de control.
  
   - **Usuario del cubo: contraseña &amp; del nombre de usuario:** Nombre y contraseña de la cuenta de servicio de dominio (enmascarado) que desencadenarán el procesamiento del cubo. Si se seleccionó el componente de archivo QoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo del usuario del trabajo del Agente SQL, pero recomendamos especificar otra cuenta de servicio de dominio para que el programa de instalación pueda conceder el privilegio mínimo requerido.
    
9. Al hacer clic en siguiente, se realizará otro turno de validación y se informará de cualquier problema. Una vez completada la validación correctamente, el instalador irá a la página de configuración del portal. 
    
10. En la página Configuración del portal, proporcione la siguiente información:
    
    - **Servidor SQL Server de calidad:** Nombre de la instancia de SQL Server en la que se encuentra la base de datos del archivo de calidad. Tenga en cuenta que, a diferencia de la página Configuración del archivo de calidad del archivo y la página Configuración del cubo, el nombre del equipo no es fijo y debe proporcionarse. Si se seleccionó el componente de archivo QoE para la instalación, este campo estará previamente rellenado con el valor proporcionado en la página de configuración del archivo de calidad.
    
    - **Servidor de análisis de cubos:** Nombre de la instancia de SQL Server Analysis Services para la ubicación del cubo. Si se seleccionó el componente de cubo para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración del cubo.
    
    - **SQL Server del repositorio:** Nombre de la instancia de SQL Server donde se va a crear la base de datos del repositorio. Si el nombre de la instancia de SQL Server en el que se encuentra la base de datos de archivo de QoE se ha proporcionado anteriormente en la configuración (en otros componentes), este campo estará previamente rellenado con el nombre de la instancia de SQL Server de archivo de QoE. Puede ser cualquier instancia de SQL Server.
    
    - **Base de datos del repositorio:** De forma predeterminada, la opción se establece en "crear una nueva base de datos". Puesto que la actualización de BD de repositorio no es compatible, la única circunstancia en la que se puede usar la opción "usar base de datos existente" es si la base de datos del repositorio existente tiene el mismo esquema que la compilación que se va a instalar.
    
    - **Usuario del grupo de aplicaciones de IIS &amp; : contraseña del nombre de usuario:** Cuenta con la que se debe ejecutar el grupo de aplicaciones de IIS. Los campos nombre de usuario y contraseña aparecerán atenuados si se seleccionan las cuentas del sistema integrado. Estos campos solo se habilitan si se selecciona "otro" en el cuadro desplegable para que el usuario pueda escribir la información de la cuenta de servicio de dominio.
    
11. Al hacer clic en siguiente, la última ronda de validación se realizará para asegurarse de que se puede acceder a las instancias de SQL Server con las credenciales proporcionadas y de que IIS está disponible en el equipo. Una vez completada la validación correctamente, el instalador continuará con la configuración. 
    
Una vez finalizado el instalador, lo más probable es que el trabajo del Agente SQL Server esté en curso, realizando la carga inicial de los datos de la calidad de la calidad y el procesamiento del cubo. En función de la cantidad de datos de QoE, el portal no tendrá datos disponibles para su visualización. Para comprobar el estado de la carga de datos y el procesamiento del cubo, `http://<machinename>/CQD/#/Health`vaya a. 
> [!NOTE]
> Observe que la dirección URL para comprobar el estado del procesamiento del cubo de descarga distingue entre mayúsculas y minúsculas. Si escribe ' Health ', la dirección URL no funcionará. Debes introducir ' Health ' al final de la dirección URL con una H mayúscula. 
  
Los mensajes de registro detallados se mostrarán si el modo de depuración está habilitado. Para habilitar el modo de depuración, vaya a **%SystemDrive%\Archivos de Files\Skype para empresas 2015 CQD\QoEDataService\web.config**y actualice la siguiente línea para que el valor se establezca en **verdadero**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Se puede acceder a la Página principal `http://<machinename>/CQD`del portal a través de. 
## <a name="managing-user-access-for-the-portal"></a>Administrar el acceso de los usuarios del portal

Para administrar la autorización de usuario para el portal, se recomienda usar la autorización de URL, que se presentó en IIS 7,0. Para obtener más información sobre la seguridad de IIS, vea Descripción de la [autorización de URL de iis 7,0 ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Cualquier sitio web o aplicación web hereda la autorización de dirección URL predeterminada configurada para el IIS completo, que normalmente es "permitir a todos los usuarios". Si el acceso al portal tiene que ser más restrictivo, los administradores pueden conceder acceso solo a un grupo específico de usuarios mediante la edición de las "reglas de autorización".
  
![Implementar la calidad de llamadas: reglas de autorización en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> El icono de reglas de autorización no se debe confundir con la "autorización de .NET" en la sección ASP.NET, que es un mecanismo de autorización diferente. 
  
Los administradores deben quitar primero la regla heredada "permitir todos los usuarios". Esto evita que los usuarios no autorizados tengan acceso al portal.
  
![Implementar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Después, los administradores deben agregar nuevas reglas de autorización y conceder a los usuarios específicos el permiso para acceder al portal. Se recomienda crear un grupo local denominado "CQDPortalUsers" para administrar los usuarios.
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Los detalles de configuración se almacenan en la Web. config, que se encuentra en el directorio físico del portal.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

El siguiente paso es configurar el panel del CQD. Una vez que los usuarios sean autenticados por IIS, deberán tener permisos de archivo en el directorio de CQD para poder acceder al contenido del portal web. Es posible cambiar las ACL mediante la pestaña seguridad de las propiedades del directorio CQD para agregar usuarios individuales o grupos; sin embargo, el enfoque recomendado es dejar los permisos de archivo intactos. En su lugar, cambie la configuración de IIS para usar el proceso de trabajo de IIS para obtener acceso al directorio de CQD independientemente del usuario autenticado. 
  
> [!IMPORTANT]
> Es importante que solo cambie esta configuración para la aplicación CQD y no para las dos aplicaciones API: QoEDataService y QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuración del acceso a archivos para el CQD (panel)

1. Abra el editor de configuración de CQD.
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. En sección, elija **System. WebServer/serverRuntime**.
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Cambie authenticatedUserOverride a **UseWorkerProcessUser**.
    
     ![Implementar el panel de calidad de llamadas: editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Haga clic en **aplicar** en el lado derecho de la página.
    
## <a name="known-issues"></a>Problemas conocidos

### <a name="the-cqd-shows-no-data-after-deployment"></a>El CQD no muestra datos después de la implementación

Es posible que reciba el siguiente error:

*No pudimos realizar la consulta mientras se ejecutaba en el cubo. Use el editor de consultas para modificar la consulta y corregir los problemas. Asegúrese también de que el cubo es accesible.*

Esto significa que el cubo debe procesarse en SQL Server Analysis Services antes de usarlo en el CQD. Para solucionar esto, siga estos pasos:

1. Abra SQL Management Studio y seleccione **Analysis Services**.

2. Expanda el objeto **QoECube** , seleccione la **métrica de QoE**, haga clic con el botón derecho y, a continuación, elija **examinar**. 

    Si devuelve un explorador vacío, el cubo aún no se ha realizado.

3. Haga clic con el botón secundario en ganancia **métrica de QoE** y elija **procesar**.

4. Cuando el procesamiento haya finalizado, vuelva a hacer clic con el botón derecho en el objeto y elija **examinar** para confirmar que la página del explorador muestra los datos. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Los usuarios tienen problemas para iniciar sesión porque el instalador no puede crear la configuración correcta en IIS

En raras ocasiones, el instalador no puede crear la configuración correcta en IIS. El cambio manual es necesario para permitir que los usuarios inicien sesión en el CQD. Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:
  
1. Abra el administrador de IIS y vaya al sitio web predeterminado.
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Haz clic en "autenticación". Si la "autenticación anónima", "ASP.NET suplantación", "autenticación de formularios" y "autenticación de Windows" no coinciden con la configuración que se muestra a continuación, cámbielas manualmente para que coincidan con los valores siguientes. Se debe deshabilitar el resto de los mecanismos de autenticación.
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Para "autenticación de Windows", haga clic en configuración avanzada, en la parte derecha.
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Configure "protección extendida" para que acepte y active la casilla "habilitar la autenticación de modo kernel".
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita los pasos anteriores para cada una de las entradas "CQD", "QoEDataService" y "QoERepositoryService", que se encuentran debajo de "sitio web predeterminado".
    
Para los enlaces de Puerto HTTP y HTTPS, el instalador creará enlaces de puertos en los números de puertos predeterminados (puerto 80 para HTTP y puerto 443 para HTTPS). Si hay otro sitio web en el equipo que usa estos enlaces, se producirá un conflicto y no se podrá predecir el comportamiento de IIS. La mejor manera de evitar este problema es asegurarse de que no hay otros sitios web asignados a los puertos 80 y 443 antes de instalar el CQD. 
  
Para habilitar SSL/TLS en IIS y obligar a los usuarios a conectarse a través de HTTPS seguro en lugar de HTTP:
  
1. Configurar la capa de sockets seguros en IIS, vea [configurar el nivel de sockets seguros en IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Una vez hecho esto `http` , `https`reemplaza por.
    
2. Para obtener instrucciones sobre cómo habilitar TLS en las conexiones de SQL Server, consulte [Cómo habilitar el cifrado SSL para una instancia de SQL Server mediante Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).
    
## <a name="cube-sync-fails"></a>Error en la sincronización del cubo

QoEMetrics puede contener algunos registros no válidos basados en los relojes de los usuarios finales. Si el sesgo horario es superior a 60 años, se producirá un error en la importación del cubo.
  
 Comprueba la hora de finalización mínima y máxima de la hora de finalización/hora de las siguientes opciones. Busque y elimine registros en el futuro muy lejano y muy lejano, se pueden descartar y se descartarán los procesos de sincronización.
  
- Seleccione mín (StartTime) desde CqdPartitionedStreamView
    
- Seleccione MAX (StartTime) FROM CqdPartitionedStreamView
    
- Seleccione mín (EndTime) desde CqdPartitionedStreamView
    
- Seleccione MAX (EndTime) desde CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tareas posteriores a la instalación

### <a name="importing-buildings-and-networks"></a>Importar edificios y redes

Después de instalar el CQD, realice las siguientes tareas de configuración:
  
1. Definir tipos de creación (recomendado)
    
2. Definir tipos de propiedad de construcción (recomendado)
    
3. Definir tipos de red (muy recomendable)
    
4. Importar edificios (recomendado)
    
5. Importar subredes (recomendado)
    
### <a name="define-building-types"></a>Definir tipos de creación

Los tipos de construcción se usan para describir las diferentes definiciones o tipos de edificios de su organización. 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Ejemplos
  
- Sede central
    
- Oficina remota
    
- Ubicación de la empresa conjunta
    
  **Ejemplo de sintaxis SQL**
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Los parámetros BuildingTypeId y BuildingTypeDesc son obligatorios.
  
### <a name="define-building-ownership-types"></a>Definir tipos de propiedad de construcción

Los tipos de propiedad se usan para distinguir los activos de propiedad y concesiones.
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Ejemplos
  
- Contoso alquilado no RE&amp;F
    
- RE&amp;alquilada de Contoso F
    
- Propiedad de Contoso
    
- Arrendamiento de subsidiarias
    
  **Ejemplo de sintaxis SQL**
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

Los parámetros OwnershipTypeId y OwnershipTypeDesc son obligatorios. 
  
### <a name="define-network-names"></a>Definir nombres de red

Los tipos de red se usan para describir distintos tipos de redes dentro de la organización. Esto le ofrece la posibilidad de filtrar (o filtrar) determinados tipos de red.
  
> [!NOTE]
> Es muy recomendable definir nombres de red, pero es opcional. Si decide no definir nombres de red, asegúrese de que la entrada de CqdNetwork tiene un BuildingId de 0. 
  
Ejemplos
  
- VPN
    
- PRÁCTICO
    
  **Ejemplo de sintaxis SQL**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Los parámetros NetworkNameID y red son obligatorios, el parámetro NetworkType es opcional, pero se recomienda.
  
### <a name="import-buildings"></a>Importar edificios

La importación de edificios te brinda la posibilidad de obtener información específica (llamadas deficientes por construcción en WiFi/cableada, etc.). 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Antes de importar un nuevo edificio, ya tiene un BuildingKey predefinido. Para ello, emita el comando SQL "SELECT MAX (BuildingKey) FROM CqdBuilding" para identificar el valor actual y agregar 1 al resultado.
  
 **Ejemplo de sintaxis SQL**
  
```
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

Se necesitan los parámetros BuildingKey, edificio, BuildingShortName, OwnershipTypeId, BuildingTypeId, los otros parámetros son opcionales.
  
### <a name="import-subnets"></a>Importar subredes

La importación de edificios te brinda la posibilidad de obtener información específica (llamadas deficientes por construcción en WiFi/cableada, etc.). 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Importar subredes y asignarlas a los edificios importados en el último paso. Si decide no rellenar red, asegúrese de que cada entrada de esta tabla use un NetworkNameID de 0.
  
 **Ejemplo de sintaxis SQL**
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

La red y los parámetros UpdatedDate son obligatorios, los otros parámetros son opcionales.
  
### <a name="optional-bssid"></a>Opcional: BSSID

Rellenar la información de BSSID proporciona una correlación adicional de secuencias WiFi por controlador o radio. Esto es además de filtrar por edificio o subred. 
  
 **Ejemplo de sintaxis SQL**
  
```
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**Detalles de CqdBssidTable**

|**Tal como se muestra en el CQD**|**Tabla CQDBssid**|**Entradas de ejemplo**|
|:-----|:-----|:-----|
|AP NName  <br/> |INALÁMBRICO  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (debe usar la Fformat delimitada)  <br/> |
|Control  <br/> |Building  <br/> |Aruba PA 7  <br/> |
|Dispositivo  <br/> |ess  <br/> |Controller1  <br/> |
|Aficionados  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Procesando los datos importados

De forma predeterminada, después de importar datos de edificio o de red, solo se aplicará a los registros generados después de ese momento. 
  
Para etiquetar todos los registros anteriores con estos nuevos datos, tendrá que ejecutar el procedimiento almacenado CqdUpdateBuilding, como se muestra a continuación: 
  
Asígnele la fecha del primer registro (identifique el uso del comando SELECT MIN (StartTime) de CqdPartitionedStreamView SQL), un EndDate de mañana y, a continuación, NULL para los dos últimos valores.
  
Una vez que los datos están asociados a los datos de la secuencia, el cubo SSIS debe reprocesar todos los registros. Esto también se aplica al agregar de forma masiva datos de BSSID o ISP. Asegúrese de que esté seleccionado "proceso completo".
  

