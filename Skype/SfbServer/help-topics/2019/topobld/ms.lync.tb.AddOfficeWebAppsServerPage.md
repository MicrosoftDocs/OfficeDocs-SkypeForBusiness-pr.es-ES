---
title: Agregar servidor Office Web Apps
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'El Asistente para definir nuevo Office Web Apps Server define una nueva de Office Web Apps Server en su implementación. Proporcione la información siguiente:'
ms.openlocfilehash: cab39bf2ff44704aab37593009c381b649378532
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21064045"
---
# <a name="add-office-web-apps-server"></a>Agregar servidor Office Web Apps
 
El Asistente para **Definir nuevo Office Web Apps Server** define una nueva de Office Web Apps Server en su implementación. Proporcione la información siguiente:
  
 **FQDN del servidor de Office Web Apps**: escriba el nombre de dominio completo del servidor que se va a hospedar el servidor de Office Web Apps
  
 **Dirección URL de detección de Office Web Apps Server**: escriba el localizador de completa uniforme de recursos (URL) de Office Web Apps Server
  
> [!TIP]
> Es el comportamiento predeterminado de la **dirección URL de detección de Office Web Apps Server** crear la dirección URL en función del FQDN de Office Web Apps Server en el formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . En la mayoría de los casos no será necesario cambiar el formato predeterminado. Es posible que necesite cambiar el formato predeterminado en caso de que el servidor de Office Web Apps y la dirección URL de detección de Office Web Apps Server deben ser diferentes. Por ejemplo, el servidor de aplicaciones Web de Office se coloca en la red perimetral y tendrá una dirección URL diferente en función de la ubicación.
  
 **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)**: seleccione la casilla de verificación si su Office Web Apps Server se coloca fuera de su firewall interno, como la red perimetral, de red externa o de otra zona de red no es la misma que la red interna.
  
## <a name="see-also"></a>Vea también

[Componentes y topologías de conferencia](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)