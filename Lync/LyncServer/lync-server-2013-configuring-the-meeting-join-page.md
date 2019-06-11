---
title: 'Lync Server 2013: Configuración de la página de participación en reuniones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984386eb15aac3c3d2d46c9d7aaab53457915b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="f13d5-102">Configuración de la página de participación en reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f13d5-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f13d5-103">_**Última modificación del tema:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="f13d5-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="f13d5-104">Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de la reunión detecta si un cliente de Lync 2013 ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="f13d5-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="f13d5-105">Si un cliente ya está instalado, el cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f13d5-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="f13d5-106">Si un cliente no está instalado, de forma predeterminada se abre la versión 2013 de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="f13d5-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="f13d5-107">Puede modificar el comportamiento de la página de la combinación de reuniones si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o el operador de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="f13d5-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="f13d5-108">Estas opciones de configuración se han eliminado del panel de control de Lync Server 2013, pero se configuran mediante el cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f13d5-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="f13d5-109">Conjunto de páginas de combinación de reuniones-parámetros de CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f13d5-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f13d5-110">Parámetro Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f13d5-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="f13d5-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f13d5-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f13d5-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="f13d5-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="f13d5-113">Si se establece en true, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Lync tendrán la oportunidad de unirse a la reunión mediante Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13d5-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="f13d5-114">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="f13d5-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13d5-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="f13d5-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="f13d5-116">Si se establece en true, las opciones alternativas para unirse a una conferencia en línea (como Office Communicator 2007 R2) se expandirán y mostrarán automáticamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f13d5-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="f13d5-117">Cuando se establece en false (valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="f13d5-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="f13d5-118">Para configurar la página de la combinación de reuniones con el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f13d5-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="f13d5-119">Inicie el shell de administración de Lync Server 2013: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f13d5-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f13d5-120">Para ver la configuración del servicio Web, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f13d5-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="f13d5-121">Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de su preferencia (para obtener información detallada sobre los parámetros para este cmdlet, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) en la documentación del shell de administración de Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="f13d5-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f13d5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f13d5-122">See Also</span></span>


[<span data-ttu-id="f13d5-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f13d5-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

