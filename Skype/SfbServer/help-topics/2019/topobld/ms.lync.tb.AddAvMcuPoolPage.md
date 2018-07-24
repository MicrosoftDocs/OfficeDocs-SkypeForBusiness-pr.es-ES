---
title: Agregar o grupo de servidores MCU V
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Todos los servidores Enterprise Edition Front-End de un sitio central que no tienen un combinados A / servicio de conferencia A/v puede usar el mismo A independiente o grupo de servidores de conferencia A/v. Para cada A / grupo de servidores de conferencia A/v, debe especificar un nombre de dominio completo (FQDN) para el grupo de servidores y si va a tener solo un único / servidor de conferencia A/v o múltiple, con equilibrio de carga A / servidores de conferencia A/v.
ms.openlocfilehash: c58d2e405d642209f91e38d98d5c6cbef924cd2e
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21060091"
---
# <a name="add-av-mcu-pool"></a>Agregar o grupo de servidores MCU V
 
Todos los servidores Enterprise Edition Front-End de un sitio central que no tienen un combinados A / servicio de conferencia A/v puede usar el mismo A independiente o grupo de servidores de conferencia A/v. Para cada A / grupo de servidores de conferencia A/v, debe especificar un nombre de dominio completo (FQDN) para el grupo de servidores y si va a tener solo un único / servidor de conferencia A/v o múltiple, con equilibrio de carga A / servidores de conferencia A/v.
  
> [!IMPORTANT]
> No se puede convertir un grupo de servidores de un único servidor a un grupo de varios servidores. Si más adelante decide que la organización necesita un grupo de servidores de varios servidores, debe eliminar el grupo de servidores de un solo servidor y, a continuación, agregue el grupo de servidores de varios servidores. 
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores de conferencia A/v en el futuro, seleccione **el grupo de servidores de varios equipos**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe generador de nuevo para definir el nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar el nuevo grupo de conferencia A/v miembro a través de la Skype para el Asistente para la implementación de servidor de Business. A los grupos de servidores de servidor de conferencia A/v son únicos en que no necesitan equilibradores de carga para crear un grupo de servidores. A los grupos de servidores de conferencia A/v equilibrar la carga internamente y no es necesario hardware adicional. 
  

