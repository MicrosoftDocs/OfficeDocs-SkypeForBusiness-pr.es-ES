---
title: 'Lync Server 2013: Instalar Windows PowerShell 3.0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cd8b4b48f2ff5a50ef7cafc1ec39671f672670f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="96dc2-102">Instalar Windows PowerShell 3.0 para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96dc2-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96dc2-103">_**Última modificación del tema:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="96dc2-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="96dc2-104">Para implementar Lync Server 2013 correctamente, necesitará Windows PowerShell 3,0 en cada equipo que forme parte de la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96dc2-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="96dc2-105">Ahora, para sistemas con Windows Server 2012 o Windows Server 2012 R2, no tiene que hacer nada aquí, y puede continuar con la siguiente fase de implementación, porque PowerShell 3,0 se incluye con esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="96dc2-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96dc2-106">Pero para los sistemas que ejecutan Windows Server 2008 R2 SP1, tendrá que instalar PowerShell 3,0 como requisito previo antes de instalar Lync Server 2013, o lo que no funcionará.</span><span class="sxs-lookup"><span data-stu-id="96dc2-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="96dc2-107">Para instalar PowerShell 3,0, vea <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="96dc2-107">To install PowerShell 3.0, see <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="96dc2-108">Este es un vínculo directo a la página de descarga de PowerShell 3,0, junto con información relacionada con la instalación correcta.</span><span class="sxs-lookup"><span data-stu-id="96dc2-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="96dc2-109">Una vez que haya realizado la instalación, o si solo desea comprobar la implementación de Lync Server y asegurarse de que no va a hacerlo, es muy sencillo que confirme que PowerShell 3,0 está en un servidor:</span><span class="sxs-lookup"><span data-stu-id="96dc2-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="96dc2-110">En el servidor que desea comprobar, elija **Inicio**, haga clic en **todos los programas**, en **accesorios**, en **Windows PowerShell**y, por último, en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="96dc2-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="96dc2-111">En la consola de Windows PowerShell, escriba el siguiente comando en el símbolo del sistema y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="96dc2-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="96dc2-112">Si Windows PowerShell 3,0 está instalado, verá el resultado que tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="96dc2-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

