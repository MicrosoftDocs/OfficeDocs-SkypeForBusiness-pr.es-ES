---
title: 'Lync Server 2013: preparar el bosque'
description: 'Lync Server 2013: preparar el bosque.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580006"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="d681d-103">Preparar el bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d681d-103">Preparing the forest for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d681d-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d681d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d681d-105">La preparación del bosque crea objetos y la configuración global de Active Directory y los grupos universales de Active Directory para su uso por parte de Lync Server 2013 y concede los permisos de acceso adecuados en los objetos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d681d-105">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="d681d-106">Para obtener una descripción de los grupos universales y la configuración global y los objetos creados por la preparación del bosque, consulte [cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span><span class="sxs-lookup"><span data-stu-id="d681d-106">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="d681d-107">La preparación del bosque también crea objetos que contienen conjuntos de propiedades y especificadores de presentación que se usan en Lync Server 2013 y los almacena en el contenedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="d681d-107">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d681d-108">Asegúrese de que los cambios en la preparación del esquema se han replicado en todos los controladores de dominio antes de realizar el procedimiento de preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="d681d-108">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="d681d-109">Si la replicación no se ha completado, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="d681d-109">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="d681d-110">Si va a realizar una nueva implementación de Lync Server, debe almacenar la configuración global en el contenedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="d681d-110">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="d681d-111">Si va a actualizar desde una versión anterior y sigue almacenando la configuración global en el contenedor del sistema, puede seguir usando el contenedor del sistema.</span><span class="sxs-lookup"><span data-stu-id="d681d-111">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="d681d-112">Debe ser miembro del grupo Administradores de empresas o Admins. del dominio para que el dominio raíz del bosque realice este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d681d-112">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d681d-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d681d-113">In This Section</span></span>

  - [<span data-ttu-id="d681d-114">Ejecutar la preparación del bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d681d-114">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="d681d-115">Uso de cmdlets para invertir la preparación del bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d681d-115">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

