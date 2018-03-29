---
title: Agregar grupo de directores
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir el FQDN del grupo de Director, seleccione un grupo de equipo múltiple que constará de dos o más directores en un grupo de servidores con equilibrio de carga, o un grupo de equipo único. También debe escribir el nombre de dominio completo (FQDN) que se utilizará para conectar con el grupo de directores o FQDN del Director único. En el conjunto de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para equilibrar la carga DNS.
ms.openlocfilehash: d71219f6e9c51d69bee8d2457cc30c19f4fa6c89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-pool"></a>Agregar grupo de directores
 
Para **definir el FQDN del grupo de Director**, seleccione un **grupo de equipo múltiple** que constará de dos o más directores en un grupo de servidores con equilibrio de carga, o un **grupo de equipo único**. También debe escribir el nombre de dominio completo (FQDN) que se utilizará para conectar con el grupo de directores o FQDN del Director único. En el conjunto de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para equilibrar la carga DNS.
  
> [!TIP]
> Si va a implementar un grupo de directores en el futuro, seleccione **grupo de equipo múltiple**. Aunque un grupo se define como dos o más equipos que son el equilibrio de carga, puede crear un grupo de equipo único y crear un FQDN del grupo para el equipo único. Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología para definir al nuevo miembro del grupo, publicar la nueva topología y, a continuación, configure al nuevo miembro del grupo de Director a través del Skype para el Asistente para implementación de servidor de Business. También debe agregar al nuevo miembro de grupo a los equilibradores de carga adecuada para el grupo de sistema de nombres de dominio (DNS) equilibrio de carga, o equilibradores de carga de hardware. En muchos casos, tendrá los sistemas en lugar de equilibrio de carga. Asegúrese de que está agregando el nuevo servidor de miembro a ambos. 
  

