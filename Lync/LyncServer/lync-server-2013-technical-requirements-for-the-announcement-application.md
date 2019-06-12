---
title: 'Lync Server 2013: Requisitos técnicos para la aplicación Anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Requisitos técnicos para la aplicación Anuncio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

En esta sección se describen los siguientes requisitos técnicos para la aplicación de anuncios:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de los puertos

  - Requisitos de los archivos de audio

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

La aplicación de anuncios tiene los mismos requisitos de hardware que los servidores de aplicaciones para el usuario. Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

La aplicación de anuncios tiene los mismos requisitos del sistema operativo y requisitos previos de software que los servidores front-end. Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.

Todos los servidores front-end o los servidores Standard Edition que ejecuten la aplicación de anuncio deben tener instalado el Windows Media Format Runtime para servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2. En Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows. Se necesita Windows Media Format Runtime o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que la aplicación del anuncio reproduce para los anuncios y la música.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de anuncios usa el siguiente puerto:

  - **Puerto 5071**   usado para solicitudes de escucha de SIP

<div>


> [!NOTE]  
> Este puerto es el predeterminado, pero puedes cambiarlo utilizando el cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación de anuncios admite el formato de archivo de onda (. wav) y el formato de archivo de audio de Windows Media (. WMA) para música y anuncios. Los requisitos de los archivos de audio para la aplicación de anuncios son los mismos que los de la aplicación de grupo de respuesta. Para obtener más información, consulte [requisitos técnicos para el grupo de respuesta en Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

