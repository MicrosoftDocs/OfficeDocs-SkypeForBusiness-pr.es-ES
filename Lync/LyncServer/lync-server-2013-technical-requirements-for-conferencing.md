---
title: Lync Server 2013 requisitos técnicos para conferencias
description: Lync Server 2013 requisitos técnicos para conferencias.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3b787d84288d789cd0d824081439004f19327e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577126"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Requisitos técnicos para conferencias en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-25_

Para Lync Server 2013, las capacidades de conferencia de acceso telefónico local, conferencia A/V, Conferencia de mensajería instantánea (mi) y conferencia web siempre se ejecutan en los servidores front-end.

En esta sección se describen detalladamente los requisitos de hardware y software de estos servidores, junto con la combinación admitida.

La conferencia de acceso telefónico local es una característica que incluye una variedad de componentes. Algunos componentes son específicos de las conferencias de acceso telefónico local y otros lo son de Enterprise Voice. En esta sección se describen los requisitos de los componentes específicos de las conferencias de acceso telefónico local. Para obtener más información sobre los requisitos del servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) , and [Components and Topologs for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación de planeación.

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

Debido a que la conferencia web y la conferencia A/V se colocan con el servidor front-end, los requisitos de hardware del servidor son los mismos que para los servidores front-end. Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad. Los siguientes componentes necesarios para las conferencias de acceso telefónico local también tienen los mismos requisitos de hardware que los servidores front-end:

  - Servicio de aplicación

  - Aplicación Operador de conferencia

  - Aplicación de anuncio de conferencia

Los requisitos de hardware para el servidor front-end son los mismos que para muchas otras funciones de servidor en Lync Server 2013 se describen en la siguiente tabla.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

Debido a que la conferencia web y la conferencia A/V se colocan con el servidor front-end, los requisitos de software del servidor son los mismos que para los servidores front-end. Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

Para las conferencias web, Lync Server 2013 también requiere Office Web Apps y Office Web Apps Server (antes conocido como servidor WAC) para controlar las presentaciones de PowerPoint. Para obtener más información, consulte [Configuring Integration with Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Para las conferencias de acceso telefónico local, el servicio de aplicación, la aplicación operador de conferencia y la aplicación anuncio de Conferencia tienen los mismos requisitos de sistema operativo que los servidores front-end. Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

La aplicación operador de conferencia y la aplicación anuncio de conferencia requieren que el tiempo de ejecución de Windows Media Format esté instalado en los servidores front-end. El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos audio de Windows Media (WMA) que se usan para la música en espera, nombres registrados y avisos. Excepto en el caso de Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala automáticamente como parte de la experiencia del escritorio de Windows al ejecutar el programa de instalación, pero es posible que deba reiniciar el equipo. Por lo tanto, recomendamos que instale como parte de la experiencia de escritorio de Windows, que incluye el tiempo de ejecución de Windows Media Format antes de ejecutar el programa de instalación. Windows Server 2012 y Windows Server 2012 R2 requieren Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Requisitos de puerto para conferencias de acceso telefónico local

En la tabla siguiente se describen los puertos usados por las conferencias de acceso telefónico local. Si usa un equilibrador de carga, asegúrese de que está configurado para los puertos usados por las aplicaciones que se ejecutarán en el grupo.

Estos puertos son configuraciones predeterminadas que se pueden cambiar mediante el cmdlet **Set-CsApplicationServer**. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.

<div>


> [!NOTE]  
> Todas las instancias de la misma aplicación en un grupo de servidores usan el mismo puerto de escucha de SIP.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Puertos usados por las conferencias de acceso telefónico local

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de puerto</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>Usado por la aplicación de operador de conferencia para solicitudes de escucha SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Usada por la aplicación de anuncio de conferencia para solicitudes de escucha SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Clientes admitidos para conferencias de acceso telefónico local

Puede usar al siguiente cliente para programar conferencias locales que admiten el acceso telefónico local:

  - Complemento para reunión en línea para Lync 2013 (se instala automáticamente al instalar Lync 2013 o asistente)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Requisitos de la página de configuración de conferencia de acceso telefónico local

La página de configuración de la Conferencia de acceso telefónico local admite las combinaciones de sistemas operativos y exploradores Web que se describen en la siguiente tabla.

<div>


> [!NOTE]  
> Las versiones de 32 bits y 64 bits de los sistemas operativos son compatibles.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemas operativos y exploradores web compatibles

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operativo</th>
<th>Explorador web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de archivo de audio para conferencias de acceso telefónico local

Lync Server 2013 no admite la personalización de mensajes de voz y la música para conferencias de acceso telefónico local. Sin embargo, si tiene una gran necesidad empresarial que requiera cambiar los archivos de audio predeterminados, consulte el artículo de Microsoft Knowledge Base 961177, [How to Customize Voice prompts or files Music for Dial-in audioconferencia in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

También puede usar la herramienta de administración de [mensajes de voz personalizados del operador de conferencia de Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkid=396880) , que permite a los administradores reemplazar los mensajes de voz predeterminados que se usan cuando un autor de llamada de teléfono se une a una reunión de Lync con mensajes personalizados para proporcionar una experiencia de entrada de reunión diferente. Los mensajes de voz personalizados pueden instalarse en un servidor que ejecute Lync Server 2010 o Lync Server 2013, ya sea Enterprise o Standard Edition.

La aplicación operador de conferencia y la aplicación anuncio de Conferencia tienen los siguientes requisitos para los archivos de música en espera, nombre grabado y mensajes de audio:

  - Formato de archivo de audio de Windows Media (WMA)

  - Mono de 16 bits

  - 48 kbps CBR 2 pasos (velocidad de bits constante)

  - Nivel de voz a -24DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos de usuario para conferencias de acceso telefónico local

Los usuarios de conferencias de acceso telefónico local deben tener un número de teléfono único o una extensión asignada a su cuenta. Este requisito admite la autenticación durante las conferencias de acceso telefónico local. Los usuarios empresariales (es decir, los usuarios que tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server en la organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para llamar a conferencias como un usuario autenticado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

