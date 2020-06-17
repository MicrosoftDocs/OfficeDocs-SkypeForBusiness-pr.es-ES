---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Antes de implementar el grupo piloto, debe actualizar las entradas de host DNS A para el grupo piloto. Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754060"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros DNS para una implementación de grupo de servidores piloto

Antes de implementar el grupo piloto, debe actualizar las entradas de host DNS A para el grupo piloto. Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar los registros de host DNS A

1. En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, **Herramientas administrativas ** y, a continuación, en **DNS**.
    
2. En el árbol de la consola del dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Skype empresarial Server 2019.
    
3. Haga clic en **Host nuevo (A o AAAA)**.
    
4. Haga clic en **nombre**, escriba el nombre de host del grupo de servidores de Skype empresarial Server 2019 (el nombre de dominio se asume de la zona en la que está definido el registro y no es necesario especificarlo como parte del registro A).
    
5. Haga clic en **dirección IP**y, a continuación, escriba la dirección IP del grupo de servidores front-end.
    
6. Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**. 
    
7. Cuando haya terminado, haga clic en **Listo**.
    

