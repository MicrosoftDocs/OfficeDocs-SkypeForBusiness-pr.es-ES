---
title: Implementar el panel de calidad de llamada para Skype para Business Server 2015
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
description: 'Resumen: Información sobre el proceso de implementación para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 0d096ba8c2303ca952100a8142b356944b775dcc
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569190"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a>Implementar el panel de calidad de llamada para Skype para Business Server 2015
 
**Resumen:** Obtenga información sobre el proceso de implementación para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.
  
## <a name="deployment-overview"></a>Introducción a la implementación

Panel de calidad de llamada (CQD) consta de tres componentes principales:
  
- **Base de datos de archivo**, donde se replica y se almacenan los datos de calidad de la experiencia (QoE).
    
- **Cubo**, donde se agregan los datos de la base de datos de archivo de QoE para acceso rápido y optimizado.
    
- **Portal**, donde los usuarios pueden consultar y visualizar los datos de QoE fácilmente.
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
El proceso de instalación para el archivo QoE implica la creación de la base de datos de archivo de QoE, implementación de un procedimiento almacenado de SQL Server que se moverá los datos desde el origen de base de datos de métricas de QoE en QoE Archivar base de datos y configurar el trabajo de agente SQL Server para ejecutar el almacenado procedimiento a intervalos regulares. 
  
Implementación de cubo obtiene información de usuario en donde el archivo QoE se encuentra, implementa el cubo y configura un trabajo del Agente SQL Server regular que se va a actualizar el cubo a intervalos regulares.
  
Instalación del portal crea una base de datos de repositorio que almacena la asignación de usuarios CQD a informes o consultas de cada usuario. A continuación, configura una aplicación web IIS que es el panel donde los usuarios pueden ver un conjunto de informes predefinido, así como personalizar y crear sus propias consultas para visualizar los datos del cubo. La instalación del portal crea dos aplicaciones web adicionales que expone las API para los usuarios a obtener acceso mediante programación el repositorio y el cubo. (Estas API se usan internamente por el tablero de mandos).
  

|**Fase**|**Pasos**|**Roles y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|Instalar software y hardware como requisito previo.  <br/> |Decida en la configuración de CQD y elija un servidor SQL Server desde el que se va a realizar la instalación.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Sección "Pre-requisitos para la instalación" en la documentación de implementación.  <br/> |
|Instalar CQD.  <br/> |Ejecute el MSI siguiendo el documento de implementación.  <br/> |Para realizar la instalación, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo de administradores locales y tener acceso de lectura a la base de datos de métricas de QoE en el servidor de supervisión.  <br/> |Secciones "Las cuentas y los pasos de implementación" en la documentación de implementación.  <br/> |
|Conceder acceso de usuario.  <br/> |Para administrar la autorización de usuario en el Portal, se recomienda utilizar la autorización de dirección URL, que se introdujo en IIS 7.0. Para obtener más información, vea [Autorización de dirección URL de descripción IIS 7.0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Administrar el acceso de usuario para la sección de Portal en la documentación de implementación.  <br/> |
|Opcional: Proporcionar información de asignación de subred.  <br/> |Rellenar la red y las tablas de asignación de creación en la base de datos QoE Archive.  <br/> |Una cuenta con acceso de escritura a la base de datos de archivo de QoE.  <br/> |Sección "Proporcionar información de subred" en la documentación del usuario.  <br/> |
   
## 

La implementación de panel de calidad de llamadas implica la configuración de la infraestructura e instalar el software. El siguiente procedimiento describe el proceso.
  
### <a name="deployment-steps"></a>Pasos de implementación

1. Copie la CallQualityDashboard.msi en el equipo donde se tiene que instalar el componente de base de datos de archivo de CQD (Esto es el equipo que tiene instalado SQL Server). 
    
2. Ejecute el archivo MSI (Windows solicitará ejecutar con privilegios de administrador, hágalo). 
    
3. Acepte al CLUF.
    
4. Seleccione la carpeta de destino donde los archivos relacionados con los componentes del panel de calidad de llamadas se encuentra o acepte la ubicación predeterminada.
    
5. Seleccione todas las características.
    
6. En la página Configuración del archivo de QoE, proporcione la información siguiente:
    
   - **Las métricas de QoE SQL Server:** Nombre de instancia de SQL Server para que se encuentra la base de datos de métricas de QoE (Esto será el origen de datos).
    
   - **Nombre de archivo de QoE SQL Server:** Este es el campo de sólo lectura y se fija en el nombre de dominio completo de la máquina local. Archivo de base de datos puede instalarse solo en la máquina local.
    
   - **Archivo QoE instancia de SQL Server:** Un nombre de la instancia de SQL Server local para donde es la base de datos de archivo que se creará. Para usar una instancia de SQL Server de forma predeterminada, deje este campo en blanco. Para usar una instancia con nombre de SQL Server, especifique el nombre de instancia (por ejemplo, el nombre después de la "\").
    
   - **QoE Archivar base de datos:** De forma predeterminada, esta opción se establece en "Crear nueva base de datos". Dado que no se admite la actualización de base de datos de archivo, el único caso en que se puede usar la opción "Usar la base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación que se van a instalar.
    
   - **Directorio del archivo de base de datos:** Ruta de acceso donde se deben colocar los archivos de base de datos (archivos .mdf y .ldf) para la base de datos de archivo. Esto debe estar en una unidad independiente (HDD2 en la configuración de hardware recomendada) desde el sistema operativo. Tenga en cuenta que dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se utiliza un directorio en blanco con ningún archivo.
    
   - **Usar varias particiones:** El valor predeterminado se establece en "Partición varios", lo cual requiere la edición de inteligencia empresarial o Enterprise edition de SQL Server. Para Standard edition, seleccione la opción de "Única partición". Tenga en cuenta que el rendimiento de procesamiento del cubo puede verse afectado si se usa una única partición.
    
    > [!NOTE]
    > No se puede cambiar la selección para la opción de usar varias particiones una vez finalizada la instalación. Para cambiarlo, el cubo que se necesita la característica a la primera desinstalado y, a continuación, volver a instalar mediante la opción "Cambiar" en el Panel de Control. 
  
   - **Crear particiones de directorio de archivo:** Ruta de acceso donde se deben colocar las particiones de la base de datos de archivo de QoE. Esto debe estar en una unidad independiente (HDD3 en la configuración de hardware recomendada) de la unidad de sistema operativo y la unidad de archivos de registro de base de datos SQL. Tenga en cuenta que dado que los nombres de archivo se corrigen en la instalación, para evitar posibles conflictos, se recomienda que se utiliza un directorio en blanco con ningún archivo.
    
   - **Usuario de trabajo del Agente SQL - nombre de usuario &amp; contraseña:** Nombre de cuenta de servicio de dominio y la contraseña (enmascarado) que se usará para ejecutar el paso de "Datos de archivo QoE" del trabajo de agente SQL Server (que se ejecutará el procedimiento almacenado para recuperar datos la base de datos de métricas de calidad de la experiencia en la base de datos de archivo, por lo que esta cuenta debe tener acceso de lectura a la base de datos de métricas de QoE,  como se indica en la sección cuentas. Esta cuenta también debe tener un inicio de sesión en la instancia de SQL Server de QoE archivo).
    
    > [!NOTE]
    > La cuenta que se está ejecutando la instancia de SQL Server, como NT SERVICE\MSSQLSERVER, debe tener acceso a los directorios indicadas anteriormente para que la instalación se realice correctamente. Para obtener información detallada, vea [Configurar permisos de sistema de archivos para obtener acceso al motor de base de datos](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Tras hacer clic en siguiente, el programa de instalación llevará a cabo comprobaciones de requisitos previos e informe si se producen problemas. Cuando comprobaciones de todas las de requisitos previos paso, el programa de instalación se vaya a la página de configuración de cubo. 
    
    > [!NOTE]
    > Si el programa de instalación muestra un mensaje de advertencia que el servicio Agente SQL Server para la instancia de SQL Server de QoE archivo actualmente no se está ejecutando, puede continuar con la instalación, pero posterior a la instalación por favor, asegúrese de que el servicio del Agente SQL se está ejecutando y establece el tipo de inicio Automática para que se ejecute el trabajo programado. 
  
8. En la página de configuración de cubo, proporcione la información siguiente:
    
   - **Nombre de archivo de QoE SQL Server:** Este es el campo de sólo lectura y se fija en el nombre de dominio completo de la máquina local. Cubo puede instalarse solo desde el equipo que tiene la base de datos de archivo de QoE (tenga en cuenta. Cubo propio puede instalarse en un equipo remoto. Vea más adelante)
    
   - **Archivo QoE instancia de SQL Server:** Nombre de instancia de SQL Server para que se encuentra la base de datos de archivo de QoE. Para especificar una instancia de SQL Server de forma predeterminada, deje este campo en blanco. Para especificar una instancia con nombre de SQL Server, escriba el nombre de instancia (por ejemplo, el nombre después de la "\"). Si el componente de archivo QoE se ha seleccionado para la instalación, este campo estará rellenado previamente con el valor proporcionado en la página Configuración de QoE archiving.
    
   - **Cubos de Analysis Server:** Nombre de instancia de SQL Server Analysis Services para donde es el cubo que se creará. Esto puede ser un equipo diferente, pero el usuario que instala tiene que ser un miembro de los administradores del servidor de la instancia de SQL Server Analysis Services de destino.
    
    > [!NOTE]
    >  Para obtener más información acerca de cómo configurar permisos de administrador del servidor de Analysis Services, vea [Conceder permisos de administrador del servidor (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **Usar varias particiones:** El valor predeterminado se establece en "Partición varios", lo cual requiere la edición de inteligencia empresarial o Enterprise edition de SQL Server. Para Standard edition, seleccione la opción de "Única partición". Tenga en cuenta que el rendimiento de procesamiento del cubo puede verse afectado si se usa una única partición.
    
    > [!NOTE]
    >  No se puede cambiar la selección para la opción de usar varias particiones una vez finalizada la instalación. Para cambiarlo, el cubo que se necesita la característica a la primera desinstalado y, a continuación, volver a instalar mediante la opción "Cambiar" en el Panel de Control.
  
   - **Usuario - nombre de usuario de cubos &amp; contraseña:** Nombre de cuenta de servicio de dominio y contraseña (enmascarado) que se activará el procesamiento del cubo. Si el componente de archiving QoE se ha seleccionado para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo para el usuario de trabajo del Agente SQL, pero se recomienda especificar una cuenta de servicio de dominio diferente para que el programa de instalación puede conceder el privilegios necesarios a ella.
    
9. Al hacer clic en siguiente, se realizará otra ronda de validación y se informará de cualquier problema. Tras completar correctamente la validación, el programa de instalación se vaya a la página de configuración del Portal. 
    
10. En la página Configuración de Portal, proporcione la información siguiente:
    
    - **Archivo QoE SQL Server:** Nombre de instancia de SQL Server para que se encuentra la base de datos de archivo de QoE. Tenga en cuenta que, a diferencia de la página de configuración de archivo de calidad de la experiencia y la página de configuración de cubo, el nombre del equipo no es fijo y se debe proporcionar. Si el componente de archivo QoE se ha seleccionado para la instalación, este campo estará rellenado previamente con el valor proporcionado en la página Configuración de QoE archiving.
    
    - **Cubos de Analysis Server:** Nombre de instancia de SQL Server Analysis Services para que se encuentra el cubo. Si el componente de cubo se ha seleccionado para la instalación, este campo estará rellenado previamente con el valor proporcionado en la página Configuración de cubo.
    
    - **Repositorio SQL Server:** Nombre de instancia de SQL Server donde está la base de datos de repositorio que se creará. Si se ha proporcionado el nombre de instancia de SQL Server para que se encuentra la base de datos de archivo QoE anteriormente en el programa de instalación (en otros componentes), este campo se rellena previamente con el nombre de instancia QoE Archivar base de datos SQL Server. Esto puede ser cualquier instancia de SQL Server.
    
    - **Base de datos de repositorio:** De forma predeterminada, la opción se establece en "Crear nueva base de datos". Dado que no se admite la actualización de base de datos de repositorio, el único caso en que se puede usar la opción "Usar la base de datos existente" es si la base de datos de repositorio existente tiene el mismo esquema que la compilación que se van a instalar.
    
    - **Usuario del grupo de aplicaciones IIS - nombre de usuario &amp; contraseña:** La cuenta que se debe ejecutar en el grupo de aplicaciones de IIS. Los campos nombre de usuario y la contraseña se resaltan en gris si están seleccionadas las cuentas del sistema integrado. Estos campos sólo se habilitará si "Otros" esté activada en el cuadro desplegable para que el usuario puede escribir la información de cuenta de servicio de dominio.
    
11. Al hacer clic en siguiente, se realizará la Ronda final de validación para asegurarse de que las instancias de SQL Server son accesibles utilizando las credenciales proporcionadas y que está disponible en el equipo de IIS. Tras completar correctamente la validación, el instalador continuará con el programa de instalación. 
    
Cuando se realiza el programa de instalación, es muy probable que el trabajo del Agente SQL Server será en curso, realizando la carga inicial de los datos de QoE y el procesamiento del cubo. Dependiendo de la cantidad de datos de QoE, el portal no tendrán datos disponibles para la visualización aún. Para comprobar el estado de la carga de datos y el procesamiento del cubo, vaya a `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Tenga en cuenta que la dirección URL de comprobación del estado de la descarga de procesamiento de cubos distingue mayúsculas de minúsculas. Si escribe 'estado' no funcionan en la dirección URL. Debe escribir 'Estado' al final de la dirección URL con una letra mayúscula H. 
  
Los mensajes de registro detallado se mostrarán si está habilitado el modo de depuración. Para habilitar el modo de depuración, vaya a **%SYSTEMDRIVE%\Program Files\Skype para profesionales de 2015 CQD\QoEDataService\web.config**y actualizar la siguiente línea, por lo que el valor se establece en **True**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La página principal del portal es accesible a través de `http://<machinename>/CQD`. 
## <a name="managing-user-access-for-the-portal"></a>Administrar el acceso de usuario para el Portal

Para administrar la autorización de usuario en el Portal, se recomienda utilizar la autorización de dirección URL, que se introdujo en IIS 7.0. Para obtener más información acerca de la seguridad IIS, vea [Autorización de dirección URL de descripción IIS 7.0 ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Cualquier aplicación web, web o sitio heredan el valor predeterminado configurado para IIS todo, que normalmente es "Permitir que todos los usuarios" de autorización de dirección URL. Si necesita acceso al Portal para que sea más restrictivo, a continuación, los administradores pueden conceder acceso a sólo el grupo específico de usuarios mediante la edición de las reglas de autorización"".
  
![Implementar la calidad de llamadas: reglas de autorización en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> El icono de las reglas de autorización no es debe confundirse con el "autorización de. NET" en la sección ASP.NET, que es un mecanismo de autorización diferentes. 
  
Los administradores deben quitar primero la regla heredado "permitir que todos los usuarios". Esto impide que los usuarios no autorizados acceso al Portal.
  
![Implementar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
A continuación, los administradores deben agregar nuevas reglas permitir y concesión de permiso para obtener acceso al Portal de usuarios específicos. Se recomienda que se ha creado un grupo local denominado "CQDPortalUsers" para administrar los usuarios.
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Los detalles de configuración se almacenan en el archivo web.config que se encuentra en el directorio físico del Portal.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

El siguiente paso es configurar el panel de la CQD. Después de que los usuarios se autentican con IIS, deberá tener permisos de archivo en el directorio CQD con el fin de obtener acceso al contenido del portal web. Es posible cambiar las ACL a través de la ficha seguridad de las propiedades del directorio CQD para agregar usuarios individuales o grupos; Sin embargo, el enfoque recomendado es dejar intactos los permisos de archivo. En su lugar, cambie la configuración de IIS para usar el proceso de trabajo IIS para tener acceso al directorio CQD independientemente del lugar en que se autentica el usuario. 
  
> [!IMPORTANT]
> Es importante sólo cambiar esta configuración para la aplicación de CQD y no para las dos aplicaciones de API: QoEDataService y QoERepositoryService. 
  
### <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configurar el acceso de archivo para el CQD (panel)

1. Abra el Editor de configuración de CQD.
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. En la sección, elija **system.webServer/serverRuntime**.
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Cambie authenticatedUserOverride a **UseWorkerProcessUser**.
    
     ![Implementar el panel de calidad de llamadas: editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Haga clic en **Aplicar** en el lado derecho de la página.
    
## <a name="known-issues"></a>Problemas conocidos

En algunos casos poco frecuentes, el programa de instalación no puede crear la configuración correcta en IIS. Cambio manual se requiere para permitir a los usuarios iniciar sesión en la CQD. Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:
  
1. Abra el Administrador de IIS y navegue al sitio Web predeterminado.
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Haga clic en "Autenticación". Si la "Autenticación anónima", "Suplantación de ASP.NET", "Autenticación basada en formularios" y "Autenticación de Windows" no coincide con la configuración que se muestra a continuación, cámbielos manualmente para que coincida con la siguiente configuración. Se deben deshabilitar todos los otros mecanismos de autenticación.
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Para la "Autenticación de Windows", haga clic en Configuración avanzada en el lado derecho.
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Establezca "Protección ampliada" para aceptar y Active la casilla "autenticación de modo Kernel de habilitar".
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita los pasos anteriores para cada una de las entradas de "CQD", "QoEDataService" y "QoERepositoryService" debajo de "sitio Web predeterminado".
    
Para los enlaces de puerto HTTP y HTTPS, el instalador creará los enlaces de puerto en los números de puerto predeterminado (puerto 80 para HTTP) y el puerto 443 para HTTPS. Si no hay otro sitio Web en el equipo que usa estos enlaces, habrá un conflicto y no se puede predecir el comportamiento IIS. La mejor forma de evitar este problema es asegurarse de que no hay otros sitios Web se asigna a los puertos 80 y 443 antes de instalar CQD. 
  
Para habilitar SSL/TLS en IIS y obligar a los usuarios para conectarse a través de HTTPS seguro en lugar de HTTP:
  
1. Configuración de capa de Sockets seguros en IIS, vea [Configuring Secure Sockets Layer en IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Una vez hecho, reemplace `http` con `https`.
    
2. Para obtener instrucciones acerca de cómo habilitar TLS en las conexiones de SQL Server, vea [cómo habilitar el cifrado SSL para una instancia de SQL Server mediante el uso de Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).
    
### <a name="cube-sync-fails"></a>Error de sincronización de cubo

QoEMetrics puede contener algunos registros no válidos en función de los relojes de usuario final. Si el tiempo sesgado es mayor que 60 años, se producirá un error en la importación de cubo.
  
 Compruebe el Min y Max StartTime y EndTime mediante las siguientes selecciones. Buscar y eliminar registros en el futuro últimos mucho y muy lejano, puede ignorarse e interrumpirá la seguridad de los procesos de sincronización.
  
- Seleccione MIN(StartTime) desde CqdPartitionedStreamView
    
- Seleccione MAX(StartTime) desde CqdPartitionedStreamView
    
- Seleccione MIN(EndTime) desde CqdPartitionedStreamView
    
- Seleccione MAX(EndTime) desde CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tareas posteriores a la instalación

### <a name="importing-buildings-and-networks"></a>Importación de los edificios y las redes

Después de instalar CQD, realice las siguientes tareas de configuración:
  
1. Definir tipos de creación (recomendados)
    
2. Definir tipos de propiedad de creación (recomendados)
    
3. Definir tipos de redes (altamente recomendados)
    
4. Los edificios de importación (recomendado)
    
5. Subredes de importación (recomendadas)
    
### <a name="define-building-types"></a>Definir tipos de creación

Tipos de creación se utilizan para describir las definiciones de diferentes edificios o tipos de dentro de la organización. 
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Ejemplos
  
- Sede central
    
- Remoto de Office
    
- Ubicación de participación
    
 **Sintaxis SQL de ejemplo**
  
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
  
### <a name="define-building-ownership-types"></a>Definir tipos de propiedad de creación

Tipos de propiedad se usan para distinguir vs perteneciente cedida activos.
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Ejemplos
  
- Concesión de Contoso que no sean-RE&amp;F
    
- Contoso conexión alquilada RE&amp;F
    
- Contoso que pertenecen
    
- Subsidiaria concedida
    
 **Sintaxis SQL de ejemplo**
  
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
  
### <a name="define-network-names"></a>Definir los nombres de red

Tipos de redes se utilizan para describir los diversos tipos de redes dentro de la organización. Esto le ofrece la capacidad de filtrar en (o filtrar) tipos específicos de red.
  
> [!NOTE]
> Se recomienda para definir los nombres de red, pero es opcional. Si decide no definir los nombres de red, asegúrese de que cada entrada de CqdNetwork tiene un BuildingId de 0. 
  
Ejemplos
  
- VPN
    
- LABORATORIO
    
 **Sintaxis SQL de ejemplo**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Los parámetros NetworkNameID y NetworkName son necesarios, el parámetro NetworkType es opcional pero recomendado.
  
### <a name="import-buildings"></a>Los edificios de importación

Importación de edificios le ofrece la posibilidad de obtener creación de conocimientos específicos (llamadas deficientes por a partir de WiFi o con cable, etcetera.). 
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Antes de importar un nuevo edificio debe tener un BuildingKey predefinido identificado. Para ello, ejecute el comando "Seleccione MAX(BuildingKey) desde CqdBuilding" SQL para identificar el valor actual y agregar 1 para el resultado.
  
 **Sintaxis SQL de ejemplo**
  
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

El BuildingKey, nombredeedificio, BuildingShortName, OwnershipTypeId, se requieren los parámetros BuildingTypeId, los demás parámetros son opcionales.
  
### <a name="import-subnets"></a>Importar subredes

Importación de edificios le ofrece la posibilidad de obtener creación de conocimientos específicos (llamadas deficientes por a partir de WiFi o con cable, etcetera.). 
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Importar subredes y asignarlos a los edificios importados en el último paso. Si ha decidido no rellenar NetworkName, asegúrese de que cada entrada en la tabla siguiente usa un NetworkNameID de 0.
  
 **Sintaxis SQL de ejemplo**
  
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

La red y se requieren los parámetros UpdatedDate, los demás parámetros son opcionales.
  
### <a name="optional-bssid"></a>Opcional: BSSID

Rellenar información BSSID proporciona correlación de secuencia WiFi adicional por controlador o radio. Esto es además de filtrar por crear o subred. 
  
 **Sintaxis SQL de ejemplo**
  
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
|AP NName  <br/> |PUNTO DE ACCESO  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (debe utilizar el formato delimitado)  <br/> |
|Controlador de  <br/> |Building  <br/> |AP Aruba 7  <br/> |
|Dispositivo  <br/> |ess  <br/> |Controlador1  <br/> |
|Radio  <br/> |phy  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Procesamiento de los datos importados

De forma predeterminada, después de importar datos de creación/red se aplicará sólo a registros generados después de ese punto en el tiempo. 
  
Para marcar todos los registros anteriores con estos nuevos datos, debe ejecutar el procedimiento almacenado de CqdUpdateBuilding tal y como se muestra a continuación: 
  
Asígnele la fecha de su primer registro (identificar que con el comando Seleccionar MIN(StartTime) desde CqdPartitionedStreamView SQL), una fecha de finalización de la mañana, a continuación, en NULL para los dos últimos valores.
  
Una vez que los datos se asocian con los datos de la secuencia, se necesita el cubo de SSIS para volver a procesar todos los registros. Esto también aplica cuando masiva agregar datos BSSID-ISP. Asegúrese de que esté seleccionado "Proceso completo".
  

