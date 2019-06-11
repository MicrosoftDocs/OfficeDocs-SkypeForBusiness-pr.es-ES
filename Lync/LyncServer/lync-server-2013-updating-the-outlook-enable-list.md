---
title: 'Lync Server 2013: actualización de la lista de habilitación de Outlook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c7ee75e70b52a4edd01230fe10aeb46f6e6e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="301c4-102">Actualización de la lista de habilitación de Outlook en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301c4-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="301c4-103">_**Última modificación del tema:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="301c4-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="301c4-104">Puede asegurarse de que el complemento de reuniones en línea para Microsoft Lync 2013 permanezca siempre habilitado para los usuarios mediante la creación de una directiva que lo incluya en la lista de administración de complementos para Outlook.</span><span class="sxs-lookup"><span data-stu-id="301c4-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="301c4-105">La Directiva de lista de administración de complementos se incluye en los archivos de plantillas administrativas de Office para la consola de administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="301c4-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="301c4-106">Crea una clave del registro en HKCU\\software\\\\Policies\\Microsoft\\Office\\15,0\\Outlook15 Resiliency\\AddinList.</span><span class="sxs-lookup"><span data-stu-id="301c4-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="301c4-107">Puede Agregar un valor para ucaddin. dll a esta clave y configurar el valor de ucaddin. dll para que esté siempre habilitado y para que los usuarios no puedan deshabilitarlo manualmente</span><span class="sxs-lookup"><span data-stu-id="301c4-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="301c4-108">Para agregar ucaddin. dll a la lista de complementos de Outlook</span><span class="sxs-lookup"><span data-stu-id="301c4-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="301c4-109">Para la clave del registro AddinList, que se\\encuentra\\en\\la\\sección\\directivas\\de\\software HKCU\\Microsoft Office 15,0 Outlook15 Resiliency AddinList, agregue el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="301c4-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="301c4-110">Tipo de registro =\_reg SZ</span><span class="sxs-lookup"><span data-stu-id="301c4-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="301c4-111">Name = ucaddin. dll</span><span class="sxs-lookup"><span data-stu-id="301c4-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="301c4-112">Valor = 1 (especifica que el complemento está siempre habilitado y que el usuario final no puede administrarlo)</span><span class="sxs-lookup"><span data-stu-id="301c4-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

