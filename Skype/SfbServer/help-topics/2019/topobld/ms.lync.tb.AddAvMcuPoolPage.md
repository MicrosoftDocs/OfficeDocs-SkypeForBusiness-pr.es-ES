---
title: Agregar grupo de servidores MCU de A/V
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Todos los servidores front-end de Enterprise Edition de un sitio central que no tengan instalado un servicio de conferencias A/V puede usar el mismo grupo independiente de servidores de conferencia A/V. En cada grupo de servidores de conferencia A/V, debe especificar un nombre de dominio completo para el grupo de servidores, además de indicar si habrá un solo servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.
ms.openlocfilehash: f0bfa6155320a23467545be19de290a3f1df19dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812030"
---
# <a name="add-av-mcu-pool"></a>Agregar grupo de servidores MCU de A/V
 
Todos los servidores front-end de Enterprise Edition de un sitio central que no tengan instalado un servicio de conferencias A/V puede usar el mismo grupo independiente de servidores de conferencia A/V. En cada grupo de servidores de conferencia A/V, debe especificar un nombre de dominio completo para el grupo de servidores, además de indicar si habrá un solo servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.
  
> [!IMPORTANT]
> Un grupo de servidores de un solo servidor no puede convertirse en un grupo de servidores de varios servidores. Si más adelante considera que la organización necesita un grupo de servidores de varios servidores, debe eliminar el grupo de servidores de un solo servidor y, a continuación, agregar el grupo de servidores de varios servidores. 
  
> [!TIP]
> Si tiene previsto implementar un grupo de servidores de conferencia A/V, deseleccione **Grupo de servidores de varios equipos**. Aunque se defina un grupo de servidores como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a definir el nuevo miembro del grupo de servidores, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de servidores de conferencia A/V a través del Asistente para la implementación de Skype Empresarial Server. Los grupos de servidores de conferencia A/V son únicos ya que no necesitan equilibradores de carga para crear un grupo de servidores. Estos grupos equilibran la carga internamente y no necesitan de hardware adicional. 
  

