---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que se componen de dos o más directores en un grupo de servidores con equilibrio de carga, o un grupo de servidores de un solo equipo. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al FQDN del Director único o el grupo de servidores de Director. Para un grupo de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
ms.openlocfilehash: 8dfccfdac8ee2651c935b626f2deb0e688488b54
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879275"
---
# <a name="add-director-pool"></a>Agregar grupo de servidores director
 
Para **definir el FQDN del grupo de directores**, seleccione un **grupo de varios equipos** que se componen de dos o más directores en un grupo de servidores con equilibrio de carga, o bien un **grupo de servidores de un solo equipo**. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al FQDN del Director único o el grupo de servidores de Director. Para un grupo de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
  
> [!TIP]
> Si tiene previsto implementar un grupo de directores en el futuro, seleccione **el grupo de servidores de varios equipos**. Aunque un grupo de servidores se define como dos o más equipos que están con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y cree un FQDN del grupo de servidores para el equipo único. Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe ejecutar el generador de topología de nuevo para definir al nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar al nuevo integrante de grupo de servidores de Director a través de la Skype para Asistente para implementación de Business Server. También debe agregar al nuevo integrante de grupo de servidores a los equilibradores de carga adecuada para el grupo de servidores, sistema de nombres de dominio (DNS) equilibrio de carga, o los equilibradores de carga de hardware. En muchos casos, tendrá los sistemas en lugar de equilibrio de carga. Asegúrese de que haya que agregar el nuevo servidor miembro a ambos. 
  

