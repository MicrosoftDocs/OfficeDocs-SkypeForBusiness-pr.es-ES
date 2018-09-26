---
title: Quitar archivado heredado y supervisión de servidores
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si su implementación heredada contenía un servidor de archivado o en un servidor de supervisión, después de migrar a Skype para Business Server 2019, esos servidores se pueden quitar del entorno heredado siempre que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante.
ms.openlocfilehash: 4de6d9db5538864646f978e9fc33a79b39d4c2a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028617"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Quitar archivado heredado y supervisión de servidores

Si su implementación heredada contenía un servidor de archivado o en un servidor de supervisión, después de migrar a Skype para Business Server 2019, esos servidores se puede quitarse del entorno heredado, proporcionado que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante.
  
Puede mover los usuarios a Skype para Business Server 2019 siguiendo los procedimientos descritos en [fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
Una vez que se ha confirmado que se han quitado todos los usuarios de cualquier de los grupos restantes, decommision el servidor y quitar roles. Una fecha, pero relevantes, el ejemplo es "Desinstalar Microsoft Lync Server y quitar Roles de servidor," que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).
  

