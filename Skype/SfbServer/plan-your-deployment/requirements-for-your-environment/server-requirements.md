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
description: 'Resumen: prepare los servidores de Skype Empresarial Server 2015 con este tema. Hardware, sistema operativo, bases de datos, software, todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación e implementación correctas de la granja de servidores.'
ms.openlocfilehash: b1e7e37e46d0f3f547ed843ce2510d8445a34267
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832080"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos del servidor para Skype Empresarial Server 2015
 
**Resumen:** Prepare los servidores de Skype Empresarial Server 2015 con este tema. Hardware, sistema operativo, bases de datos, software, todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación e implementación correctas de la granja de servidores.

Si está buscando requisitos del entorno, como Active Directory, DNS o certificados, puede consultar los requisitos del entorno para el documento de [Skype Empresarial Server 2015.](environmental-requirements.md)
  
Como puede esperar, hay que realizar algunos preparativos antes de empezar a implementar Skype Empresarial Server 2015. Este artículo le ayudará a planear lo siguiente:
  
- [Hardware para Skype Empresarial Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operativos para Skype Empresarial Server 2015](server-requirements.md#OS)
  
- [Bases de datos back-end que funcionarán con Skype Empresarial Server 2015](server-requirements.md#DBs)
  
- [Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para Skype Empresarial Server 2015
<a name="Hardware"> </a>

Ahora que tiene la topología sin usar (y si no lo hace, puede consultar el tema Conceptos básicos de topología para Skype Empresarial [Server 2015),](../../plan-your-deployment/topology-basics/topology-basics.md) es el momento de pensar en los servidores. Los servidores de Skype Empresarial Server 2015 necesitarán hardware de 64 bits. A continuación se indican las recomendaciones para hardware. No son requisitos, pero reflejan los requisitos necesarios para un rendimiento óptimo. Tenemos documentación de planeación de capacidad que le ayudará a determinar si necesita más de esto, en función de sus circunstancias.
  
Hardware recomendado para servidores front-end, servidores back-end, servidores Standard Edition y servidores de chat persistente:
  
|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, núcleo hexadecimal, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de Skype Empresarial Server 2015.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos con RAID 1 y 6 con RAID 10).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una sola dirección IP).  <br/> Las configuraciones duales o  múltiples no son compatibles con los servidores front-end, los servidores back-end, los servidores Standard Edition y los servidores de chat persistente. <br/> Siempre y cuando no estén expuestos al sistema operativo y se estén utilizando para supervisar y administrar el hardware del servidor, puede tener sistemas de administración fuera de banda, como DRAC o DESC. Este escenario no constituye un servidor multialocución y es compatible.  <br/> |
   
Hardware recomendado para servidores perimetrales, servidores de mediación independientes, servidores de interoperabilidad de vídeo y directores:
  
|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, cuatro núcleos, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de Skype Empresarial Server 2015.  <br/> |
|Memoria  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración raid 1 de 2x).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 4 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una sola dirección IP).  <br/> No se admiten configuraciones  duales o múltiples para servidores y directores de interoperabilidad de vídeo. <br/> Los servidores perimetrales requerirán dos interfaces de red que son adaptadores de red de doble puerto, 1 Gbps o superior (o dos adaptadores de red emparejados, para un total de cuatro, cada par se combina con una sola dirección MAC y una única dirección IP, para un total de dos pares).  <br/> En los servidores de mediación independientes, se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para permitir la configuración de una dirección IP RTC específica.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operativos para Skype Empresarial Server 2015
<a name="OS"> </a>

Una vez que tenga el hardware en su lugar, deberá instalar sistemas operativos (SO). Se trata del sistema operativo que le permitirá instalar y usar correctamente Skype Empresarial Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (necesita la actualización acumulativa 9 o posterior de Skype Empresarial). <br/> |Windows Server 2016 (necesita la actualización acumulativa 5 o posterior de Skype Empresarial. Para obtener más información, [consulte KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Sistema operativo Windows Server 2012 R2 Datacenter con todas las actualizaciones necesarias instaladas.  <br/> |Sistema operativo Windows Server 2012 R2 Standard con todas las actualizaciones necesarias instaladas.  <br/> |
|Sistema operativo Windows Server 2012 Datacenter con todas las actualizaciones necesarias instaladas.  <br/> |Sistema operativo Windows Server 2012 Standard con todas las actualizaciones necesarias instaladas.  <br/> |
   
If it's not on this list, it won't work properly, please don't try it for new installations of Skype for Business Server 2015.

> [!NOTE]
> La actualización local del sistema operativo no es compatible con Lync Server 2013. Debe implementar un grupo independiente y migrar usuarios al nuevo grupo de servidores con un sistema operativo diferente. Todos los servidores de un grupo deben tener la misma versión del sistema operativo.
  
> [!NOTE]
> Es posible que hayas observado que Windows Server 2008 R2 no está en esta lista. Esto se debe a que recomendamos Windows Server 2012 R2 para todos los servidores nuevos que se usarán para SFB. Solo debe usar Windows Server 2008 R2 cuando tenga servidores existentes con Lync Server 2013 ya instalados y tenga previsto realizar una actualización local de ellos. Windows Server 2008 R2 alcanzó el final del ciclo de vida de soporte estándar el 13/13/2015 y alcanzará el final de su ciclo de vida de soporte técnico el 14/14/2020.
  
Además del service pack más reciente, querrá asegurarse de que las siguientes actualizaciones estén instaladas cuando sea relevante para usted:
  
- Para Windows Server 2012, el artículo de KB 2858668 debe instalarse antes de una actualización. [Consébalo aquí.](https://support.microsoft.com/kb/2858668/)
    
- Si tiene Windows Server 2012 R2, instale el artículo de KB 2982006 antes de actualizar. [Se encuentra aquí.](https://support.microsoft.com/kb/2982006/)
    
- Si estás actualizando en un cuadro de Windows Server 2008 R2 (consulta la nota anterior), querrás instalar primero el artículo de KB 2533623. [Está en este vínculo.](https://support.microsoft.com/kb/2533623/)
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de datos back-end que funcionarán con Skype Empresarial Server 2015
<a name="DBs"> </a>


Al instalar Skype Empresarial Server 2015 Standard Edition, tendrá que instalar SQL Server 2014 Express (edición de 64 bits) también automáticamente.
  
Skype Empresarial Server 2015 Enterprise Edition es un poco más complicado, pero la lista compatible está a continuación (todo es una edición de 64 bits, verá que no use ediciones de 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2017 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2016 Enterprise (edición de 64 bits) con Service Pack 1 o posterior, y debe ejecutarse con la actualización acumulativa 7 o posterior de Skype Empresarial (descargar la actualización acumulativa de[Skype](https://support.microsoft.com/help/3061064)Empresarial).  <br/> |Microsoft SQL Server 2014 Enterprise (edición de 64 bits) y debe ejecutarse con la actualización acumulativa 6 o posterior ( descargar la actualización acumulativa[6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.  <br/> |
|Microsoft SQL Server 2019 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2017 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. <br/> |Microsoft SQL Server 2016 Standard (edición de 64 bits) con Service Pack 1 o posterior, y debe ejecutarse con la actualización acumulativa 7 o posterior de Skype Empresarial (descargar la actualización acumulativa de[Skype](https://support.microsoft.com/help/3061064)Empresarial).  <br/> |Microsoft SQL Server 2014 Standard (edición de 64 bits) y debes ejecutar con la actualización acumulativa 6 o posterior (descarga la actualización acumulativa[6).](https://support.microsoft.com/kb/3031047/)  <br/> |Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.  <br/> |
   
Si no ves la edición SQL Server que quieres usar, no puedes usarla.
  
- También tendrá que instalar SQL Server Reporting Services para el rol de servidor de supervisión.
- Para una conexión SQL back-end bien conectada, la conexión al front-end de Skype Empresarial debe ser local y no a través de un vínculo de baja velocidad. 
- No SQL uso compartido de back-end entre dos o más grupos de servidores.

### <a name="microsoft-exchange-storage"></a>Almacenamiento de Microsoft Exchange
Los archivos de contenido de las reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos. Si desea almacenar datos de archivo de Skype Empresarial con datos de cumplimiento de Exchange, debe usar Exchange para su implementación de Exchange y asegurarse de que el tamaño de almacenamiento máximo admite el almacenamiento de los archivos de contenido de la reunión. Debe implementar Exchange antes de implementar y habilitar el archivado mediante la opción de integración de Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el archivado en Skype Empresarial Server 2015
  
El archivado no es un rol de servidor definido, no es necesario instalar un servidor independiente para el archivado. Los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada grupo de servidores front-end de Enterprise Edition y en cada servidor Standard Edition. Deberá habilitar y publicar la topología de archivado mediante el Generador de topologías.
    
El archivado usa el almacenamiento de archivos de Skype Empresarial Server para el almacenamiento temporal de archivos de contenido de reuniones, por lo que no se configura un almacén de archivos independiente para el archivado.
    
Microsoft Message Queue No es necesario.
    
Deberá configurar la infraestructura para el almacenamiento de archivado. Esto incluye elegir exchange o el almacenamiento de archivado mediante SQL Server.   Los requisitos de infraestructura de archivado de Skype Empresarial Server son los mismos que para la implementación de Skype Empresarial Server. Para obtener más información, [consulte Requisitos para su entorno de Skype Empresarial.](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 
  
> [!NOTE]
> Para admitir usuarios que no están en servidores de Exchange o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado mediante una base de datos de SQL Server de 64 bits. 
    
Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del proceso de instalación. Para obtener más información SQL Server, consulte [la documentación SQL Server datos.](https://go.microsoft.com/fwlink/p/?linkID=129045)
    
El aumento de carga del archivado puede ser significativo. Por lo tanto, debe asegurarse de que el espacio en disco sea adecuado para los servidores front-end en los que el archivado está habilitado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL creación de reflejos, SQL agrupación en clústeres y SQL AlwaysOn

You are able to use SQL Mirroring or SQL Clustering with Skype for Business Server 2015, it's supported. SQL creación de reflejos se configura a través del Generador de topologías de Skype Empresarial Server. Si tienes intención de configurar SQL clústeres, esto se realiza en SQL Server.
  
Asegúrese de que tiene una configuración activa/pasiva para SQL clústeres, ya que eso es lo que se admite. No compartas el nodo pasivo con ninguna otra instancia SQL cliente.
  
Puede tener lo siguiente para clústeres de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2019 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2017 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2016 Standard (edición de 64 bits) con Service Pack 1 o posterior. Se recomienda ejecutar con el Service Pack más reciente.

- Microsoft SQL Server 2014 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
    
-  Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

Dieciséis nodos:

- Microsoft SQL Server 2019 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2017 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

- Microsoft SQL Server 2016 Enterprise (edición de 64 bits) con Service Pack 1 o posterior. Se recomienda ejecutar con el Service Pack más reciente.
  
- Microsoft SQL Server 2014 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
    
- Microsoft SQL Server 2012 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

> [!IMPORTANT]
> Para la actualización, queremos asegurarse de que en los servidores front-end tiene al menos SQL Server 2012 SP1 instalado antes de la actualización. [Este es un vínculo a](https://www.microsoft.com/download/details.aspx?id=35575) SP1 si quiere descargarlo inmediatamente.
  
Si necesita obtener más información sobre SQL creación de reflejos, tenemos un tema de alta disponibilidad del servidor back-end en Skype Empresarial Server 2015. Configure SQL Server clustering for Skype for Business Server 2015 has the steps for getting clustering ready. También hay vínculos adicionales sobre clústeres de conmutación por error para SQL, [para 2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)y [2008.](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)
  
> [!NOTE]
> Una novedad de la versión 2015 es la compatibilidad con SQL AlwaysOn. Es compatible y puede leer más sobre él en el tema de alta disponibilidad del servidor [back-end en Skype Empresarial Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> SQL mirroring está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error son preferidos con Skype Empresarial Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que debe instalarse antes de una implementación de Skype Empresarial Server 2015
<a name="Software"> </a>

Hay algunas cosas que necesitará instalar o configurar para cualquier servidor que ejecute Skype Empresarial Server 2015 y se enumeran a continuación. Después, hay requisitos adicionales para roles de servidor específicos.

  
 **Todos los servidores:**
  
|**Software/rol**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos los servidores de Skype Empresarial Server Windows PowerShell 3.0 instalado.  <br/> • Si estás realizando la instalación en Windows Server 2012 o Windows Server 2012 R2, estás configurado, porque ya está ahí.  <br/> • Si está realizando una actualización en Windows Server 2008 R2, puede descargar [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) para obtenerlo. <br/> **Sugerencia:** Una vez que tenga el PowerShell correcto allí, confirme que es BuildVersion 6.2.9200.0 o posterior; para ello, vaya al símbolo del sistema de PowerShell y escriba `$PSVersionTable` . Esto debería incluir la información que necesita.  <br/> |
|Microsoft .NET Framework  <br/> |Los servicios WCF son **una característica** que se instala como una característica de Windows, en el Administrador del **servidor,** sin descargas necesarias. <br/> • Debe asegurarse de que, al instalar esta característica, o si ya está instalada y la está comprobando, también se comprueba e instala la opción de activación **HTTP,** como se muestra a continuación: <br/> ![Captura de pantalla que muestra la opción de activación HTTP en las características de .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) No se preocupe si recibe una ventana emergente adicional que dice que es necesario instalar algunas otras cosas para que se instale la activación HTTP. Eso es normal, haz clic en Aceptar y continúa. Si no obtiene esta ventana emergente, suponga que esas cosas ya están instaladas y vaya adelante.  <br/> Microsoft .NET Framework suele instalarse cuando se instala Windows Server 2012 R2 o Windows Server 2016. Skype Empresarial Server funciona con las siguientes versiones de Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (para Skype Empresarial Server CU 5 o versiones posteriores)  <br/> • .NET 4.7.2 (para skype empresarial server CU 6 o versiones posteriores)  <br/>  • .NET 4.8 (para Skype Empresarial Server CU 9 o versiones posteriores) <br/>  Es probable que .NET Framework 3.5 se instale de forma predeterminada en el equipo con Windows Server 2008 R2 (definitivamente, asegúrese de estar seguro antes de actualizar), pero en realidad no estará en los servidores de Windows Server 2012/Windows Server 2012 R2 (para nuevas instalaciones). Para agregarlo, necesitarás tener acceso a la unidad de instalación o a los medios (el lugar desde el que se instaló Windows Server o desde dónde están los archivos de instalación). A continuación, instálese como una característica del Administrador del servidor y apunte a los medios de instalación (específicamente la carpeta **\sources\sxs)** cuando se le pida y continúe con la instalación. <br/> |
|Media Foundation  <br/> |Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.  <br/> Todos los servidores front-end y los servidores Standard Edition usados para las conferencias requieren el tiempo de ejecución de Windows Media Format para ejecutar los archivos de Audio de Windows Media (.wma) que reproducen las aplicaciones Estacionamiento de llamadas, Anuncio y Grupo de respuesta para anuncios y música.  <br/> |
|Windows Identity Foundation  <br/> |Necesitamos Windows Identity Foundation 3.5 para admitir escenarios de autenticación de servidor a servidor para Skype Empresarial Server 2015.  <br/> • Para Windows Server 2012 y Windows Server 2012 R2, no es necesario descargar nada. Abra **el Administrador del** servidor y vaya al Asistente para agregar roles y **características.** **Windows Identity Foundation 3.5 aparece** en la **sección** Características. Si está activada, está bien. De lo contrario, selecciónelo y haga clic en Siguiente para llegar **al botón** Instalar. <br/> |
|Herramientas de administración de servidor remoto  <br/> |Herramientas de administración de roles: herramientas de AD DS y AD LDS  <br/> |
   
 **Los servidores front-end y el servidor Standard Edition también necesitan:**
  
|**Software/rol**|**Detalles**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |Se necesita IIS en todos los servidores front-end, así como en todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características http comunes: documento predeterminado, errores HTTP, contenido estático  <br/> • Estado y diagnóstico: registro HTTP, herramientas de registro, seguimiento  <br/> • Rendimiento: compresión de contenido estático, compresión de contenido dinámico  <br/> • Seguridad: filtrado de solicitudes, autenticación de asignación de certificados de cliente, autenticación de Windows  <br/> • Desarrollo de aplicaciones: extensibilidad de .NET 3.5, extensibilidad de .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, extensiones ISAPI, filtros ISAPI  <br/> • Herramientas de administración: Consola de administración de IIS, Scripts y herramientas de administración de IIS  <br/> También debemos tener en cuenta que el acceso anónimo también es necesario, pero lo obtiene al instalar IIS, por lo que no tiene un lugar donde seleccionarlo en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, tendrás que instalar la característica **Media Foundation** en el Administrador del **servidor.** Ahora, puede iniciar la instalación de Skype Empresarial Server 2015 sin esta, pero se le pedirá que la instale y, a continuación, reinicie el servidor antes de que continúe la instalación de Skype Empresarial Server 2015. Es mejor hacerlo con antelación. <br/> |
|Silverlight  <br/> |Puede instalar la versión más reciente de Silverlight en [este vínculo.](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> Es posible que también deba habilitar la exploración de directorios si usa un equilibrador de carga. De lo contrario, se cargará una página en blanco que el equilibrador de carga podría considerar un error. 

Para ayudarle, este es un script de PowerShell de ejemplo que puede ejecutar para automatizar esto:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> El comando busca archivos de origen en un orden específico. Si estás conectado, el comando tiene acceso a Windows Update. Sin embargo, si está sin conexión, debe asegurarse de que los archivos de origen están disponibles para el comando. Para obtener más información acerca del uso de PowerShell para instalar roles y características, vea Instalar o desinstalar [roles,](https://technet.microsoft.com/library/hh831809.aspx) servicios de roles o características No olvide volver a ejecutar Windows Update después de instalar los requisitos previos, incluso si usa el comando de PowerShell.

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
    
(Si se lo está preguntando, es el mismo conjunto de módulos que los servidores front-end y los servidores Standard Edition, sin las herramientas de administración y compresión de contenido dinámico).
  
Y tenemos código de PowerShell a continuación para esto también:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Los servidores de chat persistente también necesitan:**
  
Message Queue, que también se denomina MSMQ. Es un componente de Windows Server y puedes instalarlo en la sección Características del Administrador del servidor. Si desea obtener más información sobre esto, consulte [Instalar y administrar Message Queue.](https://technet.microsoft.com/library/cc771474.aspx)
  
 **Últimas ideas:**
  
No instale ningún software cliente de Microsoft Internet Security and Acceleration (ISA) Server ni ningún otro software winsock Layered Service Providers (LSP) (aquí se incluirían firewalls de terceros o software de inspección de red antivirus) en cualquiera de los servidores front-end o servidores de mediación independientes. Se ha visto un rendimiento deficiente del tráfico de medios cuando se instala ese software.
  

