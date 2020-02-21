---
title: 'Lync Server 2013: requisitos técnicos para el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6467f4047754697322780373521cdd47fe1e1ba3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Requisitos técnicos para el estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

En esta sección se describen los siguientes requisitos técnicos para el estacionamiento de llamadas:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de puerto

  - Requisitos de archivos de audio

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

La aplicación de estacionamiento de llamadas tiene los mismos requisitos de hardware que los servidores front-end. Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

La aplicación de estacionamiento de llamadas tiene los mismos requisitos de sistema operativo y requisitos previos de software que los servidores front-end. Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

Todos los servidores front-end y los servidores Standard Edition en los que se implemente la aplicación de estacionamiento de llamadas deben tener instalado el tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. Se requiere el tiempo de ejecución de Windows Media Format o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que llaman reproducciones de estacionamiento para la música en espera.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de estacionamiento de llamadas usa el siguiente puerto:

  - **Puerto 5075**   usado para solicitudes de escucha SIP.

<div>


> [!NOTE]  
> Este puerto es una configuración predeterminada que puede cambiar mediante el cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación estacionamiento de llamadas solo admite archivos de audio de Windows Media (. WMA) para la música en espera. Puede usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera. Para descargar Expression Encoder 4, mira "Expression Encoder 4" en [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843). Use la herramienta para convertir el archivo en un formato .wma. El formato recomendado para los archivos de música en espera de estacionamiento de llamadas es media audio 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.

<div>


> [!NOTE]  
> El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

