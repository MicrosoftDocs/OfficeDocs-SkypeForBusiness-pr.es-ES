---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Proceso para comprobar la coexistencia de un grupo piloto con grupo heredado.
ms.openlocfilehash: e71160a2a20d4a80979e3c3c4875c19db181f2da
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243753"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado

 **En este artículo**
  
[Comprobar que los servicios de Skype empresarial Server 2019 se han iniciado](#sectionSection0)
  
[Abrir el panel de control de Skype empresarial Server 2019](#sectionSection1)
  
[No intente abrir la topología en el generador de topología heredado](#sectionSection2)
  
Después de implementar el grupo piloto, debe comprobar la coexistencia de las dos agrupaciones mediante las herramientas administrativas para ver la información del grupo. Para los grupos de 2019 y los grupos heredados de Skype empresarial Server, debe usar las herramientas del panel de control y del generador de topologías de Skype empresarial Server 2019. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Comprobar que los servicios de Skype empresarial Server 2019 se han iniciado
<a name="sectionSection0"> </a>

1. Desde el servidor front-end de Skype empresarial Server 2019, navegue hasta el applet Tools\Services administrativo.
    
2. Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:

    - Agente del servicio de registro centralizado
    - Uso compartido de aplicaciones
    - Servicio de prueba de audio
    - Audioconferencias y videoconferencias
    - Estacionamiento de llamadas
    - Anuncio de conferencia
    - Operador de conferencias
    - Front-end
    - Conferencias de mensajería instantánea
    - Servidores
    - Agente duplicador de réplicas
    - Grupo de respuesta
    - Conferencia web
    - Puerta de enlace de traducción de XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abrir el panel de control de Skype empresarial Server 2019
<a name="sectionSection1"> </a>

Desde el servidor front-end de su implementación de Skype empresarial Server 2019, abra el panel de control de Skype empresarial Server 2019 y seleccione el grupo heredado. Repita el procedimiento para abrir el grupo de servidores de Skype empresarial 2019.
  
> [!IMPORTANT]
> En Skype empresarial Server 2019, debe actualizar Silverlight a la versión 5 antes de usar el panel de control de Skype empresarial Server. 
  
Ahora, esta topología incluye roles de servidor heredados de Skype empresarial Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>No intente abrir la topología en el generador de topología heredado
<a name="sectionSection2"> </a>

La topología solo se puede ver con el generador de topología de Skype empresarial Server 2019. El generador de topología de Skype empresarial Server 2019 debe usarse para crear grupos de servidores para Skype empresarial Server 2019 y la instalación heredada.

  

