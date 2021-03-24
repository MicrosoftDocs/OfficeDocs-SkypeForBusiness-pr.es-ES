---
title: Agregar servidor Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'El Asistente para definir nuevo servidor de Office Web Apps define un nuevo servidor de Office Web Apps en la implementación. Proporcione la información siguiente:'
ms.openlocfilehash: 84ebc3b3ca7a413d81b4a36e62cc33a4f3fd91f0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095784"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="ab78a-104">Agregar servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="ab78a-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="ab78a-105">El **Asistente para definir nuevo servidor de Office Web Apps** define un nuevo servidor de Office Web Apps en la implementación.</span><span class="sxs-lookup"><span data-stu-id="ab78a-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="ab78a-106">Proporcione la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab78a-106">You fill in the following information:</span></span>

 <span data-ttu-id="ab78a-107">**FQDN de Office Web Apps Server:** escriba el nombre de dominio completo del servidor que hospedará Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="ab78a-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="ab78a-108">**Dirección URL de detección de Office Web Apps Server:** escriba el localizador de recursos uniforme completo (URL) de Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="ab78a-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="ab78a-109">El comportamiento predeterminado de la dirección URL de detección de **Office Web Apps Server** es crear la dirección URL basada en el FQDN de Office Web Apps Server en el formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="ab78a-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="ab78a-110">En la mayoría de los casos no será necesario cambiar el formato predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ab78a-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="ab78a-111">Es posible que deba cambiar el formato predeterminado en caso de que la dirección URL de detección de Office Web Apps Server y Office Web Apps Server sea diferente.</span><span class="sxs-lookup"><span data-stu-id="ab78a-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="ab78a-112">Por ejemplo, office web apps server se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="ab78a-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="ab78a-113">Office Web Apps Server se implementa en una red externa **(es decir, perimetral/Internet):** active la casilla si office web apps server se coloca fuera del firewall interno, como la red perimetral, la red externa u otra zona de red que no sea la misma que la red interna.</span><span class="sxs-lookup"><span data-stu-id="ab78a-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab78a-114">Ver también</span><span class="sxs-lookup"><span data-stu-id="ab78a-114">See also</span></span>

[<span data-ttu-id="ab78a-115">Componentes y topologías para conferencias</span><span class="sxs-lookup"><span data-stu-id="ab78a-115">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)