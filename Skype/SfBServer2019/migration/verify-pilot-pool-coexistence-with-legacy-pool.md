---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Proceso para comprobar la coexistencia del grupo piloto con el grupo heredado.
ms.openlocfilehash: f9a3fa8a9716d880b8fa2381fd5cafe88509504c2c142ebd5da5c5ab43667cf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341126"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredados

 **En este artículo**
  
[Comprobar que Skype Empresarial Server servicios de 2019 se han iniciado](#sectionSection0)
  
[Abra el panel Skype Empresarial Server de control de 2019](#sectionSection1)
  
[No intente abrir la topología en el Generador de topologías heredado](#sectionSection2)
  
Después de implementar el grupo piloto, verifique la coexistencia de los dos grupos de servidores con las herramientas administrativas para ver la información del grupo. Para los grupos Skype Empresarial Server 2019 y los grupos heredados, debe usar las herramientas del Panel de control de Skype Empresarial Server 2019 y el Generador de topologías. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Comprobar que Skype Empresarial Server servicios de 2019 se han iniciado
<a name="sectionSection0"> </a>

1. Desde el Skype Empresarial Server front-end de 2019, vaya al applet Administrative Tools\Services.
    
2. Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:

    - Agente de servicio de registro centralizado
    - Uso compartido de aplicaciones
    - Servicio de prueba de audio
    - Conferencias de audio/vídeo
    - Estacionamiento de llamadas
    - Anuncio de conferencia
    - Operador de conferencia
    - Front-end
    - Conferencia de mensajería instantánea
    - Mediación
    - Replica Replicator Agent
    - Grupo de respuesta
    - Conferencia web
    - Puerta de enlace de traducción XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abra el panel Skype Empresarial Server de control de 2019
<a name="sectionSection1"> </a>

En el servidor front-end de la implementación de Skype Empresarial Server 2019, abra el Panel de control de Skype Empresarial Server 2019 y seleccione el grupo heredado. Repita el procedimiento para abrir el Skype Empresarial Server de 2019.
  
> [!IMPORTANT]
> En Skype Empresarial Server 2019, debe actualizar Silverlight a Silverlight versión 5 antes de usar el panel de control Skype Empresarial Server control. 
  
Esta topología ahora incluye roles de servidor heredados Skype Empresarial Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>No intente abrir la topología en el Generador de topologías heredado
<a name="sectionSection2"> </a>

La topología solo se puede ver mediante Skype Empresarial Server generador de topologías de 2019. El Skype Empresarial Server de topologías de 2019 debe usarse para crear grupos de servidores tanto para Skype Empresarial Server 2019 como para la instalación heredada.

  

