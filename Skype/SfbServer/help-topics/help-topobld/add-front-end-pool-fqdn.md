---
title: Agregar FQDN del grupo de servidores front-end
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
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique el nombre de dominio completo del grupo de servidores front-end que está creando. El nombre de dominio completo de un grupo de servidores no puede cambiarse una vez publicada la topología que contiene el grupo de servidores front-end. Para cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y agregar un nuevo grupo con el nuevo nombre de dominio completo.
ms.openlocfilehash: 99bf31760ce908952547ccfb3f150c136966e9f0
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218861"
---
# <a name="add-front-end-pool-fqdn"></a>Agregar FQDN del grupo de servidores front-end
 
Especifique el nombre de dominio completo del grupo de servidores front-end que está creando. El nombre de dominio completo de un grupo de servidores no puede cambiarse una vez publicada la topología que contiene el grupo de servidores front-end. Para cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y agregar un nuevo grupo con el nuevo nombre de dominio completo.
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores front-end, seleccione **Grupo de servidores de varios equipos**. Aunque se defina un grupo de servidores como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté preparado para agregar más equipos al grupo más adelante, debe volver a ejecutar el generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de servidores front-end mediante el Asistente para la implementación de Skype empresarial Server. Asimismo, debe agregar el nuevo miembro del grupo de servidores al correspondiente equilibrador de carga, equilibrio de carga del Sistema de nombres de dominio (DNS) o equilibradores de carga de hardware. En muchos casos, tendrá los dos sistemas de equilibrio de carga. Compruebe que el nuevo servidor miembro se agregue a ambos. 
  

