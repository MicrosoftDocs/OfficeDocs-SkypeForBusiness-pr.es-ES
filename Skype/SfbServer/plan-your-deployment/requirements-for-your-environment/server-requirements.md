---
title: Requisitos del servidor para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumen: Prepare su Skype para servidores Business Server 2015 con este tema. Hardware, SO, bases de datos, software, todos los requisitos del sistema y recomendaciones están aquí para ayudar a garantizar una instalación correcta y la implementación de la granja de servidores.'
ms.openlocfilehash: 8a86c96554d7aa1be0597c5c82614cd43816540f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos del servidor para Skype Empresarial Server 2015
 
**Resumen:** prepare los servidores de Skype Empresarial Server 2015 con este tema. Hardware, sistemas operativos, bases de datos, software, todos los requisitos del sistema y recomendaciones están aquí para ayudar a garantizar una instalación e implementación correcta de la granja de servidores.
  
Como puede imaginar, hay algunos preparativos que debe hacer antes de empezar a implementar Skype para Business Server 2015. Este artículo lo guiará por el proceso de planificación de los siguientes elementos:
  
- [Hardware para Skype Empresarial Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operativos para Skype para Business Server 2015](server-requirements.md#OS)
  
- [Bases de datos back-end que funcionarán con Skype Empresarial Server 2015](server-requirements.md#DBs)
  
- [Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para Skype Empresarial Server 2015
<a name="Hardware"> </a>

Ahora que tiene la topología hacia abajo (y si no lo hace, puede consultar el tema [conceptos básicos de topología para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), es hora de pensar acerca de los servidores. Skype para servidores Business Server 2015 requiere hardware de 64 bits. Las recomendaciones de hardware se indican a continuación. Estos no son requisitos, pero reflejan los requisitos necesarios para obtener un rendimiento óptimo. Existe documentación de planificación de la capacidad que le ayudará a determinar si necesita un equipo superior, dependiendo de sus circunstancias.
  
Hardware recomendado para servidores frontales, Atrás servidores, servidores Standard Edition y servidores de charla persistente:
  
|**Componente de hardware**|**Recomienda**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, seis núcleos y 2,26 gigahercios (GHz) o superior.  <br/> Procesadores Intel Itanium no son compatibles para Skype para funciones de servidor de negocios 2015.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |O  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos con RAID 1 y 6 con RAID 10).   <br/> O bien  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Configuraciones de dobles o multitarjeta son **no** admite servidores frontales, servidores de fondo detrás, Standard Edition, los servidores y los servidores de charla persistente. <br/> Siempre y cuando no estén expuestos al sistema operativo y estén siendo utilizados para supervisar y administrar el hardware del servidor, puede tener sistemas de administración extraordinaria, como DRAC o ILO. Este escenario no constituye un servidor de múltiples ubicaciones, y es un escenario compatible.<br/> |
   
Hardware recomendado para servidores perimetrales, servidores de mediación independientes, servidores de vídeo interoperabilidad y directores:
  
|**Componente de hardware**|**Recomienda**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, de cuatro núcleos, 2,26 gigahercios (GHz) o superior.  <br/> Procesadores Intel Itanium no son compatibles para Skype para funciones de servidor de negocios 2015.  <br/> |
|Memoria  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |O  <br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración de 2 unidades RAID 1).  <br/> O bien  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 4 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Configuraciones de doble o multitarjeta **no** admite servidores de vídeo interoperabilidad y directores. <br/> Los servidores Edge necesitan dos interfaces de red que sean adaptadores de red de puerto doble, 1 Gbps o superior (o dos adaptadores de red emparejados para un total de cuatro; cada pareja debe formar un equipo con una sola dirección MAC y una sola dirección IP, para un total de dos parejas).  <br/> En independiente se admite la instalación de tarjetas de interfaz de red adicionales (NIC) para permitir la configuración de una dirección IP PSTN específica de servidores de mediación.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operativos para Skype para Business Server 2015
<a name="OS"> </a>

Una vez que el hardware en su lugar, debe instalar los sistemas operativos (SO). Éstos son el sistema operativo que le permitirá instalar y utilizar correctamente Skype para Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|2012 R2 Datacenter sistema operativo Windows Server con requiere todas las actualizaciones instaladas.  <br/> |Windows Server 2012 R2 OS estándar con requiere todas las actualizaciones instaladas.  <br/> |
|SO de Windows Server 2012 Datacenter con requiere todas las actualizaciones instaladas.  <br/> |Windows Server 2012 OS estándar con requiere todas las actualizaciones instaladas.  <br/> |
   
Si no está en esta lista, no funcionará correctamente, por favor no lo pruebe para las nuevas instalaciones de Skype para Business Server 2015.
  
> [!NOTE]
> Habrá reparado en que Windows Server 2008 R2 no está en la lista. Se debe a que recomendamos utilizar Windows Server 2012 R2 en los nuevos servidores para SE. Solo debe usar Windows Server 2008 R2 si tiene servidores existentes con Lync Server 2013 ya instalado y pretende realizar una actualización in situ. Windows Server 2008 R2 alcanzó el fin de su ciclo de soporte el 13 de enero de 2015. 
  
Además del último service pack, asegúrese de que las siguientes actualizaciones están instaladas donde corresponda:
  
- Antes de una actualización, es preciso instalar el artículo de Knowledge Base 2858668 para Windows Server 2012. [Obténgalo aquí](https://support.microsoft.com/en-us/kb/2858668/).
    
- Si tiene Windows Server 2012 R2, instale el artículo de Knowledge Base 2982006 antes de la actualización. [Se encuentra aquí](https://support.microsoft.com/en-us/kb/2982006/).
    
- Si está actualizando a partir de Windows Server 2008 R2 (consulte la nota anterior), es preciso instalar primero el artículo de Knowledge Base 2533623. [Es en este vínculo](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de datos back-end que funcionarán con Skype Empresarial Server 2015
<a name="DBs"> </a>

Al instalar Skype para 2015 Business Server Standard Edition, tendrá Express de SQL Server de 2014 (64-bit edition) se instala automáticamente también.
  
Skype para 2015 Business Server Enterprise es un poco más complicado, pero la lista admitida está por debajo (todo es 64-bit edition, observará, por favor, no utilice las ediciones de 32 bits):
  
||||
|:-----|:-----|:-----|
|2014 Enterprise (64-bit edition) de Microsoft SQL Server y se debe ejecutar con la actualización acumulativa 6 o posterior ([descargar actualización acumulativa 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64-bit edition) y se recomienda la ejecución con el service pack más reciente.  <br/> |Microsoft SQL Server 2008 R2 Enterprise (64-bit edition) y se recomienda la ejecución con el service pack más reciente.  <br/> |
|Microsoft SQL Server 2014 estándar (64-bit edition) y se debe ejecutar con la actualización acumulativa 6 o posterior ([descargar actualización acumulativa 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 estándar (64-bit edition) y se recomienda la ejecución con el service pack más reciente.  <br/> |Microsoft SQL Server 2008 R2 Standard (64-bit edition) y se recomienda la ejecución con el último service pack  <br/> |
   
Si no ve la edición de SQL Server que desea utilizar enumerados aquí, no puede usarlo.
  
> [!NOTE]
> También va a necesitar instalar SQL Server Reporting Services para la función de servidor de supervisión, pero necesitamos saber que esto no va a ser compatibles con SQL siempre en hasta post-RTM. 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Mirroring, SQL Clustering y SQL Always On

Puede utilizar el reflejo de SQL o SQL Clustering con Skype para Business Server 2015, que es compatible. SQL reflejo establecido a través del Skype para el generador de topología de servidor empresarial. Si eres intención sobre la configuración de clústeres de SQL, que se realiza en SQL Server.
  
Asegúrese de que tiene una configuración activo/pasivo para clústeres de SQL, ya es lo que se admite. No comparta el nodo pasivo con cualquier otra instancia SQL.
  
Puede usar lo siguiente para el clúster de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2014 estándar (64-bit edition) y se recomienda la ejecución con el service pack más reciente.
    
-  Microsoft SQL Server 2012 estándar (64-bit edition) y se recomienda la ejecución con el service pack más reciente.
    
- Microsoft SQL Server 2008 R2 Standard (64-bit edition) y se recomienda la ejecución con el service pack más reciente.
    
Dieciséis nodos:
  
- 2014 Enterprise (64-bit edition) de Microsoft SQL Server y se recomienda la ejecución con el service pack más reciente.
    
- Microsoft SQL Server 2012 Enterprise (64-bit edition) y se recomienda la ejecución con el service pack más reciente.
    
- Microsoft SQL Server 2008 R2 Enterprise (64-bit edition) y se recomienda la ejecución con el service pack más reciente.
    
> [!IMPORTANT]
> Para actualizar, queremos que para garantizar que en los servidores frontales tiene al menos el Service Pack 1 de SQL Server 2012 se instala antes de la actualización. [Éste es un vínculo](https://www.microsoft.com/en-us/download/details.aspx?id=35575) a SP1 si desea descargarlo inmediatamente.
  
Si desea leer más sobre la creación de reflejo de SQL, tenemos una alta disponibilidad de servidor nuevo en Skype para Business Server 2015 tema. Configurar organización por clústeres de SQL Server para Skype para Business Server 2015 tiene los pasos para que está preparada para clústeres. También hay más vínculos en caso de failover clustering de SQL, para [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)y [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx).
  
> [!NOTE]
> Una novedad de esta versión es la compatibilidad con SQL Always On. Es compatible y puede leer más acerca de él en el tema del [nuevo servidor de alta disponibilidad en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015
<a name="Software"> </a>

Hay algunas cosas que va a necesitar instalar o configurar para cualquier servidor que ejecute Skype para Business Server 2015 y se enumeran a continuación. Se indican también los requisitos adicionales para roles de servidor específicos.
  
 **Todos los servidores:**
  
|**Software y funciones**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Skype todos los servidores de Business Server tenga instalado Windows PowerShell 3.0.  <br/> • Si está realizando la instalación en Windows Server 2012 o R2 de Windows Server 2012, listo, porque ya no existe.  <br/> • Si está realizando una actualización de Windows Server 2008 R2, puede descargar [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) para obtenerlo. <br/> **Sugerencia:** Una vez que tiene la correcta PowerShell en allí, confirme que se trata de la versión de compilación 6.2.9200.0 o posterior yendo a la PowerShell preguntar y escribir `$PSVersionTable`. De este modo debería aparecer la información que necesita.  <br/> |
|Microsoft .NET Framework  <br/> |Los servicios de WCF es una **característica** que ha instalado como una característica de Windows, en el **Administrador del servidor**, no hay descargas necesarios. <br/> • Necesita para asegurarse de que, al instalar esta característica, o si ya está instalado y se está comprobando, que la opción de **Activación HTTP** también se comprueban e instalada, de este modo: <br/> ![Captura de pantalla que muestra la opción de activación de HTTP en las características de.NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)No se preocupe si aparece una ventana emergente adicional indicando que algunas cosas deben instalarse para que la activación de HTTP para instalarse. Es normal, haga clic en Aceptar y continúe. Si no recibe este emergente, asumir esas cosas ya están instaladas y siga adelante.  <br/> Microsoft.NET Framework se instala normalmente cuando se instalan Windows Server 2012 R2 o Windows Server 2016. Skype para Business Server funciona con las siguientes versiones de Microsoft.NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • 4.7 de .NET (por Skype para Business Server CU 5 o versiones posteriores)  <br/>  .NET Framework 3.5 es probable que se instalará de forma predeterminada en el equipo de Windows Server 2008 R2 (definitivamente Compruebe que antes de actualizar), pero en realidad no será en los servidores de Windows Server 2012 y Windows Server 2012 R2 (para las instalaciones nuevas). Para agregar en, tendrá acceso a la unidad de instalación o los medios de comunicación (el lugar que se instaló Windows Server desde o dónde están ahora los archivos de instalación). Siga adelante e instálelo como una característica desde el Administrador de servidores y seleccione el medio de instalación (concretamente, la carpeta **\sources\sxs**) cuando se le pida. Continúe y complete la instalación. <br/> |
|Media Foundation  <br/> |Para 2016 de Windows Server, Windows Server 2012 y Windows Server 2012 R2 Windows Media Format Runtime se instala con Microsoft Media Foundation.  <br/> Todos los servidores de servidores frontales y Standard Edition utilizados para conferencias requieren Windows Media Format Runtime ejecutar los archivos Windows Media Audio (.wma) que se reproducen las aplicaciones llamada Park, anuncio y el grupo de respuesta para anuncios y música.  <br/> |
|Windows Identity Foundation  <br/> |Es necesario Windows Identity Foundation 3.5 para admitir escenarios de autenticación de servidor a servidor de Skype para Business Server 2015.  <br/> • Para Windows Server 2012 y Windows Server R2 de 2012, no es necesario descargar nada. Abra el **Administrador de servidores** y vaya a **Asistente para agregar roles y características**. **Windows Identity Foundation 3.5** aparece en la sección **Características**. Si está activada, todo está bien. Si es así, seleccione la opción y haga clic en Siguiente para que aparezca el botón **Instalar**. <br/> |
|Herramientas de administración remota del servidor  <br/> |Herramientas de administración de roles: herramientas AD DS y AD LDS  <br/> |
   
 **También necesitará un servidor Standard Edition y servidores de extremo frontal:**
  
|**Software y funciones**|**Detalles**|
|:-----|:-----|
|Servicios de Internet Information Server (IIS)  <br/> |IIS es necesario en todos los servidores frontales, así como todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características HTTP comunes: contenido estático del documento, errores HTTP, predeterminado  <br/> • Salud y diagnóstico: registro, herramientas de registro, seguimiento de HTTP  <br/> • Performance: compresión de contenido estático, la compresión de contenido dinámico  <br/> • Seguridad: filtrado de solicitudes, autenticación de asignaciones de certificado de cliente, la autenticación de Windows  <br/> • Desarrollo de aplicaciones: extensibilidad de .NET 3.5 4.5 de extensibilidad de. NET, ASP.NET 3.5, ASP.NET 4.5, extensiones ISAPI, filtros ISAPI  <br/> • Herramientas de administración: consola de administración de IIS, las secuencias de comandos de administración de IIS y herramientas  <br/> También debemos mencionar también es necesario el acceso anónimo, pero que aparece al instalar IIS, para que no tenga un lugar para que seleccione en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para 2016 de Windows Server, Windows Server 2012 y Windows Server 2012 R2, debe instalar la característica de **Media Foundation** en el **Administrador del servidor**. Ahora, realmente puede iniciar su Skype para la instalación de Business Server 2015 sin este uno, pero se le pedirá para instalarlo y, a continuación, reiniciar el servidor, antes de la Skype para Business Server 2015 instalar continúa. Es preferible hacerlo antes. <br/> |
|Silverlight  <br/> |Puede instalar la versión más reciente de Silverlight en [este vínculo](https://www.microsoft.com/silverlight/).  <br/> |
   
A modo de ayuda, aquí ofrecemos un script de ejemplo de PowerShell que puede ejecutar para automatizar esto:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Los directores también deberán:**
  
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
    
(Si se lo está preguntando, es el mismo módulo que establece que los servidores Standard Edition y de servidores frontales, con la compresión de contenido dinámico y omitiera las herramientas de administración).
  
También contamos con el siguiente código de PowerShell para esto:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Servidores de charla persistente también necesitan:**
  
Message Queue Server, también denominado MSMQ. Es un componente de Windows Server, y se puede instalar en la sección de características en el administrador del servidor. Si desea obtener más información, consulte [instalar y administrar Message Queue Server](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Últimas reflexiones:**
  
No instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server o cualquier otro software de proveedores de servicios por niveles (LSP) de Winsock (cualquier software de inspección de red antivirus o firewalls de terceros podría incluirse aquí) en ninguno de los servidores front-end o servidores de mediación de independiente. Rendimiento de tráfico deficiente de los medios de comunicación se ha visto cuando dicho software instalado.
  

