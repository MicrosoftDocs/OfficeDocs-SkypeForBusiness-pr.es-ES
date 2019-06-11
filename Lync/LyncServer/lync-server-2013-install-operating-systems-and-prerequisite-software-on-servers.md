---
title: Instalar los sistemas operativos y el software necesario como requisito previo en los servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Instalar los sistemas operativos y el software necesario como requisito previo en los servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-24_

Una vez que haya configurado el hardware y la infraestructura del sistema, tendrá que instalar los sistemas operativos de Windows y las actualizaciones correspondientes, además de todos los demás programas de requisitos previos en cada servidor que vaya a implementar. Esto incluye cada rol de servidor de Lync Server 2013 y todos los servidores de infraestructura adicionales o servidores que ejecuten SQL Server que sean necesarios para su implementación.

<div>


> [!NOTE]
> En esta sección se describe la instalación de sistemas operativos y el software necesario para servidores internos. Si implementa servidores perimetrales para admitir el acceso de usuarios externos, también tendrá que instalar sistemas operativos y el software necesario para esos servidores, incluidos los servidores perimetrales y los servidores proxy inversos. Para obtener más información sobre la preparación de servidores para admitir el acceso de usuarios externos, vea preparación de la <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">instalación de servidores en la red perimetral para Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Instalar sistemas operativos Windows en servidores

En cada servidor que va a implementar, instale el sistema operativo Windows adecuado de la siguiente manera:

  - **Servidores que ejecutan Lync Server 2013**   para obtener más información sobre los requisitos del sistema operativo para servidores que ejecutan Lync Server 2013, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.

  - **Servidores de bases de datos**   para obtener información sobre los requisitos del sistema operativo para servidores de bases de datos, como la base de datos back-end, la base de datos archivada y la base de datos de supervisión, consulte la documentación de SQL Server. Para SQL Server 2012, consulte los libros en línea de SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.

<div>


> [!NOTE]
> Si está instalando Lync Server 2013 en Windows Server&nbsp;2008&nbsp;R2 con SP1, primero debe instalar la actualización que se describe en el artículo 2646886 de Microsoft Knowledge base, "Fix: el montón de daños se produce cuando un módulo llama al método InsertEntityBody en IIS 7,5 ", at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>También debe modificar el registro según se describe en el artículo de KB, los <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">identificadores de eventos 32402, 61045 se registran en los servidores front-end de Lync server 2013 que se instalan en Windows server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Instalar Windows Update en servidores

Instale las actualizaciones siguientes desde Windows Update en cada servidor:

  - **Windows Update para servidores que ejecutan Lync Server 2013**   para obtener más información sobre las actualizaciones de Windows Update necesarias para servidores que ejecutan Lync Server 2013, consulte [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la planeación documentación.

  - **Servidores de base de datos**   para obtener información sobre las actualizaciones de Windows Update necesarias para los servidores de bases de datos, como la base de datos back-end, la base de datos de archivado y la base de datos de supervisión, consulte la documentación 2012 de SQL Server. Para SQL Server 2012, consulte los libros en línea de SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Instalar otro software necesario en los servidores

Lync Server 2013 requiere la instalación del siguiente software adicional en los servidores:

  - **Requisitos previos de software para servidores que ejecutan Lync Server 2013**   los requisitos de software adicionales para servidores que ejecutan Lync Server 2013 dependen del rol de servidor que se implemente. Para obtener más información sobre los requisitos de software específicos para cada servidor, consulte [requisitos de software adicionales para Lync server 2013](lync-server-2013-additional-software-requirements.md) en la documentación de planeación.

  - **Windows Identity Foundation**   Lync Server 2013 requiere la instalación de Windows Identity Foundation para poder admitir los escenarios de autenticación de servidor a servidor. Para comprobar que ya se ha instalado en el equipo, vaya a panel de control, haga clic en **programas y características**, **vea actualizaciones instaladas**y busque en **Microsoft Windows**. Para obtener más información sobre cómo instalar Windows Identity [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.

  - **Microsoft .NET Framework 4,5**   se necesita la edición de 64 bits de Microsoft .NET Framework 4,5 para Lync Server 2013.

  - **Requisitos previos de software para servidores**   de bases de datos para obtener información sobre la actualización de Windows Update requerida para servidores de bases de datos, como la base de datos back-end, la base [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server 2012 en
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express en cada servidor Standard Edition y en cada servidor que ejecuta Lync Server 2013 en el que se encuentra el almacén de configuración local.

    
    </div>

  - **Windows Media Format Runtime**   todos los servidores front-end y los servidores Standard Edition en los que se van a implementar las conferencias deben tener instalado el Windows Media Format Runtime. El tiempo de ejecución de Windows Media Format es necesario para ejecutar los archivos de audio de Windows Media (. WMA) que las aplicaciones de los grupos estacionamiento, anuncio y respuesta de llamadas se reproducen para anuncios y música.
    
    <div>
    

    > [!NOTE]
    > Para Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Para Windows Server&nbsp;2008 y windows Server&nbsp;2008&nbsp;R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. Se recomienda instalar la experiencia de escritorio de Windows antes de instalar Lync Server 2013. Si Lync Server 2013 no encuentra este software en el servidor, le pedirá que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

