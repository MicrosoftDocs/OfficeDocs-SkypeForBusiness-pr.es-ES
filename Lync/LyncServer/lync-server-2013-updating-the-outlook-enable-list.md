---
title: 'Lync Server 2013: actualización de la lista de habilitación de Outlook'
description: 'Lync Server 2013: actualización de la lista de habilitación de Outlook.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96edc327fa1b63d5da95eb6ea36a2296659910d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546236"
---
# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="f632b-103">Actualizar la lista de habilitación de Outlook en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f632b-103">Updating the Outlook enable list in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f632b-104">_**Última modificación del tema:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="f632b-104">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="f632b-105">Puede asegurarse de que el complemento de conferencia en línea para Microsoft Lync 2013 siempre sigue habilitado para los usuarios mediante la creación de una directiva que lo incluya en la lista de administración de complementos de Outlook.</span><span class="sxs-lookup"><span data-stu-id="f632b-105">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="f632b-106">Esta directiva forma parte de los archivos de plantilla administrativa de Office de la Consola de administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="f632b-106">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="f632b-107">Crea una clave del registro en HKCU \\ software \\ Policies \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ Resiliency \\ AddinList.</span><span class="sxs-lookup"><span data-stu-id="f632b-107">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="f632b-108">Puede Agregar un valor para la ucaddin.dll a esta clave y configurar el valor de ucaddin.dll de modo que esté siempre habilitado y para que los usuarios no puedan deshabilitarlo manualmente</span><span class="sxs-lookup"><span data-stu-id="f632b-108">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="f632b-109">Para agregar ucaddin.dll a la lista de complementos de Outlook</span><span class="sxs-lookup"><span data-stu-id="f632b-109">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="f632b-110">En la clave del registro AddinList, que se encuentra en la página \\ directivas de software HKCU \\ \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ Resiliency \\ AddinList, agregue el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="f632b-110">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="f632b-111">Tipo de registro = REG \_ SZ</span><span class="sxs-lookup"><span data-stu-id="f632b-111">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="f632b-112">Nombre = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="f632b-112">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="f632b-113">Valor = 1 (significa que el complemento siempre está habilitado y que el usuario final no puede administrarlo)</span><span class="sxs-lookup"><span data-stu-id="f632b-113">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

