---
title: Agregar servidor Office Web Apps
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
description: 'El Asistente para definir servidor de Office Web Apps define un nuevo servidor de aplicaciones Web de Office en su implementación. Proporcione la información siguiente:'
ms.openlocfilehash: df8f2ba98215a597e9532e636b022edf9cb1ec19
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-office-web-apps-server"></a>Agregar servidor Office Web Apps
 
El Asistente para **Definir servidor de Office Web Apps** define un nuevo servidor de aplicaciones Web de Office en su implementación. Proporcione la información siguiente:
  
 **FQDN de servidor de Office Web Apps**: escriba el nombre de dominio completo del servidor que albergará el servidor de Office Web Apps
  
 **Dirección URL de servidor de Office Web Apps detección**: escriba el localizador de recursos (URL) del servidor Office Web Apps
  
> [!TIP]
> Es el comportamiento predeterminado de la **dirección URL de descubrimiento del servidor de Office Web Apps** crear la dirección URL basándose en el FQDN del servidor de Office Web Apps en el formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . En la mayoría de los casos no será necesario cambiar el formato predeterminado. Puede que necesite cambiar el formato predeterminado en caso de que el servidor de Office Web Apps y la dirección URL de servidor de Office Web Apps descubrimiento deben ser diferentes. Por ejemplo, el servidor de Office Web Apps se coloca en la red perimetral y tendrá una dirección URL diferente según la ubicación.
  
 **Office Web Apps Server se implementa en una red externa (es decir, perimetral e Internet)**: seleccione la casilla de verificación si el servidor de Office Web Apps se coloca fuera de su firewall interno, como la red de perímetro, red externa u otra zona de red no es la misma que la red interna.
  
## <a name="see-also"></a>Vea también

#### 

[Componentes y topologías para conferencias](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)

