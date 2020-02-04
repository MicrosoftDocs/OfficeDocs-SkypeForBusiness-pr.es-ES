---
title: Configuración de Lync Server 2013 para que funcione con Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3516822064d0fd42b44edb7af73b321644c36c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="78a73-102">Configuración de Lync Server 2013 para que funcione con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="78a73-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78a73-103">_**Última modificación del tema:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="78a73-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="78a73-104">Antes de poder configurar Lync Server 2013 para usar Office Web Apps Server, debe implementar y configurar Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="78a73-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="78a73-105">Consulte la guía de documentos sobre la **implementación de Office Web Apps Server y Office Web Apps** para obtener información detallada sobre cómo instalar y configurar un único servidor de Office Web Apps, u obtenga información sobre cómo instalar y configurar una granja de Office Web Apps Server para alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="78a73-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="78a73-106">Después de instalar Office Web Apps Server correctamente y de que su granja de servidores Web se haya configurado correctamente, debe configurar Lync Server para que se comunique con el nuevo servidor; Esto se realiza agregando la dirección URL de detección de Office Web Apps Server a su topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78a73-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="78a73-107">Realice lo siguiente para agregar Office Web Apps Server a su topología:</span><span class="sxs-lookup"><span data-stu-id="78a73-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="78a73-108">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78a73-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="78a73-109">En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78a73-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="78a73-p103">En el cuadro de diálogo **Guardar topología como**, escriba el nombre del documento de topología (por ejemplo, **PreWebAppsServerTopology**) en el cuadro **Nombre de archivo** y, después, haga clic en **Guardar**. Esta topología se podrá recuperar y volver a publicar más adelante si detecta algún problema en ella.</span><span class="sxs-lookup"><span data-stu-id="78a73-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="78a73-112">En el generador de topologías, expanda **Lync Server 2013**, expanda el nombre de su sitio, expanda **agrupaciones front end de Enterprise Edition**, haga clic con el botón secundario en el nombre de uno de sus grupos y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="78a73-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="78a73-113">En la pestaña **General** del cuadro de diálogo **Editar propiedades**, busque el encabezado **Asociar Office Web Apps Server** y haga clic en **Nuevo** (o seleccione un Office Web Apps Server de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="78a73-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="78a73-114">En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.</span><span class="sxs-lookup"><span data-stu-id="78a73-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="78a73-115">Si Office Web Apps Server está instalado en local y en la misma zona de red que Lync Server 2013, la opción **Office Web Apps Server se implementa en una red externa (es decir,** no se debe seleccionar el perímetro o la Internet).</span><span class="sxs-lookup"><span data-stu-id="78a73-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="78a73-116">Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="78a73-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="78a73-117">Haga clic en **Aceptar** en el cuadro de diálogo **Definir nuevo servidor de Office Web Apps** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="78a73-117">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="78a73-118">La dirección URL de detección de Office Web Apps aparecerá como una de las asociaciones de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="78a73-118">The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="78a73-119">Este proceso deberá repetirse con cada grupo de servidores que tenga que asociarse a Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="78a73-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="78a73-120">Después de agregar la dirección URL de detección a la topología, debe publicar esta topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="78a73-120">After you have added the discovery URL to the topology you must then publish this updated topology.</span></span> <span data-ttu-id="78a73-121">Para ello, haga lo siguiente en el Generador de topologías:</span><span class="sxs-lookup"><span data-stu-id="78a73-121">To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="78a73-122">Haga clic en **Acción** y, después, en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="78a73-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="78a73-123">En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78a73-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="78a73-124">En la página **Asistente para publicación completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="78a73-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="78a73-125">Cierre el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="78a73-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

