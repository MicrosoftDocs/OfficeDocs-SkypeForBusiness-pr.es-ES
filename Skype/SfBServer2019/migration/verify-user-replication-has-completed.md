---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Al ejecutar el cmdlet Move-CsUser, puede experimentar un error porque la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no está sincronizada porque la replicación inicial está incompleta. El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Skype empresarial Server 2019 depende de la cantidad de controladores de dominio que se hospeden en el bosque de Active Directory que aloje Skype empresarial. Grupo de servidores 2019. El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando se inicia el servidor front-end de Skype empresarial Server 2019 por primera vez. Después, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: 12bb3c29f703287934358f331dc945830e318afb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243714"
---
# <a name="verify-user-replication-has-completed"></a>La comprobación de la replicación de usuarios ha finalizado

Al ejecutar el cmdlet **Move-CsUser** , puede experimentar un error si la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no está sincronizada porque la replicación inicial está incompleta. El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Skype empresarial Server 2019 depende de la cantidad de controladores de dominio que se hospeden en el bosque de Active Directory que aloje Skype empresarial. Grupo de servidores 2019. El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando se inicia el servidor front-end de Skype empresarial Server 2019 por primera vez. Después, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para comprobar que la replicación de usuarios se ha completado

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
2. Haga clic en el menú **Inicio** y, a continuación, en **Ejecutar**. 
    
3. Escriba **eventvwr. exe**y, a continuación, haga clic en **Aceptar**.
    
4. En el visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Skype empresarial Server. 
    
5. En el panel **acciones** , haga clic en **filtrar registro actual**.
    
6. En la lista **orígenes de eventos** , haga clic en replicador de usuarios de **LS**.
    
7. En ** \<todos los\>identificadores de evento**, escriba **30024**y haga clic en **Aceptar**. 
    
8. En la lista eventos filtrados, en la pestaña **General** , busque una entrada que indique que la replicación de usuarios se ha completado correctamente. 
    

