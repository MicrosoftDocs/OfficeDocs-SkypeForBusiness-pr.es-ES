---
title: 'Lync Server 2013: restaurar o archivar datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803cb6050d4230653a13f1e3e66c2a092911c509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="a8808-102">Restaurar o archivar datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8808-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8808-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="a8808-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="a8808-104">La restauración de datos de supervisión y archivado no es necesaria para que Lync Server funcione correctamente después de un error.</span><span class="sxs-lookup"><span data-stu-id="a8808-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="a8808-105">Sin embargo, si la supervisión y el archivado de datos son esenciales para su organización, querrá restaurar los datos después de volver a crear las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a8808-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="a8808-106">En el procedimiento siguiente se describe cómo usar SQL Server Management Studio para restaurar o archivar datos.</span><span class="sxs-lookup"><span data-stu-id="a8808-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="a8808-107">Para restaurar datos de supervisión o de archivado desde un archivo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="a8808-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="a8808-108">Inicie sesión en el servidor que va a restaurar como miembro del grupo administradores en el equipo local o en un grupo con derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="a8808-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="a8808-109">Abra SQL Server Management Studio: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft SQL Server 2012** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="a8808-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="a8808-110">En **conectar con el servidor**, conéctese a la instancia de SQL Server proporcionando al menos el nombre del servidor y la información de autenticación.</span><span class="sxs-lookup"><span data-stu-id="a8808-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="a8808-111">En el **Explorador de objetos**, haga clic con el botón secundario en **bases**de datos y luego haga clic en **restaurar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="a8808-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="a8808-112">En **seleccionar una página**, haga clic en **General**y, a continuación, en **base de datos** Seleccione el nombre de la base de datos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a8808-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="a8808-113">Para una base de datos de archivado, seleccione **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="a8808-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="a8808-114">Para obtener una base de datos de grabación de detalles de llamadas (CDR), seleccione **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="a8808-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="a8808-115">Para obtener una base de datos de calidad de la experiencia (QoE), seleccione **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="a8808-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="a8808-116">Haga clic en **desde dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a8808-116">Click **From device**.</span></span>

7.  <span data-ttu-id="a8808-117">En **seleccionar los conjuntos de copia de seguridad que se restaurarán**, haga clic en el archivo de copia de seguridad y luego en **restaurar**.</span><span class="sxs-lookup"><span data-stu-id="a8808-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="a8808-118">En **seleccionar una página**, haga clic en **Opciones**, compruebe que la ruta del archivo de datos y la ruta de registro estén en la carpeta correcta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8808-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="a8808-119">Para asegurarse de que las listas de control de acceso (ACL) sean correctas</span><span class="sxs-lookup"><span data-stu-id="a8808-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="a8808-120">Expanda **bases**de datos, expanda la base de datos de archivado o supervisión, expanda **seguridad**y, a continuación, expanda **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="a8808-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="a8808-121">Compruebe que el grupo de dominio RTCComponentUniversalServices existe como usuario.</span><span class="sxs-lookup"><span data-stu-id="a8808-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="a8808-122">Si RTCComponentUniversalServices no existe en **usuarios**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8808-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="a8808-123">Haga clic con el botón secundario en **usuarios**y luego haga clic en **nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="a8808-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="a8808-124">En **nombre de inicio de sesión**, escriba el nombre del grupo que falta, RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="a8808-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="a8808-125">En pertenencia al rol de la \*\*\*\* **base de datos**, seleccione el permiso y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8808-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a8808-126">No es necesario que reinicie el servicio de archivado o supervisión.</span><span class="sxs-lookup"><span data-stu-id="a8808-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

