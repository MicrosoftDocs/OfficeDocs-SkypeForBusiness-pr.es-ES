---
title: 'Lync Server 2013: requisitos de software adicionales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e725c4c425492316d13b4a1f5957e37199f1521f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Requisitos de software adicionales para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_

Además de los requisitos de hardware y sistema operativo para las plataformas de servidor, Lync Server 2013 requiere la instalación de software adicional en los servidores que se implementan.

<div>


> [!NOTE]  
> Para obtener más información sobre los requisitos de plataforma para servidores que ejecutan Lync Server, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync server 2013</A> y la <A href="lync-server-2013-server-and-tools-operating-system-support.md">compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013</A>. Para obtener más información sobre los requisitos del sistema para equipos cliente y dispositivos, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> en la documentación referente a la planeación. Para obtener más información sobre los requisitos de software para herramientas administrativas, consulte <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative Tools software requirements in Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Software adicional necesario para todos los roles de servidor internos

En esta sección se enumera el software necesario en todos los roles de servidor internos, todos los roles de servidor de Lync Server excepto el servidor perimetral. Los requisitos para los servidores perimetrales y los grupos de servidores perimetrales se enumeran más adelante en este tema, en **software adicional para servidores perimetrales**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Cada servidor que ejecuta Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell 3,0. Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server requiere Microsoft .NET Framework 4,5 en todos los roles de servidor interno y en cualquier equipo en el que vaya a ejecutar las herramientas administrativas de Lync Server o Microsoft Lync Server 2013, herramienta de planeación. Para Lync Server 2013, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4,5 en el servidor antes de instalar Lync Server 2013. Para instalarlo manualmente, descargue Microsoft .NET 4,5 Framework desde el centro de descarga de Microsoft en[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Instalación de Microsoft .NET Framework 4,5 en servidores que ejecutan Windows Server 2012

Al instalar Microsoft .NET Framework 4,5 en servidores que van a ejecutar Lync Server 2013 y Windows Server 2012, debe realizar un paso adicional. Una vez instalado .NET Framework 4,5, use el administrador del servidor para instalar la activación HTTP.

**Para instalar la activación HTTP de .NET 4,5 en Windows Server 2012**

1.  En el menú **Inicio** , haga clic en **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de servidores**.

2.  En Administrador del servidor, en **Resumen de características**, elija **Agregar características**.

3.  Expanda **.NET Framework 4,5**.

4.  Seleccione **activación de WCF** si aún no está seleccionada. A continuación, seleccione **activación http**.

5.  Haga clic en **siguiente** y siga las instrucciones para finalizar la instalación.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**Windows Identity Foundation** en Lync Server 2013 requiere la instalación de Windows Identity Foundation para admitir escenarios de autenticación de servidor a servidor. Windows Server 2008 R2 y Windows Server 2012 requieren diferentes procedimientos para instalar la base de identidad de Windows. Seleccione el sistema operativo del servidor de la siguiente lista:

  - Windows Server 2008 R2 para Windows Server 2008 R2, puede comprobar si ya se ha instalado en el equipo. Para ello, vaya a **Agregar o quitar programas**, **vea actualizaciones instaladas**y busque en **Windows** la entrada **Windows Identity Foundation (KB974405)**. Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.

  - Windows Server 2012 para Windows Server 2012, use el **Administrador de servidores** para instalar Windows Identity Foundation. En el **Asistente para agregar roles y características**del administrador del servidor, seleccione **características**. Seleccione **Windows Identity Foundation 3,5** en la lista. Haga clic en **siguiente**y, a continuación, en **instalar**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Software adicional para todos los servidores front-end y servidores Standard Edition

Todos los servidores front-end y los servidores Standard Edition también deben ejecutar Internet Information Services (IIS) con determinados módulos. Además, todos los servidores front-end y los servidores Standard Edition en los que se implementan las conferencias, la aplicación de estacionamiento de llamadas, el anuncio o los grupos de respuesta deben ejecutar el tiempo de ejecución de Windows Media Format.

<div>

## <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

Los servidores front-end y los servidores Standard Edition deben ejecutar Internet Information Services (IIS), con los siguientes módulos:

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

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Tiempo de ejecución de Windows Media Format y experiencia de escritorio de Windows

**Experiencia de escritorio de Windows** Todos los servidores front-end y los servidores Standard Edition en los que se va a implementar la Conferencia deben tener instalado el tiempo de ejecución de Windows Media Format, que, excepto Windows Server 2012, se instala como parte de la experiencia del escritorio de Windows. Windows Server 2012 requiere Microsoft Media Foundation. Este software es necesario para ejecutar los archivos de Windows Media Audio (.wma) que reproducen las aplicaciones de estacionamiento de llamadas, anuncio y grupo de respuesta para los anuncios y la música.

Le recomendamos que instale la experiencia de escritorio de Windows antes de instalar Lync Server 2013. Si Lync Server 2013 no encuentra este software en el servidor, se le pedirá que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Software adicional para servidores front-end y servidores Standard Edition que se ejecutan en Windows Server 2012

Los servidores front-end requieren .NET 3,5, que no está instalado de forma predeterminada en Windows Server 2012. Para instalarlo, coloque los medios de instalación de Windows Server 2012 en la unidad D y escriba lo siguiente:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Para obtener más información sobre cómo instalar .NET 3,5 en servidores que ejecutan Windows Server 2012, consulte "consideraciones de implementación <https://go.microsoft.com/fwlink/p/?linkid=275032>de Microsoft .net Framework 3,5" en.

</div>

<div>

## <a name="additional-software-for-directors"></a>Software adicional para directores

Los directores deben ejecutar Internet Information Services (IIS), con los siguientes módulos:

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

  - Autenticación anónima (se instala de forma predeterminada al instalar IIS)

  - Autenticación por asignación de certificados de clientes

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Software adicional para servidores front-end de chat persistente

Los servidores front-end de chat persistente deben ejecutar Message Queuing (también conocido como MSMQ), que es un componente de Windows Server.

Para obtener información sobre cómo habilitar MSMQ, [haga clic aquí.](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Software adicional para servidores perimetrales

Los servidores perimetrales requieren el siguiente software:

  - Cada servidor que ejecuta Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell 3,0. Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server requiere Microsoft .NET Framework 4,5. Para Lync Server 2013 instalado en Windows Server 2008 R2, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4,5 en el servidor antes de instalar Lync Server 2013. Para instalarlo manualmente, descargue Microsoft .NET 4,5 Framework desde el centro de descarga de Microsoft en[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** en Lync Server 2013 requiere la instalación de Windows Identity Foundation para admitir escenarios de autenticación de servidor a servidor. Windows Server 2008 R2 y Windows Server 2012 requieren diferentes procedimientos para instalar la base de identidad de Windows. Seleccione el sistema operativo del servidor de la siguiente lista:
    
      - Windows Server 2008 R2 para Windows Server 2008 R2, puede comprobar si ya se ha instalado en el equipo. Para ello, vaya a **Agregar o quitar programas**, **vea actualizaciones instaladas**y busque en **Windows** la entrada **Windows Identity Foundation (KB974405)**. Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.
    
      - Windows Server 2012 para Windows Server 2012, use el **Administrador de servidores** para instalar Windows Identity Foundation. En el **Asistente para agregar roles y características**del administrador del servidor, seleccione **características**. Seleccione **Windows Identity Foundation 3,5** en la lista. Haga clic en **siguiente**y, a continuación, en **instalar**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>No instale proveedores de sockets por niveles en servidores multimedia

No instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server o cualquier otro software de proveedores de servicios por niveles (LSP) Winsock en cualquier servidor front-end o servidor de mediación independiente. La instalación de este software podría causar un rendimiento deficiente del tráfico de medios.

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de software de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

