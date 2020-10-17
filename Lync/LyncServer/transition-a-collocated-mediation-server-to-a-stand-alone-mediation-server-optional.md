---
title: Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)
description: Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional).
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99eb445e8377a52901f54f52ca3933babe15571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559426"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="5d8fb-103">Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)</span><span class="sxs-lookup"><span data-stu-id="5d8fb-103">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d8fb-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5d8fb-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5d8fb-105">Utilice el procedimiento siguiente para realizar la transición del servidor de mediación, combinado en el servidor Standard Edition o grupo Front-End, a un servidor de mediación independiente para una implementación de sitio único.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-105">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="5d8fb-106">Para realizar la transición de un servidor de mediación combinado a un servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="5d8fb-106">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="5d8fb-107">Abre una topología existente del Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-107">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="5d8fb-108">En el panel izquierdo, vaya a \*\*Grups de mediación  \*\*.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-108">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="5d8fb-109">Haga clic con el botón secundario en **Grupos de mediación**    y seleccione \*\*Nuevo servidor de mediación  \*\*.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-109">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="5d8fb-p101">En la página **Definir nuevo grupo de servidores de mediación**, proporcione el nombre completo del nuevo grupo de servidor de mediación. Además, seleccione si este grupo va a ser un grupo de servidor único o de varios servidores y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-p101">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="5d8fb-112">Seleccione el siguiente grupo de salto del servidor de usuario al que el nuevo servidor de mediación enrutará las llamadas entrantes y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-112">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="5d8fb-113">Seleccione el grupo perimetral que va a usar el servidor de mediación y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-113">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="5d8fb-p102">En la página **Definir nuevo grupo de servidores de mediación**, asocie la puerta de enlace RTC anterior con el servidor de mediación. Seleccione la puerta de enlace y, a continuación, haga clic en \*\*Agregar  \*\*.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-p102">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="5d8fb-116">Haga clic en \*\*Finalizar \*\* para cerrar el asistente \*\*Definir nuevo grupo de servidores de mediación  \*\*.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-116">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="5d8fb-117">En **generador de topologías**, seleccione el nodo superior **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-117">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="5d8fb-118">En el panel **Acciones**, seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-118">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="5d8fb-119">Siga los pasos descritos en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) en la documentación de implementación para instalar los archivos en el nuevo servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-119">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="5d8fb-120">Después de instalar los archivos en el servidor de mediación, vuelva al generador de topologías y en el panel izquierdo, desplácese al grupo.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-120">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="5d8fb-121">Haga clic con el botón derecho en el grupo y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-121">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="5d8fb-122">En    \*\*Servidor de mediación  \*\*, desactive la casilla **Servidor de mediación combinado habilitado** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-122">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="5d8fb-123">En **generador de topologías**, seleccione el nodo superior **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-123">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="5d8fb-124">Desde el menú **Acción**, seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="5d8fb-124">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

