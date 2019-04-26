---
title: Administrar las aplicaciones de confianza
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Una aplicación de confianza es una aplicación basada en Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que es de confianza Skype para Business Server.
ms.openlocfilehash: 3ca8621148a4b6ce3530f23a61312f63f3d3cd30
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214676"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Administrar las aplicaciones de confianza en Skype para Business Server

Una *aplicación de confianza* es una aplicación basada en Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que es de confianza Skype para Business Server. Para obtener información detallada acerca de las aplicaciones de UCMA, consulte "Unified Communications Managed API 3.0 principales documentación del SDK" en http://go.microsoft.com/fwlink/p/?linkId=210320.

Para publicar correctamente, habilitar o deshabilitar una topología al agregar o quitar una función de servidor, debe iniciar sesión como un usuario que sea miembro de los grupos RTCUniversalServerAdmins y administradores de dominio. 

Use este artículo para obtener información sobre cómo configurar un nuevo servidor de aplicaciones de confianza, ver una lista de las aplicaciones de confianza y ver la información de aplicaciones de confianza. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar un nuevo servidor de aplicaciones de confianza

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Business Server Topology Builder**.

3.  Seleccione **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.

4.  En el cuadro de diálogo **Guardar topología como** , haga clic en el archivo de generador de topología que desea usar y, a continuación, haga clic en **Guardar**.

5.  En el panel izquierdo, haga clic en **servidores de aplicaciones de confianza**y, a continuación, haga clic en **Nuevo grupo de aplicaciones de confianza**.

6.  Escriba el **FQDN del grupo de servidores** del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o varios servidores y, a continuación, haga clic en **siguiente**.

7.  En la página **Seleccionar el próximo salto** , en la lista, seleccione el Skype para grupo de negocio de servidor Front-End.

8.  Haga clic en **Finalizar**.

9.  Seleccione el nodo superior **Skype para Business Server**y, a continuación, en el menú **acciones** , haga clic en **Publicar topología**.
    
    El **Grupo de aplicaciones de confianza** debe se ha creado correctamente y asociado con el grupo de servidores Front-End correcto.


## <a name="view-a-list-of-trusted-applications"></a>Ver una lista de las aplicaciones de confianza

Puede usar el Skype para el Panel de Control de servidor empresarial para ver una lista de las aplicaciones de confianza que ha implementado en su Skype para el entorno de servidor empresarial. Una aplicación de confianza es una aplicación basada en Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que es de confianza Skype para Business Server. Esta relación de confianza se resume en la siguiente lista:

  - Las aplicaciones de confianza no son desafiadas para la autenticación por Skype para Business Server.

  - Las aplicaciones de confianza no limita a Skype para Business Server para las transacciones SIP, las conexiones ni salientes de voz a través de las llamadas del protocolo de Internet (VoIP).

  - Las aplicaciones de confianza pueden suplantar a cualquier usuario y pueden participar en conferencias sin aparecer en.

  - Las aplicaciones de confianza son gran disponibilidad y resistencia.

En Skype para el Panel de Control de servidor empresarial, puede ver el nombre de las aplicaciones, el grupo de servidores que se ejecutan y el puerto que usan.


### <a name="to-view-a-list-of-trusted-applications"></a>Para ver una lista de aplicaciones de confianza

1.  Inicie sesión en cualquier equipo en la implementación interna desde una cuenta de usuario que esté asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator. Para obtener información detallada acerca de las funciones administrativas predefinidas disponibles en Skype para Business Server, vea [control de acceso basado en roles (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3.  En la barra de navegación izquierda, haga clic en **topología**y, a continuación, haga clic en **Aplicación de confianza**.

4.  En la página de **Aplicación de confianza** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario.


## <a name="view-trusted-application-information"></a>Ver la información de aplicaciones de confianza

Puede ver información acerca de las aplicaciones de confianza mediante Windows PowerShell y el cmdlet **Get-CsTrustedApplication** . Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver las aplicaciones de confianza

Para ver todas las aplicaciones de confianza, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsConferenceDisclaimer
    
   Este comando devuelve información similar a la siguiente para cada aplicación de confianza:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   Para obtener información detallada, vea [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
