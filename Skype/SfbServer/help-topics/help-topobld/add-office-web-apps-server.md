---
title: Agregar servidor Office Web Apps
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'El Asistente para definir nuevo Office Web Apps Server define una nueva de Office Web Apps Server en su implementación. Proporcione la información siguiente:'
ms.openlocfilehash: 79f07ab88f62ba9b7e886b06b6d7c89143cd7380
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873322"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="35246-104">Agregar servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="35246-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="35246-105">El Asistente para **Definir nuevo Office Web Apps Server** define una nueva de Office Web Apps Server en su implementación.</span><span class="sxs-lookup"><span data-stu-id="35246-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="35246-106">Proporcione la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="35246-106">You fill in the following information:</span></span>

 <span data-ttu-id="35246-107">**FQDN del servidor de Office Web Apps**: escriba el nombre de dominio completo del servidor que se va a hospedar el servidor de Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="35246-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="35246-108">**Dirección URL de detección de Office Web Apps Server**: escriba el localizador de completa uniforme de recursos (URL) de Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="35246-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="35246-109">Es el comportamiento predeterminado de la **dirección URL de detección de Office Web Apps Server** crear la dirección URL en función del FQDN de Office Web Apps Server en el formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="35246-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="35246-110">En la mayoría de los casos no será necesario cambiar el formato predeterminado.</span><span class="sxs-lookup"><span data-stu-id="35246-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="35246-111">Es posible que necesite cambiar el formato predeterminado en caso de que el servidor de Office Web Apps y la dirección URL de detección de Office Web Apps Server deben ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="35246-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="35246-112">Por ejemplo, el servidor de aplicaciones Web de Office se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="35246-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="35246-113">**Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)**: seleccione la casilla de verificación si su Office Web Apps Server se coloca fuera de su firewall interno, como la red perimetral, de red externa o de otra zona de red no es la misma que la red interna.</span><span class="sxs-lookup"><span data-stu-id="35246-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="35246-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35246-114">See also</span></span>

[<span data-ttu-id="35246-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="35246-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
