---
title: 'Compatibilidad con la virtualización en Skype empresarial Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Obtenga información sobre la compatibilidad de la virtualización con Skype empresarial Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509037"
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

## <a name="stress-and-performance-tool"></a>Herramienta stress and Performance

La herramienta de esfuerzo y rendimiento de Skype empresarial Server 2019 incluye herramientas que simplifican la planeación de la capacidad de Skype empresarial Server 2019. La herramienta de esfuerzo y rendimiento de Skype empresarial Server 2019 le ayudará a:

- Simplificar la planeación de hardware para Skype empresarial Server 2019
- Proporcionar un mayor conocimiento y procedimientos recomendados para ajustar el rendimiento
- Medir el rendimiento de las implementaciones previstas de Skype empresarial Server 2019
 
Puede descargar la herramienta desde [aquí](https://www.microsoft.com/download/details.aspx?id=101447).
