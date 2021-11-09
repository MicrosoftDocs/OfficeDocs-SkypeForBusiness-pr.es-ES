---
title: Agregar dirección IP interna de equipo
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
description: Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.
ms.openlocfilehash: c0d08bf0fb4b197b32a79172c3df2c494173faa5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842082"
---
# <a name="add-edge-machine-internal-ip"></a>Agregar dirección IP interna de equipo

Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.

El FQDN que especifique debe ser idéntico al nombre del equipo configurado en el servidor. Por defecto, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, no un FQDN. Topology Builder usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo a implementarlo como servidor perimetral no unido a un dominio. Para más información sobre cómo añadir un sufijo de DNS a un nombre de equipo, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)