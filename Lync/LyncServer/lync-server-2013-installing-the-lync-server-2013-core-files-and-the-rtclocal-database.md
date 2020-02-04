---
title: Instalar los archivos básicos de Lync Server 2013 y la base de datos de RTCLocal
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
ms.openlocfilehash: da8f0dd1fb83c595ed444a487d0321c571a09315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Instalar los archivos básicos de Lync Server 2013 y la base de datos de RTCLocal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Para instalar los archivos principales de Lync Server 2013 en un equipo, complete el siguiente procedimiento. La base de datos de RTCLocal se instala automáticamente al instalar los archivos principales. Tenga en cuenta que no es necesario instalar SQL Server en los nodos de los monitores. En su lugar, SQL Server Express se instala automáticamente.

Para instalar los archivos principales de Lync Server 2013 y la base de datos RTCLocal:

1.  En el equipo del nodo de monitor, haga clic en **Inicio**, haga clic en **todos los programas**, en **accesorios**, en **símbolo del sistema**y luego en **Ejecutar como administrador**.

2.  En la ventana de consola, escriba el siguiente comando y, a continuación, presione entrar, usando la ruta de acceso adecuada a los archivos de instalación de Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Para comprobar que los componentes principales de Lync Server se instalaron correctamente, haga clic en **Inicio**, haga clic en **todos los programas**, **Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**. En el shell de administración de Lync Server 2013, escriba el siguiente comando de Windows PowerShell y, a continuación, presione ENTRAR:

    Get-CsWatcherNodeConfiguration

La primera vez que ejecute este comando, no se devolverá ningún dato porque aún no ha configurado ningún equipo de nodo de monitor. Siempre y cuando el comando se ejecute sin devolver un error, puede suponer que la configuración de Lync Server se completó correctamente.

Si el equipo del nodo de observador está ubicado dentro de la red perimetral, puede ejecutar el siguiente comando para comprobar la instalación de Lync Server 2013:

    Get-CsPinPolicy

Recibirá información similar a la siguiente, según el número de directivas de números de identificación personal (PIN) configuradas para su uso en su organización:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Si ve información sobre las directivas de PIN, significa que ha instalado correctamente los componentes principales.

</div>

<span> </span>

</div>

</div>

</div>

