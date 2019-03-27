---
title: Quitar los servidores de archivado y supervisión heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si su implementación heredada contenía un servidor de archivado o en un servidor de supervisión, después de migrar a Skype para Business Server 2019, esos servidores se pueden quitar del entorno heredado siempre que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante.
ms.openlocfilehash: 5a3a691c8f2e8a4ad3610ccf1ea947ce23b74111
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878345"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Quitar los servidores de archivado y supervisión heredados

Si su implementación heredada contenía un servidor de archivado o en un servidor de supervisión, después de migrar a Skype para Business Server 2019, esos servidores se puede quitarse del entorno heredado, proporcionado que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante.
  
Puede mover los usuarios a Skype para Business Server 2019 siguiendo los procedimientos descritos en [fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
Una vez que se ha confirmado que se han quitado todos los usuarios de cualquier de los grupos restantes, decommision el servidor y quitar roles. Una fecha, pero relevantes, el ejemplo es "Desinstalar Microsoft Lync Server y quitar Roles de servidor," que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).
  

