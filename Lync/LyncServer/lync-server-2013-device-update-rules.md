---
title: 'Lync Server 2013: reglas de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1ec593c264a1630274e83e8a7de1d193b8e5cbf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="888dc-102">Reglas de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888dc-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="888dc-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="888dc-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="888dc-104">Periódicamente, Microsoft publica un nuevo conjunto de actualizaciones de firmware de dispositivo para Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="888dc-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="888dc-105">*Las reglas de actualización de dispositivos* asocian actualizaciones de firmware con dispositivos de hardware (teléfonos y otros dispositivos que ejecutan Lync Phone Edition).</span><span class="sxs-lookup"><span data-stu-id="888dc-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="888dc-106">Para obtener el último conjunto de reglas de actualización de dispositivos, vaya a la página ayuda y soporte técnico en el sitio web de Microsoft y busque "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="888dc-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="888dc-107">Descargue el paquete de actualización y extraiga los archivos en una carpeta en el equipo en el que se van a cargar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="888dc-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="888dc-108">Una vez extraídos los archivos, importe las reglas de actualización de dispositivos que se encuentran en el extraído. Archivo CAB (que tiene el nombre UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="888dc-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="888dc-109">A continuación, use el panel de control de Lync Server o los cmdlets de Windows PowerShell para ver y administrar estas reglas para los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="888dc-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="888dc-110">En los siguientes temas se explica cómo importar, ver y administrar las reglas de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="888dc-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="888dc-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="888dc-111">In This Section</span></span>

  - [<span data-ttu-id="888dc-112">Ver información sobre las reglas de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888dc-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="888dc-113">Importar reglas de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888dc-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="888dc-114">Aprobar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888dc-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="888dc-115">Quitar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888dc-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="888dc-116">Restablecer una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888dc-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="888dc-117">Restaurar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888dc-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

