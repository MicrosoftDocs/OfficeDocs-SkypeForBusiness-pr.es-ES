---
title: Quitar un servidor Front-End de un grupo de servidores
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: El servidor Front-End no puede existir como un equipo independiente. Debe definirse como un grupo de servidores Front-End, incluso si hay un único equipo en el grupo de servidores.
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028946"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Quitar un servidor Front-End de un grupo de servidores

El servidor Front-End no puede existir como un equipo independiente. Debe definirse como un grupo de servidores Front-End, incluso si hay un único equipo en el grupo de servidores.
  
En este tema le guiará en el proceso de eliminación de un servidor individual de Front-End de un grupo de servidores Front-End existente. Si el servidor Front-End es el último servidor del grupo de servidores o si va a quitar por completo el grupo de servidores, vea [servidor Standard Edition o grupo de servidores quitar Front-End](remove-front-end-pool-or-standard-edition-server.md). No es necesario para quitar el servidor front-end individuales antes de quitar el grupo de servidores Front-End. Al quitar el grupo de servidores, quite cada servidor Front-End.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para quitar un servidor Front-End de un grupo de servidores

1. En Skype para profesionales de 2019 Front-End Server, abra el generador de topología.
    
2. Navegue hasta el nodo instalar heredado.
    
3. Expanda **grupos de servidores Front-End de Enterprise Edition**, expanda el grupo de servidores Front-End con el servidor Front-End que desea quitar, haga clic en el servidor Front-End que desea quitar y, a continuación, haga clic en **Eliminar**.
    

