---
title: Agregar servidor Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'El Asistente para definir nuevo servidor de Office Web Apps define un nuevo servidor de Office Web Apps en la implementación. Proporcione la información siguiente:'
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828600"
---
# <a name="add-office-web-apps-server"></a>Agregar servidor Office Web Apps

El **Asistente para definir nuevo servidor de Office Web Apps define** un nuevo servidor de Office Web Apps en la implementación. Proporcione la información siguiente:

 **FQDN de Office Web Apps Server:** escriba el nombre de dominio completo del servidor que hospedará Office Web Apps Server

 **Dirección URL de detección de Office Web Apps Server:** escriba el localizador uniforme de recursos (URL) completo de Office Web Apps Server

> [!TIP]
> El comportamiento predeterminado de la dirección URL de detección de **Office Web Apps Server** es crear la dirección URL basada en el FQDN de Office Web Apps Server en el formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . En la mayoría de los casos no será necesario cambiar el formato predeterminado. Es posible que deba cambiar el formato predeterminado en caso de que office Web Apps Server y la dirección URL de detección de Office Web Apps Server sean diferentes. Por ejemplo, office Web Apps Server se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.

 Office Web Apps Server se implementa en una red externa **(es decir, perimetral/Internet):** active la casilla si office Web Apps Server se coloca fuera del firewall interno, como la red perimetral, la red externa u otra zona de red que no sea la misma que la red interna.

## <a name="see-also"></a>Vea también

[Componentes y topologías para conferencias](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
