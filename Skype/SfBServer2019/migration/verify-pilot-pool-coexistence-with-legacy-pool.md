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
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751662"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredados

 **En este artículo**
  
[Comprobar que se han iniciado los servicios de Skype Empresarial Server 2019](#sectionSection0)
  
[Abrir el Panel de control de Skype Empresarial Server 2019](#sectionSection1)
  
[No intente abrir la topología en el Generador de topologías heredado](#sectionSection2)
  
Después de implementar el grupo piloto, verifique la coexistencia de los dos grupos de servidores con las herramientas administrativas para ver la información del grupo. Para los grupos de Skype Empresarial Server 2019 y los grupos heredados, debe usar las herramientas del Panel de control de Skype Empresarial Server 2019 y del Generador de topologías. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Comprobar que se han iniciado los servicios de Skype Empresarial Server 2019
<a name="sectionSection0"> </a>

1. Desde el servidor front-end de Skype Empresarial Server 2019, vaya al applet Herramientas administrativas\Servicios.
    
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

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abrir el Panel de control de Skype Empresarial Server 2019
<a name="sectionSection1"> </a>

En el servidor front-end de su implementación de Skype Empresarial Server 2019, abra el Panel de control de Skype Empresarial Server 2019 y seleccione el grupo heredado. Repita el procedimiento para abrir el grupo de Skype Empresarial Server 2019.
  
> [!IMPORTANT]
> En Skype Empresarial Server 2019, debe actualizar Silverlight a la versión 5 de Silverlight antes de usar el Panel de control de Skype Empresarial Server. 
  
Esta topología ahora incluye roles de servidor heredados y de Skype Empresarial Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>No intente abrir la topología en el Generador de topologías heredado
<a name="sectionSection2"> </a>

La topología solo se puede ver con el Generador de topologías de Skype Empresarial Server 2019. El Generador de topologías de Skype Empresarial Server 2019 debe usarse para crear grupos tanto para Skype Empresarial Server 2019 como para la instalación heredada.

  

