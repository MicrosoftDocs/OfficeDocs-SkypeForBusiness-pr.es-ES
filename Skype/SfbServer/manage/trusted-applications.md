---
title: Administrar aplicaciones de confianza
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Una aplicación de confianza es una aplicación basada en microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que es de confianza para Skype Empresarial Server.
ms.openlocfilehash: e9d29371014d902bbee38e2f3871c5579634c0f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826280"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Administrar aplicaciones de confianza en Skype Empresarial Server

Una *aplicación de confianza* es una aplicación basada en microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que es de confianza para Skype Empresarial Server. Para obtener más información acerca de las aplicaciones UCMA, consulte "Unified Communications Managed API 3.0 Core SDK Documentation" en https://go.microsoft.com/fwlink/p/?linkId=210320 .

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como usuario miembro de los grupos Administradores del dominio y RTCUniversalServerAdmins. 

Use este artículo para obtener información sobre cómo configurar un nuevo servidor de aplicaciones de confianza, ver una lista de aplicaciones de confianza y ver información de aplicaciones de confianza. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar un nuevo servidor de aplicaciones de confianza

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el Generador de topologías: **Haga** clic en Inicio, Todos los **programas,** Skype Empresarial **Server** y, a continuación, haga clic en Generador de topologías de Skype Empresarial **Server.**

3.  Seleccione **Descargar topología de la implementación existente** y haga clic en **Aceptar**.

4.  En el **cuadro de diálogo Guardar topología** como, haga clic en el archivo del Generador de topologías que desea usar y, a continuación, haga clic en **Guardar**.

5.  En el panel izquierdo, haga clic con el botón secundario en **Servidores de** aplicaciones de confianza y, a continuación, haga clic en Nuevo grupo de aplicaciones **de confianza.**

6.  Escriba elFQDN del grupo de servidores del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o varios servidores y haga clic en **Siguiente**.

7.  En la **página Seleccionar el próximo salto,** en la lista, seleccione el grupo de servidores front-end de Skype Empresarial Server.

8.  Haga clic en **Finalizar**.

9.  Seleccione el nodo superior **Skype Empresarial Server**  y, a continuación, en el menú Acciones, haga clic en **Publicar topología.**
    
    El **grupo de aplicaciones de confianza** debe haber sido creado correctamente y asociado con el grupo de servidores front-end correcto.


## <a name="view-a-list-of-trusted-applications"></a>Ver una lista de aplicaciones de confianza

Puede usar el Panel de control de Skype Empresarial Server para ver una lista de las aplicaciones de confianza que ha implementado en su entorno de Skype Empresarial Server. Una aplicación de confianza es una aplicación basada en microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que es de confianza para Skype Empresarial Server. Esta relación de confianza se resume en la siguiente lista:

  - Skype Empresarial Server no impugna la autenticación de las aplicaciones de confianza.

  - Skype Empresarial Server no limita las aplicaciones de confianza para las transacciones SIP, las conexiones o las llamadas salientes del Protocolo de voz sobre Internet (VoIP).

  - Las aplicaciones de confianza pueden suplantar a cualquier usuario y pueden unirse a conferencias sin aparecer en las listas.

  - Las aplicaciones de confianza son altamente disponibles y resistentes.

En el Panel de control de Skype Empresarial Server, puede ver el nombre de las aplicaciones, el grupo donde se ejecutan y el puerto que usan.


### <a name="to-view-a-list-of-trusted-applications"></a>Para ver una lista de aplicaciones de confianza

1.  Desde una cuenta de usuario asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk, o CsViewOnlyAdministrator , inicie sesión en cualquier equipo de su implementación interna. Para obtener más información sobre los roles administrativos predefinidos disponibles en Skype Empresarial Server, consulte Control de acceso basado [en roles (RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.

3.  En la barra de navegación izquierda, haga clic **en Topología** y, a continuación, en Aplicación **de confianza.**

4.  En la **página Aplicación de** confianza, haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario.


## <a name="view-trusted-application-information"></a>Ver información de la aplicación de confianza

Puede ver información sobre las aplicaciones de confianza con Windows PowerShell y el cmdlet **Get-CsTrustedApplication.** Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver aplicaciones de confianza

Para ver todas las aplicaciones de confianza, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
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
    
   Para obtener más información, [consulte Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
