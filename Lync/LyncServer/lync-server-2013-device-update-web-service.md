---
title: 'Lync Server 2013: servicio Web de actualización de dispositivos'
description: 'Lync Server 2013: servicio Web de actualización de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45511d34ab99f295481472f2a3c14bf21da32ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565956"
---
# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="dfdc2-103">Servicio Web de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdc2-103">Device Update Web service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfdc2-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="dfdc2-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="dfdc2-105">Lync Server incluye el servicio Web de actualización de dispositivos, que se instala automáticamente como parte del rol de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="dfdc2-105">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="dfdc2-106">Este servicio le permite descargar actualizaciones de Microsoft, probarlas y, a continuación, implementarlas en teléfonos IP de su organización.</span><span class="sxs-lookup"><span data-stu-id="dfdc2-106">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="dfdc2-107">También puede utilizar el servicio web de actualización de dispositivos para revertir a versiones anteriores del software en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dfdc2-107">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="dfdc2-108">En esta sección se proporcionan detalles sobre cómo administrar el servicio Web de actualización de dispositivos y cómo se implementaron actualizaciones mediante registros de actualización de dispositivos, Rules (Lync Phone Edition usa *reglas* para asociar actualizaciones de versión de firmware con dispositivos de hardware) y opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="dfdc2-108">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="dfdc2-109">Para obtener más información sobre el proceso y las características del servicio Web de actualización de dispositivos, consulte [actualizar dispositivos](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) en la biblioteca de TechNet de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dfdc2-109">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="dfdc2-110">(Tenga en cuenta que el servicio Web de actualización de dispositivos, al igual que todos los componentes de Lync Phone Edition, funciona de la misma manera con Lync Server 2013 como lo hace con Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="dfdc2-110">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dfdc2-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dfdc2-111">In This Section</span></span>

  - [<span data-ttu-id="dfdc2-112">Archivos y registros de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdc2-112">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="dfdc2-113">Reglas de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdc2-113">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="dfdc2-114">Opciones de configuración de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdc2-114">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="dfdc2-115">Ver actualizaciones de software para dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdc2-115">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfdc2-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dfdc2-116">See Also</span></span>


<span data-ttu-id="dfdc2-117">[Herramientas y servicios para administrar y resolver problemas de los dispositivos](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="dfdc2-117">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

