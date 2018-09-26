---
title: Comprobar la replicación de usuarios ha completado
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cuando se ejecuta el cmdlet Move-CsUser, puede experimentar un error debido a que la información de usuario entre los servicios de dominio de Active Directory (AD DS) y el Skype para bases de datos de negocio Server 2019 están sincronizados debido a que la replicación inicial está incompleta. El tiempo necesario para la finalización correcta de la Skype para la sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el Skype para la empresa Grupo de servidores de servidor 2019. El Skype para el proceso de sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 se produce cuando se inicia el Skype para profesionales de 2019 Front-End Server por primera vez. Después de, la sincronización, a continuación, se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar la replicación de usuarios ha completado antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: 43b2822303676d209dc14a3b2e06368a7d24e174
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027847"
---
# <a name="verify-user-replication-has-completed"></a>Comprobar la replicación de usuarios ha completado

Cuando se ejecuta el cmdlet **Move-CsUser** , puede experimentar un error si la información de usuario entre los servicios de dominio de Active Directory (AD DS) y el Skype para bases de datos de negocio Server 2019 está sincronizado debido a que la replicación inicial está incompleta. El tiempo necesario para la finalización correcta de la Skype para la sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el Skype para la empresa Grupo de servidores de servidor 2019. El Skype para el proceso de sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 se produce cuando se inicia el Skype para profesionales de 2019 Front-End Server por primera vez. Después de, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuarios ha completado antes de ejecutar el cmdlet **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para comprobar que la replicación de usuarios ha completado

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
2. Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**. 
    
3. Escriba **eventvwr.exe**y, a continuación, haga clic en **Aceptar**.
    
4. En el Visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Skype para Business Server. 
    
5. En el panel **acciones** , haga clic en **Filtrar registro actual**.
    
6. En la lista de **orígenes de eventos** , haga clic en **LS User Replicator**.
    
7. En ** \<todos los identificadores de evento\>**, escriba **30024**y, a continuación, haga clic en **Aceptar**. 
    
8. En la lista de eventos filtrados, en la ficha **General** , busque una entrada que indica que la replicación de usuario se ha completado correctamente. 
    

