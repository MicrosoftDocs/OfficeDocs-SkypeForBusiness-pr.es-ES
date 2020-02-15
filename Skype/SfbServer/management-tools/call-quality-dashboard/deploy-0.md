---
title: Implementar el panel de calidad de llamadas para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumen: Obtenga información sobre el proceso de implementación del panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta de Skype empresarial Server.'
ms.openlocfilehash: d42d735ab5a60ec02ad2e1f4f696908996457c0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042267"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Implementar el panel de calidad de llamadas para Skype empresarial Server
 
**Resumen:** Obtenga información sobre el proceso de implementación del panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta de Skype empresarial Server.
  
## <a name="deployment-overview"></a>Vista general de implementación

El panel de calidad de llamadas (CQD) consta de tres componentes principales:
  
- **Base**de datos de archivo, donde se replican y almacenan los datos de calidad de la experiencia (QoE).
    
- **Cube**, donde los datos de la base de datos de archivo de QoE se agregan para un acceso optimizado y rápido.
    
- **Portal**, donde los usuarios pueden consultar y visualizar fácilmente los datos de QoE.
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
El proceso de configuración para el archivo QoE implica la creación de la base de datos de archivo de QoE, la implementación de un procedimiento almacenado de SQL Server que moverá los datos de la base de datos de QoE de origen a la base de datos de archivo de QoE y la configuración del trabajo del Agente SQL Server para ejecutar el procedimiento a intervalos regulares. 
  
La implementación del cubo recibe información del usuario en el lugar en el que se encuentra el archivo de QoE, implementa el cubo y configura un trabajo del Agente SQL Server normal que actualizará el cubo a intervalos regulares.
  
La instalación del portal crea una base de datos del repositorio que almacena la asignación de usuarios del CQD para cada uno de los informes y consultas de cada usuario. A continuación, se configura una aplicación Web de IIS, que es el panel donde los usuarios pueden ver un conjunto predefinido de informes, así como personalizar y crear sus propias consultas para visualizar datos del cubo. La instalación del portal crea dos aplicaciones web adicionales que exponen las API para que los usuarios obtengan acceso mediante programación al repositorio y al cubo. (El panel también usa internamente estas API).
  

|**Fase**|**Pasos**|**Roles y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|Instale los requisitos previos de hardware y software.  <br/> |Decida la configuración del CQD y elija un servidor SQL Server desde el que se va a realizar la instalación.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Sección "requisitos previos a la instalación" en la documentación sobre implementación.  <br/> |
|Instale el CQD.  <br/> |Ejecute el MSI siguiendo el documento de implementación.  <br/> |Para realizar la configuración, la cuenta de instalación debe ser un usuario de dominio que sea miembro del grupo de administradores locales y tener acceso de lectura a la base de datos de QoE Metrics en el servidor de supervisión.  <br/> |Secciones "cuentas y pasos de implementación" en la documentación de implementación.  <br/> |
|Conceder acceso al usuario.  <br/> |Para administrar la autorización del usuario en el portal, se recomienda usar la autorización de dirección URL, que se introdujo en IIS 7,0. Para obtener más información, consulte [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |Administración del acceso de usuarios para la sección del portal en la documentación sobre implementación.  <br/> |
|Opcional: proporcionar información de asignación de subred.  <br/> |Rellene la red y cree tablas de asignación en la base de datos de archivo de QoE.  <br/> |Una cuenta con acceso de escritura a la base de datos de archivo de QoE.  <br/> |Sección "suministrar información de subred" en la documentación del usuario.  <br/> |
   


La implementación del panel de calidad de llamadas implica la configuración de la infraestructura y la instalación del software. El siguiente procedimiento describe el proceso.
  
## <a name="deployment-steps"></a>Pasos de implementación

1. Copie CallQualityDashboard. msi en el equipo en el que se instalará el componente de base de datos de archivo del CQD (es decir, el equipo que tiene instalado SQL Server). 
    
2. Ejecute el MSI (Windows le pedirá que se ejecute con privilegio de administrador, etc.). 
    
3. Acepte el CLUF.
    
4. Seleccione la carpeta de destino en la que se ubicarán los archivos relacionados con los componentes del panel de calidad de llamadas o aceptará la ubicación predeterminada.
    
5. Seleccione todas las características.
    
6. En la página Configuración del archivo de QoE, proporcione la siguiente información:
    
   - **SQL Server de las métricas de QoE:** Nombre de instancia de SQL Server en el que se encuentra la base de datos de calidad de la QoE (este será el origen de datos).
    
   - **Nombre del servidor SQL del archivo QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local. La base de datos de archivo solo puede instalarse en el equipo local.
    
   - **Instancia de archivo de SQL Server de QoE:** Un nombre de instancia local de SQL Server en el que se creará la base de datos de archivo. Para usar una instancia predeterminada de SQL Server, deje este campo en blanco. Para usar una instancia de SQL Server con nombre, especifique el nombre de la instancia (por ejemplo,\"el nombre después del ").
    
   - **Base de datos de archivo de QoE:** De forma predeterminada, esta opción está establecida en "crear nueva base de datos". Como la actualización de la base de datos de archivo no es compatible, la única circunstancia en la que se puede usar la opción "usar base de datos existente" es si la base de datos de archivo existente tiene el mismo esquema que la compilación que se va a instalar.
    
   - **Directorio de archivos de base de datos:** Ruta de acceso donde se deben colocar los archivos de base de datos (. MDF y. ldf) de la base de datos de archivo. Debe estar en una unidad (HDD2 Irán en la configuración de hardware recomendada) independiente del sistema operativo. Tenga en cuenta que, dado que los nombres de archivo se arreglan en la instalación, para evitar posibles conflictos, se recomienda que se use un directorio en blanco sin archivos.
    
   - **Usar varias particiones:** El valor predeterminado se establece en "multiple Partition", que requiere Business Intelligence Edition o Enterprise Edition de SQL Server. Para Standard Edition, seleccione la opción "partición única". Tenga en cuenta que el rendimiento del procesamiento del cubo puede verse afectado si se usa una sola partición.
    
     > [!NOTE]
     > La opción selección para usar varias particiones no se puede cambiar una vez finalizada la instalación. Para poder cambiarla, la característica de cubo debe desinstalarse primero y, a continuación, volver a instalarse con la opción "cambiar" del panel de control. 
  
   - **Directorio de archivos de partición:** Ruta de acceso en la que se deben colocar las particiones para la base de datos de archivo de QoE. Debe estar en una unidad (HDD3 en la configuración de hardware recomendada) independiente de la unidad del sistema operativo y de los archivos de registro de la base de datos de SQL. Tenga en cuenta que, dado que los nombres de archivo se arreglan en la instalación, para evitar posibles conflictos, se recomienda que se use un directorio en blanco sin archivos.
    
   - **Usuario del trabajo del Agente SQL- &amp; contraseña del nombre de usuario:** Nombre y contraseña de la cuenta de servicio del dominio (enmascarado) que se usarán para ejecutar el paso "datos del archivo de QoE" del trabajo del Agente SQL Server (que ejecutará el procedimiento almacenado para recopilar datos de QoE Metrics DB en la base de datos de archivo, por lo que esta cuenta debe tener acceso de lectura a la base de datos de QoE Metrics Esta cuenta también debe tener un inicio de sesión en la instancia de archivo de SQL Server de QoE.
    
     > [!NOTE]
     > La cuenta con la que se ejecuta la instancia de SQL Server, como NT SERVICE\MSSQLSERVER, debe tener acceso/permiso a los directorios indicados anteriormente para que la instalación se realice correctamente. Para obtener más información, vea [configurar permisos del sistema de archivos para el acceso al motor de base de datos](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)
  
7. Al hacer clic en siguiente, el instalador realizará comprobaciones y notificaciones de requisitos previos si se detecta algún problema. Cuando se superen todas las comprobaciones de requisitos previos, el instalador irá a la página de configuración de cubos. 
    
    > [!NOTE]
    > Si el instalador muestra un mensaje de advertencia que indica que el servicio Agente SQL Server para la instancia de archivo de SQL Server de QoE no se está ejecutando actualmente, la instalación puede continuar, pero después de la instalación, asegúrese de que el servicio Agente SQL se esté ejecutando y establezca el tipo de inicio en Automático para que se ejecute el trabajo programado. 
  
8. En la página Configuración de cubo, proporcione la siguiente información:
    
   - **Nombre del servidor SQL del archivo QoE:** Este campo es de solo lectura y se fija en el nombre de dominio completo del equipo local. Cube solo se puede instalar desde el equipo que tiene la base de datos de archivo de QoE (Note. El propio cubo puede instalarse en un equipo remoto. Vea a continuación)
    
   - **Instancia de archivo de SQL Server de QoE:** Nombre de instancia de SQL Server en el que se encuentra la base de datos de archivo de QoE. Para especificar una instancia de SQL Server predeterminada, deje este campo en blanco. Para especificar una instancia de SQL Server con nombre, escriba el nombre de la instancia (por ejemplo,\"el nombre después del "). Si se seleccionó el componente de archivo de QoE para la instalación, este campo se rellenará previamente con el valor que se proporciona en la página Configuración del archivo de QoE.
    
   - **Servidor de análisis de cubos:** Nombre de instancia de SQL Server Analysis Services en el que se va a crear el cubo. Puede ser un equipo diferente, pero el usuario que instala debe ser miembro de los administradores del servidor de la instancia de SQL Server Analysis Services de destino.
    
     > [!NOTE]
     >  Para obtener más información acerca de la configuración de permisos de administrador del servidor de Analysis Services, consulte [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)
  
   - **Usar varias particiones:** El valor predeterminado se establece en "multiple Partition", que requiere Business Intelligence Edition o Enterprise Edition de SQL Server. Para Standard Edition, seleccione la opción "partición única". Tenga en cuenta que el rendimiento del procesamiento del cubo puede verse afectado si se usa una sola partición.
    
     > [!NOTE]
     >  La opción selección para usar varias particiones no se puede cambiar una vez finalizada la instalación. Para poder cambiarla, la característica de cubo debe desinstalarse primero y, a continuación, volver a instalarse con la opción "cambiar" del panel de control.
  
   - **Usuario de cubo: contraseña &amp; del nombre de usuario:** Nombre y contraseña de la cuenta de servicio de dominio (enmascarado) que desencadenarán el procesamiento del cubo. Si se seleccionó el componente de archivo de QoE para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de archivo del usuario del trabajo del Agente SQL, pero recomendamos especificar una cuenta de servicio de dominio diferente para que el programa de instalación pueda conceder el privilegio mínimo requerido.
    
9. Al hacer clic en siguiente, se realizará otra ronda de validación y se informará de cualquier problema. Una vez finalizada correctamente la validación, el instalador irá a la página Configuración del portal. 
    
10. En la página Configuración del portal, proporcione la siguiente información:
    
    - **SQL Server de archivo de QoE:** Nombre de instancia de SQL Server en el que se encuentra la base de datos de archivo de QoE. Tenga en cuenta que, a diferencia de la página Configuración de archivo de QoE y la página de configuración de cubos, el nombre de la máquina no es fijo y se debe proporcionar. Si se seleccionó el componente de archivo de QoE para la instalación, este campo se rellenará previamente con el valor que se proporciona en la página Configuración del archivo de QoE.
    
    - **Servidor de análisis de cubos:** Nombre de instancia de SQL Server Analysis Services en el que se encuentra el cubo. Si se seleccionó el componente de cubo para la instalación, este campo se rellenará previamente con el valor proporcionado en la página Configuración de cubo.
    
    - **SQL Server del repositorio:** Nombre de instancia de SQL Server en el que se va a crear la base de datos del repositorio. Si el nombre de la instancia de SQL Server en el que se encuentra la base de datos de archivo de QoE se ha proporcionado anteriormente en la instalación (en otros componentes), este campo se rellenará previamente con el nombre de la instancia de archivo de base de datos de archivo de QoE. Puede ser cualquier instancia de SQL Server.
    
    - **Base de datos del repositorio:** De forma predeterminada, la opción se establece en "crear nueva base de datos". Como la actualización de la base de datos del repositorio no es compatible, la única circunstancia en la que se puede usar la opción "usar base de datos existente" es si la base de datos del repositorio existente tiene el mismo esquema que la compilación que se va a instalar.
    
    - **Usuario de grupo de aplicaciones de IIS &amp; : contraseña del nombre de usuario:** La cuenta con la que se debe ejecutar el grupo de aplicaciones de IIS. Los campos nombre de usuario y contraseña aparecerán atenuados si se seleccionan cuentas del sistema integrado. Estos campos solo se habilitarán si se selecciona "otro" en el cuadro desplegable para que el usuario pueda escribir la información de la cuenta de servicio de dominio.
    
11. Al hacer clic en siguiente, se realizará la última ronda de validación para asegurarse de que se puede tener acceso a las instancias de SQL Server con las credenciales proporcionadas y que IIS está disponible en el equipo. Una vez finalizada correctamente la validación, el instalador continuará con la instalación. 
    
Una vez finalizado el instalador, lo más probable es que el trabajo del Agente SQL Server esté en curso, con la carga inicial de los datos de QoE y el procesamiento del cubo. En función de la cantidad de datos de QoE, el portal no tendrá datos disponibles para verlos todavía. Para comprobar el estado de la carga de datos y el procesamiento del cubo, `http://<machinename>/CQD/#/Health`vaya a. 
> [!NOTE]
> Tenga en cuenta que la dirección URL para comprobar el estado del procesamiento del cubo de descarga distingue mayúsculas de minúsculas. Si escribe "Health", la dirección URL no funcionará. Debe introducir "Health" al final de la dirección URL con H mayúscula. 
  
Se mostrarán mensajes de registro detallados si está habilitado el modo de depuración. Para habilitar el modo de depuración, vaya a **%SystemDrive%\Archivos de Files\Skype para empresas 2015 CQD\QoEDataService\web.config**y actualice la siguiente línea para que el valor se establezca en **verdadero**:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La Página principal del portal es accesible `http://<machinename>/CQD`a través de. 
## <a name="managing-user-access-for-the-portal"></a>Administración del acceso de usuarios para el portal

Para administrar la autorización del usuario en el portal, se recomienda usar la autorización de dirección URL, que se introdujo en IIS 7,0. Para obtener más información sobre la seguridad de IIS, consulte [Understanding iis 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Cualquier sitio web o aplicación web hereda la autorización de dirección URL predeterminada configurada para todo IIS, que suele ser "permitir todos los usuarios". Si el acceso al portal debe ser más restrictivo, los administradores pueden conceder acceso solo a un grupo específico de usuarios mediante la edición de las "reglas de autorización".
  
![Implementar reglas de autorización de calidad de llamada en IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> El icono de reglas de autorización no se debe confundir con la "autorización de .NET" en la sección ASP.NET, que es un mecanismo de autorización diferente. 
  
Los administradores deben quitar primero la regla "permitir todos los usuarios" heredada. Esto evita que los usuarios no autorizados obtengan acceso al portal.
  
![Implementar el CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
A continuación, los administradores deben agregar nuevas reglas de permiso y dar a los usuarios específicos el permiso para obtener acceso al portal. Se recomienda crear un grupo local denominado "CQDPortalUsers" para administrar los usuarios.
  
![Implementar el panel de calidad de llamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Los detalles de configuración se almacenan en el archivo Web. config ubicado en el directorio físico del portal.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

El paso siguiente es configurar el panel del CQD. Una vez que IIS autentica a los usuarios, deberán tener permisos de archivo en el directorio del CQD para poder acceder al contenido del portal web. Es posible cambiar las ACL mediante la pestaña seguridad de las propiedades del directorio CQD para agregar usuarios individuales o grupos; sin embargo, el enfoque recomendado es dejar los permisos de archivo intactos. En su lugar, cambie la configuración de IIS para usar el proceso de trabajo de IIS para obtener acceso al directorio del CQD independientemente del usuario que esté autenticado. 
  
> [!IMPORTANT]
> Solo es importante cambiar esta configuración para la aplicación CQD y no para las dos aplicaciones API: QoEDataService y QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuración del acceso al archivo para el CQD (panel)

1. Abra el editor de configuración del CQD.
    
     ![Implementar el panel de calidad de llamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. En la sección, elija **System. WebServer/serverRuntime**.
    
     ![Implementar el panel de calidad de llamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Cambie authenticatedUserOverride a **UseWorkerProcessUser**.
    
     ![Implementar el panel de calidad de llamadas: editor de configuración](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Haga clic en **aplicar** en el lado derecho de la página.
    
## <a name="known-issues"></a>Problemas conocidos

### <a name="the-cqd-shows-no-data-after-deployment"></a>El CQD no muestra datos tras la implementación

Es posible que reciba el siguiente error:

*No pudimos realizar la consulta mientras se ejecutaba en el cubo. Use el editor de consultas para modificar la consulta y corregir los problemas. Asegúrese también de que se puede tener acceso al cubo.*

Esto significa que el cubo debe procesarse en SQL Server Analysis Services antes de usarse en el CQD. Para solucionar esto, siga estos pasos:

1. Abra SQL Management Studio y seleccione **Analysis Services**.

2. Expanda el objeto **QoECube** , seleccione la **métrica QoE**, haga clic con el botón secundario y, a continuación, elija **examinar**. 

    Si devuelve un explorador vacío, el cubo todavía no ha estado en proceso.

3. Haga clic con el botón secundario en ganancia de la **métrica de QoE** y seleccione **procesar**.

4. Una vez finalizado el procesamiento, vuelva a hacer clic con el botón secundario en el objeto y elija **examinar** para confirmar que ahora la página del explorador muestra los datos. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Los usuarios tienen problemas para iniciar sesión porque el instalador no puede crear la configuración correcta en IIS

En raras ocasiones, el instalador no puede crear la configuración correcta en IIS. Es necesario cambiar manualmente para permitir que los usuarios inicien sesión en el CQD. Si los usuarios tienen problemas para iniciar sesión, siga estos pasos:
  
1. Abra el administrador de IIS y vaya al sitio web predeterminado.
    
     ![Implementar el panel de calidad de llamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Haga clic en "autenticación". Si la "autenticación anónima", "ASP.NET Impersonation", "autenticación de formularios" y "autenticación de Windows" no coinciden con la configuración que se muestra a continuación, cámbielos manualmente para que se ajusten a los valores siguientes. Se deben deshabilitar todos los demás mecanismos de autenticación.
    
     ![Implementar el panel de calidad de llamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Para "autenticación de Windows", haga clic en configuración avanzada, en la parte derecha.
    
     ![Implementar el panel de calidad de llamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Establezca "protección extendida" para aceptar y active la casilla "habilitar la autenticación de modo kernel".
    
     ![Implementar el panel de calidad de llamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita los pasos anteriores para cada una de las entradas "CQD", "QoEDataService" y "QoERepositoryService" que se encuentran debajo de "default Web site".
    
Para los enlaces de puertos HTTP y HTTPS, el instalador creará enlaces de puertos en los números de puerto predeterminados (puerto 80 para HTTP y puerto 443 para HTTPS). Si hay otro sitio web en el equipo que usa estos enlaces, habrá un conflicto y no se podrá predecir el comportamiento de IIS. La mejor manera de evitar este problema es asegurarse de que no se asigna ningún otro sitio web a los puertos 80 y 443 antes de instalar el CQD. 
  
Para habilitar SSL/TLS en IIS y obligar a los usuarios a conectarse mediante HTTPS seguro en lugar de HTTP:
  
1. Configure Secure Sockets Layer en IIS, vea [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx). Una vez hecho, `http` Reemplace `https`por.
    
2. Para obtener instrucciones sobre cómo habilitar TLS en las conexiones de SQL Server, vea [Cómo habilitar el cifrado SSL para una instancia de SQL Server mediante Microsoft Management Console](https://support.microsoft.com/kb/316898/).
    
## <a name="cube-sync-fails"></a>Error de sincronización del cubo

QoEMetrics puede contener algunos registros no válidos basados en los relojes de los usuarios finales. Si el sesgo de tiempo es superior a 60 años, se producirá un error en la importación del cubo.
  
 Compruebe el mínimo y el máximo de StartTime/EndTime con las siguientes selecciones. Buscar y eliminar registros en el futuro muy alejado y en un futuro muy lejano, se pueden descartar y se romperán los procesos de sincronización.
  
- Seleccione MIN (StartTime) desde CqdPartitionedStreamView
    
- Seleccione MAX (StartTime) FROM CqdPartitionedStreamView
    
- Seleccione mín (EndTime) desde CqdPartitionedStreamView
    
- Seleccione MAX (EndTime) desde CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tareas posteriores a la instalación

### <a name="importing-buildings-and-networks"></a>Importación de edificios y redes

Después de instalar el CQD, realice las siguientes tareas de configuración:
  
1. Definir tipos de edificio (recomendado)
    
2. Definir tipos de propiedad de creación (recomendado)
    
3. Definir tipos de red (muy recomendable)
    
4. Importar edificios (recomendado)
    
5. Importar subredes (recomendado)
    
### <a name="define-building-types"></a>Definir tipos de edificio

Los tipos de edificio se usan para describir las diferentes definiciones o tipos de edificios dentro de la organización. 
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Ejemplos
  
- Sede
    
- Oficina remota
    
- Ubicación de empresa conjunta
    
  **Sintaxis SQL de ejemplo**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Se requieren los parámetros BuildingTypeId y BuildingTypeDesc.
  
### <a name="define-building-ownership-types"></a>Definir tipos de propiedad de creación

Los tipos de propiedad se usan para distinguir los activos de propiedad y concesiones.
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Ejemplos
  
- Contoso alquilado no RE&amp;F
    
- Contoso alquilado RE&amp;F
    
- Contoso propiedad
    
- Concesión de la subsidiaria
    
  **Sintaxis SQL de ejemplo**
  
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

Se requieren los parámetros OwnershipTypeId y OwnershipTypeDesc. 
  
### <a name="define-network-names"></a>Definir nombres de red

Los tipos de red se usan para describir distintos tipos de redes dentro de la organización. Esto le ofrece la posibilidad de filtrar (o desfiltrar) determinados tipos de red.
  
> [!NOTE]
> Es muy recomendable definir nombres de red, pero es opcional. Si decide no definir los nombres de red, asegúrese de que la entrada CqdNetwork tiene un BuildingId de 0. 
  
Ejemplos
  
- VPN
    
- LABORATORIO
    
  **Sintaxis SQL de ejemplo**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Se requieren los parámetros NetworkNameID y NetworkName, pero el parámetro NetworkType es opcional, pero se recomienda.
  
### <a name="import-buildings"></a>Importar edificios

La importación de edificios le ofrece la posibilidad de obtener información específica (llamadas deficientes por edificio en Wi-Wired, etc.). 
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Antes de importar un nuevo edificio, debe tener un BuildingKey identificado previamente. Para ello, emita el comando de SQL "SELECT MAX (BuildingKey) FROM CqdBuilding" para identificar el valor actual y agregar 1 al resultado.
  
 **Sintaxis SQL de ejemplo**
  
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

Se requieren los parámetros BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId, los otros parámetros son opcionales.
  
### <a name="import-subnets"></a>Importar subredes

La importación de edificios le ofrece la posibilidad de obtener información específica (llamadas deficientes por edificio en Wi-Wired, etc.). 
  
> [!NOTE]
> Este paso es opcional, pero se recomienda. 
  
Importar subredes y asignarlas a los edificios importados en el último paso. Si decidió no rellenar NetworkName, asegúrese de que cada entrada de esta tabla use un NetworkNameID de 0.
  
 **Sintaxis SQL de ejemplo**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

Los parámetros de red y UpdatedDate son obligatorios y los demás son opcionales.
  
### <a name="optional-bssid"></a>Opcional: BSSID

Rellenar la información de BSSID proporciona una correlación de flujos Wi-Fi adicional por controlador o radio. Esto es adicional al filtrado por edificio o subred. 
  
 **Sintaxis SQL de ejemplo**
  
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

|**Como se muestra en el CQD**|**Tabla CQDBssid**|**Entradas de ejemplo**|
|:-----|:-----|:-----|
|AP NName  <br/> |DUDOSO  <br/> |API  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (debe usar la Fformat delimitada)  <br/> |
|Controlador  <br/> |Fabrica  <br/> |Aruba AP 7  <br/> |
|Device  <br/> |ección  <br/> |Controller1  <br/> |
|Botón  <br/> |físico  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Procesar los datos importados

De forma predeterminada, después de importar datos de edificio o de red, solo se aplicará a los registros generados después de ese punto en el tiempo. 
  
Para etiquetar todos los registros anteriores con estos nuevos datos, tendrá que ejecutar el procedimiento almacenado CqdUpdateBuilding, como se muestra a continuación: 
  
Asígnele la fecha del primer registro (identifique el uso del comando SELECT MIN (StartTime) FROM CqdPartitionedStreamView SQL), una fecha de finalización del día mañana y, a continuación, NULL para los dos últimos valores.
  
Una vez que los datos se asocian a los datos de la secuencia, el cubo SSIS debe reprocesar todos los registros. Esto también se aplica al agregar de forma masiva datos de BSSID o ISP. Asegúrese de que esté seleccionado "proceso completo".
  

