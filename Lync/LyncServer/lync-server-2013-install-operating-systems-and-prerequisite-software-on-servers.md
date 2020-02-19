---
title: Instalar los sistemas operativos y el software necesario como requisito previo en los servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69ad97d578073e2b0f9ed08d929007c33e59b8fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Instalar los sistemas operativos y el software necesario como requisito previo en los servidores para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-24_

Una vez configurado el hardware y la infraestructura del sistema, deberá instalar los sistemas operativos de Windows adecuados y sus actualizaciones, además de todo el software necesario como requisito previo en cada uno de los servidores que esté implementando. Esto incluye todos los roles de servidor de Lync Server 2013 y los servidores de infraestructura adicionales o los servidores que ejecutan SQL Server que son necesarios para la implementación.

<div>


> [!NOTE]
> En esta sección se describe la instalación de sistemas operativos y el software que es requisito previo para los servidores internos. Si va a implementar servidores perimetrales para admitir el acceso de usuarios externos, también tendrá que instalar los sistemas operativos y el software necesario como requisito previo para esos servidores, incluidos los servidores perimetrales y los servidores proxy inversos. Para obtener información detallada sobre la preparación de servidores para admitir el acceso de usuarios externos, consulte preparación de la <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">instalación de servidores en la red perimetral para Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Instalar sistemas operativos Windows en servidores

En cada servidor que vaya a implementar, instale el sistema operativo Windows adecuado de la siguiente manera:

  - **Servidores que ejecutan Lync Server 2013**   para obtener más información sobre los requisitos del sistema operativo para servidores que ejecutan Lync Server 2013, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

  - **Servidores de bases de datos**   para obtener información sobre los requisitos del sistema operativo para servidores de bases de datos, incluida la base de datos back-end, la base de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server Para SQL Server 2012, consulte los libros en pantalla de SQL Server [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.

<div>


> [!NOTE]
> Si va a instalar Lync Server 2013 en Windows Server&nbsp;2008&nbsp;R2 con SP1, debe instalar primero la actualización que se describe en el artículo 2646886 de Microsoft Knowledge base, "Fix: los daños en el montón se producen cuando un módulo llama al método al InsertEntityBody en IIS 7,5", en <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>También debe modificar el registro como se describe en el artículo de KB, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">se registran los identificadores de evento 32402 y 61045 en los servidores front-end de Lync Server 2013 que están instalados en Windows server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Instalar Windows Update en los servidores

Instale las siguientes actualizaciones desde Windows Update en cada servidor:

  - **Windows Update para los servidores que ejecutan Lync Server 2013**   para obtener más información sobre las actualizaciones de Windows Update que son necesarias para los servidores que ejecutan Lync Server 2013, consulte [Additional software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación referente a la planeación.

  - **Servidores de bases de datos**   para obtener información detallada sobre las actualizaciones de Windows Update que son necesarias para los servidores de bases de datos, incluida la base de datos back-end, la base de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server 2012. Para SQL Server 2012, consulte los libros en pantalla de SQL Server [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Instalar otro software necesario como requisito previo en los servidores

Lync Server 2013 requiere la instalación del siguiente software adicional en los servidores:

  - **Requisitos previos de software para servidores que ejecutan Lync Server 2013**   los requisitos previos de software adicionales para los servidores que ejecutan Lync Server 2013 dependen de la función del servidor que se está implementando. Para obtener más información sobre los requisitos de software específicos para cada servidor, consulte [requisitos de software adicionales para Lync server 2013](lync-server-2013-additional-software-requirements.md) en la documentación referente a la planeación.

  - **Windows Identity Foundation**   Lync Server 2013 requiere la instalación de Windows Identity Foundation para poder admitir escenarios de autenticación de servidor a servidor. Para comprobar que ya se ha instalado en el equipo, vaya al panel de control, haga clic en **programas y características**, **vea actualizaciones instaladas**y busque en **Microsoft Windows**. Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.

  - **Microsoft .NET Framework 4,5**   la edición de 64 bits de Microsoft .NET Framework 4,5 es necesaria para Lync Server 2013.

  - **Requisitos previos de software para servidores**   de bases de datos para obtener información sobre la actualización de Windows necesaria para los servidores de bases de datos, incluida la base de datos back-end, la base [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server 2012 en
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express en cada servidor Standard Edition y en cada servidor que ejecuta Lync Server 2013 en el que se encuentra el almacén de configuración local.

    
    </div>

  - **El tiempo de ejecución**   de Windows Media Format todos los servidores front-end y los servidores Standard Edition en los que se va a implementar la Conferencia deben tener instalado el tiempo de ejecución de Windows Media Format. Este software es necesario para ejecutar los archivos de Windows Media Audio (.wma) que reproducen las aplicaciones de estacionamiento de llamadas, anuncio y grupo de respuesta para los anuncios y la música.
    
    <div>
    

    > [!NOTE]
    > Para Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Para Windows Server&nbsp;2008 y windows Server&nbsp;2008&nbsp;R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. Se recomienda instalar la experiencia de escritorio de Windows antes de instalar Lync Server 2013. Si Lync Server 2013 no encuentra este software en el servidor, se le pedirá que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

