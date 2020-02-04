---
title: 'Lync Server 2013: Requisitos técnicos para grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ab381a70a8a6d69170959fbaf488982887d765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Requisitos técnicos para grupos de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

En esta sección se describen los siguientes requisitos técnicos para la aplicación de grupo de respuesta:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de los puertos

  - Requisitos de los archivos de audio

  - Requisitos de la herramienta de configuración de grupos de respuesta

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

La aplicación de grupo de respuesta tiene los mismos requisitos de hardware que los servidores front-end. Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

La aplicación de grupo de respuesta tiene los mismos requisitos del sistema operativo y requisitos previos de software que los servidores front-end. Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.

Si usa archivos de audio de Windows Media (. WMA) para la música de grupo de respuesta y anuncios, todos los servidores de aplicaciones para el usuario o ediciones Standard que ejecuten la aplicación de grupo de respuesta deben tener instalado el Windows Media Format Runtime para servidores con Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows.

Para obtener más información sobre los requisitos de audio, consulte "requisitos de archivos de audio" más adelante en esta sección.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de grupo de respuesta usa los siguientes puertos:

  - **Puerto 5071**   usado para solicitudes de escucha de SIP

  - **Puerto 8404**   usado para comunicaciones entre servidores
    
    <div>
    

    > [!NOTE]  
    > Este puerto se usa para hacer coincidir el servicio y es necesario cuando la aplicación de grupo de respuesta se implementa en un grupo que tiene más de un servidor front-end.

    
    </div>

<div>


> [!NOTE]  
> Estos puertos son configuraciones predeterminadas que se pueden cambiar con el cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación de grupo de respuesta admite el formato de archivo de onda (. wav) y el formato de archivo de audio de Windows Media (. WMA) para preguntas de mensajes de grupo de respuesta, música en espera o respuesta de voz interactiva (IVR).

El formato de archivo de audio de Windows Media requiere que el Windows Media Format Runtime esté instalado en los servidores front-end que ejecutan Windows Server 2008 R2 y Windows Server 2008. Para obtener más información, mira "Requisitos de software" anteriormente en esta sección.

<div>

## <a name="supported-wave-file-formats"></a>Formatos de archivo wave compatibles

Todos los archivos wave necesitan cumplir los requisitos siguientes:

  - Archivo de 8 bits o de 16 bits

  - Formato de modulación lineal por impulsos codificados (LPCM), A-Law o mu-Law

  - Mono o estéreo

  - 4 MB o menos

Para obtener el máximo rendimiento de los archivos wave, recomendamos usar un archivo wave mono de 16 bits a 16 kHz.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Formatos de archivo de audio de Windows Media compatibles

Si usas un archivo de audio de Windows Media, considera la posibilidad de usar velocidades de bits lentas y comprueba el rendimiento del sistema cuando se somete a carga.

Puedes usar Microsoft Expression Encoder 4 para convertir un archivo al formato de audio de Windows Media. Para descargar Expression Encoder 4, consulte [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Requisitos para la herramienta de configuración del grupo de respuesta

La herramienta de configuración de grupos de respuesta admite las combinaciones de sistemas operativos y exploradores Web que se describen en la tabla siguiente.

<div>


> [!NOTE]  
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.



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
<td><p>Windows Vista con Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 con Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>Consola del agente del grupo de respuesta

La consola del agente admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.

<div>


> [!NOTE]  
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.



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
<td><p>Windows Vista con Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 con Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

