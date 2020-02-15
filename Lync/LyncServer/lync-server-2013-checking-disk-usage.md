---
title: 'Lync Server 2013: comprobación del uso de disco'
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
ms.openlocfilehash: 8532b15ac45033d966c772e6ab23403d709ed790
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="9eb9c-102">Comprobar el uso de disco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eb9c-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eb9c-103">_**Última modificación del tema:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="9eb9c-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="9eb9c-104">Las unidades de disco duro son un componente importante de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="9eb9c-105">Sin un volumen de disco libre suficiente, ni el sistema operativo ni las bases de datos de Lync Server 2013 pueden funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="9eb9c-106">Debe supervisar diariamente las estadísticas de la base de datos back-end de Lync Server 2013 para garantizar que los servidores no se queden sin espacio en disco y para prepararse para agregar recursos de almacenamiento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="9eb9c-107">Además de comprobar el espacio en discos que hospedan el sistema operativo, archivos de programa, bases de datos y registros de transacciones (back-end 2013 de Lync Server), también debe supervisar el uso del sistema de archivos que incluya espacio en disco para recursos compartidos de archivos que contengan lo siguiente importante datos</span><span class="sxs-lookup"><span data-stu-id="9eb9c-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="9eb9c-108">Contenido de reuniones</span><span class="sxs-lookup"><span data-stu-id="9eb9c-108">Meeting content</span></span>

  - <span data-ttu-id="9eb9c-109">Metadatos de contenido de reunión</span><span class="sxs-lookup"><span data-stu-id="9eb9c-109">Meeting content metadata</span></span>

  - <span data-ttu-id="9eb9c-110">Registros de cumplimiento de reuniones</span><span class="sxs-lookup"><span data-stu-id="9eb9c-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="9eb9c-111">Archivos de datos de aplicación (lo utiliza internamente el componente del servidor de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="9eb9c-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="9eb9c-112">Servicio Web del servidor de chat en grupo y carpetas de cumplimiento (para almacenar los archivos cargados en el servicio Web de chat en grupo)</span><span class="sxs-lookup"><span data-stu-id="9eb9c-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="9eb9c-113">Archivos XML de cumplimiento de chat en grupo (que contienen registros de cumplimiento de chat de grupo)</span><span class="sxs-lookup"><span data-stu-id="9eb9c-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="9eb9c-114">Archivos de actualización (para el servicio de actualización de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="9eb9c-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="9eb9c-115">Archivos de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="9eb9c-115">Address Book files</span></span>

<span data-ttu-id="9eb9c-116">Lync Server 2013 necesita espacio en el disco duro para almacenar sus bases de datos y registros de transacciones, además de los archivos en los recursos compartidos de archivos enumerados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="9eb9c-117">Debe supervisar el espacio en disco de forma regular para asegurarse de que la implementación de Lync Server 2013 no se ve afectada negativamente debido a recursos de almacenamiento insuficientes.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="9eb9c-118">Compare y mantenga la información estadística sobre el espacio disponible en disco en cada volumen de Lync Server 2013 y el crecimiento esperado de las bases de datos y los archivos de registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="9eb9c-119">Esto le ayuda a planear la capacidad y a agregar almacenamiento cuando se necesitan los recursos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="9eb9c-120">Para dar cabida a situaciones de solución de problemas y recuperación ante desastres, se recomienda que el espacio de volumen disponible sea igual o mayor que el 110 por ciento del tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="9eb9c-121">Puede comprobar el espacio libre en disco con los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9eb9c-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="9eb9c-122">**System Center Operations Manager**   se puede usar System Center Operations Manager para avisar a los administradores cuando se restringe el espacio en el volumen.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="9eb9c-123">**Ejecutar un**   espacio en disco de monitor de script mediante la ejecución de un script que le envía un mensaje si el espacio disponible en el disco duro cae por debajo del 20 por ciento.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="9eb9c-124">Puede encontrar un script de ejemplo en el centro de scripts de Microsoft en TechNet, examine:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="9eb9c-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="9eb9c-125">**El explorador**   de Windows usa el explorador de Windows para comprobar el espacio en disco en los volúmenes que almacenan las bases de datos y los registros de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

