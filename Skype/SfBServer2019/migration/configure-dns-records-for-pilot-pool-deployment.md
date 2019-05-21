---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar el grupo piloto, debe actualizar las entradas del host DNS A para la agrupación piloto. Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289626"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros DNS para una implementación de grupo de servidores piloto

Antes de implementar el grupo piloto, debe actualizar las entradas del host DNS A para la agrupación piloto. Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar registros A de host DNS

1. En el servidor del sistema de nombres de dominio (DNS), haga clic en **Inicio**, en **herramientas administrativas**y, por último, en **DNS**.
    
2. En el árbol de consola de su dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón derecho en el dominio en el que se instalará Skype empresarial Server 2019.
    
3. Haga clic en **nuevo host (A o aaaa)**.
    
4. Haga clic en **nombre**, escriba el nombre de host para el grupo de servidores de Skype empresarial 2019 (el nombre de dominio se supone de la zona en la que está definido el registro y no tiene que especificarse como parte del registro A).
    
5. Haga clic en **dirección IP**y, a continuación, escriba la dirección IP del grupo de servidores front-end.
    
6. Haga clic en **Agregar host**y, a continuación, en **Aceptar**. 
    
7. Cuando haya terminado, haga clic en **listo**.
    

