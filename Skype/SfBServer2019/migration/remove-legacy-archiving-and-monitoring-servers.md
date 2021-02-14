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
description: Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype Empresarial Server 2019, dichos servidores se pueden quitar del entorno heredado siempre que se hayan quitado todos los usuarios de los grupos heredados restantes. Puede quitar el servidor de archivado o de supervisión en cualquier secuencia. El requisito clave es quitar a todos los usuarios de todos los grupos de servidores heredados restantes.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752172"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Quitar los servidores de archivado y supervisión heredados

Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype Empresarial Server 2019, dichos servidores se pueden quitar del entorno heredado, siempre que se hayan quitado todos los usuarios de los grupos heredados restantes. Puede quitar el servidor de archivado o de supervisión en cualquier secuencia. El requisito clave es quitar a todos los usuarios de todos los grupos de servidores heredados restantes.
  
Puede mover usuarios a Skype Empresarial Server 2019 siguiendo los procedimientos descritos en la fase [4:](phase-4-move-test-users-to-the-pilot-pool.md)Mover usuarios de prueba al grupo piloto.
  
Después de confirmar que se han quitado todos los usuarios de los grupos restantes, decomise el servidor y quite roles. Un ejemplo con fecha, pero relevante, es "Desinstalar Microsoft Lync Server y quitar roles de servidor", que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .
  

