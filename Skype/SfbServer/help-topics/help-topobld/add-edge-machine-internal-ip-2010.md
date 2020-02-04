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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
ms.openlocfilehash: 4c1606dfc44a303b5e9eb8e84710b14b41b7da90
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685303"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Agregar IP interna de equipo perimetral 2010

Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.

- En **dirección IPv4 interna**, escriba la dirección IP del servidor perimetral que desea agregar al grupo.

- En nombre de dominio **interno**, escriba el nombre de dominio completo (FQDN) del servidor perimetral que desea agregar al grupo.

El FQDN que especifique debe ser idéntico al nombre del equipo que está configurado en el servidor. Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo que se va a implementar como un servidor perimetral que no está unido a un dominio. Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte [configurar DNS para la compatibilidad con Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


