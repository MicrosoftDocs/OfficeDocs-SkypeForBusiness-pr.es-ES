---
title: Agregar servidor Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'El asistente definir nuevo Office Web Apps Server define un nuevo servidor de Office Web Apps en su implementación. Proporcione la información siguiente:'
ms.openlocfilehash: f5cf9c686ec7d42db6db15021e28493507f954b5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306167"
---
# <a name="add-office-web-apps-server"></a>Agregar servidor Office Web Apps

El asistente **definir nuevo Office Web Apps Server** define un nuevo servidor de Office Web Apps en su implementación. Proporcione la información siguiente:

 **FQDN de Office Web Apps Server**: escriba el nombre de dominio completo del servidor que hospedará el servidor de Office Web Apps.

 **URL de detección de Office Web Apps Server**: escriba el localizador de recursos uniforme (URL) completo del servidor de Office Web Apps.

> [!TIP]
> El comportamiento predeterminado de la **dirección URL de detección de Office Web Apps Server** es crear la dirección URL en función del FQDN de Office Web Apps Server con el `https://<FQDN of the Office Web Apps Server/hosting/discovery` formato:. En la mayoría de los casos no será necesario cambiar el formato predeterminado. Es posible que tenga que cambiar el formato predeterminado en caso de que el servidor de Office Web Apps y la dirección URL de detección de Office Web Apps Server deban ser diferentes. Por ejemplo, su servidor de Office Web Apps se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.

 **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)**: Active la casilla si su servidor de Office Web Apps se coloca fuera de su firewall interno, como la red perimetral, la red externa u otra zona de red. eso no es lo mismo que su red interna.

## <a name="see-also"></a>Vea también

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
