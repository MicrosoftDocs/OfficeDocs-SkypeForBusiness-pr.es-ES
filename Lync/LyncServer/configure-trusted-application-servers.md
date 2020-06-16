---
title: Configuración de servidores de aplicaciones de confianza
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
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="819e8-102">Configuración de servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="819e8-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="819e8-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="819e8-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="819e8-104">En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el grupo de servidores del próximo salto como un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="819e8-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="819e8-105">En un entorno mixto, tanto el grupo de servidores de Lync Server 2010 y el grupo de servidores de Lync Server 2013 aparecen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="819e8-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="819e8-106">No se admite la selección del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="819e8-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="819e8-107">**Seleccione Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza**</span><span class="sxs-lookup"><span data-stu-id="819e8-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="819e8-108">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="819e8-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="819e8-109">En el panel izquierdo, haga clic con el botón secundario en **Servidores de aplicaciones de confianza** y, a continuación, en **Nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="819e8-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="819e8-110">Escriba el **FQDN del grupo de servidores** correspondiente al grupo de aplicaciones de confianza y seleccione si se tratará de un servidor único o de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="819e8-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="819e8-111">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="819e8-111">Click **Next**.</span></span>

5.  <span data-ttu-id="819e8-112">En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="819e8-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="819e8-113">Haga clic en \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="819e8-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="819e8-114">Seleccione el nodo superior **Lync Server** y, a continuación, en el menú **Acción**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="819e8-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="819e8-115">Compruebe que se ha creado el **Grupo de aplicaciones de confianza** y que está asociado correctamente con el grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="819e8-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

