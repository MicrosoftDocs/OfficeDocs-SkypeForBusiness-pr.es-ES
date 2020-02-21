---
title: 'Lync Server 2013: restauración de datos de archivado o supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e44bf1fe66aa7c03caea2ba367f425f1094a9a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="dda73-102">Restauración de datos de supervisión o archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dda73-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dda73-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="dda73-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="dda73-104">La restauración de datos de supervisión y archivado no es necesaria para poner Lync Server en funcionamiento tras un error.</span><span class="sxs-lookup"><span data-stu-id="dda73-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="dda73-105">Sin embargo, si los datos de supervisión y archivado son críticos para su organización, querrá restaurarlos después de volver a crear las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="dda73-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="dda73-106">El siguiente procedimiento describe cómo usar SQL Server Management Studio para restaurar los datos de archivado o supervisión.</span><span class="sxs-lookup"><span data-stu-id="dda73-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="dda73-107">Para restaurar datos de archivado o supervisión de un archivo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="dda73-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="dda73-108">Inicie sesión en el servidor que va a restaurar como miembro del grupo administradores en el equipo local o en un grupo con derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="dda73-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="dda73-109">Abra SQL Server Management Studio: haga clic en **Inicio**, en **todos los programas**, en **Microsoft SQL Server 2012** o en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="dda73-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="dda73-110">En **Conectar al servidor**, conéctese a la instancia de SQL Server indicando al menos el nombre del servidor y la información de autenticación.</span><span class="sxs-lookup"><span data-stu-id="dda73-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="dda73-111">En **Explorador de objetos**, haga clic con el botón secundario del mouse en **Bases de datos** y, a continuación, haga clic en **Restaurar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="dda73-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="dda73-112">En **Seleccionar una página**, haga clic en **General** y, a continuación, en **Base de datos de destino**, seleccione el nombre de la base de datos de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="dda73-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="dda73-113">Para una base de datos de archivado, seleccione **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="dda73-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="dda73-114">Para una base de datos de registros de detalles de las llamadas (CDR), seleccione **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="dda73-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="dda73-115">Para una base de datos de calidad de la experiencia (QoE), seleccione **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="dda73-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="dda73-116">Haga clic en **Dispositivos de origen**.</span><span class="sxs-lookup"><span data-stu-id="dda73-116">Click **From device**.</span></span>

7.  <span data-ttu-id="dda73-117">En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, haga clic en el archivo de copia de seguridad y, a continuación, haga clic en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="dda73-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="dda73-118">En **Seleccionar una página**, haga clic en **Opciones**, compruebe que la ruta del archivo de datos y la ruta del registro se encuentran en la carpeta correcta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dda73-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="dda73-119">Para asegurarse de que las listas de control de acceso (ACL) son correctas</span><span class="sxs-lookup"><span data-stu-id="dda73-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="dda73-120">Expanda **Bases de datos**, expanda la base de datos de archivado o supervisión, expanda **Seguridad** y, a continuación, expanda **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dda73-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="dda73-121">Compruebe que el grupo de dominio RTCComponentUniversalServices existe como usuario.</span><span class="sxs-lookup"><span data-stu-id="dda73-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="dda73-122">Si RTCComponentUniversalServices no existe en **usuarios**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dda73-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="dda73-123">Haga clic con el botón secundario en **Usuarios** y haga clic en **Nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="dda73-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="dda73-124">En **nombre de inicio de sesión**, escriba el nombre del grupo que falta, RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="dda73-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="dda73-125">En **Miembros del rol de base de datos**, seleccione el permiso **ServerRole** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dda73-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda73-126">No será necesario reiniciar el servicio de archivado o supervisión.</span><span class="sxs-lookup"><span data-stu-id="dda73-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

