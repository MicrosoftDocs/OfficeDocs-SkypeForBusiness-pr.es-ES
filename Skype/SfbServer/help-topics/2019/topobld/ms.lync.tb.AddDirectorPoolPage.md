---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que consistirá en dos o más directores en un grupo de carga equilibrada o en un solo grupo de equipos. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. Para un grupo de equipos de directores, esta es la entrada sistema de nombres de dominio (DNS) de la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga DNS.
ms.openlocfilehash: 491d50c733314e1811aac38c556a6d4683b6956b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796579"
---
# <a name="add-director-pool"></a>Agregar grupo de servidores director
 
Para **definir el FQDN del grupo de directores**, seleccione un **grupo de varios equipos** que consistirá en dos o más directores en un grupo de carga equilibrada o en un **solo grupo de equipos**. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. Para un grupo de equipos de directores, esta es la entrada sistema de nombres de dominio (DNS) de la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga DNS.
  
> [!TIP]
> Si piensa implementar un grupo de directores en el futuro, seleccione **varios grupos de equipos**. Aunque un grupo se define como dos o más equipos con equilibrio de carga, puede crear un único grupo de equipos y crear un FQDN de grupo para el mismo equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología de nuevo para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores mediante el Asistente para la implementación de Skype empresarial Server. También debe agregar el nuevo miembro del grupo a los equilibradores de carga adecuados para el grupo, el equilibrio de carga del sistema de nombres de dominio (DNS) o los equilibradores de carga del hardware. En muchos casos, dispondrá de ambos sistemas de equilibrio de carga. Asegúrese de agregar el nuevo servidor miembro a ambos. 
  

