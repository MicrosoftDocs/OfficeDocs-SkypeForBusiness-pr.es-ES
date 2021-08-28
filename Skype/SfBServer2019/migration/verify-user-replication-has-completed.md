---
title: La comprobación de la replicación del usuario ha finalizado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Al ejecutar el cmdlet Move-CsUser, puede experimentar un error porque la información de usuario entre los Servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype Empresarial Server 2019 no están sincronizadas porque la replicación inicial está incompleta. El tiempo necesario para completar correctamente la sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 depende del número de controladores de dominio hospedados en el bosque de Active Directory que hospeda el grupo de servidores de Skype Empresarial Server 2019. El Skype Empresarial Server de sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 se produce cuando se inicia por primera vez el servidor front-end de Skype Empresarial Server 2019. Tras ello, la sincronización se basa en el intervalo del replicador de usuarios. Realice los siguientes pasos para verificar que se haya completado la replicación de usuario antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: 893702b18b376edc32e946998aeead122bf3ed68
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599705"
---
# <a name="verify-user-replication-has-completed"></a>La comprobación de la replicación del usuario ha finalizado

Al ejecutar el cmdlet **Move-CsUser,** puede experimentar un error si la información de usuario entre los Servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype Empresarial Server 2019 no están sincronizadas porque la replicación inicial está incompleta. El tiempo necesario para completar correctamente la sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 depende del número de controladores de dominio hospedados en el bosque de Active Directory que hospeda el grupo de servidores de Skype Empresarial Server 2019. El Skype Empresarial Server de sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 se produce cuando se inicia por primera vez el servidor front-end de Skype Empresarial Server 2019. Después, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación del usuario se ha completado antes de ejecutar el cmdlet **Move-CsUser.** 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para comprobar que la replicación de usuarios se ha completado

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    
2. Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**. 
    
3. Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.
    
4. En el Visor de eventos, **haga clic en Registros de aplicaciones** y servicios para expandirlo y, a continuación, seleccione Skype Empresarial Server. 
    
5. En el panel **Acciones**, haga clic en **Filtrar registro actual**.
    
6. En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.
    
7. En **\<All Event IDs\>** , escriba **30024** y, a continuación, haga clic en **Aceptar**. 
    
8. En la lista de eventos filtrados, en la **pestaña General,** busque una entrada que indica que la replicación del usuario se ha completado correctamente. 
    

