---
title: Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4140732fd5d091f3ed03e2dadd2f827a24531e9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="c218e-102">Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)</span><span class="sxs-lookup"><span data-stu-id="c218e-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c218e-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c218e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c218e-104">Utilice el procedimiento siguiente para realizar la transición del servidor de mediación, combinado en el servidor Standard Edition o grupo Front-End, a un servidor de mediación independiente para una implementación de sitio único.</span><span class="sxs-lookup"><span data-stu-id="c218e-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="c218e-105">Para realizar la transición de un servidor de mediación combinado a un servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="c218e-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="c218e-106">Abre una topología existente del Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c218e-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="c218e-107">En el panel izquierdo, vaya a \*\*Grups de mediación  \*\*.</span><span class="sxs-lookup"><span data-stu-id="c218e-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="c218e-108">Haga clic con el botón secundario en **Grupos de mediación**    y seleccione \*\*Nuevo servidor de mediación  \*\*.</span><span class="sxs-lookup"><span data-stu-id="c218e-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="c218e-p101">En la página **Definir nuevo grupo de servidores de mediación**, proporcione el nombre completo del nuevo grupo de servidor de mediación. Además, seleccione si este grupo va a ser un grupo de servidor único o de varios servidores y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c218e-p101">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="c218e-111">Seleccione el siguiente grupo de salto del servidor de usuario al que el nuevo servidor de mediación enrutará las llamadas entrantes y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c218e-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="c218e-112">Seleccione el grupo perimetral que va a usar el servidor de mediación y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c218e-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="c218e-p102">En la página **Definir nuevo grupo de servidores de mediación**, asocie la puerta de enlace RTC anterior con el servidor de mediación. Seleccione la puerta de enlace y, a continuación, haga clic en \*\*Agregar  \*\*.</span><span class="sxs-lookup"><span data-stu-id="c218e-p102">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="c218e-115">Haga clic en \*\*Finalizar \*\* para cerrar el asistente \*\*Definir nuevo grupo de servidores de mediación  \*\*.</span><span class="sxs-lookup"><span data-stu-id="c218e-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="c218e-116">En **generador de topologías**, seleccione el nodo superior **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="c218e-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="c218e-117">En el panel **Acciones**, seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="c218e-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="c218e-118">Siga los pasos descritos en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) en la documentación de implementación para instalar los archivos en el nuevo servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c218e-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="c218e-119">Después de instalar los archivos en el servidor de mediación, vuelva al generador de topologías y en el panel izquierdo, desplácese al grupo.</span><span class="sxs-lookup"><span data-stu-id="c218e-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="c218e-120">Haga clic con el botón derecho en el grupo y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c218e-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="c218e-121">En    \*\*Servidor de mediación  \*\*, desactive la casilla **Servidor de mediación combinado habilitado** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c218e-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="c218e-122">En **generador de topologías**, seleccione el nodo superior **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="c218e-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="c218e-123">Desde el menú **Acción**, seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="c218e-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

