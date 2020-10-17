---
title: 'Lync Server 2013: instalar la base de datos del servidor Standard Edition'
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
ms.openlocfilehash: 9d4027c02a866769c5b9866f6d315d31c6dcf80c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498667"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="06c09-102">Instalar la base de datos del servidor Standard Edition para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06c09-102">Install Standard Edition server database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06c09-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="06c09-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="06c09-104">La configuración de un servidor Standard Edition como el único servidor de la infraestructura que aloja a los usuarios se diferencia de otras instalaciones de servidores en que hay una selección en el Asistente para la **implementación** específica para configurar el servidor inicial.</span><span class="sxs-lookup"><span data-stu-id="06c09-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="06c09-105">Para instalar un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="06c09-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="06c09-106">Inicie sesión en el servidor en el que va a instalar el servidor Standard Edition como administrador local o como equivalente en un dominio.</span><span class="sxs-lookup"><span data-stu-id="06c09-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="06c09-107">Si no ha preparado los servicios de dominio de Active Directory, primero realice estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="06c09-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="06c09-108">Para obtener más información, consulte [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="06c09-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="06c09-109">En el Asistente para la implementación de Lync Server, haga clic en **preparar el primer servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="06c09-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="06c09-110">En la página **Preparar un solo servidor Standard Edition**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="06c09-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="06c09-111">En la página **ejecución de comandos** , se instala SQL Server 2012 Express como almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="06c09-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="06c09-112">Se crean las reglas de firewall necesarias.</span><span class="sxs-lookup"><span data-stu-id="06c09-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="06c09-113">Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en  \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="06c09-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06c09-114">Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos.</span><span class="sxs-lookup"><span data-stu-id="06c09-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="06c09-115">Esto se debe a la instalación de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="06c09-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="06c09-116">Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="06c09-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="06c09-117">En la página del Asistente para la implementación de Lync Server, haga clic en **instalar Topology Builder** si no ha instalado previamente las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="06c09-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="06c09-118">Para obtener más información, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="06c09-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="06c09-119">Confirme que hay marcas de verificación verdes junto a “Preparar Active Directory,” “Preparar el primer servidor Standard Edition” e “Instalar Topology Builder”.</span><span class="sxs-lookup"><span data-stu-id="06c09-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

