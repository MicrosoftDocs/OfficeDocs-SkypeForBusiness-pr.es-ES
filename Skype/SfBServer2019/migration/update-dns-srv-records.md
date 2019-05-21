---
title: Actualizar registros SRV de DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
ms.openlocfilehash: bf9f9c3f16ceb2ee35cda8e833d468e202d5653c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307059"
---
# <a name="update-dns-srv-records"></a>Actualizar registros SRV de DNS

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
  
En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Skype empresarial Server 2019. Después de que todos los usuarios se hayan movido a Skype empresarial Server 2019, pero antes de que el grupo o el director heredado se haya decomisado, debe actualizar los registros SRV de DNS en el DNS interno para cada dominio SIP. En este procedimiento se supone que su DNS interno tiene zonas para sus dominios de usuario SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar un registro SRV de DNS

1. En el servidor DNS, haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.
    
2. En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que está instalado Skype empresarial Server 2019 y vaya a la configuración **_ TCP** . 
    
3. En el panel derecho, haga clic con el botón derecho en **_sipinternaltls** y seleccione **propiedades**.
    
4. En **host que ofrece este servicio**, actualice el FQDN del host para que apunte al grupo de servidores de Skype empresarial 2019.
    
5. Haga clic en **Aceptar**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition

1. Inicie sesión en un equipo cliente del dominio.
    
2. Haga clic en  **Inicio ** y en  **Ejecutar **.
    
3. En el cuadro **abrir** , escriba cmd y haga clic en **Aceptar**.
    
4. En el símbolo del sistema, escriba nslookup _ \<FQDN del grupo\> de servidores front-end_ o _ \<FQDN del servidor\>Standard Edition_y, a continuación, presione Entrar.
    
5. Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el nombre de dominio completo (FQDN).
    

