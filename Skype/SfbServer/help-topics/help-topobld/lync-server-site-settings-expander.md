---
title: Expansor de configuración de sitio de Lync Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Para editar las propiedades de un sitio ya creado, efectúe las acciones siguientes:'
ms.openlocfilehash: 9ace8cc0975e971e7f3c3fe55c89324330816f62d78b0ee5c9b23d16e9ff9689
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305472"
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

## <a name="see-also"></a>Consulte también

Para obtener información, consulte [Topologías para el acceso de usuarios externos](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).