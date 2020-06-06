---
title: 'Compatibilidad con la virtualización en Skype empresarial Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Obtenga información sobre la compatibilidad de la virtualización con Skype empresarial Server 2019.'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565959"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Compatibilidad con la virtualización en Skype empresarial Server 2019

Skype empresarial Server 2019 es compatible con la virtualización.

Aunque se admite la virtualización, hay algunos puntos clave que hay que recordar:

- Mantener una relación 1:1 de CPU virtual a CPU física.
- No mueva un servidor invitado mientras está en funcionamiento.
- No se admite la migración de un sistema activo y la portabilidad de una máquina virtual.
- Deshabilite la tecnología Hyper-Threading en todos los hosts.
- No configure la memoria dinámica en los servidores host.
- Use discos fijos o de paso a través en lugar de discos dinámicos.
- Permitir una sobrecarga del 6-10 por ciento para los hipervisores aparte de lo que requiere el invitado virtual.

## <a name="supported-hypervisors"></a>Hipervisores compatibles

SfB Server 2019 es compatible con Windows Server 2016 y Windows Server 2019.

Para los hipervisores de terceros, necesita un hipervisor que haya pasado las pruebas del programa de validación de virtualización del servidor (SVVP) para el sistema operativo relevante.

- Consulte las [versiones de Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) en la lista SVVP.
- Consulte las [versiones de Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) en la lista SVVP.