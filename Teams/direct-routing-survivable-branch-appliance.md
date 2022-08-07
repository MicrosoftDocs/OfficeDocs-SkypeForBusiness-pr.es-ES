---
title: Enrutamiento directo SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre el enrutamiento directo, como la configuración, las decisiones de implementación principales necesarias y las consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc250b0506614ef658ade9a491c5561a65b98800
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269675"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Dispositivo de rama con funciones de supervivencia (SBA) para enrutamiento directo


En ocasiones, un sitio de cliente que use enrutamiento directo para conectarse a Microsoft Phone System puede experimentar una interrupción de Internet.

Suponga que el sitio del cliente (denominado rama) no puede conectarse temporalmente a la nube de Microsoft a través del enrutamiento directo. Sin embargo, la intranet dentro de la rama sigue siendo totalmente funcional y los usuarios pueden conectarse al controlador de borde de sesión (SBC) que proporciona conectividad CON RTC.

En este artículo se describe cómo usar un dispositivo de rama con funciones de supervivencia (SBA) para habilitar Microsoft Phone System para seguir realizando y recibiendo llamadas de red telefónica conmutada (RTC) en caso de interrupción.

## <a name="prerequisites"></a>Requisitos previos

El SBA es código distribuible proporcionado por Microsoft a proveedores de SBC que después incrustan código en su firmware o lo distribuyen por separado para que el SBA se ejecute en una máquina virtual o hardware independiente. 

Para obtener el firmware de controlador de borde de sesión más reciente con el dispositivo de sucursal con funciones de supervivencia incorporado, póngase en contacto con su proveedor de SBC. Además, es necesario lo siguiente:

- El SBC debe configurarse para omisión de medios para asegurarse de que el cliente de Microsoft Teams en el sitio de la rama puede tener medios que fluyen directamente con el SBC. 

- TLS1.2 debe estar habilitado en el SO de SBA VM.
- Microsoft SBA Server usa los puertos 3443, 4444 y 8443 para comunicarse con el cliente de Teams y deben estar permitidos en el firewall. 
- Microsoft SBA Server usa el puerto 5061 (o el configurado en el SBC) para comunicarse con el SBC y debe estar permitido en el firewall. 
- El puerto UDP 123 es utilizado por el servidor SBA de Microsoft para comunicarse con el servidor NTP y se debe permitir en el firewall.
- Microsoft SBA Server usa el puerto 443 para comunicarse con Microsoft 365 y debe estar permitido en el firewall.
- Los intervalos IP de Azure y las etiquetas de servicio para la nube pública deben definirse de acuerdo con las directrices descritas en: https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>Clientes de Teams admitidos

La característica SBA es compatible con los siguientes clientes de Microsoft Teams: 

- Escritorio de Windows de Microsoft Teams 

- Escritorio de Microsoft Teams para macOS
- Teams para móviles 
- Teléfonos de Teams

## <a name="how-it-works"></a>Cómo funciona

Durante una interrupción de Internet, el cliente de Teams debe cambiar a la SBA automáticamente y las llamadas en curso deben continuar sin interrupciones. El usuario no necesita realizar ninguna acción. Tan pronto como el cliente de Teams detecta que Internet está listo y las llamadas salientes han finalizado, el cliente volverá al modo de funcionamiento normal y se conectará a otros servicios de Teams. El SBA cargará los registros de datos de llamadas recopilados en la nube y el historial de llamadas se actualizará para que el administrador de inquilinos pueda revisar esta información. 

Cuando el cliente de Microsoft Teams está en modo sin conexión, está disponible la siguiente funcionalidad relacionada con las llamadas: 

- Realizar llamadas RTC a través de SBA/SBC local con medios que fluyen a través del SBC.

- Recibir llamadas RTC a través de SBA/SBC local con medios que fluyen a través del SBC. 

- Espera y reanudación de llamadas RTC.

## <a name="configuration"></a>Configuración

Para que la característica de SBA funcione, el cliente de Teams necesita saber qué SBA están disponibles en cada sitio de la rama y qué SBA se asignan a los usuarios de ese sitio. Los pasos de configuración son los siguientes:

1. Cree los SBA.
2. Cree la directiva de supervivencia de la rama de Teams.
3. Asigne la directiva a los usuarios.
4. Registre una aplicación para el SBA con Azure Active Directory.

Toda la configuración se realiza mediante Skype for Business cmdlets de PowerShell en línea. (El Centro de administración de Teams aún no admite la característica de SBA de enrutamiento directo). 

(Para obtener información sobre cómo configurar el SBC, con vínculos a la documentación del proveedor de SBC, consulte Configuración del controlador de borde de sesión al final de este artículo).

### <a name="create-the-sbas"></a>Crear los O SBA

Para crear los SBAs, usará el cmdlet de New-CsTeamsSurvivableBranchAppliance. Este cmdlet tiene los siguientes parámetros:

| Parámetro| Descripción |
| :------------|:-------|
| Identity  | La identidad de la SBA  |
| Fqdn | El FQDN del SBA |
| Sitio | El TenantNetworkSite donde se encuentra el SBA |
| Descripción | Texto en formato gratuito |
|||

Por ejemplo:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Crear la directiva de supervivencia de la rama de Teams 

Para crear una directiva, use el cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Este cmdlet tiene los siguientes parámetros. Tenga en cuenta que la política puede contener uno o más SBA.

| Parámetro| Descripción |
| :------------|:-------|
| Identity | La identidad de la directiva |
| BranchApplianceFqdns  | El FQDN de los SBA del sitio |
||

Por ejemplo:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Puede agregar o quitar SBAs de una directiva mediante el cmdlet de Set-CsTeamsSurvivableBranchAppliancePolicy. Por ejemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Asignar una directiva a un usuario

Para asignar la directiva a usuarios individuales, usará el cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Este cmdlet tiene los siguientes parámetros:

| Parámetro| Descripción |
| :------------|:-------|
| Identity | La identidad del usuario |
| PolicyName | La identidad de la directiva |
||

Por ejemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Puede quitar una directiva a un usuario al conceder la directiva de $Null como se muestra en el ejemplo siguiente:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrar una aplicación para el SBA con Azure Active Directory

Para permitir que distintos SBA usados en su inquilino puedan leer los datos necesarios de Microsoft 365, debe registrar una aplicación para el SBA con Azure Active Directory. 

Para obtener más información sobre el registro de aplicaciones, consulte lo siguiente:

- [Desarrollar aplicaciones de línea de negocio para Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrar una aplicación con el Plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).  

Sólo necesita registrar una aplicación para su uso por todos los SBAs en su inquilino. 

Para el registro SBA, necesita los siguientes valores creados por el registro: 

- Id. de aplicación (cliente) 
- Secreto de cliente 

Para la aplicación de SBA, tenga en cuenta lo siguiente: 

- El nombre puede ser lo que decidas.  
- Tipos de cuenta admitidos = Solo en este directorio organizativo. 
- El uri de redirección web = https://login.microsoftonline.com/common/oauth2/nativeclient.
- Tokens de concesión implícitos = tokens de acceso e id. 
- Permisos de API = Acceso de inquilinos de Skype y Teams Administración -> permisos de aplicación -> application_access_custom_sba_appliance.
- Secreto de cliente: puede usar cualquier descripción y expiración. 
- Recuerde copiar el secreto del cliente inmediatamente después de crearlo. 
- El Id. de aplicación (cliente) se muestra en la pestaña Información general.

A continuación, sigue estos pasos:

1. Registre la aplicación.
2. Establezca los tokens de concesión implícitos.
3. Establecer los permisos de la API.
4. Cree el secreto de cliente.


## <a name="session-border-controller-configuration"></a>Configuración del controlador de borde de sesión 

Para obtener instrucciones paso a paso sobre cómo configurar el controlador de borde de sesión con el dispositivo de sucursal con funciones de supervivencia incrustadas, consulte la documentación proporcionada por su proveedor de SBC: 

- [AudioCodes](https://www.audiocodes.com/library/technical-documents?query=sba)

- [Cinta de opciones](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Informar de problemas

Informe de cualquier problema a la organización de soporte técnico de su proveedor de SBC. Al informar del problema, indique que tiene configurado un dispositivo de sucursal con funciones de supervivencia.

## <a name="known-issues"></a>Problemas conocidos

- Al agregar nuevos dispositivos de rama con funciones de supervivencia, es posible que tarde un poco en poder usarlos en las directivas de Dispositivo de rama con funciones de supervivencia.

- Al asignar una directiva de dispositivo de rama con funciones de supervivencia a un usuario, es posible que el SBA tarde algún tiempo en mostrarse en el resultado de Get-CsOnlineUser. 

- No se realiza la búsqueda inversa de números con los contactos de Azure AD. 

- El SBA no admite la configuración del desvío de llamadas. 

- No se admite realizar una llamada de emergencia a un número de emergencia configurado para llamadas de emergencia dinámicas (E911).
