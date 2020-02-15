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
ms.openlocfilehash: c8502e1af9ddb607c25ed04429f6b5bb7fbfe980
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="a4271-102">Instalación de los archivos principales de Lync Server 2013 y la base de datos de RTCLocal</span><span class="sxs-lookup"><span data-stu-id="a4271-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4271-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a4271-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a4271-104">Para instalar los archivos principales de Lync Server 2013 en un equipo, realice el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a4271-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="a4271-105">La base de datos RTCLocal se instalará automáticamente cuando se instalen los archivos principales.</span><span class="sxs-lookup"><span data-stu-id="a4271-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="a4271-106">Tenga en cuenta que no es necesario instalar SQL Server en los nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="a4271-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="a4271-107">En su lugar, SQL Server Express se instala automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a4271-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="a4271-108">Para instalar los archivos principales de Lync Server 2013 y la base de datos de RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="a4271-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="a4271-109">En el equipo nodo de supervisor, haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a4271-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="a4271-110">En la ventana de la consola, escriba el siguiente comando y, a continuación, presione entrar, con la ruta de acceso adecuada a los archivos de instalación de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="a4271-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="a4271-111">Para comprobar que se instalaron correctamente los componentes principales de Lync Server, haga clic en **Inicio**, **todos los programas**, **Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a4271-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="a4271-112">En el shell de administración de Lync Server 2013, escriba el siguiente comando de Windows PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a4271-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="a4271-113">La primera vez que ejecute este comando, no se devolverá ningún dato porque todavía no se han configurado equipos de nodo de supervisor.</span><span class="sxs-lookup"><span data-stu-id="a4271-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="a4271-114">Siempre que el comando se ejecute sin que se devuelva un error, puede suponer que la instalación de Lync Server se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4271-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="a4271-115">Si el equipo de nodo de monitor se encuentra dentro de la red perimetral, puede ejecutar el siguiente comando para comprobar la instalación de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a4271-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="a4271-116">Recibirá una información similar a la siguiente, en función de las directivas de número de identificación personal (PIN) configuradas para usar en su organización:</span><span class="sxs-lookup"><span data-stu-id="a4271-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="a4271-117">Si aparece información sobre las directivas PIN, quiere decir que los componentes principales se han instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4271-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

