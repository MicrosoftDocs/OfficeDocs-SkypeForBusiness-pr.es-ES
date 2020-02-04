---
title: Agregar servidor Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'El asistente definir nuevo Office Web Apps Server define un nuevo servidor de Office Web Apps en su implementación. Proporcione la información siguiente:'
ms.openlocfilehash: 2af737d2579fb4d89c6670e016ff89a8d24f3743
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685093"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="c1aed-104">Agregar servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="c1aed-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="c1aed-105">El asistente **definir nuevo Office Web Apps Server** define un nuevo servidor de Office Web Apps en su implementación.</span><span class="sxs-lookup"><span data-stu-id="c1aed-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="c1aed-106">Proporcione la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1aed-106">You fill in the following information:</span></span>

 <span data-ttu-id="c1aed-107">**FQDN de Office Web Apps Server**: escriba el nombre de dominio completo del servidor que hospedará el servidor de Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="c1aed-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="c1aed-108">**URL de detección de Office Web Apps Server**: escriba el localizador de recursos uniforme (URL) completo del servidor de Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="c1aed-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="c1aed-109">El comportamiento predeterminado de la **dirección URL de detección de Office Web Apps Server** es crear la dirección URL en función del FQDN de Office Web Apps Server con el `https://<FQDN of the Office Web Apps Server/hosting/discovery` formato:.</span><span class="sxs-lookup"><span data-stu-id="c1aed-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="c1aed-110">En la mayoría de los casos no será necesario cambiar el formato predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1aed-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="c1aed-111">Es posible que tenga que cambiar el formato predeterminado en caso de que el servidor de Office Web Apps y la dirección URL de detección de Office Web Apps Server deban ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="c1aed-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="c1aed-112">Por ejemplo, su servidor de Office Web Apps se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="c1aed-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="c1aed-113">**Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)**: Active la casilla si su servidor de Office Web Apps se coloca fuera de su firewall interno, como la red perimetral, la red externa u otra zona de red que no sea la misma que su red interna.</span><span class="sxs-lookup"><span data-stu-id="c1aed-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1aed-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1aed-114">See also</span></span>

[<span data-ttu-id="c1aed-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="c1aed-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
