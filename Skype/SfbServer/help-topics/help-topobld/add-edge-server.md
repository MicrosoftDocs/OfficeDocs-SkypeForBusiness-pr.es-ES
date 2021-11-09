---
title: Agregar servidor perimetral
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Para incorporar un servidor perimetral o un grupo de servidores perimetrales en el diseño de la topología, se debe indicar el nombre de dominio completo del servidor en el que se desea implementar el servidor perimetral o el grupo de servidores perimetrales. Antes de publicar una topología que incluya el servidor perimetral o el grupo de servidores perimetrales e instalar Skype Empresarial Server, debería haber completado todos los requisitos previos para implementar el acceso de usuarios externos. Para obtener información sobre estos requisitos previos, consulte Preparar la instalación de servidores en la red perimetral en la documentación sobre implementación.
ms.openlocfilehash: 04ab27281bd382b95ec088a9db995237d6ff7d6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837872"
---
# <a name="add-edge-server"></a>Agregar servidor perimetral

Para incorporar un servidor perimetral o un grupo de servidores perimetrales en el diseño de la topología, se debe indicar el nombre de dominio completo del servidor en el que se desea implementar el servidor perimetral o el grupo de servidores perimetrales. Antes de publicar una topología que incluya el servidor perimetral o el grupo de servidores perimetrales e instalar Skype Empresarial Server, debería haber completado todos los requisitos previos para implementar el acceso de usuarios externos. Para obtener más información sobre estos requisitos previos, vea [Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network) en la documentación sobre implementación.

> [!IMPORTANT]
> El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De forma predeterminada, un equipo no incorporado a un dominio tiene un nombre corto, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Así pues, debe configurar un sufijo del sistema de nombres de dominio DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.

> [!TIP]
> Si tiene previsto implementar un grupo de servidores perimetrales más adelante, seleccione **Grupo de servidores de varios equipos**. Aunque se defina un grupo de servidores como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo. Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a crear topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de servidores perimetrales mediante el Asistente para la implementación de Skype Empresarial Server. Asimismo, debe agregar el nuevo miembro del grupo de servidores al correspondiente equilibrador de carga, equilibrio de carga DNS o equilibradores de carga de hardware. La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No se puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral. Compruebe que el nuevo servidor miembro se agregue al equilibrador de carga adecuado.

Puede permitir que los usuarios externos tengan acceso al implementar la topología inicial o después. Para obtener más información sobre cómo agregar servidores perimetrales o un grupo de servidores perimetrales a una topología ya creada, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) en la documentación sobre implementación de servidores perimetrales.