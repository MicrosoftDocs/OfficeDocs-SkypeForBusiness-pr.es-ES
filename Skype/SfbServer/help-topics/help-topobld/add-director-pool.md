---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que consistirá en dos o más directores en un grupo de carga equilibrada o en un solo grupo de equipos. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. Para un grupo de equipos de directores, esta es la entrada sistema de nombres de dominio (DNS) de la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga DNS.
ms.openlocfilehash: 163de8a6091e74238c4a4127ae39f7cd500cdb84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304789"
---
# <a name="add-director-pool"></a>Agregar grupo de servidores director
 
Para **definir el FQDN del grupo de directores**, seleccione un **grupo de varios equipos** que consistirá en dos o más directores en un grupo de carga equilibrada o en un **solo grupo de equipos**. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. Para un grupo de equipos de directores, esta es la entrada sistema de nombres de dominio (DNS) de la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga DNS.
  
> [!TIP]
> Si piensa implementar un grupo de directores en el futuro, seleccione **varios grupos de equipos**. Aunque un grupo se define como dos o más equipos con equilibrio de carga, puede crear un único grupo de equipos y crear un FQDN de grupo para el mismo equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología de nuevo para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores mediante el Asistente para la implementación de Skype empresarial Server. También debe agregar el nuevo miembro del grupo a los equilibradores de carga adecuados para el grupo, el equilibrio de carga del sistema de nombres de dominio (DNS) o los equilibradores de carga del hardware. En muchos casos, dispondrá de ambos sistemas de equilibrio de carga. Asegúrese de agregar el nuevo servidor miembro a ambos. 
  

