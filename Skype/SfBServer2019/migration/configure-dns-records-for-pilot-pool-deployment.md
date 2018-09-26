---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar el grupo piloto, debe actualizar las entradas de Host DNS A para el grupo piloto. Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.
ms.openlocfilehash: 13492f7972e127de7a8200a0dbe933c72aba2da7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029898"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros DNS para una implementación de grupo de servidores piloto

Antes de implementar el grupo piloto, debe actualizar las entradas de Host DNS A para el grupo piloto. Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar los registros de Host DNS A

1. En el servidor del sistema de nombres de dominio (DNS), haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **DNS**.
    
2. En el árbol de consola del dominio, expanda **Zonas de búsqueda directa**y, a continuación, haga clic en el dominio en el que se va a instalar Skype para Business Server 2019.
    
3. Haga clic en **Host nuevo (A o AAAA)**.
    
4. Haga clic en **nombre**, escriba el nombre de host para el Skype para grupo de negocio Server 2019 (el nombre de dominio se deduce de la zona que se define en el registro y que no es necesario que debe escribirse como parte del registro A).
    
5. Haga clic en **Dirección IP**y, a continuación, escriba la dirección IP para el grupo de servidores Front-End.
    
6. Haga clic en **Agregar Host**y, a continuación, haga clic en **Aceptar**. 
    
7. Cuando haya terminado, haga clic en **Listo**.
    

