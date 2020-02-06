---
title: Administrar aplicaciones de confianza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Una aplicación de confianza es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Skype empresarial Server.
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817081"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Administrar aplicaciones de confianza en Skype empresarial Server

Una *aplicación de confianza* es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Skype empresarial Server. Para obtener más información acerca de las aplicaciones de UCMA, consulte "documentación de SDK de comunicaciones http://go.microsoft.com/fwlink/p/?linkId=210320unificadas de la API de Core 3,0" en.

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins. 

Use este artículo para aprender a configurar un nuevo servidor de aplicaciones de confianza, ver una lista de aplicaciones de confianza y ver la información de la aplicación de confianza. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar un nuevo servidor de aplicaciones de confianza

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Skype empresarial Server**y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.

3.  Seleccione **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.

4.  En el cuadro de diálogo **Guardar topología como** , haga clic en el archivo del generador de topología que desea usar y, a continuación, haga clic en **Guardar**.

5.  En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza**y luego haga clic en **nuevo grupo de aplicaciones de confianza**.

6.  Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o de varios servidores y, a continuación, haga clic en **siguiente**.

7.  En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end de Skype empresarial Server.

8.  Haga clic en **Finalizar**.

9.  Seleccione el nodo superior de **Skype empresarial Server**y, a continuación, en el menú **acciones** , haga clic en **publicar topología**.
    
    El **grupo de aplicaciones de confianza** se creó correctamente y se asoció con el grupo de servidores front-end correcto.


## <a name="view-a-list-of-trusted-applications"></a>Ver una lista de aplicaciones de confianza

Puede usar el panel de control de Skype empresarial Server para ver una lista de las aplicaciones de confianza que ha implementado en su entorno de Skype empresarial Server. Una aplicación de confianza es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Skype empresarial Server. Esta relación de confianza se resume en la siguiente lista:

  - Las aplicaciones de confianza no son desafiadas para la autenticación por parte de Skype empresarial Server.

  - Skype empresarial Server no limita las aplicaciones de confianza para las transacciones SIP, las conexiones o las llamadas salientes de protocolo de voz a través de Internet (VoIP).

  - Las aplicaciones de confianza pueden suplantar a cualquier usuario y pueden unirse a conferencias sin aparecer en las listas.

  - Las aplicaciones de confianza son altamente disponibles y resistentes.

En el panel de control de Skype empresarial Server, puede ver el nombre de las aplicaciones, el grupo donde se ejecutan y el puerto que usan.


### <a name="to-view-a-list-of-trusted-applications"></a>Para ver una lista de aplicaciones de confianza

1.  Inicie sesión en cualquier equipo en la implementación interna desde una cuenta de usuario que esté asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator. Para más información sobre los roles administrativos predefinidos disponibles en Skype empresarial Server, consulte [control de acceso basado en roles (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3.  En la barra de navegación izquierda, haga clic en **topología**y, a continuación, haga clic en **aplicación de confianza**.

4.  En la página de la **aplicación de confianza** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario.


## <a name="view-trusted-application-information"></a>Ver información de la aplicación de confianza

Puede ver información sobre sus aplicaciones de confianza mediante Windows PowerShell y el cmdlet **Get-CsTrustedApplication** . Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver las aplicaciones de confianza

Para ver todas las aplicaciones de confianza, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
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
    
   Para obtener más información, vea [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
