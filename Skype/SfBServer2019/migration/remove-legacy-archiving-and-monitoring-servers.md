---
title: Quitar los servidores de archivado y supervisión heredados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype Empresarial Server 2019, dichos servidores se pueden quitar del entorno heredado siempre que todos los usuarios se hayan quitado de los grupos heredados restantes. Puede quitar el servidor de archivado o de supervisión en cualquier secuencia. El requisito clave es quitar a todos los usuarios de todos los grupos de servidores heredados restantes.
ms.openlocfilehash: 204c68a50585bae033149ea75077ab0801b0bcc4aecb642c52fa96442bfc42ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304722"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Quitar los servidores de archivado y supervisión heredados

Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype Empresarial Server 2019, dichos servidores se pueden quitar del entorno heredado, siempre que se hayan quitado todos los usuarios de los grupos heredados restantes. Puede quitar el servidor de archivado o de supervisión en cualquier secuencia. El requisito clave es quitar a todos los usuarios de todos los grupos de servidores heredados restantes.
  
Puede mover usuarios a Skype Empresarial Server 2019 siguiendo los procedimientos descritos en Fase [4:](phase-4-move-test-users-to-the-pilot-pool.md)Mover usuarios de prueba al grupo piloto .
  
Después de confirmar que se han quitado todos los usuarios de los grupos de servidores restantes, descomisa el servidor y quita roles. Un ejemplo fechado, pero relevante, es "Desinstalar Microsoft Lync Server y quitar roles de servidor", que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .
  

