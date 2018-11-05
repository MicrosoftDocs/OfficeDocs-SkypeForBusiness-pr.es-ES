---
title: 'Lync Server 2013: Requisitos adicionales de software'
TOCTitle: Requisitos adicionales de software
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48275918
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos adicionales de software para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Además de los requisitos del sistema operativo y el hardware para las plataformas de servidor, Lync Server 2013 requiere la instalación de software adicional en los servidores que implemente.


> [!NOTE]
> Para ver más detalles sobre los requisitos de la plataforma de servidores que ejecutan Lync Server, consulte <A href="lync-server-2013-server-hardware-platforms.md">Plataformas de hardware de servidor para Lync Server 2013</A> y <A href="lync-server-2013-server-and-tools-operating-system-support.md">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</A>. Para ver más detalles acerca de los requisitos del sistema de dispositivos y equipos cliente, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planeación de clientes y dispositivos en Lync Server 2013</A> en la documentación sobre planeación. Para ver más información sobre los requisitos de software de las herramientas administrativas, consulte <A href="lync-server-2013-administrative-tools-software-requirements.md">Requisitos de software para herramientas administrativas en Lync Server 2013</A>.



## Software adicional necesario para todos los roles de servidor interno

En esta sección se enumera el software necesario para todos los roles de servidor interno, que todos son roles de servidor Lync Server excepto para el servidor perimetral. Los requisitos para Servidores perimetrales y Grupos de servidores perimetrales se indican más adelante en **Software adicional para servidores perimetrales**.

## Windows PowerShell 3.0

Cada servidor que ejecute Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell. Para obtener más detalles, consulte [Instalar Windows PowerShell 3.0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

## Microsoft .NET Framework 4.5

Lync Server requiere Microsoft .NET Framework 4.5 en todos los roles de servidor interno y en un equipo donde ejecutará las herramientas administrativas de Lync Server o Microsoft Lync Server 2013, herramienta de planeación. Para Lync Server 2013, debe instalar manualmente la versión de 64 bits de Microsoft .NET Framework 4.5 en el servidor antes de la instalación de Lync Server 2013. Para instalarlo manualmente, descargue Microsoft .NET 4.5 Framework desde el Centro de descarga de Microsoft en [http://go.microsoft.com/fwlink/p/?LinkId=268529](http://go.microsoft.com/fwlink/p/?linkid=268529)

## Instalar Microsoft .NET Framework 4.5 en servidores con Windows Server 2012

Cuando instale Microsoft .NET Framework 4.5 en servidores que ejecutarán Lync Server 2013 y Windows Server 2012, será necesario que realice un paso adicional. Tras la instalación de NET Framework 4.5, use el Administrador de servidores para instalar la Activación HTTP.

**Para instalar la Activación HTTP .NET 4.5 en Windows Server 2012**

1.  En el menú **Inicio** , haga clic en **Programas** , en **Herramientas administrativas** y, después, en **Administrador de servidores** .

2.  Una vez esté en Administrador de servidores, en **Resumen de características** , elija **Agregar características** .

3.  Expanda **.NET Framework 4.5** .

4.  Seleccione **Activación WCF** si no está seleccionada. Después, seleccione **Activación HTTP** .

5.  Haga clic en **Siguiente** y siga las indicaciones para completar la instalación.

## Windows Identity Foundation

**Windows Identity Foundation** en Lync Server 2013 requiere que se instale Windows Identity Foundation para dar cabida a escenarios de autenticación entre servidores. Los procedimientos para instalar Windows Identity Foundation en Windows Server 2008 R2 y Windows Server 2012 son diferentes. Seleccione el sistema operativo de la siguiente lista:

  - Windows Server 2008 R2   Para Windows Server 2008 R2, compruebe si ya está instalado en su equipo. Para ello, vaya a **Agregar o quitar programas** , **Ver actualizaciones instaladas** y busque en **Windows** la entrada **Windows Identity Foundation (KB974405)** . Para más información sobre la instalación de Windows Identity Foundation, consulte <http://go.microsoft.com/fwlink/?linkid=204657>.

  - Windows Server 2012   Para Windows Server 2012, se usa el **Administrador de servidores** para instalar Windows Identity Foundation. En el **Asistente para agregar roles y características** del Administrador de servidores, seleccione **Características** . Seleccione **Windows Identity Foundation 3.5** de la lista, haga clic en **Siguiente** y, después, en **Instalar** .

## Software adicional para todos los servidores front-end y servidores Standard Edition

Todos los servidores front-end y servidores Standard Edition deben ejecutar también Servicios de Internet Information Server (IIS) con determinados módulos. Además, todos los servidores front-end y servidores Standard Edition que tengan implementadas las conferencias, el Aplicación de estacionamiento de llamadas, los anuncios o los grupos de respuesta deben ejecutar Tiempo de ejecución de Windows Media Format.

## Servicios de Internet Information Server (IIS)

Los servidores front-end y los servidores Standard Edition deben ejecutar Servicios de Internet Information Server (IIS), con los siguientes módulos:

  - Contenido estático

  - Documento predeterminado

  - Errores HTTP

  - ASP.NET

  - Extensibilidad de .NET

  - Extensiones de Internet Server API (ISAPI)

  - Filtros ISAPI

  - Registro HTTP

  - Herramientas de registro

  - Seguimiento

  - Autenticación de Windows

  - Filtro de solicitudes

  - Compresión de contenido estático

  - Compresión de contenido dinámico

  - Consola de administración de IIS

  - Scripts y herramientas de administración de IIS

  - Autenticación anónima (se instala de forma predeterminada al instalar IIS).

  - Autenticación por asignación de certificados de clientes

## Tiempo de ejecución de Windows Media Format y experiencia de escritorio de Windows

**Experiencia de escritorio de Windows** Todos los servidores front-end y servidores Standard Edition donde se vayan a implementar las conferencias deben tener instalado el Tiempo de ejecución de Windows Media Format, que, excepto para Windows Server 2012, está instalado como parte de la experiencia de escritorio de Windows. Windows Server 2012 requiere Microsoft Media Foundation. El Tiempo de ejecución de Windows Media Format es necesario para ejecutar los archivos de Windows Media Audio (.wma) que reproducen las aplicaciones de Estacionamiento de llamadas, anuncio y grupo de respuesta para los anuncios y la música.

Se recomienda instalar la experiencia de escritorio de Windows antes de instalar Lync Server 2013. Si Lync Server 2013 no encuentra este software en el servidor, le solicitará que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.

## Software adicional para los servidores Front End y servidores Standard Edition que se ejecutan en un Windows Server 2012

Servidores front-end requiere .NET 3.5, que no está instalado de forma predeterminada en Windows Server 2012. Para instalarlo, ponga sus medios de instalación de Windows Server 2012 en la Unidad D y escriba lo siguiente:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Para más información sobre cómo instalar .NET 3.5 en servidores que ejecuten Windows Server 2012, consulte las consideraciones sobre la implementación de Microsoft .NET Framework 3.5 en <http://go.microsoft.com/fwlink/?linkid=275032>.

## Software adicional para directores

Los directores deben ejecutar Servicios de Internet Information Server (IIS), con los siguientes módulos:

  - Contenido estático

  - Documento predeterminado

  - Errores HTTP

  - ASP.NET

  - Extensibilidad de .NET

  - Extensiones de Internet Server API (ISAPI)

  - Filtros ISAPI

  - Registro HTTP

  - Herramientas de registro

  - Seguimiento

  - Autenticación de Windows

  - Filtro de solicitudes

  - Compresión de contenido estático

  - Consola de administración de IIS

  - Scripts y herramientas de administración de IIS

  - Autenticación anónima (se instala de forma predeterminada al instalar IIS).

  - Autenticación por asignación de certificados de clientes

## Software adicional para los servidores Front End de chat persistente

Los servidores Front End de chat persistente deben ejecutar colas de mensajes (también conocidas como MSMQ), que es un componente de Windows Server.

Para información sobre cómo habilitar MSMQ, [haga clic aquí.](http://technet.microsoft.com/en-us/library/cc771474.aspx)

## Software adicional para servidores perimetrales

Los Servidores perimetrales necesitan el software siguiente:

  - Cada servidor que ejecute Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell. Para obtener más detalles, consulte [Instalar Windows PowerShell 3.0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server requiere Microsoft .NET Framework 4.5. En el caso de Lync Server 2013 instalado en Windows Server 2008 R2, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4.5 en el servidor antes de instalar Lync Server 2013. Para instalarla manualmente, descargue Microsoft .NET 4.5 Framework RC del Centro de descarga de Microsoft en <http://go.microsoft.com/fwlink/?linkid=268529>

  - **Windows Identity Foundation** en Lync Server 2013 requiere que se instale Windows Identity Foundation para dar cabida a escenarios de autenticación entre servidores. Los procedimientos para instalar Windows Identity Foundation en Windows Server 2008 R2 y Windows Server 2012 son diferentes. Seleccione el sistema operativo de la siguiente lista:
    
      - Windows Server 2008 R2   Para Windows Server 2008 R2, compruebe si ya está instalado en su equipo. Para ello, vaya a **Agregar o quitar programas** , **Ver actualizaciones instaladas** y busque en **Windows** la entrada **Windows Identity Foundation (KB974405)** . Para más información sobre la instalación de Windows Identity Foundation, consulte <http://go.microsoft.com/fwlink/?linkid=204657>.
    
      - Windows Server 2012   Para Windows Server 2012, se usa el **Administrador de servidores** para instalar Windows Identity Foundation. En el **Asistente para agregar roles y características** del Administrador de servidores, seleccione **Características** . Seleccione **Windows Identity Foundation 3.5** de la lista, haga clic en **Siguiente** y, después, en **Instalar** .

## No instale proveedores de sockets por niveles en servidores multimedia

No instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server, ni ningún otro software de proveedores de servicio por niveles (LSP) Winsock, en ningún servidor front-end o servidor de mediación independiente. La instalación de este software puede provocar un rendimiento deficiente del tráfico multimedia.

## Vea también

#### Conceptos

[Requisitos de software para herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

