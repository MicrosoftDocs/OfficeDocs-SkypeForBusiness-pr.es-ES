---
title: Quitar una entrada de host autorizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71fa2b6aeb56a9adaef1f528c577b7d15c290533
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="2ee5b-102">Quitar una entrada de host autorizado</span><span class="sxs-lookup"><span data-stu-id="2ee5b-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ee5b-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="2ee5b-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="2ee5b-104">En este tema se describe cómo quitar una entrada de host autorizado heredada (conocida como *entrada de aplicación de confianza* en Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="2ee5b-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="2ee5b-105">Debe quitar las entradas de host autorizado existentes para las puertas de enlace SIP/CSTA de la implementación de Office Communications Server 2007 R2 cuando migre el control remoto de llamadas a una implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="2ee5b-106">Debe usar las herramientas administrativas incluidas con Office Communications Server 2007 R2 para quitar las entradas de host autorizadas existentes.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="2ee5b-107">Para quitar una entrada de host autorizado de una implementación de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2ee5b-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="2ee5b-108">Abra la consola administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="2ee5b-109">Expanda el árbol y haga clic con el botón secundario en el grupo en el que se creó el host autorizado.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="2ee5b-110">Haga clic en **Propiedades** y, a continuación, haga clic en **Propiedades del servidor front-end**.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="2ee5b-111">Haga clic en la pestaña **Autorización de host**.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="2ee5b-112">Seleccione un servidor y, a continuación, haga clic en \*\*Quitar \*\*.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="2ee5b-113">En **Propiedades**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2ee5b-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

