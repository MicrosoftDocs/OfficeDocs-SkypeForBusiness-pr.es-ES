---
title: Requisitos del sistema para Skype Empresarial Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 'Resumen: prepare los servidores de Skype Empresarial Server 2019 y la infraestructura de dominio con este tema. El hardware, el sistema operativo, las bases de datos, el software, todos los requisitos y recomendaciones del sistema, junto con el CERTIFICADO DNS, el recurso compartido de archivos y la información de Active Directory, están aquí para ayudar a garantizar una instalación e implementación correctas de la granja de servidores.'
ms.openlocfilehash: 8bb12fa9f5d0cd0144604f21d311c50f7f63b0f4
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232381"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Requisitos del sistema para Skype Empresarial Server 2019
 
**Resumen:** Prepare la instalación de Skype Empresarial Server 2019 con este tema. Aquí se tratan hardware, so, software, bases de datos, certificados, active diretory, DNS y archivos compartidos. Todos los requisitos y recomendaciones del sistema están aquí para ayudar a garantizar una instalación e implementación correctas de la granja de servidores.
  
Como puede esperar, hay que realizar algunos preparativos antes de empezar a implementar Skype Empresarial Server 2019. Este artículo le ayudará a planear lo siguiente:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Sistemas operativos](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Bases de datos de SQL back-end](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Sistema de nombres de dominio (DNS)](system-requirements.md#DNS)
  
- [Certificados](system-requirements.md#Certs)
  
- [Recurso compartido de archivos](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware para Skype Empresarial Server 2019
<a name="Hardware"> </a>

Una vez que haya bajado la topología (y si no lo hace, puede consultar el tema Conceptos básicos de topología para Skype Empresarial [Server 2019),](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) es el momento de pensar en los servidores. Los servidores de Skype Empresarial Server 2019 requieren hardware de 64 bits. A continuación se indican las recomendaciones para hardware. No son requisitos, pero reflejan los requisitos necesarios para un rendimiento óptimo. Tenemos documentación de planeación de capacidad que le ayudará a determinar si necesita más de esto, en función de sus circunstancias.
  
Hardware recomendado para servidores Standard Edition:

|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de Skype Empresarial Server 2019.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos con RAID 1 y 6 con RAID 10).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una sola dirección IP).  <br/> Las configuraciones duales o  múltiples no son compatibles con servidores front-end, servidores back-end y servidores Standard Edition. <br/> Siempre y cuando no estén expuestos al sistema operativo y se utilicen para supervisar y administrar el hardware del servidor, puede tener sistemas de administración fuera de banda, como DRAC o DESC. Este escenario no constituye un servidor multialocución y es compatible.  <br/> |


Hardware recomendado para servidores front-end y servidores back-end:
  
|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior. <br/> Los procesadores Intel Itanium no son compatibles con los roles de Skype Empresarial Server 2019.  <br/> |
|Memoria  <br/> |64 gigabytes (GB).  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos con RAID 1 y 6 con RAID 10).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una sola dirección IP).  <br/> Las configuraciones duales o  múltiples no son compatibles con servidores front-end, servidores back-end y servidores Standard Edition. <br/> Siempre y cuando no estén expuestos al sistema operativo y se utilicen para supervisar y administrar el hardware del servidor, puede tener sistemas de administración fuera de banda, como DRAC o DESC. Este escenario no constituye un servidor multialocución y es compatible.  <br/> |
   
Hardware recomendado para servidores perimetrales, servidores de mediación independientes y directores:
  
|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de Skype Empresarial Server 2019.  <br/> |
|Memoria  <br/> |32 gigabytes.  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración raid 1 de 2x).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 4 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una sola dirección IP).  <br/> No se admiten configuraciones  duales o múltiples para servidores y directores de interoperabilidad de vídeo. <br/> Los servidores perimetrales requerirán dos interfaces de red que son adaptadores de red de doble puerto, 1 Gbps o superior (o dos adaptadores de red emparejados, para un total de cuatro, cada par se combina con una sola dirección MAC y una única dirección IP, para un total de dos pares).  <br/> En los servidores de mediación independientes, se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para permitir la configuración de una dirección IP RTC específica.  <br/> |


> [!NOTE]
> Independientemente del rol de servidor, también recomendamos la siguiente configuración de hardware para Skype Empresarial Server 2019 (esto puede variar en función de la marca de hardware que haya comprado, por lo que consulte la documentación del fabricante para obtener información específica):
> - Configuración de BIOS: debe establecerse en PLANO desde NUMA.
> - Habilitar Hyperthreading.
> - La configuración de cola RSS debe establecerse en 8 cola.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Sistemas operativos para Skype Empresarial Server 2019
<a name="OS"> </a>

Una vez que tenga el hardware en su lugar, necesitará el sistema operativo de instalación (SO) que le permitirá instalar y usar correctamente Skype Empresarial Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Nada que no sea los sistemas operativos enumerados aquí no funcionará correctamente; Please don't try it for installs of Skype for Business Server 2019. Por ejemplo, la opción Server Core no aparece en la lista y, por lo tanto, no es compatible.

> [!NOTE]
> La actualización local del sistema operativo no es compatible con Lync Server 2013. Debe implementar un grupo independiente y migrar usuarios al nuevo grupo de servidores con un sistema operativo diferente. Todos los servidores de un grupo deben tener la misma versión del sistema operativo.

> [!NOTE]
> 
> Si vas a instalar Windows Admin Center 2019 en tu equipo con Windows Server 2019, te pedirá un puerto en el que escuchar. There's a liklilik you might choose port 443, but if that machine has Skype for Business Server 2019 installed on it, or is going to have Skype for Business Server 2019 installed on it, then you must choose a different port number.
> 
>¿Por qué es así? Si Windows Admin Center 2019 se ejecuta en el puerto 443, no podrá conectarse al servidor mediante el Panel de control de Skype Empresarial ni podrá conectarse a ningún servicio web interno que se ejecute en el servidor (servicio web de libreta de direcciones, servicio de detección automática, servicio WebTicket, etc.).  De hecho, no podrá conectarse a ninguna dirección URL de servicio web interno. Elija un puerto diferente en caso de que necesite o quiera colocar Windows Admin Center 2019 en un servidor con Skype Empresarial Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software que debe instalarse antes de una implementación de Skype Empresarial Server 2019
<a name="Software"> </a>

Hay algunas cosas que necesitará instalar o configurar para cualquier servidor que ejecute Skype Empresarial Server 2019. Estos se enumeran a continuación, seguidos de requisitos adicionales para roles de servidor específicos.

> [!IMPORTANT]
> Skype Empresarial 2019 admite .Net Framework 4.8. 
  
 **Todos los servidores:**
  
|**Software/rol**|**Detalles**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos los servidores de Skype Empresarial Server Windows PowerShell 3.0 instalado.  <br/> • Debe instalarse de forma predeterminada con Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Los servicios WCF son **una característica** que se instala como una característica de Windows, en el **Administrador** del servidor, inicialmente no se necesitan descargas. <br/> • Debe asegurarse de que, al instalar esta característica, o si ya está instalada y la está comprobando, también se comprueba e instala la opción de activación **HTTP,** de este modo: <br/> ![Captura de pantalla que muestra la opción de activación HTTP en las características de .NET Framework 4.5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> No se preocupe si recibe una ventana emergente adicional que dice que es necesario instalar algunas otras cosas para que se instale la activación HTTP. Eso es normal; haga clic en Aceptar y vaya adelante. Si no obtiene esta ventana emergente, puede suponer que esas cosas ya están instaladas y continuar.  <br/> Microsoft .NET Framework suele instalarse cuando se instala Windows Server 2016. Skype Empresarial Server requiere Microsoft .NET Framework 4.7 o 4.8, por lo que probablemente necesitará actualizarlo. Puede encontrar la actualización [aquí](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Para Windows Server 2016, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.  <br/> Todos los servidores front-end y los servidores Standard Edition usados para las conferencias requieren el tiempo de ejecución de Windows Media Format para ejecutar los archivos de Audio de Windows Media (.wma) que reproducen las aplicaciones Estacionamiento de llamadas, Anuncio y Grupo de respuesta para anuncios y música.  <br/> |
|Windows Identity Foundation  <br/> |Necesitamos Windows Identity Foundation 3.5 para admitir escenarios de autenticación de servidor a servidor para Skype Empresarial Server 2019.  <br/> • Para Windows Server 2016, no es necesario descargar nada. Abra **el Administrador del** servidor y vaya al Asistente para agregar roles y **características.** **Windows Identity Foundation 3.5 aparece** en la **sección** Características. Si está seleccionado, estás bien. De lo contrario, selecciónelo **y** haga clic en Siguiente para llegar **al botón** Instalar. <br/> |
|Herramientas de administración de servidor remoto  <br/> |Herramientas de administración de roles: herramientas de AD DS y AD LDS  <br/> |
   
 **Los servidores front-end y el servidor Standard Edition también necesitan:**
  
|**Software/rol**|**Detalles**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |Se necesita IIS en todos los servidores front-end, así como en todos los servidores Standard Edition, con los siguientes módulos seleccionados:  <br/> • Características http comunes: documento predeterminado, errores HTTP, contenido estático  <br/> • Estado y diagnóstico: registro HTTP, herramientas de registro, seguimiento  <br/> • Rendimiento: compresión de contenido estático, compresión de contenido dinámico  <br/> • Seguridad: filtrado de solicitudes, autenticación de asignación de certificados de cliente, autenticación de Windows  <br/> • Desarrollo de aplicaciones: extensibilidad de .NET 3.5, extensibilidad de .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, extensiones ISAPI, filtros ISAPI  <br/> • Herramientas de administración: Consola de administración de IIS, Scripts y herramientas de administración de IIS  <br/> Tenga en cuenta que el acceso anónimo también es necesario, pero lo obtiene al instalar IIS, por lo que no tiene lugar para seleccionarlo en la lista.  <br/> |
|Motor en tiempo de ejecución de Windows Media Format  <br/> | Para Windows Server 2016, tendrás que instalar la característica **Media Foundation** en el Administrador **del servidor.** You actually can start your Skype for Business Server 2019 installation without this, but you'll be prompted to install it, and then reboot the server, before the Skype for Business Server 2019 install continues. Es mejor hacerlo con antelación. <br/> |
|Silverlight  <br/> |Puede instalar la versión más reciente de Silverlight [aquí.](https://www.microsoft.com/silverlight/)  <br/> |
   
Para ayudarle, este es un script de PowerShell de ejemplo que puede ejecutar para automatizar esto:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bases de datos back-end que funcionarán con Skype Empresarial Server 2019
<a name="DBs"> </a>

Al instalar Skype Empresarial Server 2019 Standard Edition, tendrá SQL Server 2016 Express (edición de 64 bits).

Skype Empresarial Server 2019 Enterprise Edition requerirá un SQL Server completo, como se indica a continuación (solo la edición de 64 bits; no use ediciones de 32 bits):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (edición de 64 bits) y debe ejecutarse con las actualizaciones más recientes.  <br/> |Microsoft SQL Server 2017 (edición de 64 bits) y debe ejecutarse con las actualizaciones más recientes.  <br/> |
Microsoft SQL Server 2016 (edición de 64 bits) y debe ejecutarse con las actualizaciones más recientes.|
 |

Si no ves la edición SQL Server que quieres usar, no puedes usarla.
  
> [!NOTE]
> También debe instalar SQL Server Reporting Services para el rol de servidor de supervisión. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL clústeres y SQL AlwaysOn

SQL clústeres con Skype Empresarial Server 2019. Si desea configurar la agrupación SQL clústeres, esto se realiza en SQL Server.
  
Asegúrese de que tiene una configuración activa/pasiva para la SQL clústeres, que es compatible. No compartas el nodo pasivo con ninguna otra instancia SQL cliente.
  
Puede tener lo siguiente para clústeres de conmutación por error:
  
Dos nodos:
  
- Microsoft SQL Server 2019 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
- Microsoft SQL Server 2017 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
- Microsoft SQL Server 2016 Standard (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

Dieciséis nodos:
  
- Microsoft SQL Server 2019 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
- Microsoft SQL Server 2017 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.
- Microsoft SQL Server 2016 Enterprise (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente.

SQL se admite AlwaysOn y puede obtener más información sobre él en la alta disponibilidad del servidor [back-end en Skype Empresarial Server 2019.](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)
  

###  <a name="additional-server-installation-recommendations"></a>Recomendaciones adicionales de instalación del servidor:
  
No instale ningún software cliente de Microsoft Internet Security and Acceleration (ISA) Server ni ningún otro software winsock Layered Service Providers (LSP) (aquí se incluirían firewalls de terceros o software de inspección de red antivirus) en cualquiera de los servidores front-end o servidores de mediación independientes. Se ha observado un rendimiento deficiente del tráfico de medios cuando se instala ese software.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Aunque gran parte de los datos de configuración de los servidores y servicios se almacenan en el almacén de administración central de Skype Empresarial Server 2019, todavía hay algunas cosas almacenadas en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Extensiones para Skype Empresarial Server 2015 y Lync Server 2013, para mantener la compatibilidad con versiones anteriores admitidas  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto para aplicaciones (como la aplicación Grupo de respuesta y la aplicación Operador de conferencia)  <br/> |
||Datos publicados para lograr compatibilidad con versiones anteriores  <br/> |
||Un punto de control de servicio (SCP) para el almacén de administración central  <br/> |
||Cuenta de autenticación Kerberos (un objeto de equipo opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo para controladores de dominio

Se pueden usar los siguientes sistemas operativos de controlador de dominio:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
El nivel funcional de dominio de cualquier dominio en el que implemente Skype Empresarial Server 2019 y el nivel funcional de bosque de cualquier bosque en el que implemente Skype Empresarial Server 2019 debe ser uno de los siguientes:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
¿Puede tener controladores de dominio de solo lectura en estos entornos? Seguro, siempre y cuando también haya controladores de dominio grabables disponibles.
  
Es importante saber que Skype Empresarial Server 2019 no admite dominios con una sola etiqueta. ¿Qué son? Si tiene un dominio raíz con la etiqueta contoso.local, estará bien. Si tiene un dominio raíz que simplemente se denomina local, eso no funcionará y, como resultado, no se admite. Se ha escrito un poco más sobre esto [en este artículo de Knowledge Base.](https://support.microsoft.com/kb/300684/)
  
Skype Empresarial Server 2019 tampoco admite el cambio de nombre de dominios. If you really have to rename your domain, you'll need to uninstall Skype for Business Server 2019, do the domain rename, and then reinstall Skype for Business Server 2019.
  
Por último, puede que esté trabajando con un dominio con un entorno de AD DS bloqueado y eso es correcto. Tenemos más información sobre cómo implementar Skype Empresarial Server 2019 en un entorno de AD DS bloqueado en la documentación de implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Las topologías admitidas en Skype Empresarial Server 2019 son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
    
Tenemos diagramas y descripciones que le ayudarán a determinar qué topología tiene en su entorno o qué puede que necesite configurar antes de instalar Skype Empresarial Server 2019. Para que sea sencillo, también estamos incluyendo una clave:
  
![Es una clave para los iconos usados para los diagramas de topología de Skype Empresarial](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama del bosque único de Active Directory con un solo dominio](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No es más fácil que esto; es un bosque de dominio único, una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Un solo bosque, un solo árbol y un diagrama de dominios mutiple](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama muestra un solo bosque, de nuevo, pero también tiene uno o más dominios secundarios (hay tres en este ejemplo específico). Por lo tanto, el dominio en el que se crean los usuarios puede ser diferente del dominio en el que se implementa Skype Empresarial Server 2019. ¿Por qué preocuparse por esto? Es importante recordar que al implementar un grupo de servidores front-end de Skype Empresarial Server, todos los servidores de ese grupo deben estar en un solo dominio. Puede tener la administración entre dominios a través de la compatibilidad de Skype Empresarial Server con grupos de administradores universales de Windows.
  
En el diagrama anterior, puede ver que los usuarios de un dominio pueden acceder a los grupos de Skype Empresarial Server desde el mismo dominio o desde dominios diferentes, incluso si esos usuarios están en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Diagrama de un solo bosque, varios árboles y espacios de nombres distintos](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Es posible que tenga una topología similar a este diagrama, donde tiene un bosque, pero dentro de ese bosque hay varios dominios, con espacios de nombres de AD independientes. En este caso, este diagrama es una buena ilustración, ya que incluye usuarios de tres dominios diferentes que acceden a Skype Empresarial Server 2019. Las líneas sólidas indican que están accediendo a un grupo de Skype Empresarial Server en su propio dominio, mientras que una línea discontinua indica que van a un grupo de servidores en un árbol diferente.
  
Como puede ver, los usuarios del mismo dominio, el mismo árbol o incluso un árbol diferente pueden tener acceso a los grupos correctamente.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Varios bosques en un diagrama de topología de bosque central](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype Empresarial Server 2019 admite varios bosques configurados en una topología de bosque central. Si no está seguro de que es lo que tiene, el bosque central de la topología usa objetos en él para representar a los usuarios de los otros bosques y hospeda cuentas de usuario para cualquier usuario del bosque.
  
¿Cómo funciona? Un producto de sincronización de directorios (como Forefront Identity Manager o FIM) administra las cuentas de usuario de su organización a lo largo de su existencia. Cuando se crea o elimina una cuenta de un bosque, ese cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Claramente, si la infraestructura de AD está en su lugar, es posible que no sea fácil pasar a esta topología, pero si ya está allí o sigue planeando la infraestructura del bosque, esta puede ser una buena opción. Puede centralizar la implementación de Skype Empresarial Server 2019 en un solo bosque, mientras que los usuarios pueden buscar, comunicarse y ver la presencia de otros usuarios en cualquier bosque. Todas las actualizaciones de contactos de usuario se controlan automáticamente con software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial
<a name="BKMK_multipleforestopology"> </a>

![Varios bosques en un diagrama de topología de bosque de recursos](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es donde un bosque se dedica a ejecutar las aplicaciones de servidor, como Microsoft Exchange Server y Skype Empresarial Server 2019. Estos bosques de recursos también hospedan una representación sincronizada de objetos de usuario activos, pero no cuentas de usuario habilitadas para inicio de sesión. Por lo tanto, el bosque de recursos es un entorno de servicios compartidos para otros bosques en los que residen objetos de usuario y tienen una relación de confianza de nivel de bosque con el bosque de recursos.
  
Tenga en Exchange Server que se pueden implementar en el mismo bosque de recursos que Skype Empresarial Server o en un bosque diferente.
  
Para implementar Skype Empresarial Server 2019 en este tipo de topología, debería crear un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios (si Microsoft Exchange Server ya está en el entorno, esto se puede hacer automáticamente). A continuación, necesita una herramienta de sincronización de directorios (como Forefront Identity Manager o FIM) para administrar cuentas de usuario durante su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la topología descrita en Varios bosques en una topología de bosque de recursos [de Skype Empresarial.](system-requirements.md#BKMK_multipleforestopology)
  
En esta topología, hay uno o más bosques de usuarios y Skype Empresarial Server se implementa en un bosque de recursos dedicado. Exchange Server puede implementarse localmente en el mismo bosque de recursos o en un bosque diferente y configurarse para la implementación híbrida con Exchange Online, o exchange Online puede proporcionar servicios de correo electrónico exclusivamente para las cuentas locales. No hay ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD, un bosque de usuarios y un bosque de recursos. Los dos bosques tienen una relación de confianza. Se sincronizan con Microsoft 365 con Azure AD Connect. Todos los usuarios están habilitados para Skype Empresarial a través de Microsoft 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Hay una relación de plena confianza entre los bosques de Active Directory. La herramienta Azure Active Directory Connect se usa para sincronizar cuentas entre los bosques de usuarios locales y Microsoft 365 u Office 365.
  
 La organización también tiene Microsoft 365 u Office 365 y usa [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar sus cuentas locales con Microsoft 365 u Office 365. Los usuarios habilitados para Skype Empresarial se habilitan a través de Microsoft 365 u Office 365 y Skype Empresarial Online. Skype Empresarial Server no está implementado localmente.
  
La autenticación de inicio de sesión único la proporciona una granja de servicios de federación de Active Directory ubicada en el bosque de usuarios.
  
En este escenario, se admite la implementación de Exchange local, Exchange Online, una solución híbrida de Exchange o no tener Exchange implementado en absoluto. (El diagrama muestra solo Exchange local, pero las otras soluciones de Exchange también son totalmente compatibles).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial híbrido
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o más bosques de usuarios locales y Skype Empresarial se implementa en un bosque de recursos dedicado y está configurado para el modo híbrido con Skype Empresarial Online. Exchange Server puede implementarse localmente en el mismo bosque de recursos o en un bosque diferente y se puede configurar para la implementación híbrida con Exchange Online. Como alternativa, Exchange Online puede proporcionar exclusivamente los servicios de correo electrónico para las cuentas locales.
  
Para obtener más información, vea [Configurar un entorno de varios bosques para Skype Empresarial híbrido.](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)
  
## <a name="domain-name-system-dns"></a>Sistema de nombres de dominio (DNS)
<a name="DNS"> </a>

Skype Empresarial Server 2019 requiere DNS, por los siguientes motivos:
  
- DNS permite a Skype Empresarial Server 2019 detectar servidores internos o grupos de servidores, lo que permite las comunicaciones de servidor a servidor.
    
- DNS permite a los equipos cliente detectar el grupo de servidores front-end o el servidor Standard Edition que se usa para las transacciones SIP.
    
- Asocia direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite que los usuarios externos y los equipos cliente se conecten a los servidores perimetrales, o al proxy inverso HTTP, para mensajería instantánea (MI) o conferencias.
    
- Permite a los dispositivos de comunicaciones unificadas (UC) que no hayan iniciado sesión detectar el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos para obtener actualizaciones y enviar registros.
    
- El uso de DNS permite a los clientes móviles detectar automáticamente recursos de servicios web sin necesidad de que los usuarios escriban manualmente direcciones URL en la configuración del dispositivo.
    
- Se usa en el equilibrio de carga de DNS.
    
Es importante tener en cuenta que Skype Empresarial Server 2019 no admite nombres de dominio internacionalizados (IDN).
  
Y es muy importante recordar que cualquier nombre en DNS es idéntico al nombre de equipo configurado en cualquier servidor que esté utilizando Skype Empresarial Server 2019. En concreto, no podemos tener nombres cortos en el entorno y debemos tener FQDN para topology Builder.
  
Parece que sería lógico para cualquier equipo que ya esté unido a un dominio, pero si tiene un servidor perimetral que no está unido a su dominio, puede tener un nombre corto predeterminado, sin sufijo de dominio. Asegúrese de que ese no es el caso, ya sea en DNS o en el servidor perimetral, o en cualquier servidor o grupo de Skype Empresarial Server 2019, en ese caso.
  
Definitivamente, no use caracteres Unicode ni caracteres de subrayado. Los caracteres estándar (que son A-Z, a-z, 0-9 y guiones) son compatibles con DNS externo y las autoridades de certificación públicas (tendrá que asignar FQDN al SN en el certificado, es importante recordarlo), por lo que le ahorrará muchos problemas si lo asigna desde el principio.
  
Para obtener más información sobre los requisitos dns para redes, consulte la [sección Redes](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) de nuestra documentación de planeación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Una de las cosas más importantes que puede hacer antes de la implementación es asegurarse de que tiene los certificados en orden. Skype Empresarial Server 2019 necesita una infraestructura de clave pública (PKI) para la seguridad de la capa de transporte (TLS) y las conexiones de seguridad de la capa de transporte mutua (MTLS). Básicamente, para comunicarse de forma segura de forma estandarizada, Skype Empresarial Server usa certificados emitidos por las autoridades de certificación (CA).
  
Estos son algunos de los aspectos para los que Skype Empresarial Server 2019 usa certificados:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Federación mediante la detección automática basada en DNS de los socios
    
- Acceso de usuarios remotos a la mensajería instantánea (IM)
    
- Acceso de usuarios externos a sesiones de audio y vídeo (AV), uso compartido de aplicaciones y conferencias
    
- Hablar con aplicaciones web y Outlook Web Access (OWA)
    
Por lo tanto, la planeación de certificados es imprescindible. Ahora, echemos un vistazo a una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben estar firmados mediante un algoritmo de firma admitido por el sistema operativo. Skype Empresarial Server 2019 admite el conjunto de aplicaciones SHA-1 y SHA-2 de tamaños de resumen (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo.
    
- La inscripción automática es compatible con los servidores internos que ejecutan Skype Empresarial Server 2019.
    
- La inscripción automática no es compatible con los servidores perimetrales de Skype Empresarial Server 2019.
    
> [!NOTE]
> El uso del algoritmo de firma RSASSA-PSS no es compatible y puede provocar errores en el inicio de sesión y el reenvío de llamadas, entre otros problemas. 
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomiendan longitudes clave de 2048 y superiores.
    
- El algoritmo predeterminado de síntesis o firma hash es RSA. También ECDH_P256, ECDH_P384 y ECDH_P521 algoritmos.
    
Eso es muy importante y hay una variedad de niveles de comodidad con la solicitud de certificados de una CA. Le proporcionaremos más instrucciones a continuación para que su planificación sea lo más sencilla posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos y lo más probable es que los obtenga de una CA interna (es decir, una CA ubicada en su dominio). Si lo desea, puede solicitar estos certificados a una CA externa (una ubicada en Internet). Si se está preguntando a qué ENTIDAD pública debe ir, puede consultar la lista de asociados de certificados [de comunicaciones](/SkypeForBusiness/certification/services-ssl) unificadas.
  
También necesitará certificados cuando Skype Empresarial Server 2019 se comunique con otras aplicaciones y servidores, como Microsoft Exchange Server. Obviamente, esto tendrá que ser un certificado que estas otras aplicaciones y servidores puedan usar de forma compatible. Skype Empresarial Server 2019 y otros productos de Microsoft admiten el protocolo open authorization (OAuth) para la autenticación y autorización de servidor a servidor. Si está interesado en esto, tenemos un artículo de planeación adicional para OAuth y Skype Empresarial Server 2019.
  
Skype Empresarial Server 2019 también admite (sin necesidad) certificados firmados con la función hash criptográfica SHA-256. Para admitir el acceso externo mediante SHA-256, una CA pública debe emitir el certificado externo mediante SHA-256.
  
Para que todo sea sencillo, hemos incluido los requisitos de certificado para servidores Standard Edition, grupos de servidores front-end y otros roles en las tablas siguientes, con el contoso.com ficticio en uso para ejemplos (probablemente usará algo más para su entorno). Todos estos son certificados de servidor web estándar, con claves privadas que no son exportables. Algunos aspectos adicionales a tener en cuenta:
  
- El uso mejorado de claves (EKU) del servidor se configura automáticamente cuando se usa el asistente para certificados para solicitar certificados.
    
- Cada nombre descriptivo del certificado debe ser único en el almacén del equipo.
    
- Según los nombres de ejemplo siguientes, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deben agregarse al nombre alternativo de sujeto (SAN) del certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En los servidores Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo de servidores.  <br/> El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que es el mismo que el FQDN del servidor)  <br/> AND  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |No puede reemplazar el FQDN web interno en el Generador de topologías.  <br/> Si tiene varias direcciones URL sencillas de reunión, debe incluirlas todas como SAN.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> AND  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Reunir direcciones URL sencillas por dominio SIP  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para servidores front-end en un grupo de servidores front-end:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que NO es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de skype empresarial  <br/> AND  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> AND  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el director:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |Grupo de servidores Director  <br/> |FQDN del director, FQDN del grupo de directores.  <br/> Si este grupo es el servidor de inicio automático de sesión para los clientes y se requiere una coincidencia estricta de DNS en la directiva de grupo, también necesitará entradas para sip.sipdomain (para cada dominio SIP que tenga).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Si este grupo de servidores del director es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de skype empresarial  <br/> AND  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> AND  <br/> • Reunir direcciones URL sencillas por dominio SIP  <br/> • Dirección URL sencilla de acceso telefónico  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |El FQDN web externo del director debe ser diferente del grupo de servidores front-end o del servidor front-end.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificados para servidor de mediación independiente:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del servidor miembro del grupo de servidores  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para la aplicación de sucursal con funciones de supervivencia (concretamente, aplicación de sucursal con funciones de supervivencia 2015 para Skype Empresarial Server 2019):
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP. \< sipdomain \> (solo necesita una entrada por dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (perimetral)

Skype Empresarial Server 2019 admite el uso de un único certificado público para interfaces perimetrales externas de acceso y conferencia web, además del servicio de autenticación A/V, que se proporciona **a** través de los servidores perimetrales. La interfaz interna perimetral normalmente usará un certificado privado emitido por la CA interna, pero si lo prefiere, también puede usar un certificado público para esto, si es de una CA de confianza.
  
El proxy inverso (RP) también va a usar un certificado público y cifra la comunicación de su RP a los clientes, y el RP a los servidores internos mediante HTTP (o más exactamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si va a implementar la movilidad y admite la detección automática para clientes móviles, tendrá que incluir algunas entradas de nombre alternativo de sujeto adicionales en los certificados para admitir las conexiones seguras de los clientes móviles.
  
Necesitará nombres san para la detección automática en los siguientes certificados:
  
- Grupo de servidores Director
    
- Grupo de servidores front-end
    
- Proxy inverso
    
Los detalles se enumeran en las tablas siguientes.
  
Aquí es donde un poco de planeación previa es buena, pero a veces ha implementado Skype Empresarial Server 2019 sin tener intención de implementar la movilidad, y eso se presenta más adelante cuando ya tiene certificados en su entorno. Volver a emitirlos a través de una CA interna suele ser bastante fácil, pero con certificados públicos de una CA pública, esto puede ser un poco más caro.
  
Si eso es lo que está viendo y si tiene muchos dominios SIP (lo que encarecería la adición de SANS), puede configurar el proxy inverso para que use HTTP para la solicitud inicial del servicio de detección automática, en lugar de usar HTTPS (que es la configuración predeterminada). El [artículo Plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) contiene más información al respecto.
  
Requisitos de certificado de grupo de directores y grupo de servidores front-end:
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|Url del servicio Detección automática interna  <br/> |SAN=lyncdiscoverinternal. \< sipdomain\>  <br/> |
|Url del servicio de detección automática externa  <br/> |SAN=lyncdiscover. \< sipdomain\>  <br/> |
   
También puede usar SAN= \* . \< sipdomain\>
  
Requisitos de certificado de proxy inverso (CA pública):
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|Url del servicio de detección automática externa  <br/> |SAN=lyncdiscover. \< sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado a la escucha de SSL en el proxy inverso.
  
> [!NOTE]
> El agente de escucha de proxy inverso va a tener SAN para las direcciones URL de los servicios web externos. Algunos ejemplos serían SAN=skypewebextpool01.contoso.com y dirwebexternal.contoso.com, si ha implementado el director (que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype Empresarial Server 2019 puede usar el mismo recurso compartido de archivos para todo el almacenamiento de archivos. Debe tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en almacenamiento conectado directo (DAS) o en una red de área de almacenamiento (SAN), lo que incluye el Sistema de archivos distribuido (DFS), así como una matriz redundante de discos independientes (RAID) para almacenes de archivos. Para obtener más información sobre DFS para Windows Server 2012, echa un vistazo [a esta página DFS.](https://technet.microsoft.com/library/jj127250.aspx)
    
- Se recomienda un clúster compartido para el recurso compartido de archivos. Si ya estás usando uno, debes agrupar Windows Server 2012 o versiones posteriores

> [!Note]
> **¿Por qué la versión más reciente de Windows?** Es posible que las versiones anteriores no tengan los permisos adecuados para habilitar todas las características. Puede usar el Administrador de clústeres para crear los recursos compartidos de archivos. Vea este artículo de soporte [técnico sobre cómo crear recursos compartidos de archivos en un clúster](https://support.microsoft.com/help/224967) para obtener más información.
    
> [!CAUTION]
> Debes saber que no se admite el uso de almacenamiento conectado a la red (NAS) como recurso compartido de archivos, por lo que usa una de las opciones enumeradas anteriormente. Esta limitación de compatibilidad se debe al diseño variable de dispositivos NAS que tienen que proporcionar capacidad de adaptación del sistema de archivos al equipo basado en Windows Server que accede al sistema de archivos compartido de los dispositivos.
  







