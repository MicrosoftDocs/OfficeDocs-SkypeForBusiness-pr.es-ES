---
title: 'Lync Server 2013: instalación de los archivos del agente de Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48624e3f93ebb133743680a01399444137385a0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="36106-102">Instalar los archivos del agente Operations Manager en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36106-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36106-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="36106-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="36106-104">Para instalar los archivos del agente Operations Manager en el equipo, complete los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="36106-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="36106-105">En los medios de configuración de System Center, haga doble clic en **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="36106-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="36106-106">En el programa de instalación de System Center Operations Manager, haga clic en **instalar agente de Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="36106-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="36106-107">En el Asistente para la instalación de System Center, en la página **éste es el Asistente para la instalación de System Center Operations Manager** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36106-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="36106-108">En la página **carpeta de destino** , seleccione la carpeta en la que se instalarán los archivos del agente de Operations Manager y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36106-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="36106-109">En la página **configuración del grupo de administración** , seleccione **especificar información del grupo de administración**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36106-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="36106-110">En la página **configuración del grupo** de administración, escriba el nombre del grupo de administración de Operations Manager en el cuadro Nombre del grupo de **Administración** y, a continuación, escriba el nombre de host del servidor de Operations Manager (por ejemplo, ATL-SCOM-001) en el cuadro servidor de **Administración** .</span><span class="sxs-lookup"><span data-stu-id="36106-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="36106-111">Si ha cambiado el número de puerto que usa Operations Manager, escriba el nuevo número de puerto en el cuadro puerto del servidor de administración.</span><span class="sxs-lookup"><span data-stu-id="36106-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="36106-112">En caso contrario, deje el puerto en el valor predeterminado de 5723 y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36106-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="36106-113">En la página **cuenta de acción del agente** , seleccione **sistema local**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36106-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="36106-114">En la página **Microsoft Update** , seleccione **no quiero usar Microsoft Update**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36106-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="36106-115">En la página **listo para instalar** , haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="36106-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="36106-116">En la página **finalización del Asistente para la instalación de System Center Operations Manager** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="36106-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="36106-117">Haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="36106-117">Click **Exit**.</span></span>

<span data-ttu-id="36106-118">Si usa System Center 2007 R2, puede comprobar que el agente se ha creado haciendo clic en **Inicio**, en **todos los programas**, en **System Center Operations Manager 2007 R2**y, a continuación, en **Shell de Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="36106-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="36106-119">En el shell de Operations Manager, escriba el siguiente comando de Windows PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="36106-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="36106-120">Una lista de todos los agentes de Operations Manager aparecerá en pantalla.</span><span class="sxs-lookup"><span data-stu-id="36106-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="36106-121">Si usa System Center 2012, ejecute este comando desde el shell Operations 2012 Manager:</span><span class="sxs-lookup"><span data-stu-id="36106-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

