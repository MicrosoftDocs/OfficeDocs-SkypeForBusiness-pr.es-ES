---
title: 'Lync Server 2013: Requisitos técnicos para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 719bd7f8de6fd7356a6b2e454cc86e9aa85abd6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Requisitos técnicos para conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-25_

Para Lync Server 2013, las conferencias de acceso telefónico local, las conferencias A/V, las conferencias de mensajería instantánea (mi) y las capacidades de conferencia web siempre se ejecutan en servidores front-end.

En esta sección se detallan los requisitos de hardware y software de estos servidores, junto con el collocation compatible.

Las conferencias de acceso telefónico local son una característica que incluye una variedad de componentes. Algunos de los componentes son específicos de las conferencias de acceso telefónico local y otros son componentes de telefonía empresarial. En esta sección se describen los requisitos para los componentes específicos de las conferencias de acceso telefónico local. Para obtener más información sobre los requisitos de la puerta de enlace de red telefónica conmutada (RTC) y el servidor de mediación, consulte [componente servidor de mediación en Lync server 2013](lync-server-2013-mediation-server-component.md) , así como [componentes y topologías de servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la planificación documentación.

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

Debido a que las conferencias web y A/V se colocan con el servidor front-end, los requisitos de hardware del servidor son los mismos que los servidores front-end. Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico. Los siguientes componentes necesarios para las conferencias de acceso telefónico local también tienen los mismos requisitos de hardware que los servidores front-end:

  - Servicio de aplicaciones

  - Aplicación Operador de conferencia

  - Aplicación de anuncio de conferencia

Los requisitos de hardware para el servidor front-end son los mismos que para otros muchos roles de servidor de Lync Server 2013 se describen en la tabla siguiente.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

Debido a que las conferencias web y A/V se colocan con el servidor front-end, los requisitos de software del servidor son los mismos que los servidores front-end. Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.

Para las conferencias web, Lync Server 2013 también requiere Office Web Apps y Office Web Apps Server (anteriormente conocido como servidor WAC) para controlar presentaciones de PowerPoint. Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Para las conferencias de acceso telefónico local, servicio de aplicaciones, operador de conferencias y aplicación de anuncio de Conferencia tienen los mismos requisitos del sistema operativo que los servidores de aplicaciones para el usuario. Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.

El Asistente de conferencia y la aplicación de anuncio de conferencia requieren que Windows Media Format Runtime esté instalado en los servidores frontales. El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos de audio de Windows Media (WMA) que se usan para música en espera, nombres grabados y avisos. Excepto en el caso de Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala automáticamente como parte de la experiencia de escritorio de Windows al ejecutar el programa de instalación, pero es posible que tenga que reiniciar el equipo. Por lo tanto, le recomendamos que instale como parte de la experiencia de escritorio de Windows, que incluye el Windows Media Format Runtime antes de ejecutar el programa de instalación. Windows Server 2012 y Windows Server 2012 R2 requieren Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Requisitos de puerto para las conferencias de acceso telefónico local

En la siguiente tabla se describen los puertos que usan las conferencias de acceso telefónico local. Si usa un equilibrador de carga, asegúrese de que el equilibrador de carga está configurado para los puertos usados por todas las aplicaciones que se ejecutarán en el grupo.

Estos puertos son configuraciones predeterminadas que se pueden cambiar con el cmdlet **Set-CsApplicationServer**. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.

<div>


> [!NOTE]  
> Todas las instancias de la misma aplicación de un grupo usan el mismo puerto de escucha de SIP.



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
<td><p>Usado por la aplicación de operador de conferencia para solicitudes de escucha de SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Usado por la aplicación de anuncios de conferencias para solicitudes de escucha de SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Clientes compatibles con conferencias de acceso telefónico local

Puede usar el siguiente cliente para programar conferencias locales que admitan el acceso telefónico:

  - Complemento de reunión en línea para Lync 2013 (se instala automáticamente al instalar Lync 2013 o asistente)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Requisitos de la página de configuración de la Conferencia de acceso telefónico local

La página de configuración de la Conferencia de acceso telefónico local admite las combinaciones de sistemas operativos y exploradores Web que se describen en la tabla siguiente.

<div>


> [!NOTE]  
> se admiten las versiones de 32 y 64 bits de los sistemas operativos.



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

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de los archivos de audio para las conferencias de acceso telefónico local

Lync Server 2013 no admite la personalización de mensajes de voz y de música para conferencias de acceso telefónico local. Sin embargo, si tiene una gran necesidad comercial que le exija cambiar los archivos de audio predeterminados, consulte el artículo 961177 de Microsoft Knowledge base, [Cómo personalizar las solicitudes de voz o los archivos de música para conferencias de audio de acceso telefónico local en Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

También puede usar la herramienta de administración de [avisos de voz personalizadas del operador de conferencias de Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880) , que permite a los administradores reemplazar los avisos de voz predeterminados que se usan cuando una persona que llama a la reunión se une a una reunión de Lync con avisos personalizados para proporcionar una una experiencia de reunión diferente. Las solicitudes de voz personalizadas se pueden instalar en un servidor que ejecute Lync Server 2010 o Lync Server 2013, Enterprise o Standard.

El operador de conferencia y la aplicación de anuncio de Conferencia tienen los siguientes requisitos de música en espera, nombre grabado y archivos de solicitud de audio:

  - Formato de archivo de audio de Windows Media (WMA)

  - Mono de 16 bits

  - 48 kbps CBR 2 pasos (velocidad de bits constante)

  - Nivel de voz a -24DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos de usuario para las conferencias de acceso telefónico local

Los usuarios de conferencias de acceso telefónico local necesitan tener un número de teléfono único o una extensión asignada a su cuenta. Este requisito admite la autenticación durante las conferencias de acceso telefónico local. Los usuarios empresariales (es decir, los usuarios que tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server dentro de su organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para llamar a conferencias como un usuario autenticado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

