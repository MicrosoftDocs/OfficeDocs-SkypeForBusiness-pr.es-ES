---
title: Quitar los servidores de archivado y supervisión heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype empresarial Server 2019, esos servidores se pueden quitar del entorno heredado siempre que todos los usuarios hayan sido eliminados de cualquier grupo heredado. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo heredado.
ms.openlocfilehash: 034d2ad284c0247b19e56e4cd8d751a0cf32ee69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812998"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Quitar los servidores de archivado y supervisión heredados

Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype empresarial Server 2019, esos servidores se pueden quitar del entorno heredado, siempre y cuando todos los usuarios hayan sido eliminados de cualquier grupo heredado. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo heredado.
  
Puede mover usuarios a Skype empresarial Server 2019 siguiendo los procedimientos descritos en la [fase 4: mover usuarios de prueba a la agrupación piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
Una vez que haya confirmado que todos los usuarios se han quitado del grupo restante, decommision el servidor y quite roles. Un ejemplo de fecha, pero relevante es "desinstalar Microsoft Lync Server y quitar roles de servidor", que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).
  

