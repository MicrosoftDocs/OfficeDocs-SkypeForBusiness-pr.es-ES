---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63354b9e0b0cf44ed44f53c91061578e01fecb5
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="ee64b-102">Configurar la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="ee64b-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee64b-103">_**Última modificación del tema:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="ee64b-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="ee64b-104">Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta si un cliente de Lync 2013 ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="ee64b-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="ee64b-105">Si un cliente ya está instalado, ese cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="ee64b-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="ee64b-106">Si un cliente no está instalado, se abrirá de forma predeterminada la versión 2013 de Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="ee64b-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="ee64b-107">Puede modificar el comportamiento de la página de participación en la reunión si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o el operador de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ee64b-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="ee64b-108">Estas opciones de configuración se han quitado del panel de control de Lync Server 2013, pero puede configurarlas mediante el cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ee64b-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="ee64b-109">Parámetros de CsWebServiceConfiguration de la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="ee64b-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee64b-110">Parámetro de CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="ee64b-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="ee64b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee64b-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee64b-112">Showjoinusinglegacyclientlink establecidos</span><span class="sxs-lookup"><span data-stu-id="ee64b-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="ee64b-113">Si se establece en true, los usuarios que se unan a una reunión con una aplicación cliente distinta de Lync tendrán la oportunidad de unirse a la reunión mediante Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ee64b-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="ee64b-114">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="ee64b-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee64b-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="ee64b-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="ee64b-p104">Cuando se establece en True, se amplían automáticamente las opciones alternativas para unirse a una conferencia en línea (como Office Communicator 2007 R2) y se muestran a los usuarios. Cuando se establece en False (el valor predeterminado), estas opciones están disponibles pero el usuario tiene que mostrar la lista de opciones personalmente.</span><span class="sxs-lookup"><span data-stu-id="ee64b-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="ee64b-118">Para configurar la página de participación en la reunión mediante el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee64b-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="ee64b-119">Inicie el shell de administración de Lync Server 2013: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ee64b-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ee64b-120">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee64b-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="ee64b-121">Este cmdlet devuelve las opciones de configuración del servicio web.</span><span class="sxs-lookup"><span data-stu-id="ee64b-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="ee64b-122">Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de sus preferencias (para obtener información detallada sobre los parámetros de este cmdlet, consulte la documentación del shell de administración de Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="ee64b-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

