---
title: Actualizar registros SRV de DNS
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
description: Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753272"
---
# <a name="update-dns-srv-records"></a>Actualizar registros SRV de DNS

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
  
En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Skype empresarial Server 2019. Una vez que todos los usuarios se han movido a Skype empresarial Server 2019, pero antes de que se retire el grupo o el director heredados, debe actualizar los registros DNS SRV en el DNS interno para cada dominio SIP. En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar un registro DNS SRV

1. En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.
    
2. En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que está instalado Skype empresarial Server 2019 y vaya a la configuración de **_tcp** . 
    
3. En el panel derecho, haga clic con el botón secundario en **_sipinternaltls** y seleccione **propiedades**.
    
4. En **host que ofrece este servicio**, actualice el FQDN de host para que apunte al grupo de Skype empresarial Server 2019.
    
5. Haga clic en **Aceptar**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition

1. Inicie sesión en un equipo cliente en el dominio.
    
2. Haga clic en **Inicio** y, a continuación, en **Ejecutar**.
    
3. En el cuadro **abrir** , escriba cmd y, a continuación, haga clic en **Aceptar**.
    
4. En el símbolo del sistema, escriba nslookup _\<FQDN of the Front End pool\>_ o _\<FQDN of the Standard Edition server\>_ y, a continuación, presione Entrar.
    
5. Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.
    

