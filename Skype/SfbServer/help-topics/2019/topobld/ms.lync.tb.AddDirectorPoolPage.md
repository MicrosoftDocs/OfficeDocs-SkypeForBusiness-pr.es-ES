---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que constará de dos o más directores en un grupo de servidores con equilibrio de carga o un grupo de servidores de un solo equipo. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o al FQDN del director único. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
ms.openlocfilehash: 910ed1cee56a9a7dab395496ec1ce02f91bc2a5f00f8cbb4d8032b4170263854
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338568"
---
# <a name="add-director-pool"></a>Agregar grupo de servidores director
 
Para **definir el FQDN** del  grupo de directores, seleccione un grupo de varios equipos que constará de dos o más directores en un grupo de servidores con equilibrio de carga o un grupo de servidores de un **solo equipo.** También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o al FQDN del director único. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores director, seleccione **Grupo de servidores de varios equipos**. Aunque un grupo de servidores se define como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y crear un FQDN de grupo para el único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a ejecutar el Generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores mediante el Asistente para la implementación de Skype Empresarial Server. También debe agregar el nuevo miembro del grupo a los equilibradores de carga adecuados para el grupo, para el equilibrio de carga del Sistema de nombres de dominio (DNS) o para equilibradores de carga de hardware. En muchos casos, tendrá ambos sistemas de equilibrio de carga en su lugar. Compruebe que el nuevo servidor miembro se agregue a ambos. 
  

