---
title: 'Restaurar un servidor de servicios de fondo de la edición empresarial duplicada: reflejo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="c4f50-102">Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-Mirror</span><span class="sxs-lookup"><span data-stu-id="c4f50-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4f50-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="c4f50-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="c4f50-104">Si tiene un servidor de servicios de fondo Enterprise Edition en una configuración reflejada y solo se produce un error en el reflejo, siga los procedimientos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="c4f50-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="c4f50-105">Si la base de datos principal y el reflejo fallan, consulte [restaurar un servidor de servicios de fondo de la edición empresarial en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4f50-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="c4f50-106">Si solo se produce un error en el principal, vea [restaurar un servidor back-end de empresa duplicada en Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span><span class="sxs-lookup"><span data-stu-id="c4f50-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="c4f50-107">Si se produce un error en la base de datos que hospeda el almacén de administración central, consulte [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="c4f50-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="c4f50-108">Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4f50-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="c4f50-109">Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="c4f50-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="c4f50-110">Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="c4f50-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="c4f50-111">Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="c4f50-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="c4f50-112">Para restaurar una base de datos reflejada del servidor de servicios de fondo de la edición Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4f50-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="c4f50-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="c4f50-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="c4f50-114">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c4f50-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c4f50-115">Desinstalar reflejo.</span><span class="sxs-lookup"><span data-stu-id="c4f50-115">Uninstall mirroring.</span></span> <span data-ttu-id="c4f50-116">En primer lugar, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c4f50-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="c4f50-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c4f50-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="c4f50-118">Haga esto para todos los tipos de base de datos en este servidor.</span><span class="sxs-lookup"><span data-stu-id="c4f50-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="c4f50-119">Cree un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) (DB1.contoso.com) que el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="c4f50-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="c4f50-120">Este servidor funcionará como el nuevo reflejo.</span><span class="sxs-lookup"><span data-stu-id="c4f50-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="c4f50-121">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="c4f50-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="c4f50-122">Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los mismos nombres de instancia que antes del error.</span><span class="sxs-lookup"><span data-stu-id="c4f50-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="c4f50-123">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="c4f50-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="c4f50-124">Use el generador de topología para instalar la base de datos de reflejo.</span><span class="sxs-lookup"><span data-stu-id="c4f50-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="c4f50-125">Realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4f50-125">Perform the following:</span></span>
    
      - <span data-ttu-id="c4f50-126">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c4f50-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="c4f50-127">Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="c4f50-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="c4f50-128">Siga el Asistente para la **instalación de bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="c4f50-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="c4f50-129">En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.</span><span class="sxs-lookup"><span data-stu-id="c4f50-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="c4f50-130">Siga el asistente hasta que aparezca un mensaje de creación de una **base de datos de reflejo** .</span><span class="sxs-lookup"><span data-stu-id="c4f50-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="c4f50-131">Seleccione la base de datos que desea instalar y complete este proceso.</span><span class="sxs-lookup"><span data-stu-id="c4f50-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="c4f50-132">En lugar de ejecutar el generador de topologías, puede usar el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar el reflejo.</span><span class="sxs-lookup"><span data-stu-id="c4f50-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="c4f50-133">Para obtener más información, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4f50-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

