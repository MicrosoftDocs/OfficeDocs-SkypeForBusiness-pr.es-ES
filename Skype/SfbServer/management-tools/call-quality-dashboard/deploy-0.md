---
title: Implementar panel de calidad de la llamada de Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumen: Conozca el proceso de implementación para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: ff8f9bae2c292720bb3fd9943bc541a8eeb6759c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a>Implementar panel de calidad de la llamada de Skype para Business Server 2015
 
**Resumen:** Conozca el proceso de implementación para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
## <a name="deployment-overview"></a>Introducción a la implementación

Panel de calidad de llamada (CQD) consta de tres componentes principales:
  
- **Base de datos de archivo**, donde se replica y se almacenan los datos de la calidad de la experiencia (QoE).
    
- **Cubo**, donde se agregan los datos de base de datos de archivo de calidad para acceso rápido y optimizado.
    
- **Portal**, donde los usuarios pueden consultar y visualizar datos QoE fácilmente.
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
El proceso de instalación para el archivo QoE implica la creación de la base de datos de archivo de calidad de la experiencia, implementar un procedimiento de SQL Server almacenan que moverá los datos desde el origen de base de datos de métricas de calidad de la experiencia en base de datos de archivo de calidad de la experiencia y configurar el trabajo de agente de SQL Server para ejecutar el almacenado procedimiento a intervalos regulares. 
  
Implementación del cubo obtiene información del usuario en donde el archivo QoE se encuentra, implementa el cubo y configura un trabajo del Agente SQL Server normal que actualice el cubo a intervalos regulares.
  
Instalar portal crea una base de datos que almacena la asignación de usuarios CQD, informes y consultas de cada usuario. A continuación, configura una aplicación web IIS que es el panel donde los usuarios pueden ver un conjunto de informes predefinido, así como personalizar y crear sus propias consultas para visualizar los datos del cubo. La instalación del portal crea dos aplicaciones web adicionales que expone las API para que los usuarios obtener acceso mediante programación al repositorio y el cubo. (Estas API se utilizan internamente por el tablero de mandos).
  

|**Fase**|**Pasos**|**Funciones y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|Instalar software y hardware necesario.  <br/> |Decida la configuración CQD y elija un SQL Server desde el que se va a realizar la instalación.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Sección "Previamente instalar requisitos" en la documentación de implementación.  <br/> |
|Instalar CQD.  <br/> |Ejecute el MSI siguiendo el documento de implementación.  <br/> |Para realizar la instalación, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo local Administradores y tener acceso de lectura a la base de datos de métricas de calidad en el servidor de supervisión.  <br/> |Secciones "Cuentas y pasos de implementación" en la documentación de implementación.  <br/> |
|Conceder acceso de usuario.  <br/> |Para administrar la autorización del usuario en el Portal, se recomienda utilizar la autorización de direcciones URL, que se introdujo en IIS 7.0. Para obtener más información, vea [Autorización de direcciones URL de descripción IIS 7.0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Administrar el acceso de usuario a la sección de Portal en la documentación de implementación.  <br/> |
|Opcional: Proporcionar la información de asignación de subred.  <br/> |Llenar tablas de asignación de creación de base de datos de archivo de calidad y de red.  <br/> |Una cuenta con acceso de escritura a la base de datos de archivo de calidad.  <br/> |Sección "Proporcionar información de subred" en la documentación del usuario.  <br/> |
   
## 

Implementación de llamar al panel de calidad implica configurar la infraestructura e instalar el software. El siguiente procedimiento describe el proceso.
  
### <a name="deployment-steps"></a>Pasos de implementación

1. Copie el CallQualityDashboard.msi en el equipo donde el componente de base de datos de archivo de CQD debe ser instalado (es decir, el equipo que tiene SQL Server instalado). 
    
2. Ejecute el archivo MSI (Windows le pedirá que se ejecutan con privilegios de administrador, hágalo). 
    
3. Aceptar al CLUF.
    
4. Seleccione la carpeta de destino donde se encuentra o acepte la ubicación predeterminada archivos relacionados con componentes de panel de calidad llamar.
    
5. Seleccione todas las funciones.
    
6. En la página Configuración de archiving QoE, proporcione la siguiente información:
    
   - **De SQL Server de métricas de calidad:** Nombre de la instancia de SQL Server de donde se encuentra la base de datos de métricas de calidad (Esto será el origen de datos).
    
   - **Archivo QoE SQL Server nombre:** Esto es el campo de sólo lectura y se fija como el nombre de dominio completo del equipo local. Archivo DB puede instalarse sólo en el equipo local.
    
   - **Archivo QoE SQL Server instancia:** Un nombre de instancia de SQL Server local para que la base de datos de archivo debe ser creado. Para utilizar una instancia predeterminada de SQL Server, deje este campo en blanco. Para utilizar una instancia con nombre de SQL Server, especifique el nombre de instancia (por ejemplo, el nombre después de la "\").
    
   - **QoE Archivar base de datos:** De forma predeterminada, esta opción se establece en "Crear nueva base de datos". Dado que no se admite la actualización de archivo DB, la única circunstancia en que puede utilizarse la opción "Usar la base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación para instalarse.
    
   - **Directorio del archivo de base de datos:** Ruta de acceso donde se colocarán los archivos de base de datos (.mdf y .ldf) de la base de datos de archivo. Esto debe estar en una unidad independiente (HDD2 en la configuración de hardware recomendada) desde el sistema operativo. Tenga en cuenta que dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se utilice un directorio no tiene archivos en blanco.
    
   - **Utilizar varias particiones:** El valor predeterminado se establece en "Partición múltiples", que no requiere edición Business Intelligence o Enterprise edition de SQL Server. Para Standard edition, seleccione la opción de "Partición única". Tenga en cuenta que el rendimiento de procesamiento del cubo puede verse afectado si se utiliza una única partición.
    
    > [!NOTE]
    > No se puede cambiar la selección de la opción de usar varias particiones una vez finalizada la instalación. Para cambiarlo, el cubo característica debe ser la primera desinstala y vuelve a instalar utilizando la opción "Cambiar" Panel de Control. 
  
   - **Crear particiones de directorio de archivo:** Ruta de acceso que se deben colocar las particiones de la base de datos de archivo de calidad. Esto debe estar en una unidad independiente (HDD3 en la configuración de hardware recomendada) de la unidad de sistema operativo y la unidad de archivos de registro de base de datos SQL. Tenga en cuenta que dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se utilice un directorio no tiene archivos en blanco.
    
   - **Usuario de trabajo del Agente SQL - nombre de usuario &amp; contraseña:** Nombre de cuenta de servicio de dominio y la contraseña (máscara) que se utilizará para ejecutar el paso de "Datos de archivo de la calidad" del trabajo del agente de SQL Server (que se ejecutará el procedimiento almacenado para recuperar datos la base de datos de métricas de calidad de la experiencia en archivo DB, por lo que esta cuenta debe tener acceso de lectura a DB de métricas de calidad,  como se indica en la sección de cuentas. Esta cuenta debe tener también un inicio de sesión en la instancia de SQL Server de QoE Archive).
    
    > [!NOTE]
    > La cuenta que se está ejecutando la instancia de SQL Server, como SERVICE\MSSQLSERVER de NT, debe tener acceso a los directorios mencionados para que la instalación se realice correctamente. Para obtener información detallada, vea [Configurar permisos de sistema de archivos para obtener acceso al motor de base de datos](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Al hacer clic en siguiente, el programa de instalación llevará a cabo comprobaciones de requisitos previos e informe si se produjeran problemas. Cuando comprueba todo son un requisito previo paso, el programa de instalación se vaya a la página de configuración de cubo. 
    
    > [!NOTE]
    > Si el programa de instalación muestra un mensaje de advertencia que el servicio Agente de SQL Server para la instancia de SQL Server archivo QoE no se está ejecutando actualmente, la instalación puede continuar, pero posterior a la instalación, asegúrese que el servicio Agente SQL está ejecutando y establece el tipo de inicio en Automática para que se ejecute la tarea programada. 
  
8. En la página de configuración de cubo, proporcione la siguiente información:
    
   - **Archivo QoE SQL Server nombre:** Esto es el campo de sólo lectura y se fija como el nombre de dominio completo del equipo local. Cubo puede instalarse sólo desde el equipo que tiene la base de datos de archivo de calidad (Nota. Cubo puede instalarse en un equipo remoto. Vea a continuación)
    
   - **Archivo QoE SQL Server instancia:** Nombre de la instancia de SQL Server de donde se encuentra la base de datos de archivo QoE. Para especificar una instancia de SQL Server predeterminada, deje este campo en blanco. Para especificar una instancia con nombre de SQL Server, escriba el nombre de instancia (por ejemplo, el nombre después de la "\"). Si el componente de archiving QoE fue seleccionado para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archiving QoE.
    
   - **De cubo Analysis Server:** Nombre de la instancia de SQL Server Analysis Services para donde es necesario crear el cubo. Esto puede ser un equipo diferente, pero el usuario que instala debe ser un miembro del grupo Administradores de servidor de la instancia de Analysis Services de SQL Server de destino.
    
    > [!NOTE]
    >  Para obtener más información acerca de cómo configurar permisos de administrador de servidor de servicios de análisis, vea [Conceder permisos de administrador del servidor (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **Utilizar varias particiones:** El valor predeterminado se establece en "Partición múltiples", que no requiere edición Business Intelligence o Enterprise edition de SQL Server. Para Standard edition, seleccione la opción de "Partición única". Tenga en cuenta que el rendimiento de procesamiento del cubo puede verse afectado si se utiliza una única partición.
    
    > [!NOTE]
    >  No se puede cambiar la selección de la opción de usar varias particiones una vez finalizada la instalación. Para cambiarlo, el cubo característica debe ser la primera desinstala y vuelve a instalar utilizando la opción "Cambiar" Panel de Control.
  
   - **Usuario - nombre de usuario de cubo &amp; contraseña:** Nombre de cuenta de servicio de dominio y una contraseña (máscara) que desencadene el procesamiento del cubo. Si el componente de archiving QoE fue seleccionado para la instalación, este campo se rellenará previamente con el valor proporcionado en la página de configuración de archivo para el usuario de trabajo del Agente SQL, pero es recomendable que especifique una cuenta de servicio de dominio diferente para que el programa de instalación puede conceder la privilegios necesarios mínimos a él.
    
9. Al hacer clic en siguiente, se realizará otra ronda de validación y notificará cualquier problema. Tras completar correctamente la validación, el instalador se vaya a la página de configuración del Portal. 
    
10. En la página Configuración de Portal, proporcione la siguiente información:
    
    - **Archivo QoE SQL Server:** Nombre de la instancia de SQL Server de donde se encuentra la base de datos de archivo de calidad. Tenga en cuenta que, a diferencia de la página de configuración de archivo de calidad de la experiencia y la página de configuración de cubo, el nombre del equipo no es fijo y se debe proporcionar. Si el componente de archiving QoE fue seleccionado para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archiving QoE.
    
    - **De cubo Analysis Server:** Nombre de la instancia de SQL Server Analysis Services para donde se encuentra el cubo. Si se selecciona el componente de cubo para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de cubo.
    
    - **Repositorio de SQL Server:** Donde es la base de datos de repositorio que se cree el nombre de la instancia de SQL Server. Si se ha proporcionado el nombre de la instancia de SQL Server de donde se encuentra la base de datos de archivo QoE anteriormente en el programa de instalación (en otros componentes), este campo se rellenará previamente con el nombre de instancia QoE archivo base de datos SQL Server. Puede tratarse de cualquier instancia de SQL Server.
    
    - **Base de datos de repositorio:** De forma predeterminada la opción se establece en "Crear nueva base de datos". Dado que no se admite la actualización de la base de datos de repositorio, la única circunstancia en que puede utilizarse la opción "Usar la base de datos existente" es si la base de datos de repositorio existente tiene el mismo esquema que la compilación para instalarse.
    
    - **Grupo de aplicaciones IIS usuario - nombre de usuario &amp; contraseña:** La cuenta que se debe ejecutar en el grupo de aplicaciones IIS. Los campos nombre de usuario y la contraseña aparecerá atenuados si se seleccionan las cuentas del sistema integrado. Estos campos sólo se habilitará si "Otros" está seleccionada en el cuadro desplegable para que el usuario puede escribir la información de cuenta de servicio de dominio.
    
11. Al hacer clic en siguiente, se realizará la Ronda final de validación para asegurarse de que las instancias de SQL Server son accesibles mediante las credenciales proporcionadas y que está disponible en el equipo IIS. Tras completar correctamente la validación, el programa de instalación continuará con la instalación. 
    
Cuando el instalador haya finalizado, más probable es que el trabajo del agente de SQL Server será en curso, realizando la carga inicial de los datos de la calidad y el procesamiento del cubo. Dependiendo de la cantidad de datos de calidad, el portal no tendrá datos disponibles para su visualización aún. Para comprobar el estado de la carga de datos y el procesamiento del cubo, vaya a `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Tenga en cuenta que la dirección URL para comprobar el estado de la descarga de procesamiento de cubos distingue mayúsculas de minúsculas. Si escribe la dirección URL no funciona ' estado'. Debe especificar 'Estado' al final de la dirección URL con una mayúscula H. 
  
Mensajes de registro detallado se mostrará si está habilitado el modo de depuración. Para habilitar el modo de depuración, vaya a **%SYSTEMDRIVE%\Program Files\Skype para negocios 2015 CQD\QoEDataService\web.config**y actualizar la siguiente línea, por lo que el valor se establece en **True**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Es accesible a través de la página principal del portal `http://<machinename>/CQD`. 
## <a name="managing-user-access-for-the-portal"></a>Administración del acceso de usuario para el Portal

Para administrar la autorización del usuario en el Portal, se recomienda utilizar la autorización de direcciones URL, que se introdujo en IIS 7.0. Para obtener más información acerca de la seguridad IIS, vea [Autorización de direcciones URL de descripción IIS 7.0 ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Cualquier aplicación de web o sitio web heredan el valor predeterminado configurado para todo IIS, que normalmente es "Permitir que todos los usuarios" de autorización de direcciones URL. Si necesita acceso al Portal para que sea más restrictivo, a continuación, los administradores pueden conceder acceso a sólo el grupo de usuarios específico mediante la modificación de las reglas de autorización"".
  
![Implementar la calidad de llamadas: reglas de autorización en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> El icono de las reglas de autorización no es se debe confundir con la "autorización. NET" en la sección ASP.NET, que es un mecanismo de autorización diferente. 
  
Los administradores deben quitar primero la regla heredada "permitir que todos los usuarios". Esto impide que los usuarios no autorizados accedan al Portal.
  
![Implementar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
A continuación, los administradores deben agregar nuevas reglas permitir y conceder el permiso para acceder al Portal de usuarios específicos. Se recomienda que un grupo local llamado "CQDPortalUsers" se crea para administrar los usuarios.
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Los detalles de configuración se almacenan en el archivo web.config ubicado en el directorio físico del Portal.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

El siguiente paso es configurar el panel de la CQD. Después de que IIS autentica a los usuarios, deberán tener permisos de archivo en el directorio CQD para acceder al contenido de portal web. Es posible cambiar las ACL a través de la ficha de seguridad de las propiedades del directorio CQD para agregar usuarios individuales o grupos; Sin embargo, el enfoque recomendado es dejar intactos los permisos de archivo. En su lugar, cambie la configuración de IIS para utilizar el proceso de trabajo IIS para tener acceso al directorio CQD, independientemente de que el usuario está autenticado. 
  
> [!IMPORTANT]
> Es importante que sólo cambiar esta configuración para la aplicación de CQD y no para las dos aplicaciones API: QoEDataService y QoERepositoryService. 
  
### <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuración de acceso de archivo para el CQD (escritorio)

1. Abra el Editor de configuración para CQD.
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. En la sección, elija **system.webServer/serverRuntime**.
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Cambie authenticatedUserOverride a **UseWorkerProcessUser**.
    
     ![Implementar el panel de calidad de llamadas: editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Haga clic en **Aplicar** en el lado derecho de la página.
    
## <a name="known-issues"></a>Problemas conocidos

En raras ocasiones, el programa de instalación no puede crear la configuración correcta en IIS. Cambio manual es necesaria para permitir a los usuarios iniciar sesión en el CQD. Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:
  
1. Abra el Administrador de IIS y vaya al sitio Web predeterminado.
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Haga clic en "Autenticación". Si la "Autenticación anónima", "Suplantación de ASP.NET", "Autenticación mediante formularios" y "Autenticación de Windows" no coincide con la mostrada a continuación, cámbielos manualmente para que coincida con la siguiente configuración. Todos los otros mecanismos de autenticación deben estar deshabilitadas.
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. "Autenticación de Windows", haga clic en Configuración avanzada en el lado derecho.
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Establecer "Protección ampliada" para aceptar y Active la casilla de "autenticación de modo Kernel habilitar".
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita los pasos anteriores para cada una de las entradas de "CQD", "QoEDataService" y "QoERepositoryService" debajo de "sitio Web predeterminado".
    
Para los enlaces de puerto HTTP y HTTPS, el instalador creará enlaces de puertos en los números de puerto predeterminado (puerto 80 para HTTP) y el puerto 443 para HTTPS. Si hay otro sitio Web en el equipo que utiliza estos enlaces, habrá un conflicto y no se puede predecir el comportamiento IIS. La mejor manera de evitar este problema es asegurarse de que no hay otros sitios Web se asigna a los puertos 80 y 443 antes de instalar CQD. 
  
Para habilitar SSL/TLS en IIS y obligar a los usuarios conectarse a través de HTTPS seguro en lugar de HTTP:
  
1. Configurar Secure Sockets Layer en IIS, vea [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Una vez hecho esto, reemplace `http` con `https`.
    
2. Para obtener instrucciones acerca de cómo habilitar TLS en las conexiones de SQL Server, vea [cómo habilitar el cifrado SSL para una instancia de SQL Server utilizando Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).
    
### <a name="cube-sync-fails"></a>Error de sincronización de cubo

QoEMetrics puede contener algunos registros no válidos tomando como base los relojes del usuario final. Si el desfase temporal es mayor que 60 años, se producirá un error en la importación de cubo.
  
 Compruebe el Min y Max StartTime y EndTime mediante las siguientes selecciones. Buscar y eliminar registros en el futuro ahora, pasado y muy distante, puede tenerse y se romperán los procesos de sincronización.
  
- Seleccione MIN(StartTime) de CqdPartitionedStreamView
    
- Seleccione MAX(StartTime) de CqdPartitionedStreamView
    
- Seleccione MIN(EndTime) de CqdPartitionedStreamView
    
- Seleccione MAX(EndTime) de CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tareas posteriores a la instalación

### <a name="importing-buildings-and-networks"></a>Importación de edificios y redes

Después de instalar CQD, realice las siguientes tareas de configuración:
  
1. Definir tipos de edificio (recomendados)
    
2. Definir los tipos de propiedad del edificio (recomendados)
    
3. Definir los tipos de red (altamente recomendados)
    
4. Edificios de importación (recomendado)
    
5. Subredes de importación (recomendadas)
    
### <a name="define-building-types"></a>Definir tipos de edificios

Tipos de construcción se utilizan para describir las definiciones de diferentes edificios o tipos dentro de su organización. 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Ejemplos
  
- Sede central
    
- Oficina remota
    
- Ubicación de la empresa conjunta
    
 **Sintaxis de SQL de ejemplo**
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters') 
  
```

Los parámetros BuildingTypeId y BuildingTypeDesc son necesarios.
  
### <a name="define-building-ownership-types"></a>Definir los tipos de propiedad de edificio

Tipos de propiedad se utilizan para distinguir los activos arrendados propietario vs.
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Ejemplos
  
- Contoso arrendado no-RE&amp;F
    
- Contoso arrendado RE&amp;F
    
- Propiedad de Contoso
    
- Filial arrendado
    
 **Sintaxis de SQL de ejemplo**
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

Los parámetros OwnershipTypeId y OwnershipTypeDesc son necesarios. 
  
### <a name="define-network-names"></a>Definir nombres de red

Tipos de red se utilizan para describir los diferentes tipos de redes en la organización. Esto le da la capacidad de filtrar (o filtrar) los tipos de red específicos.
  
> [!NOTE]
> Se recomienda definir los nombres de red, pero es opcional. Si decide no definir nombres de red, asegúrese de que cada entrada de CqdNetwork tiene un BuildingId de 0. 
  
Ejemplos
  
- VPN
    
- LABORATORIO
    
 **Sintaxis de SQL de ejemplo**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Los parámetros NetworkNameID y NetworkName son necesarios, el parámetro NetworkType es opcional pero se recomienda.
  
### <a name="import-buildings"></a>Edificios de importación

Importación de edificios permite obtener creación de conocimientos específicos (llamadas deficientes por edificio en WiFi o por cable, etcetera.). 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Antes de importar un edificio nuevo ya debería tener un BuildingKey predefinido identificado. Para ello, ejecute el comando "Seleccionar MAX(BuildingKey) de CqdBuilding" SQL para identificar el valor actual y agregar 1 al resultado.
  
 **Sintaxis de SQL de ejemplo**
  
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

El BuildingKey, nombredeedificio, BuildingShortName, OwnershipTypeId, se requieren los parámetros BuildingTypeId, los otros parámetros son opcionales.
  
### <a name="import-subnets"></a>Importar subredes

Importación de edificios permite obtener creación de conocimientos específicos (llamadas deficientes por edificio en WiFi o por cable, etcetera.). 
  
> [!NOTE]
> Este paso es opcional, pero recomendado. 
  
Importar subredes y asignarlos a los edificios importados en el último paso. Si ha decidido no llenar NetworkName, asegúrese de que cada entrada en esta tabla utiliza un NetworkNameID de 0.
  
 **Sintaxis de SQL de ejemplo**
  
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

La red y se requieren parámetros de UpdatedDate, los otros parámetros son opcionales.
  
### <a name="optional-bssid"></a>Opcional: BSSID

Rellenar información de BSSID proporciona correlación de secuencia WiFi adicional por el regulador o el radio. Se trata además de filtrar por edificio o subred. 
  
 **Sintaxis de SQL de ejemplo**
  
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

|**Como se muestra en CQD**|**Tabla CQDBssid**|**Entradas de ejemplo**|
|:-----|:-----|:-----|
|AP NName  <br/> |PA  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (debe utilizar el formato delimitado)  <br/> |
|Controlador  <br/> |Building  <br/> |Aruba PA 7  <br/> |
|Dispositivo  <br/> |ess  <br/> |Controlador1  <br/> |
|Radio  <br/> |phy  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Procesamiento de los datos importados

De forma predeterminada, después de importar datos de construcción/red se aplicarán sólo a los registros generados después de que el punto en el tiempo. 
  
Para etiquetar todos los registros anteriores con estos nuevos datos, debe ejecutar el procedimiento almacenado de CqdUpdateBuilding como se muestra a continuación: 
  
Dar la fecha de su primer registro (identificar que con el comando Seleccionar MIN(StartTime) de SQL de CqdPartitionedStreamView), un EndDate del mañana, NULL para los dos últimos valores.
  
Una vez que los datos están asociados con los datos de la secuencia, el cubo de SSIS debe volver a procesar todos los registros. Esto aplica también cuando masiva agregar datos BSSID-ISP. Asegúrese de que está seleccionado "Proceso completo".
  

