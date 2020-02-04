---
title: 'Lync Server 2013: comprobar el uso del disco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="f8f9e-102">Comprobar el uso del disco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8f9e-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8f9e-103">_**Última modificación del tema:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="f8f9e-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="f8f9e-104">Las unidades de discos duros son un componente importante de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="f8f9e-105">Sin suficiente volumen de disco libre, ni el sistema operativo ni las bases de datos de Lync Server 2013 pueden funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="f8f9e-106">Debe supervisar diariamente las estadísticas de la base de datos back-end de Lync Server 2013 para asegurarse de que los servidores no se queden sin espacio en el disco y para prepararse para agregar recursos de almacenamiento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="f8f9e-107">Además de comprobar el espacio en los discos que hospedan el sistema operativo, los archivos de programa, la base de datos y los registros de transacciones (back-end de Lync Server 2013), también debe supervisar el uso del sistema de archivos que incluye espacio en el disco para los archivos compartidos que contienen lo siguiente importante datos</span><span class="sxs-lookup"><span data-stu-id="f8f9e-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="f8f9e-108">Contenido de la reunión</span><span class="sxs-lookup"><span data-stu-id="f8f9e-108">Meeting content</span></span>

  - <span data-ttu-id="f8f9e-109">Metadatos de contenido de reunión</span><span class="sxs-lookup"><span data-stu-id="f8f9e-109">Meeting content metadata</span></span>

  - <span data-ttu-id="f8f9e-110">Registros de cumplimiento de las reuniones</span><span class="sxs-lookup"><span data-stu-id="f8f9e-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="f8f9e-111">Archivos de datos de la aplicación (utilizado de forma interna por el componente de servidor de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="f8f9e-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="f8f9e-112">Servicio Web del servidor de chats grupales y carpetas de cumplimiento (para almacenar archivos cargados en el servicio Web de chat grupal)</span><span class="sxs-lookup"><span data-stu-id="f8f9e-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="f8f9e-113">Archivos XML de cumplimiento de chats grupales (que contienen registros de cumplimiento de chats grupales)</span><span class="sxs-lookup"><span data-stu-id="f8f9e-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="f8f9e-114">Archivos de actualización (para el servicio de actualización de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="f8f9e-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="f8f9e-115">Archivos de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="f8f9e-115">Address Book files</span></span>

<span data-ttu-id="f8f9e-116">Lync Server 2013 necesita espacio en el disco duro para almacenar sus bases de datos y registros de transacciones, además de los archivos en los recursos compartidos de archivos mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="f8f9e-117">Debe supervisar el espacio en disco de forma regular para asegurarse de que la implementación de Lync Server 2013 no se ve afectada negativamente debido a que no hay suficientes recursos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="f8f9e-118">Compare y mantenga información estadística sobre el espacio disponible en disco en cada volumen de Lync Server 2013 y el crecimiento esperado de las bases de datos y los archivos de registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="f8f9e-119">Esto ayuda con la planificación de capacidad y la adición de almacenamiento cuando se necesitan los recursos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="f8f9e-120">Para dar cabida a situaciones de solución de problemas y recuperación de desastres, recomendamos que el espacio de volumen disponible sea igual o superior al 110 por ciento del tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="f8f9e-121">Para comprobar el espacio libre en el disco, use los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8f9e-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="f8f9e-122">**System Center Operations Manager**   System Center Operations Manager se puede usar para avisar a los administradores cuando el espacio de volumen está restringido.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="f8f9e-123">**Ejecute**   un espacio de disco de monitor de script ejecutando una secuencia de comandos que le envíe un mensaje si el espacio disponible en el disco duro está por debajo del 20 por ciento.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="f8f9e-124">Puede encontrar una secuencia de comandos de ejemplo en Microsoft Script Center en TechNet, examinar:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="f8f9e-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="f8f9e-125">**Explorador de Windows**   use el explorador de Windows para comprobar el espacio en disco de los volúmenes que almacenan los registros y las bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

