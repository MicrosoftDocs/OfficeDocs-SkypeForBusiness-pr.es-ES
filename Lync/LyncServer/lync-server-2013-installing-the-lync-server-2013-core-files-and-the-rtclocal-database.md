---
title: Instalación de los archivos principales de Lync Server 2013 y la base de datos de RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eefd8316e0e33ab8c4418a6ce72ea9eb05fc84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Instalación de los archivos principales de Lync Server 2013 y la base de datos de RTCLocal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Para instalar los archivos principales de Lync Server 2013 en un equipo, realice el siguiente procedimiento. La base de datos RTCLocal se instalará automáticamente cuando se instalen los archivos principales. Tenga en cuenta que no es necesario instalar SQL Server en los nodos de monitor. En su lugar, SQL Server Express se instala automáticamente.

Para instalar los archivos principales de Lync Server 2013 y la base de datos de RTCLocal:

1.  En el equipo nodo de supervisor, haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.

2.  En la ventana de la consola, escriba el siguiente comando y, a continuación, presione entrar, con la ruta de acceso adecuada a los archivos de instalación de Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Para comprobar que se instalaron correctamente los componentes principales de Lync Server, haga clic en **Inicio**, **todos los programas**, **Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**. En el shell de administración de Lync Server 2013, escriba el siguiente comando de Windows PowerShell y, a continuación, presione ENTRAR:

    Get-CsWatcherNodeConfiguration

La primera vez que ejecute este comando, no se devolverá ningún dato porque todavía no se han configurado equipos de nodo de supervisor. Siempre que el comando se ejecute sin que se devuelva un error, puede suponer que la instalación de Lync Server se ha completado correctamente.

Si el equipo de nodo de monitor se encuentra dentro de la red perimetral, puede ejecutar el siguiente comando para comprobar la instalación de Lync Server 2013:

    Get-CsPinPolicy

Recibirá una información similar a la siguiente, en función de las directivas de número de identificación personal (PIN) configuradas para usar en su organización:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Si aparece información sobre las directivas PIN, quiere decir que los componentes principales se han instalado correctamente.

</div>

<span> </span>

</div>

</div>

</div>

