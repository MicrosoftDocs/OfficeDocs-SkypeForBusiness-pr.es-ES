---
title: Comprobar la coexistencia de grupo piloto con grupo heredado
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Proceso para comprobar la coexistencia del grupo piloto con grupo heredado.
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028694"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia de grupo piloto con grupo heredado

 **En este artículo**
  
[Compruebe que se han iniciado Skype para servicios de Business Server 2019](#sectionSection0)
  
[Abra el Skype para el Panel de Control de Business Server 2019](#sectionSection1)
  
[No intente abrir la topología en el generador de topología heredada](#sectionSection2)
  
Después de implementar el grupo piloto, debe comprobar la coexistencia de los dos grupos de servidores mediante las herramientas administrativas para ver la información de grupo de servidores. Para Skype para grupos de negocio Server 2019 y grupos de servidores heredados, debe usar el Skype para herramientas de Panel de Control de Business Server 2019 y generador de topología. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Compruebe que se han iniciado Skype para servicios de Business Server 2019
<a name="sectionSection0"> </a>

1. Desde Skype para profesionales de 2019 Front-End Server, navegue hasta el applet herramientas Administrativas\servicios.
    
2. Compruebe que los siguientes servicios se están ejecutando en el servidor Front-End:

    - Agente del servicio de registro centralizado
    - Uso compartido de aplicaciones
    - Servicio de prueba de audio
    - Conferencia de audio y vídeo
    - Estacionamiento de llamadas
    - Anuncio de conferencia
    - Operador de conferencia
    - Front-end
    - Conferencia de mensajería instantánea
    - Servidores
    - Agente de réplica del replicador de usuarios
    - Grupo de respuesta
    - Conferencia web
    - Traducción de puerta de enlace XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abra el Skype para el Panel de Control de Business Server 2019
<a name="sectionSection1"> </a>

Desde el servidor Front-End en su Skype para la implementación empresarial Server 2019, abra el Skype para el Panel de Control de Business Server 2019 y seleccione el grupo heredado. Repita el procedimiento para abrir el Skype para el grupo de servidores de Business Server 2019.
  
> [!IMPORTANT]
> En Skype para Business Server 2019, debe actualizar Silverlight a Silverlight, versión 5 antes de usar el Skype para el Panel de Control de servidor empresarial. 
  
Esta topología incluye ahora heredado y Skype para funciones de servidor de Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>No intente abrir la topología en el generador de topología heredada
<a name="sectionSection2"> </a>

Si se intenta abrir la topología con el generador de topología heredada, encontrará el error que aparece a continuación. Sólo se puede ver la topología con Skype para Business Server 2019 Topology Builder. Debe usarse el Skype para Business Server 2019 Topology Builder para crear grupos de servidores de Skype para Business Server 2019 y la instalación heredada.

  

