---
title: Agregar el FQDN del grupo de servidores de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que va a crear. No se puede cambiar el FQDN de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y, a continuación, agregar un nuevo grupo con el FQDN nuevo.
ms.openlocfilehash: 739a794b1b3fd8e88ae074b5c03f4c0e51fb844f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20981300"
---
# <a name="add-front-end-pool-fqdn"></a>Agregar el FQDN del grupo de servidores de Front-End
 
Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que va a crear. No se puede cambiar el FQDN de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y, a continuación, agregar un nuevo grupo con el FQDN nuevo.
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores Front-End en el futuro, seleccione **el grupo de servidores de varios equipos**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe ejecutar el generador de topología de nuevo para definir al nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar el nuevo integrante de grupo de servidores Front-End a través de la Skype para el Asistente para la implementación de servidor de negocio. También debe agregar al nuevo integrante de grupo de servidores a los equilibradores de carga adecuada para el grupo de servidores, el equilibrio de carga del sistema de nombres de dominio (DNS) o equilibradores de carga de hardware. En muchos casos, tendría los sistemas en lugar de equilibrio de carga. Asegúrese de que haya que agregar el nuevo servidor miembro a ambos. 
  

