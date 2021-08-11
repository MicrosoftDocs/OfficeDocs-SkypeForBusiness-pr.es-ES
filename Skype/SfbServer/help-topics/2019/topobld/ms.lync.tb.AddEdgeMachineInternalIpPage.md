---
title: Agregar dirección IP interna de equipo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.
ms.openlocfilehash: 72e98165d4c279d1e35e0cb36afc49835e6010f72dfe685bec0e3eb8786d469f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294387"
---
# <a name="add-edge-machine-internal-ip"></a>Agregar dirección IP interna de equipo

Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.

El FQDN que especifique debe ser idéntico al nombre del equipo configurado en el servidor. Por defecto, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, no un FQDN. Topology Builder usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo a implementarlo como servidor perimetral no unido a un dominio. Para más información sobre cómo añadir un sufijo de DNS a un nombre de equipo, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)