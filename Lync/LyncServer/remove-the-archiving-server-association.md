---
title: Quitar la Asociación del servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85e07dc3ca2da36f2c3a684be106eb4e2d428d00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="e71a5-102">Quitar la Asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="e71a5-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e71a5-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="e71a5-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="e71a5-104">Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="e71a5-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="e71a5-105">Edite las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para eliminar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="e71a5-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="e71a5-106">Una vez que borre la dependencia y elimine el servidor en el generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="e71a5-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="e71a5-107">Para quitar la asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="e71a5-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="e71a5-108">Abra el servidor front-end de Lync Server 2013 y abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="e71a5-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="e71a5-109">Navegue hasta el nodo 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e71a5-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="e71a5-110">En el generador de topologías, expanda grupos de servidores **front-end Enterprise Edition**, **servidores front-end Standard Edition**o **sitios de sucursal**, en función de dónde se haya definido el servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="e71a5-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="e71a5-111">Si tiene asociado un servidor de sucursal con funciones de supervivencia, expanda **sitios de sucursal**, expanda el nombre del sitio de sucursal y, a continuación, expanda aplicaciones de sucursal con funciones de **supervivencia**.</span><span class="sxs-lookup"><span data-stu-id="e71a5-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e71a5-112">Las <STRONG>aplicaciones de sucursal</STRONG> con funciones de supervivencia de la interfaz de usuario se aplican a un servidor de sucursal con funciones de supervivencia y una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="e71a5-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="e71a5-113">Haga clic con el botón secundario en el grupo de servidores, servidor o dispositivo asociado con el servidor de archivado y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e71a5-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="e71a5-114">En **Editar propiedades**, en **General**, en **Asociaciones**, desmarque la casilla **Asociar servidor de archivado** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e71a5-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="e71a5-115">Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de archivado que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="e71a5-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="e71a5-116">Haga clic con el botón secundario en el servidor de archivado y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e71a5-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="e71a5-117">En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e71a5-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="e71a5-118">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Lync Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e71a5-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

