---
title: Configuración de servidores de aplicaciones de confianza
description: Configurar servidores de aplicaciones de confianza.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39f439ea3e5996e0a3464540069024b70c415e3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548826"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="237c0-103">Configuración de servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="237c0-103">Configure trusted application servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="237c0-104">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="237c0-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="237c0-105">En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el grupo de servidores del próximo salto como un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237c0-105">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="237c0-106">En un entorno mixto, tanto el grupo de servidores de Lync Server 2010 y el grupo de servidores de Lync Server 2013 aparecen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="237c0-106">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="237c0-107">No se admite la selección del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="237c0-107">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="237c0-108">**Seleccione Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza**</span><span class="sxs-lookup"><span data-stu-id="237c0-108">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="237c0-109">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="237c0-109">Open Topology Builder.</span></span>

2.  <span data-ttu-id="237c0-110">En el panel izquierdo, haga clic con el botón secundario en **Servidores de aplicaciones de confianza** y, a continuación, en **Nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="237c0-110">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="237c0-111">Escriba el **FQDN del grupo de servidores** correspondiente al grupo de aplicaciones de confianza y seleccione si se tratará de un servidor único o de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="237c0-111">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="237c0-112">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="237c0-112">Click **Next**.</span></span>

5.  <span data-ttu-id="237c0-113">En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="237c0-113">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="237c0-114">Haga clic en \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="237c0-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="237c0-115">Seleccione el nodo superior **Lync Server** y, a continuación, en el menú **Acción**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="237c0-115">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="237c0-116">Compruebe que se ha creado el **Grupo de aplicaciones de confianza** y que está asociado correctamente con el grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="237c0-116">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

