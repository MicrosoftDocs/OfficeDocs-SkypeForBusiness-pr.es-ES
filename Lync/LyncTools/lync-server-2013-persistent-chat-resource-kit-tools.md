---
title: Herramientas del kit de recursos de chat persistente de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726e6bb537a16ece5c2955f005e91872f11f6a79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Herramientas del kit de recursos de chat persistente de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Las herramientas del kit de recursos de chat persistente de Lync Server 2013 ayudan a simplificar las tareas rutinarias para los administradores de ti que implementan y administran el servidor de chat persistente de Lync Server 2013. Además de las instrucciones de instalación, en este tema se describe el propósito de cada herramienta y ejemplos de uso.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Instalación de las herramientas del kit de recursos

Para instalar las herramientas del kit de recursos de Lync Server 2013, descargue **PersistentChatReskit. msi**. Ejecute **PersistentChatReskit. msi** para realizar una instalación sencilla. El archivo. msi instala todas las herramientas en la siguiente ruta de \\acceso: **archivos\\ de programa Kit\\de recursos del servidor de chat persistente de Microsoft Lync Server 2013**. Las herramientas que son ejecutables independientes se encuentran en esta carpeta. Las herramientas que también tienen archivos se encuentran en sus propias subcarpetas.

<div>


> [!IMPORTANT]  
> Después de instalar las herramientas del kit de recursos de Lync Server 2013, debe instalar <STRONG>PsExec. exe</STRONG> y copiar <STRONG>PsExec. exe</STRONG> en la siguiente \\ruta de acceso: <STRONG>archivos de programa \ Microsoft Lync Server 2013 \ opciones de recursos del servidor de chat persistente Kit\ChatStressTool</STRONG>. Si no copia <STRONG>PsExec. exe</STRONG>, la herramienta de estrés de chat persistente generará una excepción de error y no se realizará correctamente. Asegúrese de que cumple estos requisitos previos antes de ejecutar la herramienta. Para obtener más información sobre cómo instalar <STRONG>PsExec. exe</STRONG>, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.



</div>

</div>

<div>

## <a name="supported-environments"></a>Entornos compatibles

Para obtener un rendimiento óptimo, debe instalar las herramientas del kit de recursos de Lync Server 2013 en el mismo entorno y con las mismas especificaciones necesarias para Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Introducción a las herramientas del kit de recursos

Estas son las herramientas que se proporcionan en el kit de recursos de chat persistente de Lync Server 2013. En la siguiente sección se proporciona una descripción de cada herramienta, incluidos los requisitos y el uso de ejemplo.

  - AffCheck

  - ChatMonitoringSummary

  - Herramienta ChatStress

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>AffCheck

<div>

## <a name="description"></a>Descripción

La herramienta AffCheck confirma que los registros de afiliación de grupo y usuario de base de datos de servidor back-end persistente coinciden con los de servicios de dominio de Active Directory.

</div>

<div>

## <a name="requirements"></a>Requisitos

La herramienta se instala con el instalador de PersistentChatResKit en un equipo unido a un dominio.

La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a la base de datos back-end de chat persistente y servicios de dominio de Active Directory.

</div>

<div>

## <a name="usage"></a>Uso

Configure el archivo AffCheck. exe. config de acuerdo con las instrucciones del archivo de configuración y ejecute la herramienta AffCheck sin parámetros de línea de comandos. A continuación se muestran los contenidos de la AffCheck. exe. config predeterminada.

**AffCheck. exe. config:**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>Descripción

La herramienta PersistentChatMonitoringSummary mueve la información de supervisión de chat persistente desde la base de datos de supervisión a un archivo de registro CSV especificado.

El archivo CSV contendrá un desglose de las sesiones de chat persistentes por número de sesiones totales, sesiones correctas, errores inesperados, errores esperados y un desglose de los errores inesperados por identificador de diagnóstico, número de errores y descripción del error.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a la base de datos de supervisión.

La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a la base de datos de supervisión.

El archivo PersistentChatMonitoringSummary. exe. config debe contener una \<\> sección connectionStrings que defina la cadena de conexión a la base de datos de supervisión. También debe contener una clave para el PersistentChatEndpointUri en el que se recopilarán los datos de supervisión y una ruta de acceso de archivo a una ubicación para el archivo CSV que se generará. Consulte el archivo config instalado para obtener ejemplos. El archivo debe estar ubicado en el mismo directorio que la herramienta.

</div>

<div>

## <a name="usage"></a>Uso

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Estos parámetros definen la selección de datos:

**StartDateTime:** Opcionalmente, especifica la fecha de inicio del período de selección. Valor predeterminado: 1/1/1753 12:00:00 A.M.

**EndDateTime:** Opcionalmente, especifica la última fecha del período de selección. Valor predeterminado: ahora

</div>

<div>

## <a name="example"></a>Ejemplo

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>Herramienta de estrés de chat persistente

<div>

## <a name="description"></a>Descripción

La herramienta de estrés de chat persistente ofrece una forma sencilla de simular el uso del chat persistente para probar el rendimiento real, incluidos los diversos modelos de usuario para ajustarse mejor a los escenarios de uso esperados.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a la base de datos back-end de chat persistente.

Además de esta máquina del *controlador* , necesitará varias máquinas *del cargador* . Para cada 10.000 usuarios del modelo de usuario, necesitará al menos 4 GB de RAM disponible en un equipo del cargador. Por ejemplo, una ejecución con usuarios de 80K necesitará aproximadamente 32 GB de RAM distribuida en todas las máquinas del cargador. Se recomienda tener al menos tres equipos de cargador, independientemente de la carga prevista.

Los equipos del cargador deben tener instalado .NET 4,5 Framework, así como el paquete redistribuible de Visual C++ 2012.

</div>

<div>

## <a name="configuration"></a>Configuración

Copie los archivos de ChatStressTool en una carpeta compartida accesible desde todos los equipos del cargador.

Crear usuarios y canales para usarlos en el segmento de esfuerzo:

  - Cree tantos usuarios como el modelo de usuario llame a, habilítelo para Lync y establezca su Directiva de chat persistente en habilitada.

  - Cree una categoría para los canales de estrés y, a continuación, cree tantas salas como sean necesarias en esa categoría. La categoría debe tener todos los usuarios de esfuerzo en su lista de **permitidos** (mediante la adición de su uo) y las salas de estrés deben tener una configuración de privacidad de **abierta**.

  - Le recomendamos que cree salas de estrés adicionales. Puede crear salas de 50.000 con el siguiente comando de la interfaz de línea de comandos de Windows PowerShell:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Edite los archivos de configuración para que se ajusten a su topología:

En **LoaderProcess. exe. config**, cambie "Controller.contoso.com" por el nombre de dominio completo (FQDN) del equipo del controlador.

En **StressLauncher. exe. config:**

1.  Cambie el valor de configuración "LoaderBinary" a la ruta de acceso de la carpeta compartida.

2.  Cambie "AdminUser"/"AdminPassword" por las credenciales que tienen acceso de administrador a los equipos del cargador.

3.  Cambie "ChannelCategory" por el nombre de la categoría en la que se crearon los canales de estrés.

4.  Cambie "UserNamePattern" y "UserPasswordPattern" por una plantilla que coincida con las credenciales de usuario de carga. {0}se reemplaza por el número de índice del usuario.

5.  Cambie "dominio" al dominio SIP de su topología de prueba.

6.  Cambie "ConnectionString" por una cadena de conexión para la base de datos back-end de chat persistente.

7.  Cambie "UserIndexStart" al índice del primer usuario de esfuerzo.

8.  Cambie "LyncFQDN" por el FQDN de su grupo de servidores front-end.

9.  Modifique la lista "máquinas" para incluir nombres de máquina para todos los equipos del cargador.

10. Cambiar baseAddress del extremo de servicio (el valor predeterminado es "controller.contoso.com") al FQDN de su equipo de controlador.

</div>

<div>

## <a name="usage"></a>Uso

Una vez completada la configuración, abra StressLauncher. exe en el equipo del controlador. Puede iniciar StressLauncher como cualquier usuario. Las credenciales con las que se inician los procesos del cargador en los equipos del cargador deben especificarse en el archivo de configuración. También debe proporcionar una cadena de conexión que tenga acceso de lectura a la base de datos back-end de chat persistente. Si esta cadena de conexión usa la autenticación de Windows integrada, debe iniciar StressLauncher como un usuario con este acceso.

Modifique la configuración del modelo de usuario según sea necesario. Haga clic en **Iniciar carga** para iniciar una ejecución. Después de un minuto, los usuarios empezarán a iniciar sesión y la barra de progreso empezará a rellenarse. En este punto, puede que el equipo controlador funcione y realice medidas de rendimiento.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Descripción

ChatUpgradeVerifier es una herramienta de comparación de bases de datos específica de chat persistente. La herramienta compara la base de datos de chat en grupo 2007 R2 o el chat de grupo 2010 (2007/2010Db) en la base de datos del chat persistente 2013 (2013Db).

La herramienta comprobará, una por una, cada categoría, un salón de chat persistente y un complemento en 2007/2010Db para ver si aparece en el 2013Db. La comparación incluye la comprobación de todas las opciones de configuración de la categoría, el salón de chat o el complemento, todas las entidades de identidad del ámbito de la categoría y cualquier entidad de identidad de un rol en la categoría o en el salón de chat. Si una categoría o un salón de chat no aparece correctamente en 2013Db, las diferencias se generarán en un archivo de conflictos. Si, una vez que se ha realizado la actualización, se cambia 2007/2010Db y, a continuación, se ejecuta esta herramienta, se producirá un resultado de diferencias en el archivo de conflictos. Tenga en cuenta que esta aplicación es solo una herramienta de comparación de bases de datos y no valida el proceso de actualización.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a las bases de datos de back-end de chat persistente (versiones anteriores y actuales para el chat persistente).

La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a las bases de datos de chat persistente.

El archivo ChatUpgradeVerifier. exe. config debe contener el parámetro GroupChat2007R2Db o el parámetro GroupChat2010Db, con una cadena de conexión a la base de datos de chat de grupo adecuada (Groupchat 2007R2 o 2010). También debe contener un parámetro PersistentChat2013Db, con una cadena de conexión a la base de datos de chat persistente 2013.

</div>

<div>

## <a name="usage"></a>Uso

Ejecute **ChatUpgradeVerifier** sin ningún parámetro.

</div>

<div>

## <a name="example"></a>Ejemplo

![Ejecutar ChatUpgradeVerifier. exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Ejecutar ChatUpgradeVerifier. exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Informe de uso de chat persistente

<div>

## <a name="description"></a>Descripción

La herramienta ChatUsageReport genera un informe HTML del uso del servicio de chat persistente.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale las herramientas del kit de recursos de chat persistente en un equipo unido a un dominio que tenga acceso a la base de datos back-end de chat persistente.

La cuenta de usuario con la que se ejecuta la herramienta debe tener acceso de lectura a la base de datos back-end de chat persistente.

El archivo ChatUsageReport. exe. config debe contener una \<\> sección connectionStrings que defina la cadena de conexión a la base de datos back-end de chat persistente. El contenido del archivo de configuración predeterminado se incluye aquí, para su referencia.

</div>

<div>

## <a name="usage"></a>Uso

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Estos parámetros definen la selección de datos:

**StartDate:** Opcionalmente, especifica la fecha de inicio UTC del período de selección. Valor predeterminado: fecha más temprana

**EndDate:** Opcionalmente, especifica la fecha de finalización UTC del período de selección. Valor predeterminado: ahora

Estos parámetros definen cómo y qué datos se muestran:

**TopActiveUsers:** Si se especifica esto, el informe incluirá a los usuarios más activos en función del número de mensajes que el usuario haya publicado en el salón de chat durante el período seleccionado. Valor predeterminado: 10

**TopActiveRooms:** Si se especifica, el informe incluirá los n salones de chat más activos en función del número de mensajes publicados en el salón durante el período seleccionado. Valor predeterminado: 10

**LeastActiveRooms:** Si se especifica esto, el informe incluirá los salones de chat activos menos activos en relación con el número de mensajes publicados en el salón de chat durante el período seleccionado. Las salas tendrán al menos un mensaje expuesto. Valor predeterminado: 10

**RoomsInactiveSince:** Si se especifica esto, el informe incluirá una lista de salones de chat que han estado inactivos desde la fecha especificada. Valor predeterminado: tiempo completo

**OutputFolder:** La carpeta en la que se colocarán las imágenes de ChatUsageReport. html y del gráfico. Debe definirse en el archivo de configuración o en la línea de comandos.

Todos los valores de parámetros de la línea de comandos también se pueden especificar en el archivo ChatUsageReport. exe. config que se encuentra en el mismo directorio que la herramienta. Si se especifica un valor en el archivo de configuración y en la línea de comandos, el valor de la línea de comandos invalidará el valor del archivo de configuración.

</div>

<div>

## <a name="output"></a>Output

El informe siempre incluirá el siguiente resultado:

  - Principales n salones de chat activos por número de publicaciones de mensajes durante el período seleccionado.

  - Principales n usuarios activos por número de publicaciones de mensajes durante el período seleccionado.

  - Principales n salones de chat activos como mínimo por número de publicaciones de mensajes para el período seleccionado.

  - Salones de chat que están inactivos durante toda la vida de la base de datos o desde la fecha especificada.

  - Tendencia diaria de exposición de mensajes para el período seleccionado.

  - Tendencia semanal de exposición de mensajes para el período seleccionado.

  - Tendencia mensual de post de mensaje para el período seleccionado.

  - Total de publicaciones de mensajes para el período seleccionado.

  - Número total de salones habilitados.

</div>

<div>

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se genera un informe de uso para todo el año 2001 y se coloca el informe en el OutputFolder especificado en ChatUsageReport. exe. config.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport. exe. config:

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>Descripción

ScheduleADSyncForPrincipal es un script de Microsoft SQL Server 2012 que debe ejecutarse directamente desde dentro de SQL Server Management Studio cuando se conecta a la base de datos back-end de chat persistente. Esta secuencia de comandos permite forzar el chat persistente para que sincronice sus registros de un usuario con los de servicios de dominio de Active Directory, en lugar de esperar el tiempo de sincronización programado.

</div>

<div>

## <a name="requirements"></a>Requisitos

La cuenta de usuario con la que se ejecuta el script debe tener acceso de propietario a la base de datos back-end de chat persistente.

</div>

<div>

## <a name="usage"></a>Uso

A continuación se muestran los contenidos de la secuencia de comandos predeterminada:

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

