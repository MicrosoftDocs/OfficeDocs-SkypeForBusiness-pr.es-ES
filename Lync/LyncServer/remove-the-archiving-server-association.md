---
title: Quitar la asociación del servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="f6dd7-102">Quitar la asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="f6dd7-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6dd7-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f6dd7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f6dd7-104">Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo frontal, el servidor front-end, el equipo de la sucursal y el servidor de la sucursal que siguen funcionando.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="f6dd7-105">Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="f6dd7-106">Después de borrar la dependencia y de eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="f6dd7-107">Para quitar la Asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="f6dd7-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="f6dd7-108">Abra el servidor front-end 2013 de Lync Server, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="f6dd7-109">Vaya al nodo de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="f6dd7-110">En el generador de topología, expanda las **agrupaciones front end de Enterprise Edition**, **los servidores de aplicaciones para el usuario Standard Edition**o los **sitios de sucursales**en función de dónde se defina el servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="f6dd7-111">Si tiene asociado un servidor de sucursal, expanda **sitios de sucursales**, expanda el nombre del sitio de la sucursal y, a continuación, expanda **aplicaciones de sucursales**reutilizables.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6dd7-112">Los <STRONG>dispositivos</STRONG> de la interfaz de usuario que son supervivientes se aplican a los servidores de sucursal con supervivencia y con la aplicación de rama superviviente.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="f6dd7-113">Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado al servidor de archivado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="f6dd7-114">En **Editar propiedades**, en **General**, en **asociaciones**, desactive la casilla **asociar servidor** de archivado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="f6dd7-115">Repita el paso anterior para cualquier otro grupo, servidor o dispositivo asociado al servidor de archivado que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="f6dd7-116">Haga clic con el botón secundario en el servidor de archivado y luego haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="f6dd7-117">En **eliminar almacenes**dependientes, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="f6dd7-118">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Lync Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f6dd7-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

