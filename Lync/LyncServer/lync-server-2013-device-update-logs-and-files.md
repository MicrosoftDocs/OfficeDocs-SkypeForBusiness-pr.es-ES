---
title: 'Lync Server 2013: archivos y registros de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170bafb3d00940995e8355c7775681c2af5fd078
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="9571b-102">Registros y archivos de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9571b-102">Device Update logs and files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9571b-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9571b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9571b-104">Los registros de actualización de dispositivos contienen información importante que puede usar para administrar y solucionar problemas del servicio Web de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9571b-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="9571b-105">Puede cambiar lo que se registra y quitar los registros y las actualizaciones de dispositivos que no desee o que ya no necesite.</span><span class="sxs-lookup"><span data-stu-id="9571b-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="9571b-106">En esta sección se describe cómo puede usar el panel de control de Lync Server o el shell de administración de Lync Server para modificar la configuración de registro, borrar el registro de actualizaciones de dispositivos o quitar archivos de registro del servidor.</span><span class="sxs-lookup"><span data-stu-id="9571b-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9571b-107">Para obtener más información sobre los archivos de registro de actualización de dispositivos, consulte <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">tipos y ubicaciones</A> de los archivos de registro en la biblioteca de TechNet de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9571b-107">For details about device update log files, see <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="9571b-108">(Tenga en cuenta que el servicio Web de actualización de dispositivos, como todos los componentes de Lync Phone Edition, funciona de la misma manera con Lync Server 2013 como lo hace con Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="9571b-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9571b-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9571b-109">In This Section</span></span>

  - [<span data-ttu-id="9571b-110">Modificar la configuración de los archivos de registro de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9571b-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="9571b-111">Eliminar archivos de registro de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9571b-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="9571b-112">Quitar los archivos de actualización de dispositivo no asociados con un dispositivo en quitar archivos de actualización de dispositivo no asociados con un dispositivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9571b-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

