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
description: Antes de implementar el grupo piloto, debe actualizar las entradas del host A dns para el grupo piloto. Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
ms.openlocfilehash: 270b0bda7da679cb0c75e9a99e10a898dcee6ac70413ce276abfe19ba1eb2231
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337838"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros DNS para una implementación de grupo de servidores piloto

Antes de implementar el grupo piloto, debe actualizar las entradas de host A de DNS para el grupo piloto. Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Para configurar los registros de host DNS A

1. En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, en **DNS**.
    
2. En el árbol de consola del dominio, expanda **Zonas** de búsqueda directa y, a continuación, haga clic con el botón secundario en el dominio en el que Skype Empresarial Server 2019 se instalará.
    
3. Haga clic en **Host nuevo (A o AAAA)**.
    
4. Haga clic en Nombre , escriba el nombre de host del grupo de servidores de Skype Empresarial Server 2019 (el nombre de dominio se asume desde la zona en la que se define el registro y no es necesario especificarlo como parte del registro A).
    
5. Haga **clic en Dirección IP** y, a continuación, escriba la dirección IP del grupo de servidores front-end.
    
6. Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**. 
    
7. Cuando haya terminado, haga clic en **Listo**.
    

