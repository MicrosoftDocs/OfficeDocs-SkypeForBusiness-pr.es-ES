---
title: Configurar la integración de Cloud Connector con su Microsoft 365 o Office 365 organización
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Obtenga información sobre cómo configurar la integración de Cloud Connector con su Microsoft 365 o Office 365 organización.
ms.openlocfilehash: 5e6cf8033a4207b79ff2f7d0915849b19eec2b65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628532"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configurar la integración de Cloud Connector con su Microsoft 365 o Office 365 organización

> [!Important] 
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams enrutamiento [directo](/MicrosoftTeams/direct-routing-landing-page).

Obtenga información sobre cómo configurar la integración de Cloud Connector con su Microsoft 365 o Office 365 organización.
  
Una vez Skype for Business Edición de conector de nube instalación, siga los pasos de esta sección para configurar la implementación y conectarla a su Microsoft 365 o Office 365 organización.
  
## <a name="configure-firewall-settings"></a>Configurar la configuración del firewall

Configure las opciones de firewall para la configuración del firewall interno y externo para que la red perimetral abra los puertos necesarios, como se describe en Puertos y [protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) en [Plan for Skype for Business Edición de conector de nube](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurar puertas de enlace de red telefónica conmutada (RTC)

Configure troncos en cada puerta de enlace RTC para que apunten a los servidores de mediación para todos los dispositivos. Dado que el FQDN del grupo es el mismo para todos los servidores del grupo de servidores, cada tronco debe apuntar a un FQDN o dirección IP del servidor de mediación en lugar del FQDN del grupo de servidores de mediación. Los troncos deben establecerse en la misma prioridad.
  
Si usa TLS entre los servidores de mediación y las puertas de enlace, deberá configurar las puertas de enlace y los servidores de mediación para admitir MTLS de la siguiente manera:
  
1. Exporte la CA raíz desde el equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de puerta de enlace RTC para importar la CA raíz.
    
3. Importe el certificado de ca raíz para el certificado emitido a la puerta de enlace en los servidores de mediación. Si necesita obtener un certificado SSL para la puerta de enlace, puede hacerlo con el servicio de entidad de certificación que se ejecuta en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
   - Modifique la plantilla de servidor web existente para permitir que los usuarios autenticados se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir que los usuarios autenticados se inscriban. Para obtener instrucciones detalladas, vea [Plantillas de certificado](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).
    
   - Solicitar un certificado mediante complemento Certificado seleccionando la plantilla de servidor web que ha habilitado. Asegúrese de agregar nombre común en Asunto y nombre DNS en Nombre alternativo con FQDN de la puerta de enlace y confirme en clave privada que Hacer exportable clave privada está seleccionada en opciones clave. 
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de puertas de enlace RTC para importar el certificado.
    
## <a name="update-the-domain-for-your-tenant"></a>Actualizar el dominio del inquilino

Asegúrese de que ha completado los pasos para actualizar el dominio en Microsoft 365 o Office 365 y tener la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar el dominio en Microsoft 365 o Office 365, vea [Agregar un](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)dominio a Microsoft 365 o Office 365 .
  
## <a name="add-dns-records-for-your-edge"></a>Agregar registros DNS para el servidor perimetral

Agregue los siguientes registros DNS a su Microsoft 365 o Office 365 organización. Para obtener información sobre cómo agregar registros DNS, vea Agregar o editar registros DNS personalizados en Microsoft 365 [o Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Agregar un registro DNS A para el servidor perimetral de acceso.
    
2. Los registros SRV se crearán automáticamente mediante Microsoft 365 o Office 365 y los scripts de implementación. Confirme que puede buscar los dos servicios SIP siguientes en edge: \_ sip y \_ sipfederationtls.
    
     ![Confirmación de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Configurar la conectividad híbrida entre Cloud Connector Edition y Microsoft 365 o Office 365

Para configurar la conectividad híbrida entre la Skype for Business Edición de conector de nube y la Microsoft 365 o Office 365, ejecute el siguiente cmdlet en una sesión remota de PowerShell. Para obtener información sobre cómo establecer una sesión remota de PowerShell, vea: [Configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
El cmdlet establece el FQDN externo perimetral de acceso. En el primero de los comandos, el debe ser el del rol perimetral de acceso \<External Access Edge FQDN\> SIP. De forma predeterminada, debe ser ap. \<Domain Name\> .
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> El FQDN perimetral de acceso externo usado para el destino del mismo nivel debe establecerse en un sitio RTC que solo se usará como reserva en caso de que un usuario no esté asignado a un sitio RTC. Para obtener más información, vea [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurar puertas de enlace RTC

Configure troncos en cada puerta de enlace RTC para que apunten a los servidores de mediación para todos los dispositivos. Cada tronco debe apuntar a un FQDN o dirección IP del servidor de mediación en lugar del FQDN del grupo de servidores de mediación porque el FQDN del grupo es el mismo para todos los servidores del grupo. Los troncos deben establecerse en la misma prioridad.
  
Si usa TLS entre los servidores de mediación y las puertas de enlace, deberá configurar las puertas de enlace y los servidores de mediación para admitir MTLS de la siguiente manera:
  
1. Exporte la CA raíz desde el equipo de Active Directory de Cloud Connector.
    
2. Siga las instrucciones del proveedor de puerta de enlace RTC para importar la CA raíz.
    
3. Importe el certificado de ca raíz para el certificado emitido a la puerta de enlace en los servidores de mediación. Si necesita obtener un certificado SSL para la puerta de enlace, puede hacerlo con el servicio de entidad de certificación que se ejecuta en el equipo de Active Directory de Cloud Connector de la siguiente manera:
    
   - Modifique la plantilla de servidor web existente para permitir que los usuarios autenticados se inscriban o cree una nueva plantilla de servidor web para configurar otras propiedades y permitir que los usuarios autenticados se inscriban. Para obtener instrucciones detalladas, vea [Plantillas de certificado](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).
    
   - Solicitar un certificado mediante complemento Certificado seleccionando la plantilla de servidor web que ha habilitado. Asegúrese de agregar nombre común en Asunto y nombre DNS en Nombre alternativo con FQDN de la puerta de enlace y confirme en clave privada que Hacer exportable clave privada está seleccionada en opciones clave. 
    
4. Exporte el certificado SSL con clave privada y siga las instrucciones del proveedor de puertas de enlace RTC para importar el certificado.
    
5. Las puertas de enlace RTC de un sitio RTC solo deben conectarse a los servidores de mediación del mismo sitio.
    
## <a name="set-up-your-users"></a>Configurar los usuarios

Inicie sesión en el Centro de administración de Microsoft 365, agregue los usuarios que se habilitarán para los servicios de voz en línea y asigne una licencia E5 o un complemento Sistema telefónico la licencia de E3 a estos usuarios. Para obtener información sobre cómo agregar usuarios, vea [Agregar usuarios a Microsoft 365 para empresas](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Habilitar usuarios para servicios Sistema telefónico voz y correo de voz
 
Después de agregar los usuarios a Microsoft 365 o Office 365, habilite sus cuentas para los Sistema telefónico de voz, incluido el correo de voz. Para habilitar estas funcionalidades, debe iniciar sesión en su organización Microsoft 365 o Office 365 con una cuenta que sea un rol de administrador global y poder ejecutar PowerShell remoto. Para obtener información sobre cómo establecer una sesión remota de PowerShell, vea: [Configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- Asigne la directiva al usuario y configure el número de teléfono de voz empresarial del usuario, que especifique con el valor del **parámetro Identity:**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Se puede especificar una identidad de usuario mediante la dirección SIP del usuario, el nombre principal de usuario (UPN) o el nombre para mostrar de Active Directory del usuario (por ejemplo, "Bob Kelly"). El carácter asterisco ( ) también se puede usar con el nombre para mostrar \* como identidad del usuario. Por ejemplo, identity " Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor \* de cadena "Smith".
  
A continuación, puede comprobar que los usuarios se agregaron y habilitaron mediante el siguiente script:
  
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

Deberá decidir si los usuarios deben poder realizar llamadas internacionales. De forma predeterminada, las llamadas internacionales están habilitadas. Puede deshabilitar o habilitar a los usuarios para la marcación internacional mediante el Centro de administración de Skype Empresarial línea.
  
Para deshabilitar las llamadas internacionales por usuario, ejecute el siguiente cmdlet en Skype Empresarial PowerShell en línea:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para volver a habilitar las llamadas internacionales por usuario después de deshabilitarla, ejecute el mismo cmdlet, pero cambie el valor **de PolicyName** a *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Asignar usuarios a sitios RTC

Use PowerShell remoto de inquilino para asignar un sitio a los usuarios incluso si solo implementó un solo sitio. Para obtener información sobre cómo establecer una sesión remota de PowerShell, vea: [Configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Si no se asigna ningún sitio RTC a un usuario, la conectividad híbrida entre la implementación de Skype for Business Edición de conector de nube y la organización de Microsoft 365 o Office 365 volverá a usar el nivel de inquilino predeterminado uno (destino del mismo nivel) para que se puedan completar las llamadas. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurar el servidor de mediación híbrido en línea Configuración
<a name="BKMK_ConfigureMediationServer"> </a>

Cuando una llamada P2P se escala a una conferencia RTC, el servidor de conferencias Skype Empresarial Online enviará una invitación al servidor de mediación de Cloud Connector. Para asegurarse de que Microsoft 365 o Office 365 puede enrutar esta invitación correctamente, debe configurar una configuración en el inquilino en línea para cada servidor de mediación de Cloud Connector de la siguiente manera: 
  
1. Cree un usuario en el Centro de administración de Microsoft 365. Use cualquier nombre de usuario que desee, como "MediationServer1".
    
    Use el dominio SIP predeterminado de Cloud Connector (el primer dominio SIP del archivo .ini) como dominio de usuario.
    
    Tenga en cuenta que la asignación de licencias solo es necesaria para la propagación del usuario en el Skype Empresarial en línea. Asigne una licencia de Microsoft 365 o Office 365 (como E5) a la cuenta que cree, permita hasta una hora para que los cambios se propaguen, compruebe que las cuentas de usuario se hayan aprovisionado correctamente en el directorio en línea de Skype Empresarial ejecutando el siguiente cmdlet y, a continuación, quite la licencia de esta cuenta.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Inicie una sesión remota de PowerShell de Azure AD de inquilino con sus credenciales de administrador global o de usuario y, a continuación, ejecute el siguiente cmdlet para establecer el departamento de la cuenta de usuario de Azure AD configurada en el paso 1 en "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Inicie un inquilino Skype Empresarial sesión remota de PowerShell con sus credenciales de administrador de inquilino de Skype Empresarial y, a continuación, ejecute el siguiente cmdlet para establecer el FQDN del servidor de mediación y del servidor perimetral en esa cuenta de usuario, reemplazando con el nombre para mostrar del usuario para la cuenta que creó en el paso \<DisplayName\> 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Para Identity, use el nombre para mostrar de la cuenta de usuario que creó para este servidor de mediación.
    
    Para  *MediationServerFQDN,*  use el FQDN interno definido para el servidor de mediación.
    
    Para  *EdgeServerExternalFQDN,*  use el FQDN externo definido para el proxy de acceso de servidor perimetral. Si hay varios sitios RTC de Cloud Connector, elija el FQDN del proxy de acceso de servidor perimetral asignado al sitio donde se encuentra el servidor de mediación.
    
4. Si hay varios servidores de mediación de Cloud Connector (varios sitios, HA), repita los pasos anteriores para cada uno de ellos.
