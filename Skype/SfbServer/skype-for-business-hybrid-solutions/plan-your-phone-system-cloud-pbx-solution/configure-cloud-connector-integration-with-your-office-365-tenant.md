---
title: Configurar la integración de Cloud Connector con el inquilino de Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Aprenda a configurar la integración de la nube de conector con el inquilino de Office 365.
ms.openlocfilehash: c8e74353bc9b1201d8e4ff11f27a3542f24cb373
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configurar la integración de Cloud Connector con el inquilino de Office 365
 
Aprenda a configurar la integración de la nube de conector con el inquilino de Office 365.
  
Una vez completada la instalación de Skype Empresarial Cloud Connector Edition, lleve a cabo los pasos detallados en esta sección para configurar su implementación y conectarla con el inquilino de Office 365.
  
## <a name="configure-firewall-settings"></a>Establecer la configuración del firewall

Configurar el firewall para la configuración del firewall interno y externo para la red perimetral abrir los puertos necesarios según se describe en los [puertos y protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) en el [Plan de Skype para conector de nube Business Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurar las puertas de enlace para la red telefónica conmutada (RTC)

Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o el FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.
  
Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:
  
1. Exporte la CA raíz del equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.
    
3. Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
  - Modificar la plantilla de servidor Web existente para permitir a los usuarios autenticados inscribir o crear una nueva plantilla de servidor Web para configurar otras propiedades y permiten a los usuarios autenticados para inscribirse. Para obtener instrucciones detalladas, consulte [Plantillas de certificado](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
  - Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado. Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave. Para obtener instrucciones detalladas, vea [Solicitar un certificado](https://technet.microsoft.com/en-us/library/cc730689.aspx).
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.
    
## <a name="update-the-domain-for-your-tenant"></a>Actualizar el dominio del inquilino

Asegúrese de haber completado los pasos para actualizar el dominio en Office 365 y de tener la capacidad para agregar registros DNS. Para obtener más información acerca de cómo configurar tu dominio en Office 365, consulte [vídeo: configurar tu dominio en Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Agregar registros DNS en Office 365 desde el perímetro

Agregue los siguientes registros DNS a su inquilino de Office 365. Para obtener información acerca de cómo agregar registros DNS para los clientes de Office 365, consulte [Agregar o editar registros DNS personalizados en Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Agregar un registro A de DNS para el acceso perimetral.
    
2. Office 365 y los scripts de implementación crearán automáticamente registros SRV. Confirme que puede buscar los siguientes dos servicios SIP en el perímetro: _sip y _sipfederationtls.
    
     ![Confirmación de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configuración de la conectividad híbrida entre Cloud Connector Edition y Office 365

Para configurar la conectividad híbrida entre su Skype para la implementación del conector de nube Business Edition y los inquilinos de Office 365, ejecute el siguiente cmdlet en una sesión remota de PowerShell. Para aprender a establecer una sesión remota de PowerShell, vea: [Usar Windows PowerShell para administrar Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
El cmdlet establece los FQDN externos para el servidor perimetral de acceso. En el primero de los comandos, el \<nombre completo externo borde de acceso\> debe ser el de la función de servidor perimetral de acceso SIP. De forma predeterminada, éste debe ser ap.\<nombre de dominio\>.
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> El nombre completo externo de borde de acceso de destino del mismo nivel debe establecerse en un sitio PSTN que sólo se utilizará como reserva en caso de que un usuario no está asignado a un sitio de RTC. Para obtener más información, vea [implementar un único sitio en nube conector](deploy-a-single-site-in-cloud-connector.md) e [implementar varios sitios en el conector de la nube](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurar las puertas de enlace RTC

Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o al FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.
  
Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:
  
1. Exporte la CA raíz del equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.
    
3. Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
  - Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban. Para obtener instrucciones detalladas, consulte [Plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).
    
  - Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado. Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave. Para obtener instrucciones detalladas, vea [Solicitar un certificado](https://technet.microsoft.com/library/cc730689.aspx).
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.
    
5. Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente con los servidores de mediación en el mismo sitio.
    
## <a name="set-up-your-users-in-office-365"></a>Configurar usuarios en Office 365

Inicie sesión en el portal de administración de Office 365, agregue los usuarios que estarán habilitados para servicios de voz en línea y asignar una licencia E5 o sistema de teléfono en el complemento de Office 365 a la licencia de E3 a estos usuarios. Para obtener información sobre cómo agregar usuarios, consulte [Adición de usuarios a Office 365 para el negocio](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Permitir a los usuarios para el sistema de teléfono de servicios de voz y correo de voz de Office 365

Después de agregar los usuarios a Office 365, habilitar sus cuentas para el sistema de teléfono de servicios de voz de Office 365, incluido el correo de voz. Para habilitar estas funcionalidades, debe iniciar sesión en el inquilino de Office 365 con una cuenta que sea del rol de administrador global de Office 365 y debe poder ejecutar PowerShell remoto. Para aprender a establecer una sesión remota de PowerShell, vea: [Usar Windows PowerShell para administrar Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Asignar la directiva al usuario y configure voz número de teléfono profesional el usuario, que se especifica con el valor del parámetro **Identity** :
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > También puede especificar la identidad de un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Guillermo Rodarte").  
  
Después puede comprobar si se agregaron los usuarios y si se los habilitó con el siguiente script:
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

Tendrá que decidir si los usuarios deberán tener la capacidad de realizar llamadas internacionales, lo que está habilitado de manera predeterminada. Puede habilitar o deshabilitar el marcado internacional para los usuarios con el centro de administración en línea de Skype Empresarial.
  
Para deshabilitar las llamadas internacionales para cada usuario en particular, ejecute el siguiente cmdlet en el PowerShell de Skype Empresarial Online:
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para volver a habilitar internacional de una llamada a cada usuario una vez que se ha deshabilitado, ejecute el cmdlet de la mismo, pero cambie el valor de **PolicyName** a *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Asignar usuarios a sitios de RTC

Use el PowerShell remoto del inquilino para asignar un sitio a los usuarios, aunque haya implementado solo un único sitio. Para aprender a establecer una sesión remota de PowerShell, vea: [Usar Windows PowerShell para administrar Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Si no se asigna ningún sitio de RTC a un usuario, la conectividad híbrida entre la implementación de Skype Empresarial Cloud Connector Edition y el inquilino de Office 365 volverá a usar el valor predeterminado uno del nivel del inquilino (Peer Destination) para que puedan completarse las llamadas. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configuración de las opciones del servidor de mediación híbrido en línea
<a name="BKMK_ConfigureMediationServer"> </a>

Cuando una llamada P2P se remite a una conferencia de RTC, el Skype para los negocios en línea conferencing server enviará una invitación para el servidor de mediación de conector de nube. Para asegurarse de que Office 365 puede enrutar correctamente esta invitación, necesitará configurar una opción en el arrendatario en línea para cada servidor de mediación de conector de nube como sigue: 
  
1. Cree un usuario en el portal de administración de Office 365. Utilizar cualquier nombre de usuario que desee, como "MediationServer1".
    
    Utilice el dominio SIP predeterminado del conector de la nube (el primer dominio SIP en el archivo .ini) como el dominio del usuario.
    
    No asigne ninguna licencia de Office 365 (como E5) a la cuenta que cree. Espere a que la sincronización de AD de Office 365 se complete.
    
2. Iniciar una sesión de PowerShell remota de inquilinos utilizando sus credenciales de administrador de inquilinos y ejecute el siguiente cmdlet para configurar el servidor de mediación y el FQDN del servidor de borde para que el usuario de cuenta, reemplazar \<DisplayName\> con el nombre para mostrar del usuario para el cuenta creada:
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    Para Identity, use el nombre para mostrar de la cuenta de usuario de Office 365 que haya creado para este servidor de mediación.
    
    Para *MediationServerFQDN* , utilice el FQDN interno definido para el servidor de mediación.
    
    Para *EdgeServerExternalFQDN* , utilice el nombre completo externo definido para el servidor Proxy de acceso del servidor de borde. Si existen varios sitios RTC de Cloud Connector, elija el FQDN del proxy de acceso de servidor perimetral asignado al sitio donde se encuentra el servidor de mediación.
    
3. Si hay varios servidores de mediación de Cloud Connector (varios sitios, HA), repita los pasos anteriores para cada uno de ellos.
    

