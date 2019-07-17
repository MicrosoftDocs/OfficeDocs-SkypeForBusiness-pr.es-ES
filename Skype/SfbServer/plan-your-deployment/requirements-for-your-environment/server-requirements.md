---
title: Requisitos del servidor para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumen: Prepare los servidores de Skype empresarial Server 2015 con este tema. Hardware, sistema operativo, bases de datos, software, todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación y una implementación correctas de su granja de servidores.'
ms.openlocfilehash: 368c719ac4e61b62ab4c52c50433bf6cc996c886
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2019
ms.locfileid: "35758952"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Server requirements for Skype for Business Server 2015
 
**Resumen:** prepare los servidores de Skype Empresarial Server 2015 con este tema. Hardware, sistemas operativos, bases de datos, software, todos los requisitos del sistema y recomendaciones están aquí para ayudar a garantizar una instalación e implementación correcta de la granja de servidores.

Si está buscando requisitos ambientales, como Active Directory, DNS o certificados, puede consultar los [requisitos ambientales para el documento de Skype empresarial Server 2015](environmental-requirements.md) .
  
Como cabría esperar, hay algunos preparativos que debe hacer antes de empezar a implementar Skype empresarial Server 2015. Este artículo lo guiará por el proceso de planificación de los siguientes elementos:
  
- [Hardware para Skype Empresarial Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operativos para Skype empresarial Server 2015](server-requirements.md#OS)
  
- [Bases de datos back-end que funcionarán con Skype Empresarial Server 2015](server-requirements.md#DBs)
  
- [Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para Skype Empresarial Server 2015
<a name="Hardware"> </a>

Ahora que tiene su topología (y, de lo contrario, puede consultar los [conceptos básicos de topología de Skype empresarial Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), es el momento de pensar en los servidores. Los servidores de Skype empresarial Server 2015 requerirán hardware de 64 bits. Las recomendaciones de hardware se indican a continuación. No hay requisitos, pero reflejan los requisitos necesarios para un rendimiento óptimo. Existe documentación de planificación de la capacidad que le ayudará a determinar si necesita un equipo superior, dependiendo de sus circunstancias.
  
Hardware recomendado para servidores front-end, servidores de servicios de fondo, servidores Standard Edition y servidores de chat persistentes:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, seis núcleos y 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de 2015 de Skype empresarial Server.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |O  <br/> • 8 o más unidades de disco duro de 10000 RPM con un mínimo de 72 GB de espacio en disco (dos de los discos que usan RAID 1 y 6 con RAID 10).  <br/> O BIEN  <br/> • Unidades de estado sólido (SSDs) capaces de proporcionar el mismo espacio libre y un rendimiento similar a las unidades de disco mecánicas de 8 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Las configuraciones dual o multitarjeta **no** son compatibles con los servidores front-end, los servidores de back-end, los servidores Standard Edition y los servidores de chat persistentes. <br/> Siempre y cuando no estén expuestos al sistema operativo y estén siendo utilizados para supervisar y administrar el hardware del servidor, puede tener sistemas de administración extraordinaria, como DRAC o ILO. Este escenario no constituye un servidor de múltiples ubicaciones, y es un escenario compatible.<br/> |
   
Hardware recomendado para servidores perimetrales, servidores de mediación independientes, servidores de interoperabilidad de vídeo y directores:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, de cuatro núcleos, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de 2015 de Skype empresarial Server.  <br/> |
|Memoria  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |O  <br/> • 4 unidades de disco duro de 10000 RPM con un mínimo de 72 GB de espacio libre en el disco (los discos deben tener una configuración RAID 1 2x).  <br/> O BIEN  <br/> • Unidades de estado sólido (SSDs) capaces de proporcionar el mismo espacio libre y un rendimiento similar a las unidades de disco mecánicas de 4 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> **No** se admiten las configuraciones dual o multitarjeta para los directores y servidores de interoperabilidad. <br/> Los servidores Edge necesitan dos interfaces de red que sean adaptadores de red de puerto doble, 1 Gbps o superior (o dos adaptadores de red emparejados para un total de cuatro; cada pareja debe formar un equipo con una sola dirección MAC y una sola dirección IP, para un total de dos parejas).  <br/> En los servidores de mediación independiente, se admite la instalación de tarjetas de interfaz de red (NICs) adicionales para permitir la configuración de una dirección IP de RTC específica.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operativos para Skype empresarial Server 2015
<a name="OS"> </a>

Una vez que haya instalado el hardware, tendrá que instalar sistemas operativos (SO). Estos son los sistemas operativos que le permitirán instalar y usar correctamente Skype empresarial Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (necesita la actualización acumulativa 9 o posterior de Skype empresarial). <br/> |Windows Server 2016 (necesita la actualización acumulativa 5 de Skype para empresas o una versión posterior. Para obtener más información, consulte [KB4015888](https://support.microsoft.com/en-gb/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Sistema operativo Windows Server 2012 R2 Datacenter con todas las actualizaciones necesarias instaladas.  <br/> |Sistema operativo Windows Server 2012 R2 Standard con todas las actualizaciones necesarias instaladas.  <br/> |
|Sistema operativo Windows Server 2012 Datacenter con todas las actualizaciones necesarias instaladas.  <br/> |Sistema operativo estándar de Windows Server 2012 con todas las actualizaciones necesarias instaladas.  <br/> |
   
Si no está en esta lista, no funcionará correctamente; no lo pruebe para obtener nuevas instalaciones de Skype empresarial Server 2015.
  
> [!NOTE]
> Es posible que haya observado que Windows Server 2008 R2 no está en esta lista. Esto se debe a que recomendamos Windows Server 2012 R2 para que todos los servidores nuevos se usen para SFB. Solo debe usar Windows Server 2008 R2 cuando tiene servidores existentes con Lync Server 2013 ya instalado y está intentando realizar una actualización local de los mismos y le interesa. Windows Server 2008 R2 llegó al final del ciclo de vida de soporte técnico básico en 1/13/2015 y llegará al final de su ciclo de vida de soporte técnico en 1/14/2020.
  
Además del último service pack, asegúrese de que las siguientes actualizaciones están instaladas donde corresponda:
  
- Antes de una actualización, es preciso instalar el artículo de Knowledge Base 2858668 para Windows Server 2012. [Obténla aquí](https://support.microsoft.com/en-us/kb/2858668/).
    
- Si tiene Windows Server 2012 R2, instale el artículo de Knowledge Base 2982006 antes de la actualización. Se [encuentra aquí](https://support.microsoft.com/en-us/kb/2982006/).
    
- Si está actualizando a partir de Windows Server 2008 R2 (consulte la nota anterior), es preciso instalar primero el artículo de Knowledge Base 2533623. [Está en este vínculo](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de datos back-end que funcionarán con Skype Empresarial Server 2015
<a name="DBs"> </a>

Al instalar Skype empresarial Server 2015 Standard Edition, también se instala automáticamente SQL Server 2014 Express (64-bit Edition).
  
Skype empresarial Server 2015 Enterprise Edition es un poco más complicado, pero la lista admitida se encuentra a continuación (todo es 64-bit Edition, observará que no use las ediciones de 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-bit Edition) y le recomendamos que ejecute el Service Pack más reciente. <br/> |Microsoft SQL Server 2017 Enterprise (64-bit Edition) y le recomendamos que ejecute el Service Pack más reciente. <br/> |Microsoft SQL Server 2016 Enterprise (64-bit Edition) con Service Pack 1 o posterior, y debe ejecutarse con la actualización acumulativa 7 o posterior de Skype empresarial ([descargar la actualización acumulativa de Skype empresarial](https://support.microsoft.com/en-us/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (64-bit Edition) y debe ejecutarse con la actualización acumulativa 6 o posterior ([descargar la actualización acumulativa 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64-bit Edition) y le recomendamos que ejecute el Service Pack más reciente.  <br/> |
|Microsoft SQL Server 2019 Standard (edición de 64 bits) y le recomendamos que ejecute el Service Pack más reciente. <br/> |Microsoft SQL Server 2017 Standard (edición de 64 bits) y le recomendamos que ejecute el Service Pack más reciente. <br/> |Microsoft SQL Server 2016 Standard (64-bit Edition) con Service Pack 1 o posterior, y debe ejecutar la actualización acumulativa 7 o posterior de Skype empresarial ([descargar la actualización acumulativa de Skype empresarial](https://support.microsoft.com/en-us/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (edición de 64 bits) y debe ejecutarse con la actualización acumulativa 6 o posterior ([descargar la actualización acumulativa 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edición de 64 bits) y le recomendamos que ejecute el Service Pack más reciente.  <br/> |
   
Si no ve la edición de SQL Server que quiere usar en la lista, no puede usarla.
  
> [!NOTE]
> También tendrá que instalar SQL Server Reporting Services para el rol de servidor de supervisión.

### <a name="microsoft-exchange-storage"></a>Almacenamiento de Microsoft Exchange
Meeting content files, such as PowerPoint presentations, are archived as attachments. Si desea almacenar datos de archivo de Skype empresarial con datos de cumplimiento de Exchange, debe usar Exchange para la implementación de Exchange y asegurarse de que el tamaño máximo de almacenamiento admita el almacenamiento de los archivos de contenido de la reunión. Debe implementar Exchange antes de implementar y habilitar el archivado mediante la opción de integración de Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el archivado en Skype Empresarial Server 2015
  
El archivado no es un rol de servidor definido, no es necesario instalar un servidor independiente para archivar. Los agentes unificados de recopilación de datos se instalan y activan automáticamente en todos los servidores Enterprise Edition front end y en todos los servidores Standard Edition. Necesitará habilitar y publicar la topología de archivado por medio del Generador de topologías.
    
El archivado usa el almacenamiento de archivos de Skype empresarial Server para el almacenamiento temporal de los archivos de contenido de la reunión, por lo que no se configura un almacén de archivos independiente para archivar.
    
Microsoft Message Queue Server no es necesario.
    
Es preciso configurar la infraestructura para el almacenamiento del archivado. Esto incluye la elección de almacenamiento de Exchange o de archivado con SQL Server.   Los requisitos de la infraestructura de archivado de Skype empresarial Server son los mismos que para la implementación de Skype empresarial Server. Para obtener más información, consulte [requisitos para su entorno de Skype empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Para admitir usuarios que no estén alojados en servidores de Exchange, o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado mediante una base de datos SQL Server de 64 bits. 
    
Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación. Para obtener más información sobre SQL Server, consulte la [documentación de SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
El aumento en la carga del archivado puede ser considerable. Por lo tanto, debe asegurarse de que el espacio de disco es adecuado para los servidores front-end en los que está habilitado el archivado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Mirroring, SQL Clustering y SQL Always On

Puede usar el reflejo de SQL o el clúster SQL con Skype empresarial Server 2015, que es compatible. La configuración del reflejo de SQL mediante el generador de topologías de Skype empresarial Server. Si está intentando configurar clústeres de SQL, eso se hace en SQL Server.
  
Asegúrese de que tiene una configuración de activo/pasivo para la organización en clústeres de SQL, ya que es la que se admite. No comparta el nodo pasivo con ninguna otra instancia de SQL.
  
Puede usar lo siguiente para el clúster de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2019 Standard (edición de 64 bits) y le recomendamos que ejecute el Service Pack más reciente.

- Microsoft SQL Server 2017 Standard (edición de 64 bits) y le recomendamos que ejecute el Service Pack más reciente.

- Microsoft SQL Server 2016 Standard (edición de 64 bits) con Service Pack 1 o posterior. Le recomendamos que ejecute el Service Pack más reciente.

- Microsoft SQL Server 2014 Standard (edición de 64 bits) y le recomendamos que ejecute el Service Pack más reciente.
    
-  Microsoft SQL Server 2012 Standard (edición de 64 bits) y le recomendamos que ejecute el Service Pack más reciente.

Dieciséis nodos:

- Microsoft SQL Server 2019 Enterprise (64-bit Edition) y le recomendamos que ejecute el Service Pack más reciente.

- Microsoft SQL Server 2017 Enterprise (64-bit Edition) y le recomendamos que ejecute el Service Pack más reciente.

- Microsoft SQL Server 2016 Enterprise (64-bit Edition) con Service Pack 1 o posterior. Le recomendamos que ejecute el Service Pack más reciente.
  
- Microsoft SQL Server 2014 Enterprise (64-bit Edition) y le recomendamos que ejecute el Service Pack más reciente.
    
- Microsoft SQL Server 2012 Enterprise (64-bit Edition) y le recomendamos que ejecute el Service Pack más reciente.

> [!IMPORTANT]
> Para la actualización, queremos que garantice que en los servidores front-end se haya instalado al menos SQL Server 2012 SP1 antes de la actualización. [Este es un vínculo](https://www.microsoft.com/en-us/download/details.aspx?id=35575) al SP1 si deseas descargarlo inmediatamente.
  
Si necesita más información sobre la creación de reflejos de SQL, tenemos una alta disponibilidad del servidor de servicios de fondo en Skype empresarial Server 2015 tema. Configurar clústeres de SQL Server para Skype empresarial Server 2015 tiene los pasos para preparar el clúster. También hay vínculos adicionales sobre el clúster de conmutación por error para SQL, para [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)y [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Lo nuevo en la versión 2015 es la compatibilidad de SQL Always on. Es compatible y puede obtener más información sobre él en el tema [alta disponibilidad del servidor back-end en Skype empresarial server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn, y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015
<a name="Software"> </a>

Hay algunas cosas que tendrá que instalar o configurar para cualquier servidor que ejecute Skype empresarial Server 2015, y se enumeran a continuación. Se indican también los requisitos adicionales para roles de servidor específicos.
  
 **Todos los servidores:**
  
|**Software/Rol**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos los servidores de Skype empresarial Server necesitan Windows PowerShell 3,0 instalado.  <br/> • Si va a realizar la instalación en Windows Server 2012 o Windows Server 2012 R2, está configurado porque ya está allí.  <br/> • Si está realizando una actualización en Windows Server 2008 R2, puede descargar [Windows Management Framework 3,0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) para obtenerlo. <br/> **Sugerencia:** Una vez que tenga el PowerShell correcto en ese momento, confirme que está BuildVersion 6.2.9200.0 o más tarde en el símbolo del sistema de `$PSVersionTable`PowerShell y escriba. De este modo debería aparecer la información que necesita.  <br/> |
|Microsoft .NET Framework  <br/> |Servicios WCF es una **característica** que se instala como una característica de Windows, en **Administrador del servidor**, no es necesaria ninguna descarga. <br/> • Debe asegurarse de que, cuando instale esta característica, o si ya está instalada y que la está comprobando, que la opción de **activación de http** también está activada e instalada, así: <br/> ![Captura de pantalla que muestra la opción de activación HTTP en las características de .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)No te preocupes si recibes una ventana emergente adicional que te indica que es necesario instalar otras cosas para que se instale la activación de http. Es normal, haz clic en aceptar y continúa. Si no recibes esta ventana emergente, da por sentado que las cosas ya están instaladas y continúa.  <br/> Microsoft .NET Framework suele instalarse cuando se instalan Windows Server 2012 R2 o Windows Server 2016. Skype empresarial Server funciona con las siguientes versiones de Microsoft .NET Framework:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 o superior (para Skype empresarial Server CU 5 o versiones posteriores)  <br/>  Es probable que .NET Framework 3,5 se instale de forma predeterminada en su equipo Windows Server 2008 R2 (sin duda, asegúrese de que está seguro antes de actualizar), pero en realidad no en los servidores Windows Server 2012 o Windows Server 2012 R2 (para instalaciones nuevas). Para agregarla, necesitará tener acceso a la unidad de instalación o a los medios (el lugar desde donde se instaló Windows Server o dónde se encuentran los archivos de instalación). Después, puede instalarlo como una característica del administrador del servidor y apuntar a los medios de instalación (específicamente, la carpeta **\sources\sxs** ) cuando se los solicite y continuar con la instalación. <br/> |
|Media Foundation  <br/> |Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.  <br/> Todos los servidores front-end y los servidores Standard Edition usados en las conferencias requieren que el Windows Media Format Runtime ejecute los archivos de audio de Windows Media (. WMA) que las aplicaciones de los grupos estacionamiento, anuncio y respuesta de llamadas se reproducen para anuncios y música.  <br/> |
|Windows Identity Foundation  <br/> |Necesitamos Windows Identity Foundation 3,5 para admitir escenarios de autenticación de servidor a servidor para Skype empresarial Server 2015.  <br/> • Para Windows Server 2012 y Windows Server 2012 R2, no hay necesidad de descargar nada. Abra el **Administrador de servidores** y vaya a **Asistente para agregar roles y características**. **Windows Identity Foundation 3.5** aparece en la sección **Características**. Si está activada, está bien. Si es así, seleccione la opción y haga clic en Siguiente para que aparezca el botón **Instalar**. <br/> |
|Herramientas de administración remota del servidor  <br/> |Herramientas de administración de roles: herramientas AD DS y AD LDS  <br/> |
   
 **Los servidores front-end y el servidor Standard Edition también necesitan:**
  
|**Software/Rol**|**Detalles**|
|:-----|:-----|
|Servicios de Internet Information Server (IIS)  <br/> |IIS es necesario en todos los servidores front-end, así como en todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características HTTP comunes: documento predeterminado, errores HTTP, contenido estático  <br/> • Salud y diagnóstico: registro HTTP, herramientas de registro, seguimiento  <br/> • Rendimiento: compresión de contenido estático, compresión de contenido dinámico  <br/> • Seguridad: filtrado de solicitud, autenticación de asignación de certificado de cliente, autenticación de Windows  <br/> • Desarrollo de aplicaciones: extensibilidad de .NET 3,5, extensibilidad de .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensiones ISAPI, Filtros ISAPI  <br/> • Herramientas de administración: consola de administración de IIS, scripts y herramientas de administración de IIS  <br/> También se debe tener en cuenta que también se necesita acceso anónimo, pero se obtiene cuando se instala IIS, por lo que no se tiene un lugar para seleccionarlo en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, tendrá que instalar la característica **Media Foundation** en el administrador del **servidor**. Ahora, puede iniciar su instalación de Skype empresarial Server 2015 sin esta, pero se le solicitará que lo instale y, a continuación, debe reiniciar el servidor, antes de que la instalación de Skype empresarial Server 2015 continúe. Es preferible hacerlo antes. <br/> |
|Silverlight  <br/> |Puede instalar la última versión de Silverlight en [este vínculo](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Es posible que también tenga que habilitar la exploración de directorios si está usando un equilibrador de carga. De lo contrario, se cargará una página en blanco que el equilibrador de carga podría considerar un error. 

A modo de ayuda, aquí ofrecemos un script de ejemplo de PowerShell que puede ejecutar para automatizar esto:

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> El comando busca archivos de origen en un orden específico. Si está conectado, el comando accede a Windows Update. Sin embargo, si está desconectado, debe asegurarse de que los archivos de origen están disponibles para el comando. Para obtener más información sobre cómo usar PowerShell para instalar roles y características, consulte [instalar o desinstalar roles, servicios de rol o características](https://technet.microsoft.com/en-us/library/hh831809.aspx) no olvide ejecutar Windows Update de nuevo después de instalar los requisitos previos, incluso si usa el comando PowerShell.

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
    
(Si se lo está preguntando, el mismo módulo es el mismo que el de los servidores front-end y los servidores Standard Edition, con las herramientas de administración y compresión de contenido dinámico que han salido).
  
También contamos con el siguiente código de PowerShell para esto:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Los servidores de chat persistentes también necesitan:**
  
Message Queue Server, también denominado MSMQ. Es un componente de Windows Server y puede instalarlo en la sección Características del administrador del servidor. Si desea obtener más información sobre esto, consulte [instalar y administrar Message Queue Server](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Últimas reflexiones:**
  
No instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server u otro software de proveedores de servicios de niveles (LSP) Winsock (los firewalls de terceros o el software de inspección de redes antivirus se incluirán aquí). cualquiera de los servidores front-end o servidores de mediación independiente. Se ha visto un bajo rendimiento del tráfico de medios cuando se instala el software.
  

