---
title: Actualizar registros SRV de DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.
ms.openlocfilehash: 5cdf98d065abbb57b3cb654c8b770f8f1f87500c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231386"
---
# <a name="update-dns-srv-records"></a>Actualizar registros SRV de DNS

Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.
  
En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Skype para Business Server 2019. Después de que todos los usuarios se han movido a Skype para Business Server 2019, pero antes de que se retire el Director o grupo de servidores heredado, debe actualizar los registros SRV de DNS en su DNS interno para cada dominio SIP. Este procedimiento se supone que el DNS interno tiene zonas para los dominios de usuario SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar un registro SRV de DNS

1. En el servidor DNS, haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **DNS**.
    
2. En el árbol de consola de su dominio SIP, expanda **Zonas de búsqueda directa**, expanda el dominio SIP en qué Skype para Business Server 2019 está instalado y navegue a la opción **_tcp** . 
    
3. En el panel derecho, haga clic en **_sipinternaltls** y seleccione **Propiedades**.
    
4. En **Host que ofrece este servicio**, actualice el host FQDN para que apunte a la Skype para el grupo de servidores de Business Server 2019.
    
5. Haga clic en **Aceptar**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para comprobar que se puede resolver el FQDN del servidor Standard Edition o grupo de servidores Front-End

1. Inicie sesión en un equipo cliente en el dominio.
    
2. Haga clic en  **Inicio ** y en  **Ejecutar **.
    
3. En el cuadro **Abrir** , escriba cmd y, a continuación, haga clic en **Aceptar**.
    
4. En el símbolo del sistema, escriba nslookup _ \<FQDN del grupo de servidores Front-End\> _ o _ \<FQDN del servidor Standard Edition\>_, y, a continuación, presione ENTRAR.
    
5. Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el FQDN.
    

