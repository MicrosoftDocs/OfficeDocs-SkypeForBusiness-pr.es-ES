---
title: 'Lync Server 2013: actualización desde la versión de evaluación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b4cc704a77f824cbf7b2ec8ab4920c25454f3c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="d47d5-102">Actualización de la versión de evaluación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d47d5-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d47d5-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="d47d5-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="d47d5-104">Si ha instalado la versión de evaluación de Microsoft Lync Server 2013, tendrá que actualizar esa instalación en una copia con licencia del software; Esto se debe a que la versión de evaluación vence el 180 días después de su instalación.</span><span class="sxs-lookup"><span data-stu-id="d47d5-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="d47d5-105">Sin embargo, no tendrá que desinstalar completamente la versión de evaluación y, a continuación, instalar la versión con licencia.</span><span class="sxs-lookup"><span data-stu-id="d47d5-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="d47d5-106">En su lugar, después de haber obtenido una clave de licencia válida, puede actualizar la versión de evaluación de Lync Server 2013 llevando a cabo el siguiente procedimiento en cada equipo que actúe como servidor perimetral, director o servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d47d5-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="d47d5-107">Tenga en cuenta que no es necesario actualizar equipos que lleven a cabo otras funciones de servidor, como un servidor de supervisión o un servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="d47d5-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="d47d5-108">Actualización desde la versión de evaluación de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d47d5-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="d47d5-109">Para actualizar un equipo desde la versión de evaluación de Lync Server 2013 a la versión con licencia del software:</span><span class="sxs-lookup"><span data-stu-id="d47d5-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="d47d5-110">**Actualización desde la versión de evaluación de Microsoft Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="d47d5-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="d47d5-111">Inicie sesión en el equipo como administrador local.</span><span class="sxs-lookup"><span data-stu-id="d47d5-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="d47d5-112">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d47d5-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d47d5-113">En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="d47d5-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="d47d5-114">Tenga en cuenta que es posible que tenga que especificar la ruta de acceso completa del servidor de archivos. msi.</span><span class="sxs-lookup"><span data-stu-id="d47d5-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="d47d5-115">Este archivo puede encontrarse en la carpeta Setup de los archivos de instalación de medios de volumen de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d47d5-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="d47d5-116">Cuando finalice la instalación, escriba lo siguiente en el símbolo del sistema y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="d47d5-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="d47d5-117">Repita este procedimiento en cualquier otro servidor front-end, director o servidor perimetral que ejecute una copia de evaluación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d47d5-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="d47d5-118">Este procedimiento también se debe realizar en los servidores de sucursal que se hayan implementado con los archivos de instalación de Lync Server media.</span><span class="sxs-lookup"><span data-stu-id="d47d5-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="d47d5-119">Si no está seguro de si la versión de evaluación de Lync Server se está ejecutando en un equipo determinado, puede comprobar si ejecuta el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="d47d5-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="d47d5-120">El cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analizará el equipo local y devolverá una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d47d5-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="d47d5-121">La clave de licencia por volumen de Lync Server se ha instalado en el equipo, lo que significa que no es necesaria ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="d47d5-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="d47d5-122">La clave de licencia de evaluación de Lync Server se ha instalado, lo que significa que debe actualizarse el equipo.</span><span class="sxs-lookup"><span data-stu-id="d47d5-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="d47d5-123">Que no se requiere ninguna clave de licencia por volumen en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d47d5-123">That no volume license key is required on the computer.</span></span> <span data-ttu-id="d47d5-124">La actualización de la versión de evaluación a la versión con licencia solo es necesaria en servidores front-end, directores y servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="d47d5-124">Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

