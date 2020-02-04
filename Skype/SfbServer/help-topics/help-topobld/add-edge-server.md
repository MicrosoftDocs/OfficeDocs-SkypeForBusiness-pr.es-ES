---
title: Agregar servidor perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Para incorporar un servidor perimetral o un grupo de servidores perimetrales al diseño de la topología, se necesita indicar el nombre de dominio completo del servidor en el que se quiere implementar el servidor perimetral o el grupo de servidores perimetrales. Antes de publicar una topología que incluye el servidor perimetral o el grupo de servidores perimetrales e instalar Skype empresarial Server, debe haber completado todos los requisitos previos para implementar el acceso de usuarios externos. Para más detalles sobre estos requisitos previos, mire Preparing for Installation of Servers in the Perimeter Network en la documentación de implementación.
ms.openlocfilehash: 3433f5dac67d0e02fb8e8552e205092a51082cc6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698345"
---
# <a name="add-edge-server"></a>Agregar servidor perimetral

Para incorporar un servidor perimetral o un grupo de servidores perimetrales al diseño de la topología, se necesita indicar el nombre de dominio completo del servidor en el que se quiere implementar el servidor perimetral o el grupo de servidores perimetrales. Antes de publicar una topología que incluye el servidor perimetral o el grupo de servidores perimetrales e instalar Skype empresarial Server, debe haber completado todos los requisitos previos para implementar el acceso de usuarios externos. Para más detalles sobre estos requisitos previos, mire [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) en la documentación de implementación.

> [!IMPORTANT]
> El nombre que especifique necesita ser idéntico al nombre del equipo configurado en el servidor. Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Así pues, necesita configurar un sufijo del Sistema de nombres de dominio (DNS) en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.

> [!TIP]
> Si tiene previsto implementar un grupo de servidores perimetrales más adelante, seleccione **Grupo de servidores de varios equipos**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a crear el generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el miembro del grupo de servidores perimetrales mediante el Asistente para la implementación de Skype empresarial Server. Asimismo, necesita agregar el nuevo miembro del grupo de servidores al correspondiente equilibrador de carga, equilibrio de carga DNS o equilibradores de carga de hardware. La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No se puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra. Compruebe que el nuevo servidor miembro se agrega al equilibrador de carga adecuado.

Puede permitir que los usuarios externos tengan acceso al implementar la topología inicial o más adelante. Para más detalles sobre cómo agregar servidores perimetrales o un grupo de servidores perimetrales a una topología ya existente, mire [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación de servidores perimetrales.


