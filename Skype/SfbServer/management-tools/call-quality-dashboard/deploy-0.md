---
title: Implementar panel de calidad de llamadas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumen: obtenga información sobre el proceso de implementación del Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 1f59209575284035fcdca52e4f18220aa05337af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114116"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Implementar panel de calidad de llamadas para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el proceso de implementación del Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
## <a name="deployment-overview"></a>Vista general de implementación

El Panel de calidad de llamadas (CQD) consta de tres componentes principales:
  
- **Base de datos de** archivo , donde se replican y almacenan los datos de calidad de la experiencia (QoE).
    
- **Cubo**, donde se agregan datos de la base de datos de archivos qoE para un acceso optimizado y rápido.
    
- **Portal**, donde los usuarios pueden consultar y visualizar fácilmente los datos de QoE.
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
El proceso de instalación de QoE Archive implica la creación de la base de datos de archivos qoE, la implementación de un procedimiento almacenado de SQL Server que moverá los datos de la base de datos de métricas qoE de origen a la base de datos de archivo qoE y la configuración del trabajo del agente de SQL Server para ejecutar el procedimiento almacenado en un intervalo regular. 
  
La implementación de cubos obtiene información del usuario sobre dónde se encuentra el archivo QoE, implementa el cubo y configura un trabajo de agente de SQL Server normal que actualizará el cubo en un intervalo regular.
  
La instalación del portal crea una base de datos de repositorio que almacena la asignación de usuarios de CQD a los informes o consultas de cada usuario. A continuación, configura una aplicación web de IIS que es el panel donde los usuarios pueden ver un conjunto predefinido de informes, así como personalizar y crear sus propias consultas para visualizar los datos del cubo. La instalación del portal crea dos aplicaciones web adicionales que exponen las API para que los usuarios accedan mediante programación al repositorio y al cubo. (El panel también usa internamente estas API).
  

|**Fase**|**Pasos**|**Roles y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|Instalar hardware y software previos.  <br/> |Decida la configuración de CQD y elija una SQL Server desde la que realizar la instalación.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Sección "Requisitos de instalación previa" en la documentación de implementación.  <br/> |
|Instale CQD.  <br/> |Ejecute msi siguiendo el documento de implementación.  <br/> |Para realizar la instalación, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo de administradores locales y tenga acceso de lectura a la base de datos de métricas de QoE en el servidor de supervisión.  <br/> |Secciones "Cuentas y pasos de implementación" en la documentación de implementación.  <br/> |
|Conceder acceso de usuario.  <br/> |Para administrar la autorización de usuario en el Portal, se recomienda usar la autorización de dirección URL, que se introdujo en IIS 7.0. Para obtener más información, vea [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Administración del acceso de usuario para la sección Portal en la documentación de implementación.  <br/> |
|Opcional: proporcione información de asignación de subred.  <br/> |Rellene las tablas de asignación de red y de creación en la base de datos de archivos qoE.  <br/> |Una cuenta con acceso de escritura a la base de datos de archivos QoE.  <br/> |Sección "Suministro de información de subred" en la documentación del usuario.  <br/> |
   


La implementación del Panel de calidad de llamadas implica configurar la infraestructura e instalar el software. El siguiente procedimiento describe el proceso.
  
## <a name="deployment-steps"></a>Pasos de implementación

1. Copie el CallQualityDashboard.msi en el equipo donde se va a instalar el componente de base de datos de archivo de CQD (este es el equipo que SQL Server instalado). 
    
2. Ejecute msi (Windows pedirá que se ejecute con privilegios de administrador, así que). 
    
3. Aceptar el CLUF.
    
4. Seleccione la carpeta de destino donde se ubicarán los archivos relacionados con los componentes del Panel de calidad de llamadas o acepte la ubicación predeterminada.
    
5. Seleccione todas las características.
    
6. En la página Configuración de archivo qoE, proporcione la siguiente información:
    
   - **Métricas de QoE SQL Server:** SQL Server de instancia para el lugar donde se encuentra la base de datos de métricas qoE (este será el origen de datos).
    
   - **Nombre de archivo SQL Server QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local. La base de datos de archivo solo se puede instalar en el equipo local.
    
   - **Instancia de archivo SQL Server QoE:** Un nombre SQL Server instancia local para donde se va a crear la base de datos de archivo. Para usar una instancia SQL Server predeterminada, deje este campo en blanco. Para usar una instancia SQL Server nombre, especifique el nombre de instancia (por ejemplo, el nombre después de " \" ).
    
   - **Base de datos de archivos QoE:** De forma predeterminada, esta opción se establece en "Crear nueva base de datos". Dado que no se admite la actualización de la base de datos de archivo, la única circunstancia en la que se puede usar la opción "Usar base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación que se va a instalar.
    
   - **Directorio de archivos de base de datos:** Ruta de acceso a donde deben colocarse los archivos de base de datos (.mdf y .ldf) de la base de datos de archivo. Debe estar en una unidad (HDD2 en la configuración de hardware recomendada) independiente del sistema operativo. Tenga en cuenta que, dado que los nombres de archivo están fijos en la instalación, para evitar posibles conflictos, se recomienda usar un directorio en blanco sin archivos.
    
   - **Usar varias particiones:** El valor predeterminado se establece en "Partición múltiple", que requiere business intelligence edition o enterprise edition de SQL Server. En Standard edition, selecciona la opción "Partición única". Tenga en cuenta que el rendimiento del procesamiento del cubo puede afectarse si se usa una sola partición.
    
     > [!NOTE]
     > La selección de la opción Usar varias particiones no se puede cambiar una vez completada la instalación. Para cambiarla, la característica Cubo debe desinstalarse primero y volver a instalarse con la opción "Cambiar" en el Panel de control. 
  
   - **Directorio de archivos de partición:** Ruta de acceso a donde deben colocarse las particiones de la base de datos de archivos qoE. Debe estar en una unidad (HDD3 en la configuración de hardware recomendada) independiente de la unidad del sistema operativo y de SQL de archivos de registro de base de datos. Tenga en cuenta que, dado que los nombres de archivo están fijos en la instalación, para evitar posibles conflictos, se recomienda usar un directorio en blanco sin archivos.
    
   - **SQL de trabajo del agente: nombre de usuario &amp; Contraseña:** nombre de cuenta de servicio de dominio y contraseña (enmascarada) que se usarán para ejecutar el paso "Datos de archivo qoE" del trabajo del agente de SQL Server (que ejecutará el procedimiento almacenado para capturar datos de la base de datos de métricas de QoE en la base de datos de archivo, por lo que esta cuenta debe tener acceso de lectura a la base de datos de métricas de QoE, tal como se indica en la sección Cuentas. Esta cuenta también debe tener un inicio de sesión en la instancia de QoE Archive SQL Server Instance).
    
     > [!NOTE]
     > La cuenta en la que se ejecuta la instancia de SQL Server, como NT SERVICE\MSSQLSERVER, debe tener acceso o permiso a los directorios anteriores para que la instalación se ejecute correctamente. Para obtener más información, vea [Configure File System Permissions for Database Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. Al hacer clic en siguiente, el instalador realizará comprobaciones de requisitos previos e informe si se encuentra algún problema. Cuando pasen todas las comprobaciones previas, el instalador irá a la página Configuración del cubo. 
    
    > [!NOTE]
    > Si el instalador muestra un mensaje de advertencia de que el servicio de agente de SQL Server para la instancia de QoE Archive SQL Server actualmente no se está ejecutando, la instalación puede continuar, pero después de la instalación, asegúrese de que se está ejecutando el servicio de agente de SQL y establezca el tipo de inicio en Automático para que se ejecute el trabajo programado. 
  
8. En la página Configuración del cubo, proporcione la siguiente información:
    
   - **Nombre de archivo SQL Server QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local. El cubo solo se puede instalar desde la máquina que tiene la base de datos de archivos qoE (nota. El cubo en sí puede instalarse en un equipo remoto. Vea a continuación)
    
   - **Instancia de archivo SQL Server QoE:** SQL Server de instancia para el lugar donde se encuentra la base de datos de archivo qoE. Para especificar una instancia SQL Server predeterminada, deje este campo en blanco. Para especificar una instancia SQL Server nombre, escriba el nombre de instancia (por ejemplo, el nombre después de " \" ). Si se seleccionó el componente de archivo qoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo de QoE.
    
   - **Cube Analysis Server:** SQL Server de instancia de Analysis Service para donde se va a crear el cubo. Puede ser un equipo diferente, pero el usuario de instalación debe ser miembro de los administradores de servidor de la instancia de SQL Server Analysis Service de destino.
    
     > [!NOTE]
     >  Para obtener más información acerca de la configuración de permisos de administrador de Analysis Services Server, vea [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **Usar varias particiones:** El valor predeterminado se establece en "Partición múltiple", que requiere business intelligence edition o enterprise edition de SQL Server. En Standard edition, selecciona la opción "Partición única". Tenga en cuenta que el rendimiento del procesamiento del cubo puede afectar si se usa una sola partición .
    
     > [!NOTE]
     >  La selección de la opción Usar varias particiones no se puede cambiar una vez completada la instalación. Para cambiarla, la característica Cubo debe desinstalarse primero y volver a instalarse con la opción "Cambiar" en el Panel de control.
  
   - **Usuario del cubo: nombre de usuario &amp; Contraseña: nombre** de cuenta de servicio de dominio y contraseña (enmascarada) que desencadenarán el procesamiento del cubo. Si se seleccionó el componente archivo qoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo para el usuario de trabajo del agente de SQL, pero se recomienda especificar una cuenta de servicio de dominio diferente para que el programa de instalación pueda concederle el privilegio menos necesario.
    
9. Al hacer clic en siguiente, se realizará otra ronda de validación y se notifica cualquier problema. Una vez completada correctamente la validación, el instalador irá a la página Configuración del portal. 
    
10. En la página Configuración del portal, proporcione la siguiente información:
    
    - **QoE Archive SQL Server:** SQL Server de instancia para dónde se encuentra la base de datos de archivos qoE. Tenga en cuenta que, a diferencia de la página Configuración de archivo de QoE y la página Configuración del cubo, el nombre de la máquina no es fijo y debe proporcionarse. Si se seleccionó el componente de archivo qoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo de QoE.
    
    - **Cube Analysis Server:** SQL Server de instancia de Analysis Service para el lugar donde se encuentra el cubo. Si se seleccionó el componente Cube para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración del cubo.
    
    - **Repositorio SQL Server:** SQL Server de instancia donde se va a crear la base de datos de repositorio. Si el nombre de instancia de SQL Server donde se encuentra la base de datos de archivos qoE se ha proporcionado anteriormente en la instalación (en otros componentes), este campo se rellenará previamente con el nombre de instancia de archivo de QoE SQL Server instancia. Puede ser cualquier SQL Server instancia.
    
    - **Base de datos de repositorio:** De forma predeterminada, la opción se establece en "Crear nueva base de datos". Dado que no se admite la actualización de base de datos de repositorio, la única circunstancia en la que se puede usar la opción "Usar base de datos existente" es si la base de datos de repositorio existente tiene el mismo esquema que la compilación que se va a instalar.
    
    - **Usuario del grupo de aplicaciones de IIS: nombre de usuario &amp; Contraseña: la** cuenta en la que debe ejecutarse el grupo de aplicaciones de IIS. Los campos Nombre de usuario y Contraseña se atenuarán si se seleccionan cuentas del sistema integradas. Estos campos solo se habilitarán si "Other" está seleccionado en el cuadro desplegable para que el usuario pueda escribir la información de la cuenta de servicio de dominio.
    
11. Al hacer clic en siguiente, se realizará la última ronda de validación para asegurarse de que las instancias SQL Server son accesibles con las credenciales proporcionadas y que IIS está disponible en el equipo. Una vez completada correctamente la validación, el instalador continuará con la instalación. 
    
Cuando el instalador haya terminado, lo más probable es que el trabajo SQL Server agente esté en curso, realizando la carga inicial de los datos de QoE y el procesamiento del cubo. Según la cantidad de datos de QoE, el portal no tendrá datos disponibles para su visualización todavía. Para comprobar el estado de la carga de datos y el procesamiento del cubo, vaya a  `http://<machinename>/CQD/#/Health` . 
> [!NOTE]
> Tenga en cuenta que la dirección URL para comprobar el estado del procesamiento del cubo de descarga distingue mayúsculas de minúsculas. Si escribe "estado", la dirección URL no funcionará. Debe escribir "Estado" al final de la dirección URL con una H mayúscula. 
  
Los mensajes de registro detallados se mostrarán si el modo de depuración está habilitado. Para habilitar el modo de depuración, vaya a **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config** y actualice la siguiente línea para que el valor se establezca en **True**:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Se puede acceder a la página del portal principal a través  `http://<machinename>/CQD` de . 
## <a name="managing-user-access-for-the-portal"></a>Administración del acceso de usuarios para el portal

Para administrar la autorización de usuario en el Portal, se recomienda usar la autorización de dirección URL, que se introdujo en IIS 7.0. Para obtener más información sobre la seguridad de IIS, vea [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Cualquier sitio web o aplicación web hereda la autorización de dirección URL predeterminada configurada para todo IIS, que suele ser "Permitir todos los usuarios". Si el acceso al Portal debe ser más restrictivo, los administradores solo pueden conceder acceso al grupo específico de usuarios editando las "Reglas de autorización".
  
![Implementar calidad de llamadas: reglas de autorización en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> El icono Reglas de autorización no debe confundirse con la "Autorización de.NET" en la sección ASP.NET, que es un mecanismo de autorización diferente. 
  
Los administradores deben quitar primero la regla heredada "Permitir todos los usuarios". Esto impide que los usuarios no autorizados accedan al Portal.
  
![Implementar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
A continuación, los administradores deben agregar nuevas reglas de permiso y conceder a usuarios específicos el permiso para acceder al Portal. Se recomienda crear un grupo local denominado "CQDPortalUsers" para administrar los usuarios.
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Los detalles de configuración se almacenan en el web.config ubicado en el directorio físico del portal.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

El siguiente paso es configurar el panel del CQD. Una vez que IIS autentique a los usuarios, tendrán que tener permisos de archivo en el directorio CQD para tener acceso al contenido del portal web. Es posible cambiar las ACL a través de la pestaña de seguridad de las propiedades del directorio CQD para agregar usuarios o grupos individuales; sin embargo, el enfoque recomendado es dejar los permisos de archivo intactos. En su lugar, cambie la configuración de IIS para usar el proceso de trabajo de IIS para obtener acceso al directorio CQD independientemente del usuario autenticado. 
  
> [!IMPORTANT]
> Es importante cambiar solo esta configuración para la aplicación CQD y no para las dos aplicaciones de API: QoEDataService y QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuración del acceso a archivos para el CQD (panel)

1. Abra el Editor de configuración para CQD.
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. En Sección, elija **system.webServer/serverRuntime**.
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Cambie authenticatedUserOverride a **UseWorkerProcessUser**.
    
     ![Implementar panel de calidad de llamadas: Editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Haga **clic en** Aplicar en el lado derecho de la página.
    
## <a name="known-issues"></a>Problemas conocidos

### <a name="the-cqd-shows-no-data-after-deployment"></a>El CQD no muestra datos después de la implementación

Es posible que reciba el siguiente error:

*No se pudo realizar la consulta mientras se ejecutaba en el cubo. Use el Editor de consultas para modificar la consulta y solucionar cualquier problema. Asegúrese también de que el cubo es accesible.*

Esto significa que el cubo debe procesarse en SQL Server Analysis Services antes de usarse en CQD. Para resolver esto, siga estos pasos:

1. Abra SQL Management Studio y seleccione **Analysis Services**.

2. Expanda el **objeto QoECube,** seleccione **QoE Metric**, haga clic con el botón secundario y, a continuación, elija **Examinar**. 

    Si devuelve el explorador vacío, el cubo aún no se ha realizado.

3. Haga clic con el botón **secundario en Angain métrica qoE** y elija **Procesar**.

4. Cuando se complete el procesamiento, haga clic con el botón secundario en el objeto de nuevo y elija **Examinar** para confirmar que la página del explorador muestra ahora datos. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Los usuarios tienen problemas para iniciar sesión porque el instalador no puede crear la configuración correcta en IIS

En raras ocasiones, el instalador no puede crear la configuración correcta en IIS. El cambio manual es necesario para permitir que los usuarios inicien sesión en el CQD. Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:
  
1. Abra el Administrador de IIS y vaya a Sitio web predeterminado.
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Haga clic en "Autenticación". Si "Autenticación anónima", "suplantación de ASP.NET", "Autenticación de formulario" y "Autenticación de Windows" no coinciden con la configuración que se muestra a continuación, cámbienlas manualmente para que coincidan con la configuración siguiente. Todos los demás mecanismos de autenticación deben deshabilitarse.
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Para "Autenticación de Windows", haz clic en Configuración avanzada en el lado derecho.
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Establezca "Protección extendida" en Aceptar y active la casilla "Habilitar autenticación en modo kernel".
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita los pasos anteriores para cada una de las entradas "CQD", "QoEDataService" y "QoERepositoryService" debajo de "Sitio web predeterminado".
    
Para los enlaces de puerto HTTP y HTTPS, el instalador creará enlaces de puerto en los números de puerto predeterminados (puerto 80 para HTTP y puerto 443 para HTTPS). Si hay otro sitio web en la máquina que usa estos enlaces, habrá un conflicto y no se puede predecir el comportamiento de IIS. La mejor manera de evitar este problema es asegurarse de que ningún otro sitio web esté asignado a los puertos 80 y 443 antes de instalar CQD. 
  
Para habilitar SSL/TLS en IIS y forzar a los usuarios a conectarse a través de HTTPS seguro en lugar de HTTP:
  
1. Configure Secure Sockets Layer in IIS, consulte [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)). Una vez terminado, reemplace  `http` por `https` .
    
2. Para obtener instrucciones sobre cómo habilitar TLS en las conexiones SQL Server, vea [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).
    
## <a name="cube-sync-fails"></a>Error en la sincronización de cubos

QoEMetrics puede contener algunos registros no válidos en función de los relojes del usuario final. Si el sesgo de tiempo es mayor que 60 años, se producirá un error en la importación del cubo.
  
 Comprueba Min y Max StartTime/EndTime con las selecciones siguientes. Busque y elimine registros en el futuro lejano y muy lejano, se pueden ignorar y romperán los procesos de sincronización.
  
- Seleccionar MIN(StartTime) FROM CqdPartitionedStreamView
    
- Seleccionar MAX(StartTime) FROM CqdPartitionedStreamView
    
- Seleccionar MIN(EndTime) FROM CqdPartitionedStreamView
    
- Seleccionar MAX(EndTime) FROM CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tareas posteriores a la instalación

### <a name="importing-buildings-and-networks"></a>Importar edificios y redes

Después de instalar CQD, realice las siguientes tareas de configuración:
  
1. Definir tipos de creación (recomendado)
    
2. Definir tipos de propiedad de edificio (recomendado)
    
3. Definir tipos de red (muy recomendado)
    
4. Importar edificios (recomendado)
    
5. Importar subredes (recomendado)
    
### <a name="define-building-types"></a>Definir tipos de creación

Los tipos de creación se usan para describir las diferentes definiciones o tipos de edificios de la organización. 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Ejemplos
  
- Headquarters
    
- Oficina remota
    
- Ubicación de la empresa conjunta
    
  **Sintaxis SQL ejemplo**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Los parámetros BuildingTypeId y BuildingTypeDesc son necesarios.
  
### <a name="define-building-ownership-types"></a>Definir tipos de propiedad de creación

Los tipos de propiedad se usan para distinguir los activos de propiedad frente a los arrendados.
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Ejemplos
  
- Contoso Leased non-RE &amp; F
    
- Contoso Leased RE &amp; F
    
- Contoso Owned
    
- Subsidiaria arrendada
    
  **Sintaxis SQL ejemplo**
  
```SQL
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

Los parámetros OwnershipTypeId y OwnershipTypeDesc son necesarios. 
  
### <a name="define-network-names"></a>Definir nombres de red

Los tipos de red se usan para describir diferentes tipos de redes dentro de la organización. Esto le permite filtrar (o filtrar) tipos de red específicos.
  
> [!NOTE]
> Se recomienda definir nombres de red, pero es opcional. Si decide no definir nombres de red, asegúrese de que cada entrada CqdNetwork tiene un BuildingId de 0. 
  
Ejemplos
  
- VPN
    
- LAB
    
  **Sintaxis SQL ejemplo**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Los parámetros NetworkNameID y NetworkName son necesarios, el parámetro NetworkType es opcional pero recomendado.
  
### <a name="import-buildings"></a>Importar edificios

Importar edificios le ofrece la capacidad de obtener información específica de la creación (llamadas deficientes por edificio en WiFi/Wired, etc.). 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Antes de importar un nuevo edificio, ya debería tener una buildingKey predefinida identificada. Para ello, emita el comando "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL para identificar el valor actual y agregar 1 al resultado.
  
 **Sintaxis SQL ejemplo**
  
```SQL
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

Los parámetros BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId son necesarios y los demás parámetros son opcionales.
  
### <a name="import-subnets"></a>Importar subredes

Importar edificios le ofrece la capacidad de obtener información específica de la creación (llamadas deficientes por edificio en WiFi/Wired, etc.). 
  
> [!NOTE]
> Este paso es opcional, pero recomendado.
  
Importe subredes y asignelas a los edificios importados en el último paso. Si decidió no rellenar NetworkName, asegúrese de que cada entrada de esta tabla usa un NetworkNameID de 0. Para obtener más información SQL sintaxis y parámetros para el Panel de calidad de llamadas, vea [Use Call Quality Dashboard for Skype for Business Server](./use.md).
  
 **Sintaxis SQL ejemplo**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

Los parámetros Network y UpdatedDate son necesarios, los otros parámetros son opcionales.
  
### <a name="optional-bssid"></a>Opcional: BSSID

Rellenar información BSSID le proporciona una correlación de secuencias WiFi adicional por controlador o radio. Esto se suma al filtrado mediante la creación o subred. 
  
 **Sintaxis SQL ejemplo**
  
```SQL
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

|**Como se muestra en CQD**|**Tabla CQDBssid**|**Entradas de ejemplo**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (debe usar el fformat delimitado)  <br/> |
|Controlador  <br/> |Creación  <br/> |Aruba AP 7  <br/> |
|Dispositivo  <br/> |ess  <br/> |Controlador1  <br/> |
|Radio  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Procesamiento de los datos importados

De forma predeterminada, después de importar datos de creación o red, solo se aplicará a los registros generados después de ese momento. 
  
Para etiquetar todos los registros anteriores con estos nuevos datos, deberá ejecutar el procedimiento almacenado CqdUpdateBuilding como se muestra a continuación: 
  
Déle la fecha del primer registro (identifique que mediante el comando Seleccionar MIN(StartTime) FROM CqdPartitionedStreamView SQL ), un EndDate de mañana y, a continuación, NULL para los dos últimos valores.
  
Una vez que los datos están asociados con datos de secuencia, el cubo SSIS debe volver a procesar todos los registros. Esto también se aplica al agregar datos BSSID/ISP en masa. Asegúrese de que "Process Full" está seleccionado.
