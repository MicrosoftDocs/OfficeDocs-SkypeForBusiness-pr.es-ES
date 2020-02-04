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

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="1e403-102">Instalar los archivos básicos de Lync Server 2013 y la base de datos de RTCLocal</span><span class="sxs-lookup"><span data-stu-id="1e403-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e403-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1e403-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1e403-104">Para instalar los archivos principales de Lync Server 2013 en un equipo, complete el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1e403-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="1e403-105">La base de datos de RTCLocal se instala automáticamente al instalar los archivos principales.</span><span class="sxs-lookup"><span data-stu-id="1e403-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="1e403-106">Tenga en cuenta que no es necesario instalar SQL Server en los nodos de los monitores.</span><span class="sxs-lookup"><span data-stu-id="1e403-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="1e403-107">En su lugar, SQL Server Express se instala automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1e403-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="1e403-108">Para instalar los archivos principales de Lync Server 2013 y la base de datos RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="1e403-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="1e403-109">En el equipo del nodo de monitor, haga clic en **Inicio**, haga clic en **todos los programas**, en **accesorios**, en **símbolo del sistema**y luego en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1e403-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="1e403-110">En la ventana de consola, escriba el siguiente comando y, a continuación, presione entrar, usando la ruta de acceso adecuada a los archivos de instalación de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1e403-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="1e403-111">Para comprobar que los componentes principales de Lync Server se instalaron correctamente, haga clic en **Inicio**, haga clic en **todos los programas**, **Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1e403-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="1e403-112">En el shell de administración de Lync Server 2013, escriba el siguiente comando de Windows PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1e403-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="1e403-113">La primera vez que ejecute este comando, no se devolverá ningún dato porque aún no ha configurado ningún equipo de nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="1e403-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="1e403-114">Siempre y cuando el comando se ejecute sin devolver un error, puede suponer que la configuración de Lync Server se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e403-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="1e403-115">Si el equipo del nodo de observador está ubicado dentro de la red perimetral, puede ejecutar el siguiente comando para comprobar la instalación de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1e403-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="1e403-116">Recibirá información similar a la siguiente, según el número de directivas de números de identificación personal (PIN) configuradas para su uso en su organización:</span><span class="sxs-lookup"><span data-stu-id="1e403-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="1e403-117">Si ve información sobre las directivas de PIN, significa que ha instalado correctamente los componentes principales.</span><span class="sxs-lookup"><span data-stu-id="1e403-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

