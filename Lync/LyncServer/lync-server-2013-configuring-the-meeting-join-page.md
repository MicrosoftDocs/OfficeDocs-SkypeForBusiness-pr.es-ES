---
title: 'Lync Server 2013: configuración de la página para unirse a la reunión'
description: 'Lync Server 2013: configurar la página de participación en la reunión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e7c9dde0fdb6829da7bd11e16261a4bd76b7554
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564306"
---
# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="6b51e-103">Configuración de la página de participación en la reunión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b51e-103">Configuring the meeting join page in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b51e-104">_**Última modificación del tema:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="6b51e-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="6b51e-105">Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta si un cliente de Lync 2013 ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="6b51e-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="6b51e-106">Si hay uno instalado, el cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="6b51e-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="6b51e-107">Si un cliente no está instalado, se abre de forma predeterminada la versión 2013 de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="6b51e-107">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="6b51e-108">Puede modificar el comportamiento de la página de participación en la reunión si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o el operador de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="6b51e-108">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="6b51e-109">Estas opciones de configuración se han quitado del panel de control de Lync Server 2013, pero puede configurarlas mediante el cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6b51e-109">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="6b51e-110">Parámetros de Set-CsWebServiceConfiguration de la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="6b51e-110">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b51e-111">Parámetro Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="6b51e-111">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="6b51e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b51e-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b51e-113">Showjoinusinglegacyclientlink establecidos</span><span class="sxs-lookup"><span data-stu-id="6b51e-113">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="6b51e-114">Si se establece en true, los usuarios que se unan a una reunión con una aplicación cliente distinta de Lync tendrán la oportunidad de unirse a la reunión mediante Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6b51e-114">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="6b51e-115">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="6b51e-115">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b51e-116">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="6b51e-116">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="6b51e-p104">Cuando se establece en True, se amplían automáticamente las opciones alternativas para unirse a una conferencia en línea (como Office Communicator 2007 R2) y se muestran a los usuarios. Cuando se establece en False (el valor predeterminado), estas opciones están disponibles pero el usuario tiene que mostrar la lista de opciones personalmente.</span><span class="sxs-lookup"><span data-stu-id="6b51e-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="6b51e-119">Para configurar la página de participación en la reunión mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b51e-119">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="6b51e-120">Inicie el shell de administración de Lync Server 2013: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6b51e-120">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6b51e-121">Para ver las opciones de configuración del servicio web, ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b51e-121">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="6b51e-122">Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de sus preferencias (para obtener información detallada sobre los parámetros de este cmdlet, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) en la documentación del shell de administración de Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="6b51e-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b51e-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b51e-123">See Also</span></span>


[<span data-ttu-id="6b51e-124">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="6b51e-124">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

