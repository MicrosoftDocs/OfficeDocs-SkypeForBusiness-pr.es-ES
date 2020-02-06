---
title: Agregar IP interna de equipo perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
ms.openlocfilehash: fba327a08d8998056c42a39190fd8b3bf44ff08b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798247"
---
# <a name="add-edge-machine-internal-ip"></a>Agregar IP interna de equipo perimetral

Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.

El FQDN que especifique debe ser idéntico al nombre de equipo configurado en el servidor. Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo que se va a implementar como un servidor perimetral que no está unido a un dominio. Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte [configurar DNS para la compatibilidad con Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


