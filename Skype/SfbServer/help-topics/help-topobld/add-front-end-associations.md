---
title: Agregar asociaciones front-end
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
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 'Puede habilitar la compatibilidad con determinadas características que requieran la implementación de otros servidores asociando los roles de servidor con el grupo de servidores front-end ahora. También puede asociar los roles de servidor con el grupo de servidores front-end más adelante. Los roles de servidor que se pueden asociar con un grupo de servidores front-end incluyen:'
ms.openlocfilehash: dd1e5a7ffa91e5a46cde0faff99fe67ab083e7bc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862617"
---
# <a name="add-front-end-associations"></a>Agregar asociaciones front-end

Puede habilitar la compatibilidad con determinadas características que requieran la implementación de otros servidores asociando los roles de servidor con el grupo de servidores front-end ahora. También puede asociar los roles de servidor con el grupo de servidores front-end más adelante. Los roles de servidor que se pueden asociar con un grupo de servidores front-end incluyen:

- Servidor perimetral A/V. Para más información sobre la implementación de un servidor perimetral A/V, consulte [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) en la documentación sobre planificación.

> [!IMPORTANT]
> Si habilita ahora la compatibilidad de cualquiera de estas características, el diseño de la topología que publique incluirá los componentes del servidor que se requieren para implementar cada una de las características seleccionadas. Para que la publicación de una topología se realice con éxito, debe tener los equipos físicos unidos en el dominio. Por ejemplo, si habilita la compatibilidad con el archivado ahora, debe implementar un servidor de archivado y configurar las opciones de archivado adecuadas antes de iniciar las comunicaciones de archivado para su organización.