---
title: Configurar servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="1296b-102">Configurar servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="1296b-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1296b-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="1296b-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="1296b-104">En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de próximos saltos para que sea un grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1296b-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="1296b-105">En un entorno mixto, tanto el grupo heredado de Lync Server 2010 y el grupo de servidores Lync Server 2013 aparecen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1296b-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="1296b-106">No se puede seleccionar el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="1296b-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="1296b-107">**Seleccione Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza**</span><span class="sxs-lookup"><span data-stu-id="1296b-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="1296b-108">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="1296b-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="1296b-109">En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza** y haga clic en **nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="1296b-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="1296b-110">Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza y seleccione si será un servidor único o de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="1296b-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="1296b-111">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1296b-111">Click **Next**.</span></span>

5.  <span data-ttu-id="1296b-112">En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1296b-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="1296b-113">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1296b-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="1296b-114">Seleccione el nodo superior de **Lync Server** y, en el menú **acción** , seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="1296b-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="1296b-115">Compruebe que el **grupo de aplicaciones de confianza** se haya creado correctamente y que esté asociado al grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="1296b-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

