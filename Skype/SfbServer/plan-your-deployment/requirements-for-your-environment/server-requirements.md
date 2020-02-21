---
title: Requisitos de servidor para Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: Prepare los servidores de Skype empresarial Server 2015 con este tema. Hardware, so, bases de datos, software, todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación y una implementación correctas de la granja de servidores.'
ms.openlocfilehash: f1898fc9de5999276b963a78c181e3b098876b69
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160397"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos de servidor para Skype empresarial Server 2015
 
**Resumen:** Prepare los servidores de Skype empresarial Server 2015 con este tema. Hardware, so, bases de datos, software, todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación y una implementación correctas de la granja de servidores.

Si está buscando requisitos del entorno, como Active Directory, DNS o certificados, puede consultar los [requisitos del entorno para Skype empresarial Server 2015](environmental-requirements.md) doc.
  
Como cabría esperar, hay algunos preparativos que debe realizar antes de empezar a implementar Skype empresarial Server 2015. Este artículo le guiará a través de la planeación de lo siguiente:
  
- [Hardware para Skype empresarial Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operativos para Skype empresarial Server 2015](server-requirements.md#OS)
  
- [Bases de datos back-end que funcionarán con Skype empresarial Server 2015](server-requirements.md#DBs)
  
- [Software que debe instalarse antes de una implementación de Skype empresarial Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para Skype empresarial Server 2015
<a name="Hardware"> </a>

Ahora que tiene la topología desactivada (y, si no es así, consulte el tema sobre los [conceptos básicos de la topología de la topología de Skype empresarial Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), es el momento de pensar en los servidores. Los servidores de Skype empresarial Server 2015 necesitarán hardware de 64 bits. Nuestras recomendaciones para el hardware se encuentran a continuación. Estos no son requisitos, pero reflejan los requisitos necesarios para un rendimiento óptimo. Disponemos de documentación de planeación de capacidad que le ayudará a determinar si necesita más, según sus circunstancias.
  
Hardware recomendado para los servidores front-end, los servidores back-end, los servidores Standard Edition y los servidores de chat persistente:
  
|**Componente de hardware**|**Recomenda**|
|:-----|:-----|
|CPU  <br/> |procesador dual de 64 bits, HEX-Core, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de Skype empresarial Server 2015.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |NI  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos que usan RAID 1 y 6 con RAID 10).  <br/> O BIEN  <br/> • Unidades de estado sólido (SSDs) capaces de proporcionar el mismo espacio libre y un rendimiento similar a las unidades de disco mecánicas de 8 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto dual, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar en un equipo con una sola dirección MAC y una sola dirección IP).  <br/> **No** se admiten las configuraciones dual o multitarjeta para los servidores front-end, los servidores back-end, los servidores Standard Edition y los servidores de chat persistente. <br/> Siempre que no se expongan al sistema operativo y se usen para supervisar y administrar el hardware del servidor, puede tener sistemas de administración fuera de banda, como DRAC o ILO. Este escenario no constituye un servidor de host múltiple y es compatible.  <br/> |
   
Hardware recomendado para los servidores perimetrales, los servidores de mediación independientes, los servidores de interoperabilidad de vídeo y los directores:
  
|**Componente de hardware**|**Recomenda**|
|:-----|:-----|
|CPU  <br/> |procesador dual de 64 bits, cuatro núcleos, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de Skype empresarial Server 2015.  <br/> |
|Memoria  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |NI  <br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración de 2 unidades RAID 1).  <br/> O BIEN  <br/> • Unidades de estado sólido (SSDs) capaces de proporcionar el mismo espacio libre y un rendimiento similar a las unidades de disco mecánicas de 4 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto dual, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar en un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Las configuraciones dual o multitarjeta **no** son compatibles con los directores y los servidores de interoperabilidad de vídeo. <br/> Los servidores perimetrales requerirán dos interfaces de red que sean adaptadores de red de puerto dual, 1 Gbps o superior (o dos adaptadores de red emparejados, para un total de cuatro, cada par se integra con una sola dirección MAC y una sola dirección IP, para un total de dos pares).  <br/> En los servidores de mediación independientes, se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para permitir la configuración de una dirección IP de RTC específica.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operativos para Skype empresarial Server 2015
<a name="OS"> </a>

Una vez que tenga el hardware en su ubicación, deberá instalar sistemas operativos (SO). Se trata del sistema operativo que le permitirá instalar y usar correctamente Skype empresarial Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (necesita la actualización acumulativa 9 o posterior de Skype empresarial). <br/> |Windows Server 2016 (necesita la actualización acumulativa 5 o posterior de Skype empresarial). Para obtener más información, consulte [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Sistema operativo Windows Server 2012 R2 Datacenter con todas las actualizaciones necesarias instaladas.  <br/> |Sistema operativo Windows Server 2012 R2 Standard con todas las actualizaciones necesarias instaladas.  <br/> |
|Sistema operativo Windows Server 2012 Datacenter con todas las actualizaciones necesarias instaladas.  <br/> |Sistema operativo Windows Server 2012 Standard con todas las actualizaciones necesarias instaladas.  <br/> |
   
Si no está en esta lista, no funcionará correctamente; no lo intente para las nuevas instalaciones de Skype empresarial Server 2015. Tenga en cuenta que la actualización en el lugar del sistema operativo no es compatible con Lync Server 2013.  Debe implementar un grupo independiente y migrar los usuarios al nuevo grupo con un sistema operativo diferente.
  
> [!NOTE]
> Es posible que haya observado que Windows Server 2008 R2 no está en esta lista. Esto se debe a que recomendamos que Windows Server 2012 R2 para todos los servidores nuevos que se usen para SFB. Solo debe usar Windows Server 2008 R2 si tiene servidores existentes con Lync Server 2013 ya instalado y está intentando realizar una actualización en el mismo punto de los mismos. Windows Server 2008 R2 llegó al final del ciclo de vida de soporte técnico estándar el 1/13/2015 y llegará al final de su ciclo de vida de soporte técnico el 1/14/2020.
  
Además de la versión más reciente del Service Pack, querrá asegurarse de que las siguientes actualizaciones se instalan cuando le resulte relevante:
  
- Para Windows Server 2012, el artículo 2858668 de KB debe instalarse antes de una actualización. [Obtenerla aquí](https://support.microsoft.com/kb/2858668/).
    
- Si tiene Windows Server 2012 R2, instale el artículo 2982006 de KB antes de realizar la actualización. Se [encuentra aquí](https://support.microsoft.com/kb/2982006/).
    
- Si va a actualizar en un cuadro de Windows Server 2008 R2 (vea la nota anterior), querrá instalar primero el artículo de KB 2533623. [Se encuentra en este vínculo](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de datos back-end que funcionarán con Skype empresarial Server 2015
<a name="DBs"> </a>


Al instalar Skype empresarial Server 2015 Standard Edition, también se instala automáticamente SQL Server 2014 Express (64-bit Edition).
  
Skype empresarial Server 2015 Enterprise Edition es un poco más complicado, pero la lista admitida es la siguiente (todo lo que es la edición de 64 bits, observará que no use las ediciones de 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edición de 64 bits), y se recomienda ejecutar con el último Service Pack. <br/> |Microsoft SQL Server 2017 Enterprise (edición de 64 bits), y se recomienda ejecutar con el último Service Pack. <br/> |Microsoft SQL Server 2016 Enterprise (edición de 64 bits) con Service Pack 1 o posterior y debe ejecutarse con la actualización acumulativa 7 o posterior de Skype empresarial ([descargar la actualización acumulativa de Skype empresarial](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (edición de 64 bits), y debe ejecutarse con la actualización acumulativa 6 o posterior ([descargar la actualización acumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edición de 64 bits), y se recomienda ejecutar con el último Service Pack.  <br/> |
|Microsoft SQL Server 2019 Standard (edición de 64 bits) y se recomienda ejecutar con el último Service Pack. <br/> |Microsoft SQL Server 2017 Standard (edición de 64 bits) y se recomienda ejecutar con el último Service Pack. <br/> |Microsoft SQL Server 2016 Standard (edición de 64 bits) con Service Pack 1 o posterior y debe ejecutarse con la actualización acumulativa 7 o posterior de Skype empresarial ([descargar la actualización acumulativa de Skype empresarial](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (edición de 64 bits), y debe ejecutarse con la actualización acumulativa 6 o posterior ([descargar la actualización acumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda ejecutar con el último Service Pack.  <br/> |
   
Si no ve la edición de SQL Server que desea usar en la lista, no puede usarla.
  
- También tendrá que instalar SQL Server Reporting Services para el rol del servidor de supervisión.
- Para un back-end de SQL bien conectado, la conexión al front-end de Skype empresarial debe ser local y no a través de un vínculo de baja velocidad. 
- No se admite el uso compartido de SQL back-end entre dos o más grupos de servidores.

### <a name="microsoft-exchange-storage"></a>Almacenamiento de Microsoft Exchange
Los archivos de contenido de las reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos. Si desea almacenar datos de archivo de Skype empresarial con datos de cumplimiento de Exchange, debe usar Exchange para la implementación de Exchange y asegurarse de que el tamaño máximo de almacenamiento admita el almacenamiento de los archivos de contenido de la reunión. Debe implementar Exchange antes de implementar y habilitar el archivado con la opción de integración de Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el archivado en Skype empresarial Server 2015
  
El archivado no es un rol de servidor definido, no es necesario instalar un servidor independiente para el archivado. Los agentes unificados de recopilación de datos se instalan y activan automáticamente en cada grupo de servidores front-end Enterprise Edition y en cada servidor Standard Edition. Tendrá que habilitar y publicar la topología de archivado con el generador de topologías.
    
El archivado usa el almacenamiento de archivos de Skype empresarial Server para el almacenamiento temporal de los archivos de contenido de reuniones, por lo que no se configura un almacén de archivos independiente para el archivado.
    
Microsoft Message Queue Server no es necesario.
    
Tendrá que configurar la infraestructura para el almacenamiento de archivado. Esto incluye la elección del almacenamiento de Exchange o de archivado con SQL Server.   Los requisitos de la infraestructura de archivado de Skype empresarial Server son los mismos que para la implementación de Skype empresarial Server. Para obtener información detallada, consulte [Requirements for your Skype for Business Environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Para admitir usuarios que no están hospedados en servidores de Exchange, o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado con una base de datos de SQL Server de 64 bits. 
    
Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del proceso de instalación. Para obtener más información acerca de SQL Server, consulte la [documentación de SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
El aumento de la carga para el archivado puede ser significativo. Por lo tanto, debe asegurarse de que el espacio en disco es adecuado para los servidores front-end en los que el archivado está habilitado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Creación de reflejos de SQL, agrupación en clústeres de SQL y SQL AlwaysOn

Puede usar la creación de reflejos de SQL o el agrupamiento en clústeres de SQL con Skype empresarial Server 2015, es compatible. Configuración de la creación de reflejos de SQL mediante el generador de topologías de Skype empresarial Server. Si está intentando configurar clústeres de SQL, esto se realiza en SQL Server.
  
Asegúrese de que tiene una configuración activa/pasiva para los clústeres de SQL, tal y como se admite. No comparta el nodo pasivo con ninguna otra instancia de SQL.
  
Puede tener lo siguiente para el clúster de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2019 Standard (edición de 64 bits) y se recomienda ejecutar con el último Service Pack.

- Microsoft SQL Server 2017 Standard (edición de 64 bits) y se recomienda ejecutar con el último Service Pack.

- Microsoft SQL Server 2016 Standard (edición de 64 bits) con Service Pack 1 o posterior. Se recomienda ejecutar con el último Service Pack.

- Microsoft SQL Server 2014 Standard (edición de 64 bits) y se recomienda ejecutar con el último Service Pack.
    
-  Microsoft SQL Server 2012 Standard (edición de 64 bits) y se recomienda ejecutar con el último Service Pack.

Dieciséis nodos:

- Microsoft SQL Server 2019 Enterprise (edición de 64 bits), y se recomienda ejecutar con el último Service Pack.

- Microsoft SQL Server 2017 Enterprise (edición de 64 bits), y se recomienda ejecutar con el último Service Pack.

- Microsoft SQL Server 2016 Enterprise (edición de 64 bits) con Service Pack 1 o posterior. Se recomienda ejecutar con el último Service Pack.
  
- Microsoft SQL Server 2014 Enterprise (edición de 64 bits), y se recomienda ejecutar con el último Service Pack.
    
- Microsoft SQL Server 2012 Enterprise (edición de 64 bits), y se recomienda ejecutar con el último Service Pack.

> [!IMPORTANT]
> Para la actualización, queremos garantizar que, en los servidores front-end, tenga al menos SQL Server 2012 SP1 instalado antes de la actualización. [Este es un vínculo](https://www.microsoft.com/download/details.aspx?id=35575) a SP1 si quiere descargarlo de inmediato.
  
Si necesita más información sobre la creación de reflejos de SQL, tenemos un tema de alta disponibilidad del servidor back-end en Skype empresarial Server 2015. Configure SQL Server clustering for Skype for Business Server 2015 tiene los pasos para preparar la organización por clústeres. También hay más vínculos en los clústeres de conmutación por error para SQL, para [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)y [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> New to the 2015 release es compatible con SQL AlwaysOn. Es compatible y puede obtener más información en el tema [back end Server High Availability in Skype for Business server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no se admite en Skype empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que debe instalarse antes de una implementación de Skype empresarial Server 2015
<a name="Software"> </a>

Hay algunas cosas que tendrá que instalar o configurar para cualquier servidor que ejecute Skype empresarial Server 2015 y se enumeran a continuación. Después de esto son requisitos adicionales para roles de servidor específicos.
  
> [Nota] Skype empresarial Server 2015 no es compatible con .NET Framework 4,8.
  
 **Todos los servidores:**
  
|**Software o rol**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos los servidores de Skype empresarial Server necesitan Windows PowerShell 3,0 instalado.  <br/> • Si va a realizar la instalación en Windows Server 2012 o en Windows Server 2012 R2, está configurado porque ya existe.  <br/> • Si va a realizar una actualización en Windows Server 2008 R2, puede descargar [Windows Management Framework 3,0](https://www.microsoft.com/download/details.aspx?id=34595) para obtenerla. <br/> **Sugerencia:** Una vez que tenga el PowerShell correcto en ese momento, confirme que es BuildVersion 6.2.9200.0 o posterior yendo al símbolo del sistema de PowerShell `$PSVersionTable`y escribiendo. Esto debe incluir la información que necesita.  <br/> |
|Microsoft .NET Framework  <br/> |Servicios WCF es una **característica** que se instala como una característica de Windows, en **Administrador de servidores**, no se necesitan descargas. <br/> • Asegúrese de que, al instalar esta característica, o si ya está instalada y de que la está comprobando, que la opción de **activación http** también está seleccionada e instalada, de la siguiente manera: <br/> ![Captura de pantalla que muestra la opción activación HTTP en las características de .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)No se preocupe si recibe una ventana emergente adicional que indica que es necesario instalar otras cosas para que se instale la activación http. Es normal, haga clic en aceptar y continúe. Si no aparece esta ventana emergente, da por sentado que ya están instaladas y continúa.  <br/> Microsoft .NET Framework suele instalarse cuando se instalan Windows Server 2012 R2 o Windows Server 2016. Skype empresarial Server funciona con las siguientes versiones de Microsoft .NET Framework:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (para Skype empresarial Server CU 5 o versiones posteriores)  <br/> • .NET 4.7.2 (para Skype empresarial Server CU 6 o versiones posteriores)  <br/>  Es probable que .NET Framework 3,5 se instale de forma predeterminada en el equipo con Windows Server 2008 R2 (sin duda, asegúrese de que antes de realizar la actualización), pero en realidad no se incluirá en los servidores de Windows Server 2012 o Windows Server 2012 R2 (para instalaciones nuevas). Para agregarla a, necesitará tener acceso a la unidad de instalación o los medios (el lugar desde el que se instaló Windows Server o dónde se encuentran los archivos de instalación en este momento). Después, siga adelante e instálelo como una característica del administrador de servidores y elija los medios de instalación (en concreto, la carpeta **\sources\sxs** ) cuando se le solicite y continúe con la instalación. <br/> |
|Media Foundation  <br/> |Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.  <br/> Todos los servidores front-end y los servidores Standard Edition usados para las conferencias requieren el tiempo de ejecución de Windows Media Format para ejecutar los archivos de audio de Windows Media (. WMA) que las aplicaciones de estacionamiento, anuncio y grupo de respuesta de llamadas se reproducen para anuncios y música.  <br/> |
|Windows Identity Foundation  <br/> |Se necesita Windows Identity Foundation 3,5 para admitir escenarios de autenticación de servidor a servidor para Skype empresarial Server 2015.  <br/> • Para Windows Server 2012 y Windows Server 2012 R2, no hay necesidad de descargar nada. Abra el **Administrador del servidor**y vaya al **Asistente para agregar roles y características**. **Windows Identity Foundation 3,5** aparece en la sección **características** . Si está activada, está bien. En caso contrario, selecciónelo y haga clic en siguiente para llegar al botón **instalar** . <br/> |
|Herramientas de administración de servidor remoto  <br/> |Herramientas de administración de roles: herramientas de AD DS y AD LDS  <br/> |
   
 **Los servidores front-end y el servidor Standard Edition también necesitan:**
  
|**Software o rol**|**Detalles**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS es necesario en todos los servidores front-end, así como en todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características HTTP comunes: documento predeterminado, errores HTTP, contenido estático  <br/> • Mantenimiento y diagnóstico: registro HTTP, herramientas de registro, seguimiento  <br/> • Rendimiento: compresión de contenido estático, compresión de contenido dinámico  <br/> • Seguridad: filtrado de solicitudes, autenticación de asignación de certificados de cliente, autenticación de Windows  <br/> • Desarrollo de aplicaciones: extensibilidad de .NET 3,5, extensibilidad de .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensiones ISAPI, Filtros ISAPI  <br/> • Herramientas de administración: consola de administración de IIS, scripts y herramientas de administración de IIS  <br/> También se debe tener en cuenta que también se necesita acceso anónimo, pero se obtiene al instalar IIS, por lo que no tiene un punto para seleccionarlo en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para Windows Server 2016, Windows Server 2012 y Windows Server 2012 R2, tendrá que instalar la característica de **Media Foundation** en el **Administrador de servidores**. Ahora, puede iniciar su instalación de Skype empresarial Server 2015 sin este otro, pero se le pedirá que lo instale y, a continuación, reinicie el servidor, antes de que la instalación de Skype empresarial Server 2015 continúe. Mejor hacerlo antes de tiempo. <br/> |
|Silverlight  <br/> |Puede instalar la última versión de Silverlight en [este vínculo](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Es posible que también necesite habilitar el examen de directorios si usa un equilibrador de carga. De lo contrario, se cargará una página en blanco que el equilibrador de carga podría considerar un error. 

Para ayudarle, le mostramos un script de PowerShell de ejemplo que puede ejecutar para automatizar este procedimiento:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> El comando busca archivos de origen en un orden específico. Si está en línea, el comando obtiene acceso a Windows Update. Sin embargo, si está sin conexión, debe asegurarse de que los archivos de origen estén disponibles para el comando. Para obtener más información sobre el uso de PowerShell para instalar roles y características, vea [instalar o desinstalar roles, servicios de rol o características](https://technet.microsoft.com/library/hh831809.aspx) no olvide ejecutar de nuevo Windows Update después de instalar los requisitos previos, incluso si usa el comando de PowerShell.

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
    
  - Extensibilidad de .NET 3,5
    
  - Extensibilidad de .NET 4.5
    
  - ASP.NET 3,5
    
  - ASP.NET 4,5
    
  - Extensión ISAPI
    
  - Filtros ISAPI
    
(Si se está preguntando, se trata del mismo módulo que los servidores front-end y los servidores Standard Edition, con las herramientas de administración y compresión de contenido dinámico que se han dejado fuera).
  
Además, aquí tiene cierto código de PowerShell:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Los servidores de chat persistente también necesitan:**
  
Message Queue Server, que también se denomina MSMQ. Es un componente de Windows Server y puede instalarlo en la sección Características del administrador del servidor. Si desea obtener más información al respecto, consulte [instalar y administrar Message Queue Server](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Últimos Comentarios:**
  
No instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server o cualquier otro software de proveedores de servicios por niveles (LSP) Winsock (los firewalls de terceros o el software de inspección de red antivirus se incluir? aquí) en cualquiera de los servidores front-end o servidores de mediación independientes. Se ha observado un rendimiento deficiente del tráfico de medios cuando se instala el software.
  

