---
title: 'Lync Server 2013: requisitos técnicos para la aplicación de anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54371acb29bcc7d9b6581cbfd26199888dcfe893
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536107"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Requisitos técnicos para la aplicación de anuncio en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

En esta sección se describen los siguientes requisitos técnicos para la aplicación de anuncio:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de puerto

  - Requisitos de archivos de audio

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

La aplicación de anuncio tiene los mismos requisitos de hardware que los servidores front-end. Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

La aplicación de anuncio tiene los mismos requisitos de sistema operativo y requisitos previos de software que los servidores front-end. Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

Todos los servidores front-end o servidores Standard Edition que ejecutan la aplicación de anuncio deben tener instalado el tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. Se requiere el tiempo de ejecución de Windows Media Format o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que la aplicación de anuncio reproduce para los anuncios y la música.

</div>

<div>

## <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de anuncio usa el siguiente puerto:

  - **Puerto 5071**     Se usa para solicitudes de escucha SIP

<div>


> [!NOTE]  
> Este puertos es el predeterminado, pero puede cambiarlo utilizando el cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación de anuncio admite el formato de archivo de onda (. wav) y el formato de archivo de audio de Windows Media (. WMA) para música y anuncios. Los requisitos de archivos de audio para la aplicación de anuncio son los mismos que para la aplicación de grupo de respuesta. Para obtener más información, consulte [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

