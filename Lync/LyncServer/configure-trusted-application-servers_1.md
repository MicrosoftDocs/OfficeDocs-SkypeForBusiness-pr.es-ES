---
title: Configuración de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cbaba4f59a22de6fcee38ee51845d551033cfea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="0d397-102">Configuración de servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="0d397-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d397-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="0d397-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="0d397-104">En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza después de combinar la topología heredada de Office Communications Server con Lync Server 2013 y define un nuevo servidor de aplicaciones de confianza con el generador de topologías, debe establecer el grupo de servidores de próximo salto para que sea un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d397-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="0d397-105">En un entorno combinado, tanto el grupo de servidores de Office Communications Server heredado como el grupo de servidores de Lync Server 2013 aparecen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0d397-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="0d397-106">*No* se puede seleccionar el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="0d397-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="0d397-107">Para seleccionar Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="0d397-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="0d397-108">Abrir una topología existente en el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="0d397-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="0d397-109">En el panel izquierdo, haga clic con el botón derecho en **Servidores de aplicaciones de confianza** y haga clic en **Nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="0d397-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="0d397-110">Introduzca el **FQDN del grupo de servidores** del grupo de aplicaciones de confianza y seleccione si será una implementación de un solo servidor o de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="0d397-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="0d397-111">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0d397-111">Click **Next**.</span></span>

5.  <span data-ttu-id="0d397-112">En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d397-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="0d397-113">![Cuadro de diálogo definir nuevo grupo de aplicaciones de confianza](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de aplicaciones de confianza")</span><span class="sxs-lookup"><span data-stu-id="0d397-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="0d397-114">Haga clic en  \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="0d397-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="0d397-115">Seleccione el nodo superior **Lync Server** y en el panel  **Acciones**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="0d397-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="0d397-116">El **Grupo de aplicaciones de confianza** se creó correctamente y está asociado con el grupo de front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="0d397-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

