---
title: Expansor de configuración de sitio de Lync Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar las propiedades de un sitio ya creado, efectúe las acciones siguientes:'
ms.openlocfilehash: 4bcf07ef1b550fb96ce503f31b4026ccc4ae6960
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115380"
---
# <a name="lync-server-site-settings-expander"></a>Expansor de configuración de sitio de Lync Server

Para editar las propiedades de un sitio ya creado, efectúe las acciones siguientes:



## <a name="site-properties"></a>Propiedades del sitio

En las propiedades del sitio se puede cambiar o modificar las opciones Nombre del sitio (obligatorio), Descripción (opcional), Ciudad (opcional), Estado o provincia (opcional) y País o región (opcional).

Para obtener más información sobre las propiedades de los sitios, consulte [Agregar sucursales a la topología](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).

## <a name="federation-route-properties"></a>Propiedades de la ruta de federación

Para definir una asignación de ruta de federación de un sitio, primero debe tener la federación habilitada en un servidor perimetral o grupo de servidores perimetrales. Si la federación no está habilitada en un servidor perimetral o un grupo de servidores perimetrales, la configuración de la asignación de ruta de federación para el sitio no se podrá modificar.

Si se ha definido una configuración de federación del servidor o grupo de servidores perimetrales, seleccione **Habilitar** en el nivel del sitio. A continuación, seleccione un servidor perimetral o director de la lista desplegable para definirlos como ruta de federación.

> [!CAUTION]
> Esta configuración afectará a todos los sitios. Asegúrese de que la configuración que está configurando en este sitio es adecuada para todos los sitios.

## <a name="see-also"></a>Ver también

Para obtener información, consulte [Topologías para el acceso de usuarios externos](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).