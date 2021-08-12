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
ms.openlocfilehash: 0c3454bd4fbf8ecdc28730da378357e9d50efec3c12ba5b3926abb61010979ab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327056"
---
# <a name="update-dns-srv-records"></a>Actualizar registros SRV de DNS

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
  
En este tema se describe cómo actualizar los registros del Sistema de nombres de dominio (DNS) después de migrar a Skype Empresarial Server 2019. Después de que todos los usuarios se hayan movido a Skype Empresarial Server 2019, pero antes de retirar el grupo heredado o director, debe actualizar los registros SRV dns en su DNS interno para cada dominio SIP. En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar un registro DNS SRV

1. En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.
    
2. En el árbol de consola del dominio SIP, expanda **Zonas** de búsqueda directa, expanda el dominio SIP en el que está instalado Skype Empresarial Server 2019 y vaya a la configuración **_tcp** búsqueda. 
    
3. En el panel derecho, haga clic con el botón **secundario en _sipinternaltls** y seleccione **Propiedades**.
    
4. En **Host que ofrece este servicio,** actualice el FQDN de host para que apunte al grupo Skype Empresarial Server 2019.
    
5. Haga clic en **Aceptar**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition

1. Inicie sesión en un equipo cliente en el dominio.
    
2. Haga clic en **Inicio** y, a continuación, en **Ejecutar**.
    
3. En el **cuadro Abrir,** escriba cmd y, a continuación, haga clic en **Aceptar**.
    
4. En el símbolo del sistema, escriba nslookup _\<FQDN of the Front End pool\>_ o  _\<FQDN of the Standard Edition server\>_ , y, a continuación, presione ENTRAR.
    
5. Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.
    

