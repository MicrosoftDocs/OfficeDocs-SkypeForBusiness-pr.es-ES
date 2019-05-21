---
title: Agregar FQDN del grupo de servidores front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique el nombre de dominio completo (FQDN) del grupo de servidores front-end que está creando. No puede cambiar el FQDN de un grupo después de publicar la topología que contiene el grupo de servidores front-end. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo y, a continuación, agregar un nuevo grupo con el nuevo FQDN.
ms.openlocfilehash: 058e1cc6a1e510ba57bb28a694a9ddc7e9759f90
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275363"
---
# <a name="add-front-end-pool-fqdn"></a>Agregar FQDN del grupo de servidores front-end
 
Especifique el nombre de dominio completo (FQDN) del grupo de servidores front-end que está creando. No puede cambiar el FQDN de un grupo después de publicar la topología que contiene el grupo de servidores front-end. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo y, a continuación, agregar un nuevo grupo con el nuevo FQDN.
  
> [!TIP]
> Si piensa implementar un grupo front-end en el futuro, seleccione **varios grupos de equipos**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología de nuevo para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de servidores front-end con el Asistente para la implementación de Skype empresarial Server. También debe agregar el nuevo miembro del grupo a los equilibradores de carga adecuados para el grupo, el equilibrio de carga del sistema de nombres de dominio (DNS) o los equilibradores de carga de hardware. En muchos casos, tendríamos ambos sistemas de equilibrio de carga. Asegúrese de agregar el nuevo servidor miembro a ambos. 
  

