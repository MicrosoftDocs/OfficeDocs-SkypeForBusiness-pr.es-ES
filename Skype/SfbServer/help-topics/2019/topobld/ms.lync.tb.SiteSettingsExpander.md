---
title: Expansor de configuración de sitio de Lync Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar las propiedades de un sitio existente, realice lo siguiente:'
ms.openlocfilehash: b9660fcfbabc1276a5a470d6f83752981c35c54f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258238"
---
# <a name="lync-server-site-settings-expander"></a>Expansor de configuración de sitio de Lync Server

Para editar las propiedades de un sitio existente, realice lo siguiente:



## <a name="site-properties"></a>Propiedades de sitio

En Propiedades de sitio, puede cambiar o modificar el sitio nombre (obligatorio), descripción (opcional), ciudad (opcional), estado o provincia (opcional) y el código de país o región (opcional).

Para obtener información detallada acerca de las propiedades de sitio, vea [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Propiedades de ruta de federación

Para establecer una asignación de ruta de federación de sitio, primero debe tener habilitada en un servidor perimetral o un grupo de servidores perimetrales de federación. Si no está habilitada la federación en un servidor perimetral o grupo de servidores, la configuración de asignación de ruta de federación para el sitio no estará disponible para su modificación.

Si se ha configurado la configuración de federación en el servidor perimetral o grupo de servidores, seleccione **Habilitar** en el nivel de sitio. A continuación, seleccione una arista o un Director de la lista desplegable para establecer como la ruta de federación.

> [!CAUTION]
> Esta configuración afectará a todos los sitios. Asegúrese de que la configuración que se va a configurar en este sitio es adecuada para todos los sitios.

## <a name="see-also"></a>Vea también

Para obtener información detallada, vea [topologías para acceso de usuarios externos](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


