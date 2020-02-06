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
- NOCSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'El asistente definir nuevo Office Web Apps Server define un nuevo servidor de Office Web Apps en su implementación. Proporcione la información siguiente:'
ms.openlocfilehash: 9f0d9680e57dd55b0a4370364aff23c7f37f57a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820722"
---
# <a name="add-office-web-apps-server"></a>Agregar servidor Office Web Apps

El asistente **definir nuevo Office Web Apps Server** define un nuevo servidor de Office Web Apps en su implementación. Proporcione la información siguiente:

 **FQDN de Office Web Apps Server**: escriba el nombre de dominio completo del servidor que hospedará el servidor de Office Web Apps.

 **URL de detección de Office Web Apps Server**: escriba el localizador de recursos uniforme (URL) completo del servidor de Office Web Apps.

> [!TIP]
> El comportamiento predeterminado de la **dirección URL de detección de Office Web Apps Server** es crear la dirección URL en función del FQDN de Office Web Apps Server con el `https://<FQDN of the Office Web Apps Server/hosting/discovery` formato:. En la mayoría de los casos no será necesario cambiar el formato predeterminado. Es posible que tenga que cambiar el formato predeterminado en caso de que el servidor de Office Web Apps y la dirección URL de detección de Office Web Apps Server deban ser diferentes. Por ejemplo, su servidor de Office Web Apps se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.

 **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)**: Active la casilla si su servidor de Office Web Apps se coloca fuera de su firewall interno, como la red perimetral, la red externa u otra zona de red que no sea la misma que su red interna.

## <a name="see-also"></a>Vea también

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
