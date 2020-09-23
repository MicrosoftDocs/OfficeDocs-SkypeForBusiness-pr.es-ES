---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que constará de dos o más directores en un grupo de carga equilibrada o en un grupo de servidores de un solo equipo. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219491"
---
# <a name="add-director-pool"></a>Agregar grupo de servidores director
 
Para **definir el FQDN del grupo de directores**, seleccione un **grupo de varios equipos** que constará de dos o más directores en un grupo de carga equilibrada o en un grupo de servidores de un **solo equipo**. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores director, seleccione **Grupo de servidores de varios equipos**. Aunque un grupo se define como dos o más equipos con equilibrio de carga, puede crear un grupo de un solo equipo y crear un FQDN de grupo de servidores para el único equipo. Cuando esté preparado para agregar más equipos al grupo más adelante, debe volver a ejecutar el generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores mediante el Asistente para la implementación de Skype empresarial Server. También debe agregar el nuevo miembro del grupo de servidores a los equilibradores de carga apropiados para el grupo de servidores, para el equilibrio de carga del sistema de nombres de dominio (DNS) o para equilibradores de carga de hardware. En muchos casos, tendrá ambos sistemas de equilibrio de carga en su ubicación. Compruebe que el nuevo servidor miembro se agregue a ambos. 
  

