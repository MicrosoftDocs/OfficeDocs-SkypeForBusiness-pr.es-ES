---
title: Agregar servidor Office Web Apps
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'El Asistente para definir Office Web Apps Server define un nuevo Office Web Apps Server en la implementación. Proporcione la información siguiente:'
ms.openlocfilehash: d8f86890face6ae6a948a5006b101bc8585f16a4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766918"
---
# <a name="add-office-web-apps-server"></a>Agregar servidor Office Web Apps

El **Asistente para definir Office Web Apps Server** define un nuevo Office Web Apps Server en la implementación. Proporcione la información siguiente:

 **Office FQDN de Web Apps Server:** escriba el nombre de dominio completo del servidor que hospedará el servidor Office Web Apps Server

 **Office URL de detección de Web Apps Server:** escriba el localizador de recursos uniforme completo (URL) del servidor Office Web Apps Server

> [!TIP]
> El comportamiento predeterminado de la **dirección URL de detección** de Office Web Apps Server es crear la dirección URL basada en el FQDN del servidor Office Web Apps server con el formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . En la mayoría de los casos no será necesario cambiar el formato predeterminado. Es posible que deba cambiar el formato predeterminado en caso de que Office Web Apps Server y la dirección URL de detección Office Web Apps Server sean diferentes. Por ejemplo, el Office Web Apps Server se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.

 Office Web Apps Server se implementa en una red externa **(es decir, perimetral/Internet):** active la casilla si el servidor de aplicaciones web de Office se coloca fuera del firewall interno, como la red perimetral, la red externa u otra zona de red que no sea la misma que la red interna.

## <a name="see-also"></a>Consulte también

[Componentes y topologías para conferencias](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)