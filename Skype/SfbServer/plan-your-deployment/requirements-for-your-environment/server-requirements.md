---
title: Requisitos del servidor para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumen: prepare los servidores Skype Empresarial Server 2015 con este tema. Hardware, sistema operativo, bases de datos, software, todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación e implementación correctas de la granja de servidores.'
ms.openlocfilehash: 8dd32e9d27120e4809cb2f5ce557657e0b4864d60d7095a5e2eb799dc7fdfc83
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276615"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos del servidor para Skype Empresarial Server 2015
 
**Resumen:** Prepare los servidores Skype Empresarial Server 2015 con este tema. Hardware, sistema operativo, bases de datos, software, todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación e implementación correctas de la granja de servidores.

Si está buscando requisitos de entorno, como Active Directory, DNS o certificados, puede consultar el documento Requisitos del entorno para Skype Empresarial Server [2015.](environmental-requirements.md)
  
Como es de esperar, hay algunos preparativos que debe realizar antes de empezar a implementar Skype Empresarial Server 2015. Este artículo le ayudará a planear lo siguiente:
  
- [Hardware para Skype Empresarial Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operativos para Skype Empresarial Server 2015](server-requirements.md#OS)
  
- [Bases de datos back-end que funcionarán con Skype Empresarial Server 2015](server-requirements.md#DBs)
  
- [Software que debe instalarse antes de una implementación Skype Empresarial Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para Skype Empresarial Server 2015
<a name="Hardware"> </a>

Ahora que tiene la topología abajo (y si no lo hace, puede consultar el tema [Topology Basics for Skype Empresarial Server 2015),](../../plan-your-deployment/topology-basics/topology-basics.md) es hora de pensar en los servidores. Skype Empresarial Server servidores de 2015 necesitarán hardware de 64 bits. A continuación se indican nuestras recomendaciones para hardware. No son requisitos, pero reflejan los requisitos necesarios para un rendimiento óptimo. Tenemos documentación de planeación de capacidad que le ayudará a determinar si necesita más de esto, en función de sus circunstancias.
  
Hardware recomendado para servidores front-end, servidores back-end, servidores Standard Edition servidores y servidores de chat persistente:
  
|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, hex-core, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles Skype Empresarial Server roles de 2015.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos que usan RAID 1 y 6 con RAID 10).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una única dirección IP).  <br/> Las configuraciones duales o  multialod no son compatibles con servidores front-end, servidores back-end, servidores Standard Edition y servidores de chat persistente. <br/> Siempre que no estén expuestos al sistema operativo y se estén utilizando para supervisar y administrar el hardware del servidor, puede tener fuera de los sistemas de administración de bandas, como DRAC o ILO. Este escenario no constituye un servidor multialocución y es compatible.  <br/> |
   
Hardware recomendado para servidores perimetrales, servidores de mediación independientes, servidores de interoperabilidad de vídeo y directores:
  
|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, cuatro núcleos, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles Skype Empresarial Server roles de 2015.  <br/> |
|Memoria  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración de 2x RAID 1).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 4 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una única dirección IP).  <br/> Las configuraciones duales o multialod no son **compatibles** con los servidores y directores de interoperabilidad de vídeo. <br/> Los servidores perimetrales necesitarán dos interfaces de red que sean adaptadores de red de doble puerto, 1 Gbps o superior (o dos adaptadores de red emparejados, para un total de cuatro, cada par se combina con una sola dirección MAC y una sola dirección IP, para un total de dos pares).  <br/> En servidores de mediación independientes, se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para permitir la configuración de una dirección IP RTC específica.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operativos para Skype Empresarial Server 2015
<a name="OS"> </a>

Una vez que haya instalado el hardware, deberá instalar sistemas operativos (SO). Estos son los sos que le permitirán instalar y usar correctamente Skype Empresarial Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (necesita Skype Empresarial acumulativa 9 o posterior). <br/> |Windows Server 2016 (necesita una Skype Empresarial acumulativa 5 o posterior. Para obtener más información, [compruebe KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 Sistema operativo de centro de datos R2 con todas las actualizaciones necesarias instaladas.  <br/> |Windows Server 2012 R2 Sistema operativo estándar con todas las actualizaciones necesarias instaladas.  <br/> |
|Windows Server 2012 Datacenter Sistema operativo con todas las actualizaciones necesarias instaladas.  <br/> |Windows Server 2012 Standard Sistema operativo con todas las actualizaciones necesarias instaladas.  <br/> |
   
Si no está en esta lista, no funcionará correctamente, no lo intente para las nuevas instalaciones de Skype Empresarial Server 2015.

> [!NOTE]
> La actualización local del sistema operativo no se admite con Lync Server 2013. Debe implementar un grupo de servidores independiente y migrar usuarios al nuevo grupo con un sistema operativo diferente. Todos los servidores de un grupo deben tener la misma versión del sistema operativo.
  
> [!NOTE]
> Es posible que haya notado Windows server 2008 R2 no está en esta lista. Esto se debe a que recomendamos Windows Server 2012 R2 para que todos los servidores nuevos se usen para SFB. Solo debe usar Windows Server 2008 R2 cuando ya haya instalado servidores existentes con Lync Server 2013 y tenga la intención de realizar una actualización local de ellos. Windows Server 2008 R2 llegó al final del ciclo de vida de soporte técnico estándar el 13/13/2015 y llegará al final de su ciclo de vida de soporte técnico el 14/14/2020.
  
Además del service pack más reciente, querrás asegurarte de que las siguientes actualizaciones estén instaladas cuando sea relevante para ti:
  
- Por Windows Server 2012, el artículo de KB 2858668 debe instalarse antes de una actualización. [Obtenga aquí](https://support.microsoft.com/kb/2858668/).
    
- Si ha actualizado Windows Server 2012 R2, instale el artículo de KB 2982006 antes de actualizar. [Se encuentra aquí](https://support.microsoft.com/kb/2982006/).
    
- Si está actualizando en un cuadro de Windows Server 2008 R2 (consulte la nota anterior), primero querrá instalar el artículo kb 2533623. [Está en este vínculo](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de datos back-end que funcionarán con Skype Empresarial Server 2015
<a name="DBs"> </a>


Al instalar Skype Empresarial Server 2015 Standard Edition, tendrás que SQL Server 2014 Express (edición de 64 bits) también se instala automáticamente.
  
Skype Empresarial Server 2015 Enterprise Edition es un poco más complicado, pero la lista admitida está a continuación (todo es una edición de 64 bits, se dará cuenta, no use ediciones de 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2017 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2016 Enterprise (edición de 64 bits) con Service Pack 1 o posterior, y debe ejecutar con una actualización acumulativa 7 o posterior de Skype Empresarial ( descargar[Skype Empresarial actualización](https://support.microsoft.com/help/3061064)acumulativa ).  <br/> |Microsoft SQL Server 2014 Enterprise (edición de 64 bits) y debe ejecutar con la actualización acumulativa 6 o posterior ( descargar la actualización acumulativa[6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.  <br/> |
|Microsoft SQL Server 2019 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2017 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2016 Standard (edición de 64 bits) con Service Pack 1 o posterior, y debe ejecutar con una actualización acumulativa 7 o posterior de Skype Empresarial ( descargar[Skype Empresarial actualización](https://support.microsoft.com/help/3061064)acumulativa ).  <br/> |Microsoft SQL Server 2014 Standard (edición de 64 bits) y debe ejecutar con la actualización acumulativa 6 o posterior ( descargar la actualización acumulativa[6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.  <br/> |
   
Si no ves la edición SQL Server que quieres usar, no puedes usarla.
  
- También tendrá que instalar el SQL Server Reporting Services para el rol servidor de supervisión.
- Para un back-end SQL bien conectado, la conexión al front-end Skype Empresarial debe ser local y no a través de un vínculo de baja velocidad. 
- No se SQL uso compartido entre dos o más grupos de servidores.

### <a name="microsoft-exchange-storage"></a>Almacenamiento Exchange Microsoft
Los archivos de contenido de las reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos. Si desea almacenar datos de archivo Skype Empresarial con datos de cumplimiento de Exchange, debe usar Exchange para la implementación de Exchange y asegurarse de que el tamaño máximo de almacenamiento admite el almacenamiento de los archivos de contenido de la reunión. Debe implementar Exchange antes de implementar y habilitar el archivado mediante la opción de integración Exchange Microsoft. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para archivado en Skype Empresarial Server 2015
  
El archivado no es un rol de servidor definido, no es necesario instalar un servidor independiente para el archivado. Los agentes de recopilación de datos unificados se instalan y activan automáticamente en Enterprise Edition grupo de servidores front-end y en todos los Standard Edition servidor. Deberá habilitar y publicar la topología de archivado mediante el Generador de topologías.
    
El archivado usa el Skype Empresarial Server de archivos para el almacenamiento temporal de archivos de contenido de reuniones, por lo que no se configura un almacén de archivos independiente para el archivado.
    
Microsoft Message Queue No es necesario.
    
Deberá configurar la infraestructura para el almacenamiento de archivado. Esto incluye elegir entre el almacenamiento Exchange o el almacenamiento de archivado mediante SQL Server.   Skype Empresarial Server Los requisitos de infraestructura de archivado son los mismos que para la implementación de Skype Empresarial Server. Para obtener más información, vea [Requirements for your Skype Empresarial environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Para admitir usuarios que no se encuentran en servidores Exchange o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado con una base de datos SQL Server de 64 bits. 
    
Debe configurar las plataformas SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del proceso de instalación. Para obtener más información SQL Server, consulte [la SQL Server .](/sql/sql-server/)
    
El aumento de carga para el archivado puede ser significativo. Por lo tanto, debe asegurarse de que el espacio en disco sea adecuado para los servidores front-end en los que está habilitado el archivado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Creación de reflejos, SQL clústeres y SQL AlwaysOn

Puede usar la creación SQL creación SQL creación de SQL con Skype Empresarial Server 2015, que es compatible. SQL La creación de reflejos se configura a través Skype Empresarial Server generador de topologías. Si tiene la intención de configurar SQL clustering, se realiza en SQL Server.
  
Asegúrese de que tiene una configuración activa/pasiva para la SQL clústeres, ya que eso es lo que se admite. No comparta el nodo pasivo con ninguna otra SQL instancia.
  
Puede tener lo siguiente para clústeres de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2019 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2017 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2016 Standard (edición de 64 bits) con Service Pack 1 o posterior. Se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2014 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
    
-  Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

Dieciséis nodos:

- Microsoft SQL Server 2019 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2017 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2016 Enterprise (edición de 64 bits) con Service Pack 1 o posterior. Se recomienda ejecutar con el service pack más reciente.
  
- Microsoft SQL Server 2014 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
    
- Microsoft SQL Server 2012 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

> [!IMPORTANT]
> Para la actualización, queremos que se asegure de que en los servidores front-end tiene al menos SQL Server 2012 SP1 instalado antes de la actualización. [Este es un vínculo a](https://www.microsoft.com/download/details.aspx?id=35575) SP1 si quieres descargarlo inmediatamente.
  
Si necesita obtener más información sobre SQL creación de reflejo, tenemos un tema de alta disponibilidad del servidor back-end en Skype Empresarial Server 2015. Configure SQL Server clustering for Skype Empresarial Server 2015 has the steps for getting clustering ready. También hay vínculos adicionales sobre clústeres de conmutación por error para SQL, [para 2014](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation), [2012](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))y [2008](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)).
  
> [!NOTE]
> La nueva versión de 2015 es compatible con SQL AlwaysOn. Se admite y puede leer más sobre él en el tema [Back End Server high availability in Skype Empresarial Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> SQL La creación de reflejos está disponible Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error se prefieren Skype Empresarial Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que debe instalarse antes de una implementación Skype Empresarial Server 2015
<a name="Software"> </a>

Hay algunas cosas que tendrá que instalar o configurar para cualquier servidor que ejecute Skype Empresarial Server 2015 y se enumeran a continuación. Después, hay requisitos adicionales para roles de servidor específicos.

  
 **Todos los servidores:**
  
|**Software/Rol**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos Skype Empresarial Server servidores necesitan Windows PowerShell 3.0 instalado.  <br/> • Si está realizando la instalación en Windows Server 2012 o Windows Server 2012 R2, está configurado, porque ya está ahí.  <br/> • Si está realizando una actualización en Windows Server 2008 R2, puede descargar la [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) para obtenerla. <br/> **Sugerencia:** Una vez que tenga el PowerShell correcto, confirme que se trata de BuildVersion 6.2.9200.0 o posterior yendo al símbolo del sistema de PowerShell y escribiendo `$PSVersionTable` . Esto debería incluir la información que necesita.  <br/> |
|Microsoft .NET Framework  <br/> |Los servicios WCF **son una característica** que se instala como una característica Windows, en **El** Administrador del servidor, no se necesitan descargas. <br/> • Debe asegurarse de que, al instalar esta característica, o si ya está instalada y está comprobando, que la opción activación **HTTP** también está activada e instalada, como se muestra a continuación: <br/> ![Captura de pantalla que muestra la opción activación HTTP .NET Framework características de 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) No se preocupe si obtiene una ventana emergente adicional que dice que es necesario instalar otras cosas para que se instale la activación HTTP. Eso es normal, haz clic en Aceptar y sigue adelante. Si no obtienes esta ventana emergente, asume que esas cosas ya están instaladas y sigue adelante.  <br/> Microsoft .NET Framework suele instalarse cuando Windows Server 2012 R2 o Windows Server 2016 se instalan. Skype Empresarial Server funciona con las siguientes versiones de Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (para Skype Empresarial Server CU 5 o versiones posteriores)  <br/> • .NET 4.7.2 (para Skype Empresarial Server CU 6 o versiones posteriores)  <br/>  • .NET 4.8 (para Skype Empresarial Server CU 9 o versiones posteriores) <br/>  .NET Framework 3.5 probablemente se instalará de forma predeterminada en el equipo de Windows Server 2008 R2 (definitivamente asegúrese de estar seguro antes de actualizar), pero en realidad no estará en los servidores Windows Server 2012/Windows Server 2012 R2 (para nuevas instalaciones). Para agregarlo, necesitarás acceso a la unidad de instalación o a los medios (el lugar desde el que se instaló el servidor de Windows o desde donde están los archivos de instalación ahora). A continuación, continúe e instálelo como una característica del Administrador de servidores y señale a los medios de instalación (específicamente la carpeta **\sources\sxs)** cuando se le pida y continúe con su instalación. <br/> |
|Media Foundation  <br/> |Por Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2 Windows Media Format Runtime instala con Microsoft Media Foundation.  <br/> Todos los servidores front-end y los servidores Standard Edition usados para conferencias requieren Windows Media Format Runtime para ejecutar los archivos de audio multimedia (.wma) de Windows que las aplicaciones de estacionamiento de llamadas, anuncio y grupo de respuesta reproducen para anuncios y música.  <br/> |
|Windows Identity Foundation  <br/> |Necesitamos Windows Identity Foundation 3.5 para admitir escenarios de autenticación de servidor a servidor para Skype Empresarial Server 2015.  <br/> • Para Windows Server 2012 y Windows Server 2012 R2, no es necesario descargar nada. Abra **el Administrador del** servidor y vaya al Asistente para agregar roles y **características.** **Windows Identity Foundation 3.5** aparece en la **sección** Características. Si está comprobado, estás bien. De lo contrario, selecciónelo y haga clic en Siguiente para llegar al **botón** Instalar. <br/> |
|Herramientas de administración de servidor remoto  <br/> |Herramientas de administración de roles: herramientas de AD DS y AD LDS  <br/> |
   
 **Los servidores front-end Standard Edition servidor también necesitan:**
  
|**Software/Rol**|**Detalles**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS es necesario en todos los servidores front-end, así como en todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características HTTP comunes: documento predeterminado, errores HTTP, contenido estático  <br/> • Estado y diagnóstico: registro HTTP, herramientas de registro, seguimiento  <br/> • Rendimiento: compresión de contenido estático, compresión dinámica de contenido  <br/> • Seguridad: filtrado de solicitudes, autenticación de asignación de certificados de cliente, Windows autenticación  <br/> • Desarrollo de aplicaciones: extensibilidad de .NET 3.5, extensibilidad de .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, extensiones ISAPI, filtros ISAPI  <br/> • Herramientas de administración: Consola de administración de IIS, Scripts y herramientas de administración de IIS  <br/> También debemos tener en cuenta que el acceso anónimo también es necesario, pero se obtiene al instalar IIS, por lo que no tiene un lugar para seleccionarlo en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, deberá instalar la característica Media **Foundation** en **el Administrador del servidor**. Ahora, en realidad puede iniciar la instalación de Skype Empresarial Server 2015 sin esta, pero se le pedirá que lo instale y, a continuación, reinicie el servidor, antes de que continúe la instalación de Skype Empresarial Server 2015. Es mejor hacerlo con antelación. <br/> |
|Silverlight  <br/> |Puede instalar la versión más reciente de Silverlight en [este vínculo](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Es posible que también necesite habilitar la exploración de directorios si usa un equilibrador de carga. De lo contrario, se cargará una página en blanco que el equilibrador de carga podría considerar un error. 

Para ayudarle, este es un script de PowerShell de ejemplo que puede ejecutar para automatizar esto:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> El comando busca archivos de origen en un orden específico. Si está en línea, el comando tiene acceso a Windows Update. Sin embargo, si está sin conexión, debe asegurarse de que los archivos de origen están disponibles para el comando. Para obtener más información acerca del uso de PowerShell para instalar roles y características, vea [Install or Uninstall Roles, Role Services o Features](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.

 **Los directores también necesitan:**
  
IIS, con los siguientes módulos seleccionados:
  
- Características comunes de HTTP
    
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
    
  - Filtrado de solicitudes
    
  - Autenticación por asignación de certificados de clientes
    
  - Autenticación de Windows
    
- Desarrollo de aplicaciones
    
  - Extensibilidad de .NET 3.5
    
  - Extensibilidad de .NET 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - Extensión ISAPI
    
  - Filtros ISAPI
    
(Si se lo está preguntando, es el mismo conjunto de módulos que los servidores front-end y los servidores Standard Edition, con las herramientas de administración y compresión de contenido dinámicos que se han quedado fuera).
  
Y también tenemos código de PowerShell a continuación:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Los servidores de chat persistente también necesitan:**
  
Message Queue Queue, que también se denomina MSMQ. Es un componente Windows server y puede instalarlo en la sección Características del Administrador del servidor. Si desea obtener más información sobre esto, consulte [Instalación y administración de Message Queue Queue.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11))
  
 **Últimas ideas:**
  
No instale ningún software cliente del servidor de Microsoft Internet Security and Acceleration (ISA) ni ningún otro software de proveedores de servicios en capas de Winsock (LSP) (aquí se incluirían firewalls de terceros o software de inspección de red antivirus) en cualquiera de los servidores front-end o servidores de mediación independientes. El rendimiento del tráfico de medios deficiente se ha visto cuando se instala ese software.
