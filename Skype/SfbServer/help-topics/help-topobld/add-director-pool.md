---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que constará de dos o más directores en un grupo de servidores con equilibrio de carga o un grupo de servidores de un solo equipo. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o al FQDN del director único. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
ms.openlocfilehash: 9a338cffcbd489bf9953f416b51464d5f1c49ce1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418613"
---
# <a name="add-director-pool"></a>Agregar grupo de servidores director
 
Para **definir el FQDN** del grupo de directores,  seleccione un grupo de varios equipos que constará de dos o más directores en un grupo de servidores con equilibrio de carga o un grupo de **servidores de un solo equipo**. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o al FQDN del director único. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores director, seleccione **Grupo de servidores de varios equipos**. Aunque un grupo de servidores se define como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y crear un FQDN de grupo para el único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a ejecutar el Generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores mediante el Asistente para la implementación de Skype Empresarial Server. También debe agregar el nuevo miembro del grupo a los equilibradores de carga adecuados para el grupo, para el equilibrio de carga del Sistema de nombres de dominio (DNS) o para equilibradores de carga de hardware. En muchos casos, tendrá ambos sistemas de equilibrio de carga en su lugar. Compruebe que el nuevo servidor miembro se agregue a ambos. 
  

