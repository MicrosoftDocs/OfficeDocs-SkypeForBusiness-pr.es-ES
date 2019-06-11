---
title: Transición de un servidor de mediación en un servidor de mediación independiente (opcional)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="2c960-102">Transición de un servidor de mediación en un servidor de mediación independiente (opcional)</span><span class="sxs-lookup"><span data-stu-id="2c960-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c960-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2c960-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2c960-104">Use el procedimiento que se indica a continuación para realizar la transición de su servidor de mediación, en el servidor Standard Edition o en el grupo front-end, a un servidor de mediación independiente para una implementación de sitio único.</span><span class="sxs-lookup"><span data-stu-id="2c960-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="2c960-105">Para migrar un servidor de mediación ordenada a un servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="2c960-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="2c960-106">Abra una topología existente desde el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="2c960-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="2c960-107">En el panel de la izquierda, vaya a **grupos**de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c960-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="2c960-108">Haga clic con el botón secundario en **grupos** de mediación y seleccione **nuevo servidor**de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c960-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="2c960-109">En la página **definir nuevo grupo** de mediación, proporcione el FQDN del nuevo grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c960-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="2c960-110">Además, seleccione si este grupo será un solo servidor o un grupo de varios servidores y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2c960-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="2c960-111">Seleccione el grupo de servidores front-end de próximo salto al que el servidor de mediación enrutará las llamadas entrantes y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2c960-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="2c960-112">Seleccione el grupo perimetral que va a usar el servidor de mediación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2c960-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="2c960-113">En la página **especificar puertas de enlace RTC** , asocie la puerta de enlace RTC anterior con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c960-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="2c960-114">Seleccione la puerta de enlace y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2c960-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="2c960-115">Haga clic en **Finalizar** para cerrar el asistente **definir nuevo grupo** de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c960-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="2c960-116">En el **generador**de topologías, seleccione el nodo superior de **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="2c960-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="2c960-117">En el panel **acciones** , seleccione **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="2c960-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="2c960-118">Siga los pasos que se indican en [instalar los archivos de Media Server en Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) en la documentación de implementación para instalar los archivos en el nuevo servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c960-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="2c960-119">Una vez que los archivos estén instalados en el servidor de mediación, vuelva al generador de topología y, en el panel izquierdo, vaya al grupo.</span><span class="sxs-lookup"><span data-stu-id="2c960-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="2c960-120">Haga clic con el botón derecho en el grupo y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2c960-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="2c960-121">En **servidor**de mediación, desactive la casilla servidor de mediación con el que **está habilitada** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2c960-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="2c960-122">En el **generador**de topologías, seleccione el nodo superior de **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="2c960-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="2c960-123">En el menú **acción** , seleccione **publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="2c960-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

