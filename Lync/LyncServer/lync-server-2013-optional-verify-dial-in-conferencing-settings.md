---
title: 'Lync Server 2013: (Opcional) Comprobar la configuración de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177d8516dcb91272eca2a70b89026fc0e175a73a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="f3344-102">(Opcional) Comprobar la configuración de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3344-102">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3344-103">_**Última modificación del tema:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="f3344-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="f3344-104">Como comprobación final de la configuración de las conferencias de acceso telefónico local, puede buscar planes de marcado que tengan una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso, así como números de acceso que no tengan asignada una región de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="f3344-104">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="f3344-105">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="f3344-105">This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="f3344-106">Para buscar planes de marcado con una región de conferencia de acceso telefónico local que no se usa en un número de acceso</span><span class="sxs-lookup"><span data-stu-id="f3344-106">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="f3344-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="f3344-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f3344-108">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f3344-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f3344-109">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="f3344-109">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="f3344-110">Este cmdlet devuelve todos los planes de marcado que tienen una región de conferencia de acceso telefónico local que no es usada por ningún número de acceso.</span><span class="sxs-lookup"><span data-stu-id="f3344-110">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="f3344-111">Para buscar números de acceso sin regiones asignadas</span><span class="sxs-lookup"><span data-stu-id="f3344-111">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="f3344-112">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="f3344-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f3344-113">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f3344-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f3344-114">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="f3344-114">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="f3344-115">Este cmdlet devuelve todos los números de acceso de conferencia de acceso telefónico local que no están asociados a ninguna región.</span><span class="sxs-lookup"><span data-stu-id="f3344-115">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

