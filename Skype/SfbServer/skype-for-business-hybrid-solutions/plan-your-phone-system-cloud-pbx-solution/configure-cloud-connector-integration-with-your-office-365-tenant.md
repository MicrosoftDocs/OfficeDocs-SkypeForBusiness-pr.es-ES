---
title: Configurar la integración de Cloud Connector con la organización de Microsoft 365 u Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Obtenga información sobre cómo configurar la integración de Cloud Connector con su organización de Microsoft 365 u Office 365.
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359076"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configurar la integración de Cloud Connector con la organización de Microsoft 365 u Office 365

> [!Important] 
> Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Obtenga información sobre cómo configurar la integración de Cloud Connector con su organización de Microsoft 365 u Office 365.
  
Una vez completada la instalación de Skype empresarial Cloud Connector Edition, realice los pasos de esta sección para configurar su implementación y conectarla a la organización de Microsoft 365 u Office 365.
  
## <a name="configure-firewall-settings"></a>Configurar las opciones del firewall

Configure las opciones de Firewall para la configuración del firewall interno y externo de la red perimetral para abrir los puertos necesarios, tal y como se describe en [puertos y protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) en [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurar puertas de enlace de red telefónica conmutada (RTC)

Configure los troncos en cada puerta de enlace RTC para que apunten a los servidores de mediación de todos los dispositivos. Debido a que el FQDN del grupo de servidores es el mismo para todos los servidores del grupo, cada tronco debe apuntar a un FQDN o dirección IP del servidor de mediación en lugar del FQDN del grupo de servidores de mediación. Los troncos deben configurarse con la misma prioridad.
  
Si usa TLS entre los servidores de mediación y las puertas de enlace, tendrá que configurar las puertas de enlace y los servidores de mediación para que admitan MTLS de la siguiente manera:
  
1. Exporte la CA raíz del equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la entidad de certificación raíz.
    
3. Importe el certificado de CA raíz del certificado emitido a la puerta de enlace en los servidores de mediación. Si necesita obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se ejecuta en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
   - Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban. Para obtener instrucciones detalladas, consulte [plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Solicite un certificado con el complemento de certificado seleccionando la plantilla de servidor Web que ha habilitado. Asegúrese de agregar un nombre común en asunto y nombre DNS en nombre alternativo con FQDN de la puerta de enlace y confirme que la clave privada que hace que la clave privada sea exportable está seleccionada en opciones de clave. 
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importar el certificado.
    
## <a name="update-the-domain-for-your-tenant"></a>Actualizar el dominio de su espacio empresarial

Asegúrese de que ha completado los pasos para actualizar el dominio en Microsoft 365 u Office 365 y tiene la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar el dominio en Microsoft 365 u Office 365, consulte [Agregar un dominio a microsoft 365 u office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-for-your-edge"></a>Agregar registros DNS para el servidor perimetral

Agregue los siguientes registros DNS a su organización de Microsoft 365 u Office 365. Para obtener información sobre cómo agregar registros DNS, vea [Agregar o editar registros DNS personalizados en Microsoft 365 u Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Agregar un registro A de DNS para el servidor perimetral de acceso.
    
2. Los registros SRV se crearán automáticamente con Microsoft 365 u Office 365 y los scripts de implementación. Confirme que puede buscar los siguientes dos servicios SIP en el perímetro: \_ SIP y \_ sipfederationtls.
    
     ![Confirmación de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Configurar la conectividad híbrida entre Cloud Connector Edition y Microsoft 365 u Office 365

Para configurar la conectividad híbrida entre su implementación de Skype empresarial Cloud Connector Edition y su organización de Microsoft 365 u Office 365, ejecute el siguiente cmdlet en una sesión remota de PowerShell. Para obtener información sobre cómo establecer una sesión remota de PowerShell, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
El cmdlet establece el FQDN externo del servidor perimetral de acceso. En el primero de los comandos, el \<External Access Edge FQDN\> debe ser el del rol perimetral de acceso SIP. De forma predeterminada, debe ser AP. \<Domain Name\> .
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> El FQDN del servidor perimetral de acceso externo usado para el destino del mismo nivel debe establecerse en un sitio RTC que solo se usará como reserva en caso de que un usuario no esté asignado a un sitio RTC. Para obtener más información, vea [deploy a Single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [deploy Multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurar puertas de enlace RTC

Configure los troncos en cada puerta de enlace RTC para que apunten a los servidores de mediación de todos los dispositivos. Cada tronco debe apuntar a un FQDN o dirección IP del servidor de mediación en lugar del FQDN del grupo de servidores de mediación porque el FQDN del grupo de servidores es el mismo para todos los servidores del grupo. Los troncos deben configurarse con la misma prioridad.
  
Si usa TLS entre los servidores de mediación y las puertas de enlace, tendrá que configurar las puertas de enlace y los servidores de mediación para que admitan MTLS de la siguiente manera:
  
1. Exporte la CA raíz del equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de la puerta de enlace RTC para importar la entidad de certificación raíz.
    
3. Importe el certificado de CA raíz del certificado emitido a la puerta de enlace en los servidores de mediación. Si necesita obtener un certificado SSL para la puerta de enlace, puede hacerlo usando el servicio de entidad de certificación que se ejecuta en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
   - Modifique la plantilla de servidor web existente para permitir a los usuarios autenticados que se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir a los usuarios autenticados que se inscriban. Para obtener instrucciones detalladas, consulte [plantillas de certificado](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Solicite un certificado con el complemento de certificado seleccionando la plantilla de servidor Web que ha habilitado. Asegúrese de agregar un nombre común en asunto y nombre DNS en nombre alternativo con FQDN de la puerta de enlace y confirme que la clave privada que hace que la clave privada sea exportable está seleccionada en opciones de clave. 
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de la puerta de enlace RTC para importar el certificado.
    
5. Las puertas de enlace RTC en un sitio RTC solo deben conectarse a los servidores de mediación en el mismo sitio.
    
## <a name="set-up-your-users"></a>Configurar los usuarios

Inicie sesión en el centro de administración de Microsoft 365, agregue los usuarios que se habilitarán para los servicios de voz en línea y asigne una licencia E5 o un complemento de sistema telefónico a la licencia E3 para estos usuarios. Para obtener información sobre cómo agregar usuarios, consulte [Agregar usuarios a Microsoft 365 para empresas](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Habilitar a los usuarios para los servicios de voz y voz del sistema telefónico
 
Después de agregar los usuarios a Microsoft 365 u Office 365, habilite sus cuentas para los servicios de voz de sistema telefónico, incluido el correo de voz. Para habilitar estas funciones, debe iniciar sesión en su organización de Microsoft 365 u Office 365 con una cuenta que sea un rol de administrador global y que pueda ejecutar PowerShell remoto. Para obtener información sobre cómo establecer una sesión remota de PowerShell, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- Asigne la Directiva a su usuario y configure el número de teléfono de voz empresarial del usuario, que se especifica con el valor del parámetro **Identity** :
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Se puede especificar una identidad de usuario con la dirección SIP del usuario, el nombre principal del usuario (UPN) o el nombre para mostrar de Active Directory del usuario (por ejemplo, "Bob Kelly"). El carácter asterisco ( \* ) también puede usarse con el nombre para mostrar como identidad del usuario. Por ejemplo, la identidad " \* Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor de cadena "Smith".
  
A continuación, puede comprobar que los usuarios se han agregado y habilitado mediante el siguiente script:
  
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

Deberá decidir si los usuarios deben poder realizar llamadas internacionales. De forma predeterminada, la llamada internacional está habilitada. Puede deshabilitar o habilitar a los usuarios para el marcado internacional mediante el centro de administración de Skype empresarial en línea.
  
Para deshabilitar las llamadas internacionales en función de cada usuario, ejecute el siguiente cmdlet en PowerShell de Skype empresarial online:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para volver a habilitar las llamadas internacionales en función de cada usuario después de que se haya deshabilitado, ejecute el mismo cmdlet, pero cambie el valor de **PolicyName** a *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Asignar usuarios a sitios RTC

Use el PowerShell remoto del inquilino para asignar un sitio a los usuarios, incluso si solo implementó un sitio único. Para obtener información sobre cómo establecer una sesión remota de PowerShell, consulte: [configurar el equipo para Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Si no se ha asignado ningún sitio RTC a un usuario, la conectividad híbrida entre su implementación de Skype empresarial Cloud Connector Edition y la organización de Microsoft 365 u Office 365 se revertirá para usar el nivel predeterminado del inquilino (destino del mismo nivel) para que las llamadas se puedan completar. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurar las opciones del servidor de mediación híbrida en línea
<a name="BKMK_ConfigureMediationServer"> </a>

Cuando se escala una llamada P2P a una conferencia RTC, el servidor de conferencia de Skype empresarial online enviará una invitación al servidor de mediación de Cloud Connector. Para asegurarse de que Microsoft 365 u Office 365 puede redirigir esta invitación correctamente, debe configurar una opción de configuración en su inquilino en línea para cada servidor de mediación de Cloud Connector de la siguiente manera: 
  
1. Cree un usuario en el centro de administración de Microsoft 365. Use el nombre de usuario que desee, como "MediationServer1".
    
    Use el dominio SIP predeterminado de Cloud Connector (el primer dominio SIP del archivo. ini) como dominio del usuario.
    
    Tenga en cuenta que la asignación de licencias solo es necesaria para la propagación del usuario en el directorio de Skype empresarial online. Asigne una licencia de Microsoft 365 o de Office 365 (como E5) a la cuenta que cree, deje hasta una hora para que los cambios se propaguen, compruebe que las cuentas de usuario se hayan aprovisionado correctamente en el directorio de Skype empresarial online ejecutando el siguiente cmdlet y, a continuación, quite la licencia de esta cuenta.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Inicie una sesión de PowerShell remoto de Azure AD de inquilino con sus credenciales de administrador global o de usuario y, a continuación, ejecute el siguiente cmdlet para establecer el Departamento de la cuenta de usuario de Azure AD configurada en el paso 1 en "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Inicie una sesión remota de PowerShell de Skype empresarial de inquilino con sus credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para establecer el servidor de mediación y el FQDN del servidor perimetral en esa cuenta de usuario, reemplazando \<DisplayName\> por el nombre para mostrar del usuario para la cuenta que creó en el paso 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Para identidad, use el nombre para mostrar de la cuenta de usuario que ha creado para este servidor de mediación.
    
    Para  *MediationServerFQDN*  , use el FQDN interno definido para el servidor de mediación.
    
    Para  *EdgeServerExternalFQDN*  , use el FQDN externo definido para el proxy de acceso del servidor perimetral. Si hay varios sitios RTC de Cloud Connector, elija el FQDN del proxy de acceso del servidor perimetral asignado al sitio donde se encuentra el servidor de mediación.
    
4. Si hay varios servidores de mediación de Cloud Connector (varios sitios, HA), repita los pasos anteriores para cada uno de ellos.
    
