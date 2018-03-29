---
title: Agregue el FQDN del grupo de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que está creando. No puede cambiar el nombre completo de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End. Si necesita cambiar el nombre de un grupo, debe eliminar el grupo y, a continuación, agregar un nuevo grupo con el nuevo nombre de dominio completo.
ms.openlocfilehash: 73fce35786cdce2a39ebf2981b59a500991112f0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-pool-fqdn"></a>Agregue el FQDN del grupo de Front-End
 
Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que está creando. No puede cambiar el nombre completo de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End. Si necesita cambiar el nombre de un grupo, debe eliminar el grupo y, a continuación, agregar un nuevo grupo con el nuevo nombre de dominio completo.
  
> [!TIP]
> Si va a implementar un grupo de servidores Front-End en el futuro, seleccione **grupo de equipo múltiple**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología para definir al nuevo miembro del grupo, publicar la nueva topología y configurar el nuevo miembro de grupo de servidores Front-End mediante el Skype para el Asistente para implementación de Business Server. También debe agregar al nuevo miembro de grupo a los equilibradores de carga adecuada para el grupo, equilibrio de carga de sistema de nombres de dominio (DNS) o equilibradores de carga hardware. En muchos casos, tendría los sistemas en lugar de equilibrio de carga. Asegúrese de que está agregando el nuevo servidor de miembro a ambos. 
  

