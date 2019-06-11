---
title: 'Lync Server 2013: Requisitos adicionales de software'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Requisitos adicionales de software para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_

Además de los requisitos de hardware y sistema operativo para las plataformas de servidor, Lync Server 2013 requiere la instalación de software adicional en los servidores que implemente.

<div>


> [!NOTE]  
> Para obtener más información sobre los requisitos de plataforma para servidores que ejecutan Lync Server, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync server 2013</A> y <A href="lync-server-2013-server-and-tools-operating-system-support.md">compatibilidad del sistema operativo de servidor y herramientas en Lync Server 2013</A>. Para obtener más información sobre los requisitos del sistema para equipos y dispositivos cliente, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">planificación de clientes y dispositivos en Lync Server 2013</A> en la documentación de planeación. Para obtener más información sobre los requisitos de software para herramientas administrativas, consulte <A href="lync-server-2013-administrative-tools-software-requirements.md">requisitos de software de herramientas administrativas en Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Software adicional necesario para todos los roles de servidor internos

Esta sección muestra el software necesario en todos los roles de servidor internos, que son los roles de Lync Server Server excepto el servidor perimetral. Los requisitos para los servidores perimetrales y las agrupaciones perimetrales se enumeran más adelante en este tema, **software adicional para servidores perimetrales**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Cada servidor que ejecute Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell 3,0. Para obtener más información, consulte [instalar Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server requiere Microsoft .NET Framework 4,5 en todos los roles de servidor internos y en cualquier equipo en el que se ejecuten las herramientas administrativas de Lync Server o Microsoft Lync Server 2013, herramienta de planeación. Para Lync Server 2013, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4,5 en el servidor antes de instalar Lync Server 2013. Para instalarlo manualmente, descargue Microsoft .NET 4,5 Framework desde el centro de descarga de Microsoft en[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Instalar Microsoft .NET Framework 4,5 en servidores con Windows Server 2012

Al instalar Microsoft .NET Framework 4,5 en servidores que ejecutarán Lync Server 2013 y Windows Server 2012, debe realizar un paso adicional. Después de instalar .NET Framework 4,5, use el administrador del servidor para instalar la activación de HTTP.

**Para instalar la activación HTTP de .NET 4,5 en Windows Server 2012**

1.  En el menú **Inicio** , haga clic en **programas**y, a continuación, en **herramientas administrativas**y en **Administrador del servidor**.

2.  En Administrador del servidor, en **Resumen de características**, elija **Agregar características**.

3.  Expanda **.NET Framework 4,5**.

4.  Seleccione **activación de WCF** si aún no está seleccionada. Después, seleccione **activación http**.

5.  Haga clic en **siguiente** y siga las indicaciones para finalizar la instalación.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**Windows Identity Foundation** en Lync Server 2013 requiere la instalación de Windows Identity Foundation para admitir escenarios de autenticación de servidor a servidor. Windows Server 2008 R2 y Windows Server 2012 requieren procedimientos diferentes para instalar Windows Identify Foundation. Seleccione el sistema operativo de su servidor en la siguiente lista:

  - Windows Server 2008 R2 para Windows Server 2008 R2, puede comprobar si ya se ha instalado en el equipo. Para ello, vaya a **Agregar o quitar programas**, **ver actualizaciones instaladas**y busque en **Windows** la base de **identidad de Windows (KB974405)**. Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.

  - Windows Server 2012 para Windows Server 2012, use el **Administrador del servidor** para instalar Windows Identity Foundation. En el administrador del servidor, **agregue roles y características y**, después, seleccione **características**. Seleccione **Windows Identity Foundation 3,5** de la lista. Haga clic en **siguiente**y luego en **instalar**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Software adicional para todos los servidores front-end y los servidores Standard Edition

Todos los servidores front-end y los servidores Standard Edition también deben ejecutar servicios de Internet Information Server (IIS) con determinados módulos. Además, todos los servidores front-end y los servidores Standard Edition en los que se implementan las conferencias, la aplicación de estacionamiento de llamadas, la presentación o los grupos de respuesta deben ejecutar el Windows Media Format Runtime.

<div>

## <a name="internet-information-services-iis"></a>Servicios de Internet Information Server (IIS)

Los servidores front-end y los servidores Standard Edition deben ejecutar servicios de Internet Information Server (IIS), con los siguientes módulos:

  - Contenido estático

  - Documento predeterminado

  - Errores HTTP

  - ASP.NET

  - Extensibilidad de .NET

  - Extensiones de API de servidor de Internet (ISAPI)

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

  - Autenticación anónima (se instala de forma predeterminada cuando se instala IIS).

  - Autenticación por asignación de certificados de clientes

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime y experiencia de escritorio de Windows

**Experiencia de escritorio de Windows** Todos los servidores front-end y los servidores Standard Edition en los que se implemente la Conferencia deben tener instalado el Windows Media Format Runtime, que, excepto Windows Server 2012, se instala como parte de la experiencia de escritorio de Windows. Windows Server 2012 requiere Microsoft Media Foundation. El tiempo de ejecución de Windows Media Format es necesario para ejecutar los archivos de audio de Windows Media (. WMA) que las aplicaciones de los grupos estacionamiento, anuncio y respuesta de llamadas se reproducen para anuncios y música.

Le recomendamos que instale la experiencia de escritorio de Windows antes de instalar Lync Server 2013. Si Lync Server 2013 no encuentra este software en el servidor, le pedirá que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Software adicional para servidores front-end y servidores Standard Edition que se ejecutan en Windows Server 2012

Los servidores front-end requieren .NET 3,5, que no se instala de forma predeterminada en Windows Server 2012. Para instalarlo, ponga el medio de instalación de Windows Server 2012 en la unidad D y escriba lo siguiente:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Para obtener más información sobre cómo instalar .NET 3,5 en servidores que ejecuten Windows Server 2012, consulte "consideraciones de implementación <https://go.microsoft.com/fwlink/p/?linkid=275032>de Microsoft .net Framework 3,5" en.

</div>

<div>

## <a name="additional-software-for-directors"></a>Software adicional para directores

Los directores deben ejecutar servicios de Internet Information Server (IIS), con los siguientes módulos:

  - Contenido estático

  - Documento predeterminado

  - Errores HTTP

  - ASP.NET

  - Extensibilidad de .NET

  - Extensiones de API de servidor de Internet (ISAPI)

  - Filtros ISAPI

  - Registro HTTP

  - Herramientas de registro

  - Seguimiento

  - Autenticación de Windows

  - Filtro de solicitudes

  - Compresión de contenido estático

  - Consola de administración de IIS

  - Scripts y herramientas de administración de IIS

  - Autenticación anónima (se instala de forma predeterminada cuando se instala IIS).

  - Autenticación por asignación de certificados de clientes

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Software adicional para servidores de solicitudes de cliente de chat persistentes

Los servidores de solicitudes de cliente de chat persistente deben ejecutar Message Queuing (también conocido como MSMQ), que es un componente de Windows Server.

Para obtener información sobre cómo habilitar MSMQ, [haga clic aquí.](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Software adicional para servidores perimetrales

Los servidores perimetrales requieren el software siguiente:

  - Cada servidor que ejecute Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell 3,0. Para obtener más información, consulte [instalar Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server requiere Microsoft .NET Framework 4,5. Para Lync Server 2013 instalado en Windows Server 2008 R2, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4,5 en el servidor antes de instalar Lync Server 2013. Para instalarlo manualmente, descargue Microsoft .NET 4,5 Framework desde el centro de descarga de Microsoft en[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** en Lync Server 2013 requiere la instalación de Windows Identity Foundation para admitir escenarios de autenticación de servidor a servidor. Windows Server 2008 R2 y Windows Server 2012 requieren procedimientos diferentes para instalar Windows Identify Foundation. Seleccione el sistema operativo de su servidor en la siguiente lista:
    
      - Windows Server 2008 R2 para Windows Server 2008 R2, puede comprobar si ya se ha instalado en el equipo. Para ello, vaya a **Agregar o quitar programas**, **ver actualizaciones instaladas**y busque en **Windows** la base de **identidad de Windows (KB974405)**. Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.
    
      - Windows Server 2012 para Windows Server 2012, use el **Administrador del servidor** para instalar Windows Identity Foundation. En el administrador del servidor, **agregue roles y características y**, después, seleccione **características**. Seleccione **Windows Identity Foundation 3,5** de la lista. Haga clic en **siguiente**y luego en **instalar**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>No instalar proveedores de sockets superpuestos en servidores multimedia

No instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server o cualquier otro software de proveedores de servicios de niveles (LSP) Winsock, en servidores de aplicaciones para usuario o en servidores de mediación independientes. Instalar este software podría causar un bajo rendimiento del tráfico de medios.

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de software para herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

