---
title: Configurar la integración de Cloud Connector con el inquilino de Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Aprenda a configurar la integración de conector de nube con su inquilino de Office 365.
ms.openlocfilehash: ed9437026ddbae07aadbe81585886ed0cb5cb0cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002860"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configure Cloud Connector integration with your Office 365 tenant
 
Aprenda a configurar la integración de conector de nube con su inquilino de Office 365.
  
Una vez completada la instalación de Skype Empresarial Cloud Connector Edition, lleve a cabo los pasos detallados en esta sección para configurar su implementación y conectarla con el inquilino de Office 365.
  
## <a name="configure-firewall-settings"></a>Establecer la configuración del firewall

Configure las opciones de Firewall para la configuración de su firewall interno y externo en la red perimetral para abrir los puertos necesarios, tal y como se describe en [puertos y protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) en [Plan for Skype empresarial Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurar las puertas de enlace para la red telefónica conmutada (RTC)

Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o el FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.
  
Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:
  
1. Exporte la CA raíz del equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.
    
3. Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
   - Modifique la plantilla de servidor web existente para permitir que los usuarios autenticados inscriban o creen una nueva plantilla de servidor web para configurar otras propiedades y permitir la inscripción de usuarios autenticados. Para obtener instrucciones detalladas, consulte [plantillas de certificado](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
   - Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado. Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave. 
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.
    
## <a name="update-the-domain-for-your-tenant"></a>Actualizar el dominio del inquilino

Asegúrese de haber completado los pasos para actualizar el dominio en Office 365 y de tener la capacidad para agregar registros DNS. Para obtener más información sobre cómo configurar su dominio en Office 365, vea [Agregar un dominio a office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Agregar registros DNS en Office 365 desde el perímetro

Agregue los siguientes registros DNS a su inquilino de Office 365. Para obtener información sobre cómo agregar registros DNS a su inquilino de Office 365, vea [Agregar o editar registros DNS personalizados en office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Agregar un registro A de DNS para el acceso perimetral.
    
2. Office 365 y los scripts de implementación crearán automáticamente registros SRV. Confirme que puede buscar los siguientes dos servicios SIP en el perímetro: _sip y _sipfederationtls.
    
     ![Confirmación de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configuración de la conectividad híbrida entre Cloud Connector Edition y Office 365

Para configurar la conectividad híbrida entre la implementación de Skype empresarial Cloud Connector Edition y su inquilino de Office 365, ejecute el siguiente cmdlet en una sesión de PowerShell remota. Para obtener información sobre cómo establecer una sesión de PowerShell remota, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
El cmdlet establece los FQDN externos para el servidor perimetral de acceso. En el primero de los comandos, el \<FQDN\> del perímetro de acceso externo debe ser el de la función perimetral de acceso de SIP. De forma predeterminada, debe ser AP.\<Domain Name\>.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> El FQDN de Edge de acceso externo usado para el destino del mismo nivel debe establecerse en un sitio RTC que solo se usará como reserva en caso de que no se haya asignado a un usuario a un sitio RTC. Para obtener más información, consulte [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) y [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurar las puertas de enlace RTC

Configure los troncos en cada puerta de enlace RTC para que apunten de nuevo a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a la dirección IP o al FQDN de un servidor de mediación en lugar de al FQDN del grupo de servidores de mediación, porque este es el mismo para todos los servidores del grupo. Debe configurarse el mismo nivel de prioridad para los troncos.
  
Si está usando TLS entre los servidores de mediación y las puertas de enlace, deberá configurarlos para que admitan MTLS de la siguiente manera:
  
1. Exporte la CA raíz del equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la CA raíz.
    
3. Importe el certificado de la CA raíz para aquel que fuera emitido para su puerta de enlace en los servidores de mediación. Si tiene que obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se esté ejecutando en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
   - Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban. Para obtener instrucciones detalladas, consulte [plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Solicite un certificado con el complemento para certificados seleccionando la plantilla de servidor web que haya habilitado. Asegúrese de agregar Nombre común en Asunto y Nombre DNS en Nombre alternativo con el FQDN de la puerta de enlace, y confirme en Clave privada que Hacer exportable la clave privada esté seleccionada en las opciones de clave. 
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importarlo.
    
5. Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente con los servidores de mediación en el mismo sitio.
    
## <a name="set-up-your-users-in-office-365"></a>Configurar usuarios en Office 365

Inicie sesión en el portal de administración de Office 365, agregue los usuarios que se habilitarán para los servicios de voz en línea y asigne una licencia o sistema telefónico de E5 en el complemento de Office 365 a la licencia E3 para estos usuarios. Para obtener información sobre cómo agregar usuarios, consulte [Agregar usuarios a Office 365 para empresas](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Habilitar usuarios para el sistema telefónico en los servicios de voz y correo de voz de Office 365

Después de agregar los usuarios a Office 365, habilite sus cuentas para el sistema telefónico en los servicios de voz de Office 365, incluido el buzón de voz. Para habilitar estas funcionalidades, debe iniciar sesión en el inquilino de Office 365 con una cuenta que sea del rol de administrador global de Office 365 y debe poder ejecutar PowerShell remoto. Para obtener más información sobre cómo establecer una sesión remota de PowerShell, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Asigne la Directiva al usuario y configure el número de teléfono de la voz empresarial del usuario, que se especifica con el valor del parámetro **Identity** :
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Una identidad de usuario se puede especificar mediante la dirección SIP del usuario, el nombre principal de usuario (UPN) o el nombre para mostrar de Active Directory del usuario (por ejemplo, "Bob Kelly"). El carácter asterisco\*() también se puede usar con el nombre para mostrar como la identidad del usuario. Por ejemplo, la identidad "\*Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor de cadena "Smith".
  
Después puede comprobar si se agregaron los usuarios y si se los habilitó con el siguiente script:
  
```powershell
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
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para volver a habilitar las llamadas internacionales por usuario, después de haberla deshabilitado, ejecute el mismo cmdlet, pero cambie el valor de **PolicyName** a *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Asignar usuarios a sitios de RTC

Use el PowerShell remoto del inquilino para asignar un sitio a los usuarios, aunque haya implementado solo un único sitio. Para obtener información sobre cómo establecer una sesión de PowerShell remota, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
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

Cuando se transfiere una llamada P2P a una conferencia RTC, el servidor de conferencia de Skype empresarial online enviará una invitación al servidor de servicios de conexión en la nube. Para asegurarse de que Office 365 pueda enrutar esta invitación correctamente, debe configurar una opción de configuración en su inquilino en línea para cada servidor de mediación de conector en la nube de la siguiente manera: 
  
1. Cree un usuario en el portal de administración de Office 365. Use el nombre de usuario que desee, como "MediationServer1".
    
    Use el dominio SIP predeterminado del conector de nube (el primer dominio SIP del archivo. ini) como dominio de usuario.
    
    Tenga en cuenta que la asignación de licencias solo es necesaria para la propagación del usuario en el directorio de Skype empresarial online. Asigne una licencia de Office 365 (como E5) a la cuenta que cree, espere hasta una hora para que se propaguen los cambios, compruebe que las cuentas de usuario se hayan aprovisionado correctamente en el directorio de Skype empresarial online ejecutando el siguiente cmdlet y, a continuación, quite el licencia de esta cuenta.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Inicie una sesión de PowerShell remoto de Azure AD de inquilino con sus credenciales de administrador global o de usuario y, a continuación, ejecute el siguiente cmdlet para establecer el Departamento de la cuenta de usuario de Azure AD configurada en el paso 1 en "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Inicie una sesión de PowerShell en un inquilino de Skype empresarial remoto con sus credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para configurar el servidor de mediación y el FQDN del servidor perimetral a esa cuenta de usuario, sustituyendo \<DisplayName\> por el nombre para mostrar del usuario para la cuenta que creó en el paso 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Para Identity, use el nombre para mostrar de la cuenta de usuario de Office 365 que haya creado para este servidor de mediación.
    
    Para *MediationServerFQDN* , use el nombre completo interno definido para el servidor de mediación.
    
    Para *EdgeServerExternalFQDN* , use el nombre completo externo definido para el proxy de acceso del servidor perimetral. Si existen varios sitios RTC de Cloud Connector, elija el FQDN del proxy de acceso de servidor perimetral asignado al sitio donde se encuentra el servidor de mediación.
    
4. Si hay varios servidores de mediación de Cloud Connector (varios sitios, HA), repita los pasos anteriores para cada uno de ellos.
    

