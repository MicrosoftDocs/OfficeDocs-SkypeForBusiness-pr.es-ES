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
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'El asistente definir nuevo servidor de Office Web Apps define un nuevo servidor de Office Web Apps en su implementación. Proporcione la información siguiente:'
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218731"
---
# <a name="add-office-web-apps-server"></a>Agregar servidor Office Web Apps

El asistente **definir nuevo servidor de Office Web Apps** define un nuevo servidor de Office Web Apps en su implementación. Proporcione la información siguiente:

 **FQDN del servidor de Office Web Apps**: escriba el nombre de dominio completo del servidor que va a hospedar el servidor de Office Web Apps

 **Dirección URL de detección del servidor de Office Web Apps**: escriba el localizador uniforme de recursos (URL) completo del servidor de Office Web Apps

> [!TIP]
> El comportamiento predeterminado de la **dirección URL de detección del servidor de Office Web Apps** es crear la dirección URL basada en el FQDN del servidor de Office Web Apps en el formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . En la mayoría de los casos no será necesario cambiar el formato predeterminado. Es posible que deba cambiar el formato predeterminado en caso de que el servidor de Office Web Apps y la dirección URL de detección de Office Web Apps Server deban ser diferentes. Por ejemplo, el servidor de Office Web Apps se coloca en la red perimetral y tendrá una dirección URL diferente según la ubicación.

 **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)**: Active la casilla si su servidor de Office Web Apps se coloca fuera del firewall interno, como la red perimetral, la red externa u otra zona de red que no sea la misma que la red interna.

## <a name="see-also"></a>Vea también

[Componentes y topologías para conferencias](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
