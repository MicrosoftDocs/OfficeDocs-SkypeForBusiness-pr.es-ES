---
title: Agregar servidor perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Para incorporar un servidor perimetral o un grupo de servidores perimetrales al diseño de la topología, se necesita indicar el nombre de dominio completo del servidor en el que se quiere implementar el servidor perimetral o el grupo de servidores perimetrales. Antes de publicar una topología que incluye el servidor perimetral o grupo de servidores perimetrales e instalación de Skype para Business Server, debe haber completado todos los requisitos previos para la implementación de acceso de usuarios externos. Para obtener información detallada acerca de estos requisitos previos, consulte preparación de la instalación de servidores en la red perimetral, en la documentación de implementación.
ms.openlocfilehash: b39161e64d4679e20c0c960811da1eb7ed705643
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244219"
---
# <a name="add-edge-server"></a>Agregar servidor perimetral

Para incorporar un servidor perimetral o un grupo de servidores perimetrales al diseño de la topología, se necesita indicar el nombre de dominio completo del servidor en el que se quiere implementar el servidor perimetral o el grupo de servidores perimetrales. Antes de publicar una topología que incluye el servidor perimetral o grupo de servidores perimetrales e instalación de Skype para Business Server, debe haber completado todos los requisitos previos para la implementación de acceso de usuarios externos. Para obtener información detallada acerca de estos requisitos previos, vea [Preparación para la instalación de servidores en la red perimetral](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) , en la documentación de implementación.

> [!IMPORTANT]
> El nombre que especifique necesita ser idéntico al nombre del equipo configurado en el servidor. Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Así pues, necesita configurar un sufijo del Sistema de nombres de dominio (DNS) en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.

> [!TIP]
> Si tiene previsto implementar un grupo de servidores perimetrales más adelante, seleccione **Grupo de servidores de varios equipos**. Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe generador de nuevo para definir al nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar el nuevo integrante de grupo de servidores de servidor perimetral a través de la Skype para el Asistente para la implementación de servidor de negocio. Asimismo, necesita agregar el nuevo miembro del grupo de servidores al correspondiente equilibrador de carga, equilibrio de carga DNS o equilibradores de carga de hardware. La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No se puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra. Compruebe que el nuevo servidor miembro se agrega al equilibrador de carga adecuado.

Puede permitir que los usuarios externos tengan acceso al implementar la topología inicial o más adelante. Para obtener información detallada sobre cómo agregar servidores perimetrales o grupo de servidores perimetrales a una topología existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación del servidor perimetral.


