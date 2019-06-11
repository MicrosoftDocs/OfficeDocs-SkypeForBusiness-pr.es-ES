---
title: 'Lync Server 2013: Preparación del bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="a342a-102">Preparación del bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a342a-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a342a-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a342a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a342a-104">La preparación del bosque crea objetos y la configuración global de Active Directory y los grupos universales de Active Directory para el uso de Lync Server 2013, y concede permisos de acceso adecuados en los objetos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a342a-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="a342a-105">Para obtener una descripción de los grupos universales y la configuración global y los objetos creados por la preparación del bosque, consulte [cambios hechos por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span><span class="sxs-lookup"><span data-stu-id="a342a-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="a342a-106">La preparación del bosque también crea objetos que contienen conjuntos de propiedades y especificadores de presentación que se usan en Lync Server 2013, y los almacena en el contenedor configuración.</span><span class="sxs-lookup"><span data-stu-id="a342a-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a342a-107">Asegúrese de que los cambios en la preparación del esquema se han replicado en todos los controladores de dominio antes de realizar el procedimiento de preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="a342a-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="a342a-108">Si la replicación no se completa, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="a342a-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="a342a-109">Si va a realizar una nueva implementación de Lync Server, debe almacenar la configuración global en el contenedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="a342a-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="a342a-110">Si está actualizando desde una versión anterior y aún así almacena la configuración global en el contenedor del sistema, puede seguir usando el contenedor del sistema.</span><span class="sxs-lookup"><span data-stu-id="a342a-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="a342a-111">Para realizar este procedimiento, debe ser miembro del grupo administradores de dominio o administradores de dominio del dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="a342a-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a342a-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a342a-112">In This Section</span></span>

  - [<span data-ttu-id="a342a-113">Ejecutar la preparación del bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a342a-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="a342a-114">Usar cmdlets para invertir la preparación del bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a342a-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

