---
title: Requisitos del sistema para Skype para Business Server 2019
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 'Resumen: Prepare su Skype Business Server 2019 servidores y la infraestructura de dominio con este tema. Hardware, sistema operativo, las bases de datos, software, todos los requisitos del sistema y recomendaciones, junto con el certificado de DNS, recurso compartido de archivos e información de Active Directory, están aquí ayudar a garantizar una instalación correcta y la implementación de la granja de servidores.'
ms.openlocfilehash: db5bada7b89de2fafc4d72c9fa5fcac05d8611ce
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297771"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Requisitos del sistema para Skype para Business Server 2019
 
**Resumen:** Preparar la instalación de Skype para Business Server 2019 con este tema. Aquí se tratan hardware, sistema operativo, software, bases de datos, certificados, Active Directory, DNS y uso compartido de archivos. Todos los requisitos del sistema y las recomendaciones están aquí para ayudar a garantizar una instalación correcta y la implementación de la granja de servidores.
  
Como era de esperar, hay algunos preparativos que debe hacer antes de empezar a implementar Skype para Business Server 2019. Este artículo lo guiará por el proceso de planificación de los siguientes elementos:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Sistemas operativos](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Bases de datos SQL back-end](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Sistema de nombre de dominio (DNS)](system-requirements.md#DNS)
  
- [Certificados](system-requirements.md#Certs)
  
- [Recurso compartido de archivos](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware de Skype para Business Server 2019
<a name="Hardware"> </a>

Después de que tiene la topología hacia abajo (y si no lo hace, puede desproteger el tema de [conceptos básicos de la topología de Skype para Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), es el momento de pensar acerca de los servidores. Skype para Business Server 2019 servidores requieren un hardware de 64 bits. Las recomendaciones de hardware se indican a continuación. Estos no son los requisitos, pero que reflejan los requisitos necesarios para un rendimiento óptimo. Existe documentación de planificación de la capacidad que le ayudará a determinar si necesita un equipo superior, dependiendo de sus circunstancias.
  
Hardware recomendado para los servidores Standard Edition:

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no se admiten para Skype para funciones de Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |O  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos con RAID 1 y 6 con RAID 10).   <br/> O bien  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Las configuraciones de host múltiple o dobles son **no** admite los servidores para servidores Front-End, servidores Back-End y Standard Edition. <br/> Siempre que no se exponen en el sistema operativo y se usan para supervisar y administrar el hardware del servidor, puede hacer que los sistemas de administración fuera de banda, como DRAC o ILO. Este escenario no constituye un servidor de múltiples ubicaciones, y es un escenario compatible.  <br/> |


Hardware recomendado para servidores Front-End y servidores Back-End:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior. <br/> Los procesadores Intel Itanium no se admiten para Skype para funciones de Business Server 2019.  <br/> |
|Memoria  <br/> |64 gigabytes (GB).  <br/> |
|Disco  <br/> |O  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos con RAID 1 y 6 con RAID 10).   <br/> O bien  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Las configuraciones de host múltiple o dobles son **no** admite los servidores para servidores Front-End, servidores Back-End y Standard Edition. <br/> Siempre que no se exponen en el sistema operativo y se usan para supervisar y administrar el hardware del servidor, puede hacer que los sistemas de administración fuera de banda, como DRAC o ILO. Este escenario no constituye un servidor de múltiples ubicaciones, y es un escenario compatible.  <br/> |
   
Hardware recomendado para los servidores perimetrales, servidores de mediación independiente y directores:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no se admiten para Skype para funciones de Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabytes.  <br/> |
|Disco  <br/> |O  <br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración de 2 unidades RAID 1).  <br/> O bien  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 4 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (pueden usarse dos adaptadores de red, pero es necesario formar con ellos un equipo con una sola dirección MAC y una sola dirección IP).  <br/> Son las configuraciones de dobles u host múltiple **no** se admite para los servidores de la interoperabilidad de vídeo y directores. <br/> Los servidores Edge necesitan dos interfaces de red que sean adaptadores de red de puerto doble, 1 Gbps o superior (o dos adaptadores de red emparejados para un total de cuatro; cada pareja debe formar un equipo con una sola dirección MAC y una sola dirección IP, para un total de dos parejas).  <br/> En los servidores de mediación independiente, se admite la instalación de tarjetas de interfaz de red adicionales (NIC) para permitir la configuración de una dirección IP de PSTN específica.  <br/> |


> [!NOTE]
> Independientemente de la función de servidor, también se recomienda la siguiente configuración de hardware para Skype para Business Server 2019 (Esto puede variar según la marca del hardware ha comprado, lo, consulte la documentación del fabricante para obtener detalles específicos):
> - Configuración de BIOS - debe establecerse en plano de NUMA.
> - Habilitar Hyper-Threading.
> - La configuración de cola RSS debe establecerse en cola 8.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Sistemas operativos para Skype para Business Server 2019
<a name="OS"> </a>

Una vez que tenga el hardware en su lugar, que necesitará para el sistema operativo de instalación (SO) que le permitirá instalar y usar correctamente Skype para Business Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Cualquier cosa que no son los sistemas operativos que se muestra aquí no funcionará correctamente; Por favor, no lo pruebe para instalaciones de Skype para Business Server 2019.

> [!NOTE]
> 
> Si va a instalar 2019 de centro de administración de Windows en el equipo de Windows Server 2019, le pedirá un puerto escuchar en. Hay una posibilidad es posible que elija el puerto 443, pero si ese equipo tiene Skype para Business Server 2019 instalado en él, o va a tener Skype para Business Server 2019 instalado en él, debe elegir un número de puerto diferente.
> 
>¿Por qué es el caso? Si 2019 de centro de administración de Windows se está ejecutando en el puerto 443, no podrá conectarse al servidor mediante el Skype para el Panel de Control, ni podrá conectarse a cualquier servicio web interno que se ejecutan en el servidor (servicio de Web de la libreta de direcciones Autodiscover Service, WebTicket Service, etcetera).  De hecho, no podrá conectarse a cualquier dirección URL del servicio Web interno. Elija un puerto diferente, en caso necesario o desea colocar 2019 de centro de administración de Windows en un servidor con Skype para Business Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software que debe instalarse antes de una Skype para la implementación empresarial Server 2019
<a name="Software"> </a>

Hay algunas cosas que va a necesitar instalar o configurar para cualquier servidor que ejecute Skype para Business Server 2019. Se muestran a continuación, seguido de los requisitos adicionales para funciones de servidor específicas.
  
 **Todos los servidores:**
  
|**Software y funciones**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos los Skype para servidores Business Server necesita Windows PowerShell 3.0 instalado.  <br/> • Esto debe instalarse de forma predeterminada con Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Los servicios de WCF es una **característica** que no se ha instalado como una característica de Windows, en **Administrador del servidor**, ninguna descarga sea necesaria. <br/> • Necesita para asegurarse de que, al instalar esta característica, o si ya está instalado y se está revisando en él, que la opción de **Activación HTTP** es también comprueba e instalada, de este modo: <br/> ![Captura de pantalla que muestra la opción Activación HTTP bajo las características de .NET Framework 4.5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> No se preocupe si obtener un elemento emergente adicional que indica que deban instalarse para que la activación HTTP a instalarse algunas otras cosas. Que es normal; Haga clic en Aceptar y continúe. Si no se obtienen emergente, puede asumir esas cosas ya están instaladas y seguir adelante.  <br/> Normalmente, se instala Microsoft .NET Framework cuando se instala Windows Server 2016. Skype para Business Server funciona con las siguientes versiones de Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7 <br/> |
|Media Foundation  <br/> |Para Windows Server 2016, el tiempo de ejecución de formato de Windows Media se instala con Microsoft Media Foundation.  <br/> Usada para conferencias de todos los servidores de servidores Front-End y Standard Edition requieren Windows Media Format Runtime ejecutar los archivos de Windows Media Audio (.wma) que las aplicaciones de estacionamiento de llamadas, el anuncio y el grupo de respuesta reproducción para música y anuncios.  <br/> |
|Windows Identity Foundation  <br/> |Es necesario Windows Identity Foundation 3.5 para admitir escenarios de autenticación de servidor a servidor para Skype para Business Server 2019.  <br/> • Para Windows Server 2016, no es necesario descargar nada. Abra el **Administrador de servidores** y vaya a **Asistente para agregar roles y características**. **Windows Identity Foundation 3.5** aparece en la sección **Características**. Si está seleccionada, se puede proceder. En caso contrario, selecciónela y haga clic en **siguiente** para alcanzar el botón **instalar** . <br/> |
|Herramientas de administración remota del servidor  <br/> |Herramientas de administración de roles: herramientas AD DS y AD LDS  <br/> |
   
 **También necesita Front-End servidores y servidor Standard Edition:**
  
|**Software y funciones**|**Detalles**|
|:-----|:-----|
|Servicios de Internet Information Server (IIS)  <br/> |IIS es necesario en todos los servidores Front-End, así como todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características comunes de HTTP: contenido estático de documento, errores HTTP, predeterminado  <br/> • Estado y diagnóstico: registro, herramientas de registro, el seguimiento de HTTP  <br/> • Rendimiento: compresión de contenido estático, compresión de contenido dinámico  <br/> • Seguridad: solicitud de filtrado, autenticación de asignación de certificados de cliente, la autenticación de Windows  <br/> • El desarrollo de aplicaciones: extensibilidad de .NET 3.5, extensibilidad de .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, las extensiones ISAPI, filtros ISAPI  <br/> • Herramientas de administración: consola de administración de IIS, las secuencias de comandos de administración de IIS y herramientas  <br/> Tenga en cuenta que también se necesita el acceso anónimo, pero tendrá al instalar IIS, por lo que no tiene un lugar para seleccionar en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para Windows Server 2016, debe instalar la característica de **Media Foundation** en **Administrador del servidor**. Puede iniciar realmente la Skype para la instalación de Business Server 2019 sin esto, pero se le pedirá que lo instale y, a continuación, reiniciar el servidor, antes de la Skype para Business Server 2019 instalar continúa. Es mejor hacer antes de tiempo. <br/> |
|Silverlight  <br/> |Puede instalar la versión más reciente de Silverlight [aquí](https://www.microsoft.com/silverlight/).  <br/> |
   
A modo de ayuda, aquí ofrecemos un script de ejemplo de PowerShell que puede ejecutar para automatizar esto:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bases de datos back-end que funcionarán con Skype para Business Server 2019
<a name="DBs"> </a>

Al instalar Skype para 2019 Business Server Standard Edition, tendrá que SQL Server 2016 Express (edición de 64 bits).

Skype para Business Server 2019 Enterprise Edition requerirá completa de SQL Server, como se indica a continuación (edición de 64 bits sólo; no utilice las ediciones de 32 bits):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2016 (edición de 64 bits) y se debe ejecutar con las últimas actualizaciones.  <br/> ||
 |
   
Si no ve la edición de SQL Server que desea usar que se muestra aquí, no se puede usar.
  
> [!NOTE]
> También debe instalar SQL Server Reporting Services para el rol de servidor de supervisión. 
  
### <a name="sql-clustering-and-sql-always-on"></a>Agrupación en clústeres de SQL y SQL siempre activado

Se admite la agrupación en clústeres de SQL con Skype para Business Server 2019. Si desea configurar un clúster de SQL, que se realiza en SQL Server.
  
Asegúrese de que tiene una configuración activo/pasivo para clústeres de SQL, que es compatible. No compartir el nodo pasivo con cualquier otra instancia SQL.
  
Puede usar lo siguiente para el clúster de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2016 Standard (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
Dieciséis nodos:
  
- Microsoft SQL Server 2016 Enterprise (edición de 64 bits) y se recomienda la ejecución con el último service pack.
    
Tendremos un artículo, agrupación en clústeres de Skype para Business Server 2019, que tendrán los pasos para obtener la agrupación en clústeres listo para configurar SQL Server.
 
Se admite SQL siempre en, y pueden leer más información acerca de él en el [servidor Back-End de alta disponibilidad en Skype para Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recomendaciones de instalación de servidor adicional:
  
Por favor, no instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server, o cualquier otro software de proveedores de servicios por niveles (LSP) de Winsock (los firewalls de terceros o software de inspección de red contra virus sería incluido aquí) en cualquiera de los servidores front-end o servidores de mediación independiente. Se ha visto el rendimiento del tráfico de medios deficiente cuando se instaló ese software.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Aunque gran parte de los datos de configuración para los servidores y servicios se almacena en la Skype para el almacén de Administración Central de Business Server 2019, hay algunas cosas que siguen almacenados en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Versiones compatibles de extensiones de Skype para Business Server 2015 y Lync Server 2013 mantener la compatibilidad con versiones anteriores con el anterior  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto para aplicaciones (como la aplicación de grupo de respuesta y la aplicación operador de conferencia)  <br/> |
||Datos publicados para compatibilidad con versiones anteriores  <br/> |
||Un servicio punto de control (SCP) para el almacén de Administración Central  <br/> |
||Cuenta de autenticación de Kerberos (un objeto de equipo opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>SO para controladores de dominio

Se pueden usar los siguientes sistemas operativos de controlador de dominio:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
El nivel funcional de dominio de cualquier dominio en que implementar Skype para Business Server 2019 y el nivel funcional de bosque de cualquier bosque implementar Skype para Business Server 2019 en, deben ser una de las siguientes opciones:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
¿Puede haber controladores de dominio de solo lectura en estos entornos? Por supuesto, el mismo tiempo que allí también están controladores de dominio de escritura disponibles.
  
Es importante saber que Skype para Business Server 2019 no admite dominios de etiqueta única. ¿Qué son? Si tiene un dominio raíz con la etiqueta contoso.local, que se va a estar bien. Si tiene un dominio raíz sólo con el nombre local, que no se va a trabajar y no se admite como resultado. Puede encontrar más información al respecto en [este artículo de la Knowledge Base](https://support.microsoft.com/kb/300684/en-us).
  
Skype para Business Server 2019 también no admite el cambio de nombre de dominios. Si realmente tiene que cambiar el nombre de su dominio, se podrá necesita para desinstalar Skype para Business Server 2019, realice el cambio de nombre de dominio y, a continuación, vuelva a instalar Skype para Business Server 2019.
  
Por último, se puede estar tratando con un dominio con un entorno de AD DS bloqueados, y que son muy bien. Hemos desarrollado para obtener más información acerca de cómo implementar Skype para Business Server 2019 en un entorno de AD DS bloqueado en la documentación de implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Las topologías compatibles de Skype para Business Server 2019 son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
    
Disponemos de diagramas y descripciones que le ayudarán a determinar qué topología tiene en su entorno, o lo que es posible que necesite configurar antes de instalar Skype para Business Server 2019. Para mantener la simple, también incluimos una clave:
  
![Leyenda de los iconos usados en los diagramas de topología de Skype Empresarial](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama de un solo bosque de Active Directory con un único dominio](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No puede ser más fácil que esto; es un bosque de dominio único, una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Diagrama de un solo bosque con un único árbol y varios dominios](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama incluye también un único bosque, pero tiene también uno o más dominios secundarios (tres, en este ejemplo concreto). Por lo que el dominio de en que los usuarios se crean puede ser diferente del dominio Skype para Business Server 2019 se implementa en. ¿Por qué esto es importante? Es importante recordar que cuando se implementa un Skype para grupo de negocio de servidor Front-End, todos los servidores de ese grupo de servidores deben estar en un solo dominio. Puede tener la administración entre dominios a través de Skype para Business Server admiten de grupos de administradores universales de Windows.
  
En el diagrama anterior, puede ver que los usuarios de un dominio tienen acceso a Skype para grupos de servidores de negocio desde el mismo dominio o de dominios diferentes, incluso si los usuarios se encuentran en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Diagrama de un solo bosque con varios árboles y espacios de nombres separados](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Puede que tenga una topología similar a este diagrama, donde tiene uno de los bosques, pero dentro de ese bosque son varios dominios, con espacios de nombres independientes de AD. En este caso, este diagrama es un buen ejemplo, ya que incluye a los usuarios en diferentes tres dominios acceso a Skype para Business Server 2019. Líneas sólidas indican que tiene acceso un Skype para grupo de servidores de negocio en su propio dominio, mientras que una línea discontinua indica que va a un grupo de servidores en un árbol diferente por completo.
  
Como puede ver, los usuarios en el mismo dominio, el mismo árbol o incluso un árbol diferente pueden tener acceso a los grupos de servidores correctamente.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Diagrama de varios bosques en una topología de bosque central](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype para Business Server 2019 es compatible con varios bosques configurados en una topología de bosque central. Si no está seguro de que es lo que tiene, el bosque central en la topología utiliza objetos en ella para representar a los usuarios en los otros bosques y las cuentas de usuario de hosts de los usuarios en el bosque.
  
¿Cómo funciona? Un producto de sincronización de directorios (por ejemplo, Forefront Identity Manager, o FIM) administra las cuentas de usuario de su organización a lo largo de su existencia. Cuando una cuenta se crea o elimina en un bosque, este cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Sin lugar a dudas, si la infraestructura de AD está en su lugar, mover a esta topología es posible que no sea fácil, pero si ya está allí, o aún planeación su infraestructura de bosque, esto puede ser una buena opción. Puede centralizar su Skype para la implementación empresarial Server 2019 dentro de un solo bosque, mientras que los usuarios pueden buscar, comunicarse y ver la presencia de otros usuarios en cualquier bosque. Todas las actualizaciones de contacto de usuario se controlan automáticamente con el software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial
<a name="BKMK_multipleforestopology"> </a>

![Diagrama de varios bosques en una topología de bosque de recursos](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es donde un bosque está dedicado a la ejecución de las aplicaciones de servidor, como Microsoft Exchange Server y Skype para Business Server 2019. Este bosques de recursos también hospeda una representación sincronizada de objetos de usuario activo, pero no las cuentas de usuario habilitado para el inicio de sesión. Por lo que el bosque de recursos es un entorno de servicios compartidos para otros bosques en la que residen objetos de usuario y tienen una relación de confianza de nivel de bosque con el bosque de recursos.
  
Tenga en cuenta que se puede implementar Exchange Server en el mismo bosque de recursos como Skype para Business Server o en un bosque diferente.
  
Para implementar Skype para Business Server 2019 en este tipo de topología, crearía un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios (si ya está en el entorno de Microsoft Exchange Server, esto puede hacerse para usted). A continuación, necesita una herramienta de sincronización de Active directory (como Forefront Identity Manager, o FIM) para administrar cuentas de usuario a través de su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la descrita en [Varios bosques en una topología de bosque de recursos de Skype Empresarial](system-requirements.md#BKMK_multipleforestopology).
  
En esta topología, hay uno o más bosques de usuarios y Skype para Business Server se implementa en un bosque de recursos dedicado. Exchange Server puede ser instalados en servidores locales en el mismo bosque de recursos o de un bosque diferente y configurado para la implementación híbrida con Exchange Online, o se pueden proporcionar servicios de correo electrónico exclusivamente por Exchange Online para las cuentas locales. No existe ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD, uno de usuario y uno de recurso. Ambos bosques tienen una relación de confianza y se sincronizan con Office 365 mediante Azure AD Connect. Todos los usuarios se habilitan para Skype Empresarial a través de Office 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Hay una relación de total confianza entre los bosques de Active Directory. La herramienta Azure Active Directory Connect se utiliza para sincronizar cuentas entre los bosques de usuarios locales y Office 365.
  
 La organización también tiene Office 365 y usa [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar sus cuentas locales con Office 365. Los usuarios habilitados para Skype para la empresa están habilitados a través de Office 365 y Skype para profesionales en línea. Skype para Business Server no está instalados en servidores locales.
  
Autenticación de inicio de sesión único es proporcionada por una granja de servidores de servicios de federación de Active Directory que se encuentra en el bosque de usuarios.
  
En este escenario, se admite para implementar Exchange local, Exchange Online, una solución híbrida de Exchange, o bien de no tener Exchange implementado en absoluto. (El diagrama muestra solo Exchange local, pero las otras soluciones para Exchange también son totalmente compatibles).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con una implementación híbrida de Skype Empresarial 
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o más local bosques de usuarios, y se implementa en un bosque de recursos dedicado de Skype para la empresa y está configurado para el modo híbrido con Skype para profesionales en línea. Exchange Server puede ser instalados en servidores locales en el mismo bosque de recursos o de un bosque diferente y puede configurarse para implementación híbrida con Exchange Online. Como alternativa, pueden proporcionar servicios de correo electrónico exclusivamente por Exchange Online para las cuentas locales.
  
Para obtener más información, vea [Configure un entorno de varios bosque para entornos híbridos Skype para la empresa](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de nombre de dominio (DNS)
<a name="DNS"> </a>

Skype para Business Server 2019 requiere DNS, por los motivos siguientes:
  
- DNS permite Skype para Business Server 2019 detectar los servidores internos o grupos de servidores, lo que permite para las comunicaciones de servidor a servidor.
    
- DNS permite a cliente máquinas detectar el grupo de servidores Front-End o el servidor Standard Edition que se utiliza para las transacciones SIP.
    
- Asocia las direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite a los usuarios externos y los equipos cliente para conectarse a los servidores perimetrales, o el proxy inverso HTTP, para la mensajería instantánea (IM) o conferencia.
    
- Comunicaciones unificadas (UC) permite detectar dispositivos que no están registrados en el grupo de servidores Front-End o un servidor Standard Edition que está ejecutando el servicio web de actualización de dispositivos para obtener actualizaciones y envíe los registros.
    
- El uso de DNS permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.
    
- Ha usado en el equilibrio de carga de DNS.
    
Es importante tener en cuenta que Skype para Business Server 2019 no admite nombres de dominio internacionalizados (IDN).
  
Y es extremadamente importante recordar que cualquier nombre en DNS ser idéntico al nombre de equipo configurado en cualquier servidor que usa Skype para Business Server 2019. En concreto, se no puede tener cualquier nombre de short en el entorno y deben tener nombres de dominio completos para el generador de topología.
  
Esto parece que sería lógico para cualquier equipo que se ha unido a un dominio, pero si tiene un servidor perimetral que no está unido a su dominio, puede tener un valor predeterminado de un nombre corto con ningún sufijo de dominio. Asegúrese de que no es el caso, en DNS o en el servidor perimetral o cualquier Skype para Business Server 2019 servidor o grupo de servidores, en realidad.
  
Definitivamente no utilice caracteres Unicode o caracteres de subrayado. Los caracteres estándar (que son A-z, a-z, 0-9 y guiones) son compatibles con DNS externos y certificación pública (que necesitará para asignar nombres de dominio completos al nombre de sujeto en el certificado, es importante recordar), por lo que se va de repuesto usted mismo una gran cantidad de problemas si asigna el nombre Teniendo esto en cuenta desde el inicio.
  
Si quiere más información sobre los requisitos de DNS para redes, consulte la sección [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) de la documentación de planificación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Unas de las cosas más importantes que puede hacer antes de la implementación es asegurarse de que sus certificados están en orden. Skype para Business Server 2019 necesita una infraestructura de clave pública (PKI) para el transporte layer security (TLS) y conexiones de seguridad (MTLS) de capa de transporte mutua. Básicamente, para comunicarse de forma segura en una forma estandarizada, Skype para Business Server utiliza certificados emitidos por entidades de certificación (CA).
  
Éstas son algunas de las cosas que Skype para Business Server 2019 utiliza certificados para:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Uso de la detección automática de DNS de los socios de federación
    
- Acceso de usuarios remotos a la mensajería instantánea (MI)
    
- Acceso de usuarios externos a sesiones de audio/vídeo (A/V), a uso compartido de aplicaciones y a conferencias
    
- Hablar con aplicaciones web y Outlook Web Access (OWA)
    
Por lo que la planificación de certificado es obligatorio. Ahora, vamos a examinar una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben estar firmados mediante un algoritmo de firma compatible con el sistema operativo. Skype para Business Server 2019 admite el SHA-1 y SHA-2 suite de síntesis de tamaños (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo.
    
- Se admite la inscripción automática para los servidores internos de Skype para Business Server 2019.
    
- No se admite la inscripción automática para Skype para los servidores perimetrales de Business Server 2019.
    
> [!NOTE]
> No está permitido usar el algoritmo de firma RSASSA-PSS, ya que podría dar lugar a errores en problemas relacionados con el inicio de sesión y el desvío de llamadas, entre otros.  
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomienda usar longitudes de clave de 2048 y superiores.
    
- El algoritmo de firma hash o implícito predeterminado es RSA. También se admiten los algoritmos ECDH_P256, ECDH_P384 y ECDH_P521.
    
Que es un lote pensar y hay una gran variedad de niveles de comodidad con solicitar certificados a una entidad de certificación. Le ofrecemos algunos consejos más detallados a continuación para realizar la planeación sea lo más sencillo como sea posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos, y es probable que se obtendrá de una CA interna (es decir, una entidad de certificación que se encuentra en el dominio). Si desea, puede solicitar estos certificados desde una CA externa (uno que se encuentra en Internet). Si se pregunta qué entidad de certificación pública deben ir a, puede consultar la lista de [los socios de certificados de comunicaciones unificadas](https://support.microsoft.com/kb/929395/en-us) .
  
También va a necesitar certificados cuando Skype para Business Server 2019 se comunica con otras aplicaciones y servidores, como Microsoft Exchange Server. Esto, evidentemente, deberá ser un certificado que pueden usar estas otras aplicaciones y servidores de una manera compatible. Skype para Business Server 2019 y otros productos de Microsoft admite el protocolo Open Authorization (OAuth) para la autorización y autenticación de servidor a servidor. Si está interesado en esta, tenemos un artículo de planeación adicional para OAuth y Skype para Business Server 2019.
  
Skype para Business Server 2019 también incluye compatibilidad con (sin necesidad de) los certificados firmados con la función de algoritmo hash SHA-256. Para permitir el acceso externo mediante SHA-256, una entidad de certificación pública que usa SHA-256 emite el certificado externo.
  
Para mantener las cosas sencilla, hemos los requisitos de certificado para los servidores Standard Edition, los grupos de servidores Front-End y otras funciones, en las tablas siguientes, con el ficticia contoso.com usada para ver ejemplos (que probablemente se van a usar algo más para el entorno). Estos son todos los certificados de servidor web estándar, con las claves privadas que están no exportable. Aspectos adicionales que se tenga en cuenta:
  
- El uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el asistente para certificados para solicitar certificados.
    
- El nombre descriptivo de cada certificado debe ser único en el almacén del equipo.
    
- Según los nombres de ejemplo que aparece a continuación, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deben agregarse a nombre de alternativa de sujeto del certificado (SAN).
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre común o nombre de sujeto**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En los servidores Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo.  <br/> El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Internal web FQDN (que es el mismo que el FQDN del servidor)  <br/> Y  <br/> • Direcciones URL sencillas de reunión  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN =\*. contoso.com  <br/> |No se puede invalidar el FQDN en el generador de web interno.  <br/> Si tiene varias URL simples de reunión, debe incluir todos ellos como SANs.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de web externo  <br/> Y  <br/> Dirección URL sencilla de • dial-in  <br/> • Cumplir con las direcciones URL sencillas por dominio SIP  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias URL simples de reunión, debe incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para servidores Front-End de un grupo de servidores Front-End:
  
|**Certificado**|**Nombre común o nombre de sujeto**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • Internal web FQDN (que no es el mismo que el FQDN del servidor)  <br/> FQDN del servidor •  <br/> • Skype para el FQDN del grupo de negocio  <br/> Y  <br/> • Direcciones URL sencillas de reunión  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias URL simples de reunión, debe incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de web externo  <br/> Y  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias URL simples de reunión, debe incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el Director:
  
|**Certificado**|**Nombre común o nombre de sujeto**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |Grupo de directores  <br/> |FQDN del Director, FQDN del grupo de servidores Director.  <br/> Si este grupo de servidores es el servidor de inicio de sesión automático para los clientes y es necesaria la coincidencia de DNS en la directiva de grupo, necesitará también entradas para sip.sipdomain (para cada dominio SIP que tiene).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Si este grupo de servidores de Director es el servidor de inicio de sesión automático para los clientes y exacta de DNS es necesario en la directiva de grupo, necesitará también SAN; SAN=SIP.fabrikam.com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Internal web FQDN (que es el mismo que el FQDN del servidor)  <br/> FQDN del servidor •  <br/> • Skype para el FQDN del grupo de negocio  <br/> Y  <br/> • Direcciones URL sencillas de reunión  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN =\*. contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de web externo  <br/> Y  <br/> • Cumplir con las direcciones URL sencillas por dominio SIP  <br/> Dirección URL sencilla de • dial-in  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |El FQDN de web externo de Director debe ser distinto del grupo de servidores Front-End o un servidor Front-End.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN =\*. contoso.com  <br/> |
   
Certificados para el servidor de mediación independiente:
  
|**Certificado**|**Nombre común o nombre de sujeto**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del miembro del grupo de servidores  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para la aplicación de sucursal con funciones de supervivencia (específicamente, con funciones de supervivencia aplicación de sucursal 2015 para Skype para Business Server 2019):
  
|**Certificado**|**Nombre común o nombre de sujeto**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP. \<sipdomain\> (necesita sólo una entrada por dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (Edge)

Skype para Business Server 2019 admite el uso de un **solo certificado público** para interfaces externas del borde de conferencia de web y de acceso, además de la A y servicio de autenticación de V, que se proporciona a través de los servidores perimetrales. La interfaz perimetral interna normalmente utiliza un certificado privado emitido por la entidad de certificación interna, pero si lo prefiere, puede usar un certificado público para esto también, si procede de una entidad de certificación de confianza.
  
Su proxy inverso (RP) también usa un certificado público y cifra sus propias comunicaciones con los clientes y los servidores internos mediante HTTP (o, para ser más precisos, TLS por HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si va a implementar movilidad y está fomentando la detección automática para clientes móviles, va a necesitar incluir algunas entradas de nombre alternativo de sujeto adicional en los certificados para admitir las conexiones seguras de los clientes móviles.
  
Necesitará nombres de SAN para la detección automática en los siguientes certificados:
  
- Grupo de directores
    
- Grupo de servidores front-end
    
- Proxy inverso
    
Las características específicas se enumeran en las tablas siguientes.
  
Aquí es donde previamente un poco de planeación es bueno, pero a veces que ha implementado Skype para Business Server 2019 sin que tengan la intención de implementar la movilidad, que aparece más adelante cuando ya tiene certificados en el entorno. Volver a emitir los certificados desde una CA interna suele ser sencillo, pero en el caso de una CA pública puede resultar un poco más caro.
  
Si eso es lo que está viendo, y si tiene una gran cantidad de dominios SIP (que provocará que la adición de SAN más costoso), puede configurar el proxy inverso para usar HTTP para la solicitud inicial de Autodiscover Service, en lugar de usar HTTPS (que es el valor predeterminado configuración). El artículo de [planeación de movilidad](../../SfbServer/plan-your-deployment/mobility.md) tiene más información sobre esto.
  
Requisitos de certificado de grupo de directores y grupo de servidores Front-End:
  
|**Descripción**|**Entrada SAN**|
|:-----|:-----|
|URL del servicio Detección automática interna  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Como alternativa, puede usar SAN =\*. \<sipdomain\>
  
Requisitos de certificado (CA pública) de proxy inverso
  
|**Descripción**|**Entrada SAN**|
|:-----|:-----|
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado al agente de escucha SSL de su proxy inverso.
  
> [!NOTE]
> El agente de escucha de proxy inverso se va a tener SANs para sus direcciones de URL de servicios Web externos. Algunos ejemplos serían SAN=skypewebextpool01.contoso.com y dirwebexternal.contoso.com, si ha implementado el Director, (que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype para Business Server 2019 puede usar el mismo recurso compartido de archivos para el almacenamiento de todos los archivos. Deberá tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en un almacenamiento conectado directo (DAS) o en un almacenamiento en red (SAN), y esto incluye el sistema de archivos distribuidos (DFS) y las matrices redundantes de discos independientes (RAID). Para obtener más información sobre el uso de DFS con Windows Server 2012, consulte [esta página](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Se recomienda un clúster compartido para el recurso compartido de archivos. Si está utilizando uno, debe organizar en clústeres Windows Server 2012 o Windows Server 2012 R2. ¿Por qué el más reciente para Windows? Las versiones más antiguas no pueden tener los permisos adecuados para habilitar todas las características. Puede usar el Administrador de clústeres para crear los recursos compartidos de archivos y, en este artículo de [creación de un clúster](https://support.microsoft.com/en-us/help/224967) KB le ayudará con esos detalles.
    
> [!CAUTION]
> Es preciso que recuerde que no se admite el uso del almacenamiento conectado a la red (NAS) como recurso compartido de archivo, de modo que utilice una de las opciones que se han descrito anteriormente. 
  








