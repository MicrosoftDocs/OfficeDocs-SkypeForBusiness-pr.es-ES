---
title: Agregar IP interna de servidor perimetral 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
ms.openlocfilehash: dfe5d082b14d5480061f7262c481e455b7eb8a1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302447"
---
# <a name="add-edge-server-internal-ip-2010"></a>Agregar IP interna de servidor perimetral 2010

Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.

El FQDN que especifique debe ser idéntico al nombre del equipo que está configurado en el servidor. Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo que se va a implementar como un servidor perimetral que no está unido a un dominio. Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte [configurar DNS para la compatibilidad con Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).


