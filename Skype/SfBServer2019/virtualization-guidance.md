---
title: 'Compatibilidad con la virtualización Skype Empresarial Server 2019 '
ms.reviewer: corbinm
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Resumen: obtenga información sobre la compatibilidad de virtualización para Skype Empresarial Server 2019.'
ms.openlocfilehash: 850bfc0ae19aa8391baca6c9a8b6f1dde85cde2d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767108"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Compatibilidad con la virtualización Skype Empresarial Server 2019

Skype Empresarial Server 2019 es compatible con la virtualización.

Aunque se admite la virtualización, hay algunos puntos clave que recordar:

- Mantener una relación 1:1 de CPU virtual a CPU física.
- No mueva un servidor invitado mientras esté en funcionamiento.
- No se admite la migración de un sistema en directo ni la portabilidad de una máquina virtual.
- Deshabilitar el hyper-threading en todos los hosts.
- No configure la memoria dinámica en los servidores host.
- Use discos fijos o de paso a través en lugar de discos dinámicos.
- Permitir una sobrecarga de entre un 6 y un 10 por ciento para hipervisores más allá de lo que requiere el invitado virtual.

## <a name="supported-hypervisors"></a>Hipervisores compatibles

SfB Server 2019 se admite en Windows Server 2016 y Windows Server 2019.

Para hipervisores de terceros, necesita un hipervisor que haya pasado las pruebas del Programa de validación de virtualización de servidores (SVVP) para el sistema operativo correspondiente.

- Consulta las [Windows Server 2016 en](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) la lista SVVP.
- Vea el [Windows Server 2019 en](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) la lista SVVP.

## <a name="stress-and-performance-tool"></a>Herramienta de esfuerzo y rendimiento

La Skype Empresarial Server 2019 stress and performance tool incluye herramientas que simplifican la planeación de capacidad para Skype Empresarial Server 2019. La Skype Empresarial Server 2019 Stress and Performance Tool le ayudará a:

- Simplificar la planeación de hardware para Skype Empresarial Server 2019
- Proporcionar un mayor conocimiento y procedimientos recomendados para la optimización del rendimiento
- Medir el rendimiento de las implementaciones Skype Empresarial Server 2019
 
Puede descargar la herramienta desde [aquí](https://www.microsoft.com/download/details.aspx?id=101447).
