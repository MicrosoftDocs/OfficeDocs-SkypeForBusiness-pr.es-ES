---
title: Agregar FQDN del grupo de servidores front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que va a crear. No se puede cambiar el FQDN de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y, a continuación, agregar un nuevo grupo con el FQDN nuevo.
ms.openlocfilehash: f11d45c881053298374f92f692b623f5cee2e183
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888999"
---
# <a name="add-front-end-pool-fqdn"></a>Agregar FQDN del grupo de servidores front-end
 
Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que va a crear. No se puede cambiar el FQDN de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y, a continuación, agregar un nuevo grupo con el FQDN nuevo.
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores Front-End en el futuro, seleccione **el grupo de servidores de varios equipos**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe ejecutar el generador de topología de nuevo para definir al nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar el nuevo integrante de grupo de servidores Front-End a través de la Skype para el Asistente para la implementación de servidor de negocio. También debe agregar al nuevo integrante de grupo de servidores a los equilibradores de carga adecuada para el grupo de servidores, el equilibrio de carga del sistema de nombres de dominio (DNS) o equilibradores de carga de hardware. En muchos casos, tendría los sistemas en lugar de equilibrio de carga. Asegúrese de que haya que agregar el nuevo servidor miembro a ambos. 
  

