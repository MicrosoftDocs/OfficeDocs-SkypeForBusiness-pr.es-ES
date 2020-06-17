---
title: La comprobación de la replicación de usuarios ha finalizado
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
description: Cuando se ejecuta el cmdlet Move-CsUser, puede experimentar un error porque la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no están sincronizadas porque la replicación inicial está incompleta. El tiempo que tarda la finalización con éxito de la sincronización inicial del servicio de replicador de usuarios de Skype empresarial Server 2019 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el grupo de servidores de Skype empresarial 2019. El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando el servidor front-end de Skype empresarial Server 2019 se inicia por primera vez. Tras ello, la sincronización se basa en el intervalo del replicador de usuarios. Realice los siguientes pasos para verificar que se haya completado la replicación de usuario antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751652"
---
# <a name="verify-user-replication-has-completed"></a>La comprobación de la replicación de usuarios ha finalizado

Cuando se ejecuta el cmdlet **Move-CsUser** , puede experimentar un error si la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no están sincronizadas porque la replicación inicial está incompleta. El tiempo que tarda la finalización con éxito de la sincronización inicial del servicio de replicador de usuarios de Skype empresarial Server 2019 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el grupo de servidores de Skype empresarial 2019. El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando el servidor front-end de Skype empresarial Server 2019 se inicia por primera vez. A continuación, la sincronización se basa en el intervalo de replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuarios se ha completado antes de ejecutar el cmdlet **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para comprobar que la replicación de usuarios se ha completado

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    
2. Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**. 
    
3. Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.
    
4. En el visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Skype empresarial Server. 
    
5. En el panel **Acciones**, haga clic en **Filtrar registro actual**.
    
6. En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.
    
7. En **\<All Event IDs\>** , escriba **30024**y, a continuación, haga clic en **Aceptar**. 
    
8. En la lista de eventos filtrados, en la pestaña **General** , busque una entrada que indique que la replicación de usuarios se ha completado correctamente. 
    

