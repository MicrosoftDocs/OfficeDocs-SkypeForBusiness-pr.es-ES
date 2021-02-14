---
title: 'Compatibilidad con la virtualización de Skype Empresarial Server 2019 '
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
description: 'Resumen: obtenga información sobre la compatibilidad con la virtualización de Skype Empresarial Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509037"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Compatibilidad con la virtualización de Skype Empresarial Server 2019

Skype Empresarial Server 2019 es compatible con la virtualización.

Aunque se admite la virtualización, hay algunos puntos clave que recordar:

- Mantenga una proporción de 1:1 de CPU virtual a CPU física.
- No mueva un servidor invitado mientras esté operativo.
- No se admite la migración de un sistema en directo y la portabilidad de una máquina virtual.
- Deshabilitar hyper-threading en todos los hosts.
- No configure memoria dinámica en servidores host.
- Usa discos fijos o de paso a través en lugar de discos dinámicos.
- Permitir una sobrecarga del 6 al 10 por ciento para hipervisores más allá de lo que requiere el invitado virtual.

## <a name="supported-hypervisors"></a>Hipervisores compatibles

SfB Server 2019 es compatible con Windows Server 2016 y Windows Server 2019.

Para hipervisores de terceros, necesitas un hipervisor que haya superado las pruebas del Programa de validación de virtualización de servidores (SVVP) para el sistema operativo correspondiente.

- Consulta las [versiones de Windows Server 2016 en](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) la lista SVVP.
- Consulta las [versiones de Windows Server 2019 en](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) la lista SVVP.

## <a name="stress-and-performance-tool"></a>Herramienta de esfuerzo y rendimiento

La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2019 incluye herramientas que simplifican la planeación de capacidad para Skype Empresarial Server 2019. La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2019 le ayudará a:

- Simplificar la planeación de hardware para Skype Empresarial Server 2019
- Proporcionar un mayor conocimiento y procedimientos recomendados para el ajuste del rendimiento
- Medir el rendimiento de las implementaciones de Skype Empresarial Server 2019 previstas
 
Puede descargar la herramienta desde [aquí.](https://www.microsoft.com/download/details.aspx?id=101447)
