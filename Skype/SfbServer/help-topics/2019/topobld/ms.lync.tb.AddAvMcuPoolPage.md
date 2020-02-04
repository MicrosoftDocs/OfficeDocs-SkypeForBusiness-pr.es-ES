---
title: Agregar grupo de servidores MCU de A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Todos los servidores de aplicaciones para el usuario de Enterprise Edition de un sitio central que no dispongan de un servicio de conferencia A/V, pueden usar el mismo grupo independiente de conferencias A/V. Para cada grupo de conferencias A/V, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tendrá un único servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.
ms.openlocfilehash: 0cef8dd5c99859f03018d959f0d2d5a9d0523681
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689695"
---
# <a name="add-av-mcu-pool"></a>Agregar grupo de servidores MCU de A/V
 
Todos los servidores de aplicaciones para el usuario de Enterprise Edition de un sitio central que no dispongan de un servicio de conferencia A/V, pueden usar el mismo grupo independiente de conferencias A/V. Para cada grupo de conferencias A/V, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tendrá un único servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.
  
> [!IMPORTANT]
> No se puede convertir un grupo de un solo servidor en un grupo de varios servidores. Si más tarde decide que su organización necesita un grupo de varios servidores, debe eliminar el grupo de servidores únicos y, a continuación, agregar el grupo de varios servidores. 
  
> [!TIP]
> Si piensa implementar un grupo de conferencias A/V en el futuro, seleccione **varios grupos de equipos**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a crear el generador de topología para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de conferencias a/V mediante el Asistente para la implementación de Skype empresarial Server. Los grupos de servidores de conferencia a/V son únicos, ya que no necesitan equilibradores de carga para crear un grupo. Los grupos de conferencia A/V realizan un equilibrio de carga interno y no necesitan hardware adicional. 
  

