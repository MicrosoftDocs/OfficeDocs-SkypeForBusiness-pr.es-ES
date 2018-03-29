---
title: Añadir A / V MCU Pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos los servidores Enterprise Edition Front End de un sitio central que no tienen un colocadas A / servicio de conferencias audiovisuales puede utilizar la misma independiente / grupo de conferencias audiovisuales. Para cada A / grupo de conferencias audiovisuales, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tiene sólo un único / V Conferencing Server o múltiple, equilibrio de carga A / V servidores de conferencia.
ms.openlocfilehash: d1712829030836446c06a2e335c424d51a19e466
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-av-mcu-pool"></a>Añadir A / V MCU Pool
 
Todos los servidores Enterprise Edition Front End de un sitio central que no tienen un colocadas A / servicio de conferencias audiovisuales puede utilizar la misma independiente / grupo de conferencias audiovisuales. Para cada A / grupo de conferencias audiovisuales, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tiene sólo un único / V Conferencing Server o múltiple, equilibrio de carga A / V servidores de conferencia.
  
> [!IMPORTANT]
> No se puede convertir un grupo de servidor único a una agrupación de varios servidores. Si más adelante decide que su organización tiene un grupo de varios servidores, debe eliminar el grupo de servidor único y, a continuación, agregue la agrupación de varios servidores. 
  
> [!TIP]
> Si piensa implementar una A / grupo de conferencias audiovisuales en el futuro, seleccione **varios grupo de equipo**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo posteriormente, primero debe el generador de topología para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo A / conferencias audiovisuales grupo miembro mediante el Skype para el Asistente para implementación de Business Server. A / grupos V Conferencing Server son exclusivas en tanto no necesita equilibradores de carga para crear un grupo. A / grupos de conferencias audiovisuales equilibrar la carga internamente y no es necesario hardware adicional. 
  

