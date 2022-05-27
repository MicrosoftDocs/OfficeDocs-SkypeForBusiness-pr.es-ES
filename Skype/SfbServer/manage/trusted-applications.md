---
title: Administración de aplicaciones de confianza
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Una aplicación de confianza es una aplicación basada en el SDK de Microsoft Unified Communications Managed API (UCMA) 3.0 Core que es de confianza para Skype Empresarial Server.
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674542"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Administración de aplicaciones de confianza en Skype Empresarial Server

Una *aplicación de confianza* es una aplicación basada en el SDK de Microsoft Unified Communications Managed API (UCMA) 3.0 Core que es de confianza para Skype Empresarial Server. Para obtener más información sobre las aplicaciones UCMA, consulte "Documentación del SDK principal de Unified Communications Managed API 3.0" en https://go.microsoft.com/fwlink/p/?linkId=210320.

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como usuario miembro de los grupos Administradores del dominio y RTCUniversalServerAdmins. 

Use este artículo para aprender a configurar un nuevo servidor de aplicaciones de confianza, ver una lista de aplicaciones de confianza y ver información de aplicaciones de confianza. 

## <a name="configure-a-new-trusted-application-server"></a>Configuración de un nuevo servidor de aplicaciones de confianza

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Iniciar generador de topologías: haga clic en **Inicio**, todos **los programas**, **Skype Empresarial Server** y, a continuación, haga clic en **Skype Empresarial Server Generador de topologías**.

3.  Seleccione **Descargar topología de la implementación existente** y haga clic en **Aceptar**.

4.  En el cuadro **de diálogo Guardar topología como** , haga clic en el archivo del Generador de topologías que desea usar y, a continuación, haga clic en **Guardar**.

5.  En el panel izquierdo, haga clic con el botón derecho en **Servidores de aplicaciones de confianza** y, a continuación, haga clic en **Nuevo grupo de aplicaciones de confianza**.

6.  Escriba elFQDN del grupo de servidores del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o varios servidores y haga clic en **Siguiente**.

7.  En la página **Seleccionar el próximo salto**, en la lista, seleccione el grupo de servidores front-end Skype Empresarial Server.

8.  Haga clic en **Finalizar**.

9.  Seleccione el nodo superior **Skype Empresarial Server** y, a continuación, en el menú **Acciones**, haga clic en **Publicar topología**.
    
    El **grupo de aplicaciones de confianza** debe haberse creado correctamente y asociarse al grupo de servidores front-end correcto.


## <a name="view-a-list-of-trusted-applications"></a>Ver una lista de aplicaciones de confianza

Puede usar la Skype Empresarial Server Panel de control para ver una lista de las aplicaciones de confianza que ha implementado en el entorno de Skype Empresarial Server. Una aplicación de confianza es una aplicación basada en el SDK de Microsoft Unified Communications Managed API (UCMA) 3.0 Core que es de confianza para Skype Empresarial Server. Esta relación de confianza se resume en la lista siguiente:

  - Las aplicaciones de confianza no son desafiadas para la autenticación por Skype Empresarial Server.

  - Las aplicaciones de confianza no están limitadas por Skype Empresarial Server para transacciones SIP, conexiones o llamadas salientes de Voz a través de Internet (VoIP).

  - Las aplicaciones de confianza pueden suplantar a cualquier usuario y pueden unirse a conferencias sin aparecer en listas.

  - Las aplicaciones de confianza son de alta disponibilidad y resistentes.

En el Skype Empresarial Server Panel de control, puede ver el nombre de las aplicaciones, el grupo donde se ejecutan y el puerto que usan.


### <a name="to-view-a-list-of-trusted-applications"></a>Para ver una lista de aplicaciones de confianza

1.  Desde una cuenta de usuario asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk, o CsViewOnlyAdministrator , inicie sesión en cualquier equipo de su implementación interna. Para obtener más información sobre los roles administrativos predefinidos disponibles en Skype Empresarial Server, consulte [Control de acceso basado en rol (RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Abra una ventana del explorador y escriba la dirección URL de Administración para abrir el Skype Empresarial Server Panel de control.

3.  En la barra de navegación izquierda, haga clic en **Topologíay**, a continuación, haga clic en **Aplicación de confianza**.

4.  En la página **Aplicación de confianza** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario.


## <a name="view-trusted-application-information"></a>Visualización de información de aplicaciones de confianza

Puede ver información sobre las aplicaciones de confianza mediante Windows PowerShell y el cmdlet **Get-CsTrustedApplication**. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver aplicaciones de confianza

Para ver todas las aplicaciones de confianza, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
   **Get-CsConferenceDisclaimer**
    
   Este comando devuelve información similar a la siguiente para cada aplicación de confianza:
    
   Identidad: CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Contactos de aplicación,CN=Servicio RTC,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool : 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn: urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   Displayname:<br/>
   DisplayNumber :<br/>
   LineURI :<br/>
   PrimaryLanguage: 0<br/>
   SecondaryLanguages : {}<br/>
   EnterpriseVoiceEnabled: True<br/>
   ExUmEnabled: False<br/>
   Enabled : True<br/>
    
   Para obtener más información, consulte [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).