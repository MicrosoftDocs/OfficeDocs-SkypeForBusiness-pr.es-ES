---
title: Requisitos del servidor para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumen: prepare los servidores de Skype Empresarial Server 2015 con este tema. Hardware, sistemas operativos, bases de datos, software, todos los requisitos del sistema y recomendaciones están aquí para ayudar a garantizar una instalación e implementación correcta de la granja de servidores.'
ms.openlocfilehash: dfcde40c8084279dca39e830a84ad6e9631530dd
ms.sourcegitcommit: 98c0d578f5ebbe884a5965ccaba131ee4dd84185
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2018
ms.locfileid: "19046023"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos del servidor para Skype Empresarial Server 2015
 
**Resumen:** prepare los servidores de Skype Empresarial Server 2015 con este tema. Hardware, sistemas operativos, bases de datos, software, todos los requisitos del sistema y recomendaciones están aquí para ayudar a garantizar una instalación e implementación correcta de la granja de servidores.
  
Como era de esperar, hay algunos preparativos que debe hacer antes de empezar a implementar Skype para Business Server 2015. Este artículo lo guiará por el proceso de planificación de los siguientes elementos:
  
- [Hardware para Skype Empresarial Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operativos para Skype para Business Server 2015](server-requirements.md#OS)
  
- [Bases de datos back-end que funcionarán con Skype Empresarial Server 2015](server-requirements.md#DBs)
  
- [Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para Skype Empresarial Server 2015
<a name="Hardware"> </a>

Ahora que tiene la topología hacia abajo (y si no lo hace, puede desproteger el tema de [conceptos básicos de la topología de Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), es el momento de pensar acerca de los servidores. Skype para servidores Business Server 2015 requiere un hardware de 64 bits. Las recomendaciones de hardware se indican a continuación. Estos no son los requisitos, pero que reflejan los requisitos necesarios para un rendimiento óptimo. Existe documentación de planificación de la capacidad que le ayudará a determinar si necesita un equipo superior, dependiendo de sus circunstancias.
  
Hardware recomendado para los servidores Front-End, servidores Back-End, servidores Standard Edition y servidores de Chat persistente:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, seis núcleos y 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no se admiten para Skype para funciones de Business Server 2015.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |O  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos con RAID 1 y 6 con RAID 10).   <br/> O bien  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Configuraciones de host múltiple o dobles son **no** se admite para servidores Front-End, servidores Back-End, Standard Edition, los servidores y servidores de Chat persistente. <br/> Siempre y cuando no estén expuestos al sistema operativo y estén siendo utilizados para supervisar y administrar el hardware del servidor, puede tener sistemas de administración extraordinaria, como DRAC o ILO. Este escenario no constituye un servidor de múltiples ubicaciones, y es un escenario compatible.<br/> |
   
Hardware recomendado para los servidores perimetrales, servidores de mediación independiente, los servidores de interoperabilidad de vídeo y directores:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, de cuatro núcleos, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no se admiten para Skype para funciones de Business Server 2015.  <br/> |
|Memoria  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |O  <br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración de 2 unidades RAID 1).  <br/> O bien  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 4 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Son las configuraciones de dobles u host múltiple **no** se admite para los servidores de la interoperabilidad de vídeo y directores. <br/> Los servidores Edge necesitan dos interfaces de red que sean adaptadores de red de puerto doble, 1 Gbps o superior (o dos adaptadores de red emparejados para un total de cuatro; cada pareja debe formar un equipo con una sola dirección MAC y una sola dirección IP, para un total de dos parejas).  <br/> En independiente es compatible con la instalación de tarjetas de interfaz de red adicionales (NIC) para permitir la configuración de una dirección IP de PSTN específica de los servidores de mediación.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operativos para Skype para Business Server 2015
<a name="OS"> </a>

Una vez que tenga el hardware en su lugar, debe instalar sistemas operativos (SO). Estos son el sistema operativo que le permitirá instalar y usar correctamente Skype para Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 R2 Datacenter OS con requiere todas las actualizaciones instaladas.  <br/> |Windows Server 2012 R2 OS estándar con requiere todas las actualizaciones instaladas.  <br/> |
|2012 Datacenter sistema operativo Windows Server con requiere todas las actualizaciones instaladas.  <br/> |Windows Server 2012 OS estándar con requiere todas las actualizaciones instaladas.  <br/> |
   
Si no está en esta lista, no funcionará correctamente, por favor, no lo pruebe para las nuevas instalaciones de Skype para Business Server 2015.
  
> [!NOTE]
> Habrá reparado en que Windows Server 2008 R2 no está en la lista. Se debe a que recomendamos utilizar Windows Server 2012 R2 en los nuevos servidores para SE. Solo debe usar Windows Server 2008 R2 si tiene servidores existentes con Lync Server 2013 ya instalado y pretende realizar una actualización in situ. Windows Server 2008 R2 alcanzó el fin de su ciclo de soporte el 13 de enero de 2015. 
  
Además del último service pack, asegúrese de que las siguientes actualizaciones están instaladas donde corresponda:
  
- Antes de una actualización, es preciso instalar el artículo de Knowledge Base 2858668 para Windows Server 2012. [Obtener aquí](https://support.microsoft.com/en-us/kb/2858668/).
    
- Si tiene Windows Server 2012 R2, instale el artículo de Knowledge Base 2982006 antes de la actualización. [Se encuentra aquí](https://support.microsoft.com/en-us/kb/2982006/).
    
- Si está actualizando a partir de Windows Server 2008 R2 (consulte la nota anterior), es preciso instalar primero el artículo de Knowledge Base 2533623. [Es en este vínculo](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de datos back-end que funcionarán con Skype Empresarial Server 2015
<a name="DBs"> </a>

Al instalar Skype para 2015 Business Server Standard Edition, tendrá 2014 de SQL Server Express (edición de 64 bits) se instala automáticamente también.
  
Skype para Business Server 2015 Enterprise Edition es un poco más complicado, pero la lista admitida es inferior a (todo lo que es la edición de 64 bits, observará, por favor, no use las ediciones de 32 bits):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2014 Enterprise (edición de 64 bits) y se debe ejecutar con actualización acumulativa 6 o posterior ([Descargue la actualización acumulativa 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edición de 64 bits) y se recomienda la ejecución con el último service pack.  <br/> |Microsoft SQL Server 2008 R2 Enterprise (edición de 64 bits) y se recomienda la ejecución con el último service pack.  <br/> |
|Microsoft SQL Server 2014 Standard (edición de 64 bits) y se debe ejecutar con actualización acumulativa 6 o posterior ([Descargue la actualización acumulativa 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda la ejecución con el último service pack.  <br/> |Microsoft SQL Server 2008 R2 Standard (edición de 64 bits) y se recomienda la ejecución con el último service pack  <br/> |
   
Si no ve la edición de SQL Server que desea usar que se muestra aquí, no se puede usar.
  
> [!NOTE]
> También va a necesitar instalar SQL Server Reporting Services para el rol de servidor de supervisión, pero debe saber que esto no se va a ser compatibles con SQL siempre en hasta post-RTM. 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Mirroring, SQL Clustering y SQL Always On

Puede usar la creación de reflejos de SQL o agrupación en clústeres de SQL con Skype para Business Server 2015, que es compatible. Reflejo de SQL configurar a través de la Skype para Business Server Topology Builder. Si usted es la intención sobre la configuración de agrupación en clústeres de SQL, que se realiza en SQL Server.
  
Asegúrese de que tiene una configuración activo/pasivo para la agrupación en clústeres de SQL, ya es lo que se admite. No compartir el nodo pasivo con cualquier otra instancia SQL.
  
Puede usar lo siguiente para el clúster de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2014 Standard (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
-  Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
- Microsoft SQL Server 2008 R2 Standard (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
Dieciséis nodos:
  
- Microsoft SQL Server 2014 Enterprise (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
- Microsoft SQL Server 2012 Enterprise (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
- Microsoft SQL Server 2008 R2 Enterprise (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
> [!IMPORTANT]
> Para la actualización, ¿desea asegurarse de que en los servidores Front-End que tiene al menos SQL Server 2012 SP1 instalado antes de la actualización. [Éste es un vínculo](https://www.microsoft.com/en-us/download/details.aspx?id=35575) a SP1 si desea descargarlo inmediatamente.
  
Si necesita leer hasta obtener más información sobre la creación de reflejo de SQL, tenemos una alta disponibilidad de servidor Back-End en Skype para tema Business Server 2015. Configurar la agrupación en clústeres de SQL Server para Skype para Business Server 2015 tiene los pasos para que está preparada para clústeres. También existen aún más vínculos en de conmutación por error de SQL, para [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)y [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Una novedad de esta versión es la compatibilidad con SQL Always On. Es compatible y puede leer más información acerca de él en el tema de [servidor Back-End de alta disponibilidad en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015
<a name="Software"> </a>

Hay algunas cosas que va a necesitar instalar o configurar para cualquier servidor que ejecute Skype para Business Server 2015, y se enumeran a continuación. Se indican también los requisitos adicionales para roles de servidor específicos.
  
 **Todos los servidores:**
  
|**Software/Rol**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos los Skype para servidores Business Server necesita Windows PowerShell 3.0 instalado.  <br/> • Si está realizando la instalación en Windows Server 2012 R2 o Windows Server 2012, está establecido, porque ya existe.  <br/> • Si está realizando una actualización en Windows Server 2008 R2, puede descargar [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) para obtenerlo. <br/> **Sugerencia:** Una vez que tenga la correcta PowerShell en allí, confirme que es la versión de compilación 6.2.9200.0 o posterior yendo a la PowerShell preguntar y escriba `$PSVersionTable`. De este modo debería aparecer la información que necesita.  <br/> |
|Microsoft .NET Framework  <br/> |Los servicios de WCF es una **característica** que no se ha instalado como una característica de Windows, en **Administrador del servidor**, ninguna descarga sea necesaria. <br/> • Necesita para asegurarse de que, al instalar esta característica, o si ya está instalado y se está revisando en él, que la opción de **Activación HTTP** es también comprueba e instalada, de este modo: <br/> ![Captura de pantalla que muestra la opción de activación de HTTP en las características de .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)No se preocupe si obtener un elemento emergente adicional que indica que deban instalarse para que la activación HTTP a instalarse algunas otras cosas. Que es normal, haga clic en Aceptar y continúe. Si no se obtienen emergente, a continuación, se supone esas cosas ya están instaladas y vamos.  <br/> Normalmente, se instala Microsoft .NET Framework cuando se instaló Windows Server 2012 R2 o Windows Server 2016. Skype para Business Server funciona con las siguientes versiones de Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • 4.7 de .NET (por Skype para Business Server CU 5 o versiones posteriores)  <br/>  De forma predeterminada en el equipo de Windows Server 2008 R2 es probable que se va a instalar .NET framework 3.5 (definitivamente Compruebe que antes de actualizar), pero en realidad no se convertirá en los servidores de Windows Server 2012 o Windows Server 2012 R2 (para nuevas instalaciones). Para agregar en, necesitará tener acceso a su medio o la unidad de instalación (el lugar que se ha instalado el servidor de Windows desde o dónde están ahora los archivos de instalación). Siga adelante e instálelo como una característica desde el Administrador de servidores y seleccione el medio de instalación (concretamente, la carpeta **\sources\sxs**) cuando se le pida. Continúe y complete la instalación. <br/> |
|Media Foundation  <br/> |Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2 el tiempo de ejecución de formato de Windows Media se instala con Microsoft Media Foundation.  <br/> Usada para conferencias de todos los servidores de servidores Front-End y Standard Edition requieren Windows Media Format Runtime ejecutar los archivos de Windows Media Audio (.wma) que las aplicaciones de estacionamiento de llamadas, el anuncio y el grupo de respuesta reproducción para música y anuncios.  <br/> |
|Windows Identity Foundation  <br/> |Es necesario Windows Identity Foundation 3.5 para admitir escenarios de autenticación de servidor a servidor para Skype para Business Server 2015.  <br/> • Para Windows Server 2012 y Windows Server 2012 R2, no es necesario descargar nada. Abra el **Administrador de servidores** y vaya a **Asistente para agregar roles y características**. **Windows Identity Foundation 3.5** aparece en la sección **Características**. Si está activado, se puede proceder. Si es así, seleccione la opción y haga clic en Siguiente para que aparezca el botón **Instalar**. <br/> |
|Herramientas de administración remota del servidor  <br/> |Herramientas de administración de roles: herramientas AD DS y AD LDS  <br/> |
   
 **También necesita Front-End servidores y servidor Standard Edition:**
  
|**Software/Rol**|**Detalles**|
|:-----|:-----|
|Servicios de Internet Information Server (IIS)  <br/> |IIS es necesario en todos los servidores Front-End, así como todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características comunes de HTTP: contenido estático de documento, errores HTTP, predeterminado  <br/> • Estado y diagnóstico: registro, herramientas de registro, el seguimiento de HTTP  <br/> • Rendimiento: compresión de contenido estático, compresión de contenido dinámico  <br/> • Seguridad: solicitud de filtrado, autenticación de asignación de certificados de cliente, la autenticación de Windows  <br/> • El desarrollo de aplicaciones: extensibilidad de .NET 3.5, extensibilidad de .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, las extensiones ISAPI, filtros ISAPI  <br/> • Herramientas de administración: consola de administración de IIS, las secuencias de comandos de administración de IIS y herramientas  <br/> También debemos mencionar también se necesita el acceso anónimo, pero tendrá que al instalar IIS, por lo que no tiene un lugar para que seleccione en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, debe instalar la característica de **Media Foundation** en **Administrador del servidor**. Ahora, puede iniciar realmente la Skype para la instalación de Business Server 2015 sin este uno, pero se le pedirá que lo instale y, a continuación, reiniciar el servidor, antes de la Skype para Business Server 2015 instalar continúa. Es preferible hacerlo antes. <br/> |
|Silverlight  <br/> |Puede instalar la versión más reciente de Silverlight en [este vínculo](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> También es posible que necesite habilitar examen de directorios si usa un equilibrador de carga. En caso contrario, carga una página en blanco que el equilibrador de carga es posible que considere la posibilidad de un error. 

A modo de ayuda, aquí ofrecemos un script de ejemplo de PowerShell que puede ejecutar para automatizar esto:

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> El comando busca los archivos de origen en un orden específico. Si está conectado, el comando obtiene acceso a Windows Update. Sin embargo, si están sin conexión, debe asegurarse de que los archivos de origen están disponibles para el comando. Para obtener más información acerca del uso de PowerShell para instalar funciones y características, vea [instalar o desinstalar funciones, servicios de rol o características](https://technet.microsoft.com/en-us/library/hh831809.aspx) no olvide volver a ejecutar Windows Update después de instalar los requisitos previos, incluso si se usa el comando de PowerShell.

 **Los directores también necesitan:**
  
IIS, con los siguientes módulos seleccionados:
  
- Características HTTP comunes
    
  - Documento predeterminado
    
  - Errores HTTP
    
  - Contenido estático
    
- Estado y diagnóstico
    
  - Registro HTTP
    
  - Herramientas de registro
    
  - Seguimiento
    
- Rendimiento
    
  - Compresión de contenido estático
    
- Seguridad
    
  - Filtro de solicitudes
    
  - Autenticación por asignación de certificados de clientes
    
  - Autenticación de Windows
    
- Desarrollo de aplicaciones
    
  - Extensibilidad de .NET 3.5
    
  - Extensibilidad de .NET 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - Extensión ISAPI
    
  - Filtros ISAPI
    
(Si se lo está preguntando, es el mismo módulo establecer que los servidores front-end y Standard Edition, con la compresión de contenido dinámico y herramientas de administración de la izquierda).
  
También contamos con el siguiente código de PowerShell para esto:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **También necesita servidores de Chat persistente:**
  
Message Queue Server, también denominado MSMQ. Es un componente de servidor de Windows y puede instalarlo en la sección de características en el administrador del servidor. Si desea más información acerca de esto, consulte [instalación y administración de Message Queue Server](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Últimas reflexiones:**
  
Por favor, no instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server, o cualquier otro software de proveedores de servicios por niveles (LSP) de Winsock (los firewalls de terceros o software de inspección de red contra virus sería incluido aquí) en cualquiera de los servidores front-end o servidores de mediación independiente. Se ha visto el rendimiento del tráfico de medios deficiente cuando de instala ese software.
  

