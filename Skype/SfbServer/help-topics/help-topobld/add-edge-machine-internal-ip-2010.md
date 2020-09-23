---
title: Agregar IP interna de equipo perimetral 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno del servidor perimetral.
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219384"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Agregar IP interna de equipo perimetral 2010

Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno del servidor perimetral.

- En **dirección IPv4 interna**, escriba la dirección IP del servidor perimetral que desea agregar al grupo.

- En **FQDN interno**, escriba el nombre de dominio completo (FQDN) del servidor perimetral que desea agregar al grupo.

El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN). Topology Builder usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo a implementarlo como servidor perimetral no unido a un dominio. Para más información sobre cómo añadir un sufijo de DNS a un nombre de equipo, consulte [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


