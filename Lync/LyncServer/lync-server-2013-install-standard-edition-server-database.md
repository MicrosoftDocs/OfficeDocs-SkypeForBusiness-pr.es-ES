---
title: 'Lync Server 2013: Instalar la base de datos del servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f2ef304b1a603203d09f260b8d3c7c46e23ccf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="92300-102">Instalar la base de datos del servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92300-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92300-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="92300-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="92300-104">Configurar un servidor Standard Edition como el único servidor de la infraestructura en el que los usuarios de la casa difiere de otras instalaciones de servidor, en la que hay una selección en el Asistente para la **implementación** específicamente para configurar el servidor inicial.</span><span class="sxs-lookup"><span data-stu-id="92300-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="92300-105">Para instalar un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="92300-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="92300-106">Inicie sesión en el servidor en el que va a instalar el servidor Standard Edition como administrador local o como un equivalente de dominio.</span><span class="sxs-lookup"><span data-stu-id="92300-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="92300-107">Si no ha preparado los servicios de dominio de Active Directory, primero realice esos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="92300-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="92300-108">Para obtener más información, vea [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="92300-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="92300-109">En el Asistente para la implementación de Lync Server, haga clic en **preparar el primer servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="92300-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="92300-110">En la página **preparar un solo servidor Standard Edition** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92300-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="92300-111">En la página **comandos en ejecución** , SQL Server 2012 Express está instalado como almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="92300-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="92300-112">Se crean las reglas de Firewall necesarias.</span><span class="sxs-lookup"><span data-stu-id="92300-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="92300-113">Cuando haya finalizado la instalación de la base de datos y el software necesario, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="92300-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92300-114">La instalación inicial puede llevar algún tiempo sin actualizaciones visibles en la pantalla Resumen de salida del comando.</span><span class="sxs-lookup"><span data-stu-id="92300-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="92300-115">Esto se debe a la instalación de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="92300-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="92300-116">Si necesita supervisar la instalación de la base de datos, use el administrador de tareas para supervisar la configuración.</span><span class="sxs-lookup"><span data-stu-id="92300-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="92300-117">En la página del Asistente para la implementación de Lync Server, haga clic en **instalar generador de topologías** si todavía no ha instalado las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="92300-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="92300-118">Para obtener información detallada, consulte [instalar herramientas administrativas 2013 de Lync Server](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="92300-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="92300-119">Confirme que hay marcas de verificación verdes junto a "preparar Active Directory", "preparar el primer servidor Standard Edition" e "instalar el generador de topología".</span><span class="sxs-lookup"><span data-stu-id="92300-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

