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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre enrutamiento directo, como la configuración, las decisiones básicas de implementación necesarias y las consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196494"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Dispositivo de rama intercambiable (SBA) para enrutamiento directo


En ocasiones, un sitio de cliente que usa enrutamiento directo para conectarse a Microsoft Phone System puede experimentar una interrupción de Internet.

Suponga que el sitio del cliente (denominado una rama) no puede conectarse temporalmente a la nube de Microsoft a través del enrutamiento directo. Sin embargo, la intranet dentro de la rama sigue siendo completamente funcional y los usuarios pueden conectarse al controlador de borde de sesión (SBC) que proporciona conectividad RTC.

En este artículo se describe cómo usar un dispositivo de sucursal fácilmente (SBA) para permitir que Microsoft Phone System siga haciendo y recibiendo llamadas de red telefónica conmutada (RTC) públicas en caso de interrupción.

## <a name="prerequisites"></a>Requisitos previos

Microsoft distribuye el código SBA a los proveedores de SBC que después insertan código en su firmware o lo distribuyen por separado para que SBA se ejecute en una máquina virtual o hardware independiente. 

Para obtener el firmware más reciente del controlador de borde de sesión con el dispositivo de rama intercambiable insertado, póngase en contacto con su proveedor de SBC. Además, es necesario lo siguiente:

- Es necesario configurar SBC para omitir medios para asegurarse de que el cliente de Microsoft Teams en el sitio de rama puede tener medios que fluyen directamente con la SBC. 

- TLS1.2 debe estar habilitado en el sistema operativo SBA VM.

## <a name="supported-teams-clients"></a>Clientes de Teams compatibles

La característica SBA es compatible con los siguientes clientes de Microsoft Teams: 

- Escritorio de Microsoft Teams para Windows 

- Escritorio de Microsoft Teams para macOS 

## <a name="how-it-works"></a>Cómo funciona

Durante una interrupción de Internet, el cliente de Teams debe cambiar al SBA automáticamente y las llamadas en curso deberían continuar sin interrupciones. El usuario no necesita realizar ninguna acción. Tan pronto como el cliente de Teams detecta que Internet está listo y las llamadas salientes han finalizado, el cliente volverá al modo de funcionamiento normal y se conectará a otros servicios de Teams. El SBA cargará los registros de datos de llamadas recopilados en la nube y el historial de llamadas se actualizará para que el administrador de inquilinos pueda revisar esta información. 

Cuando el cliente de Microsoft Teams está en modo sin conexión, está disponible la siguiente funcionalidad relacionada con las llamadas: 

- Realizar llamadas RTC a través de SBA/SBC local con medios que fluyen por la SBC.

- Recibir llamadas RTC a través de SBA/SBC local con medios que fluyen por la SBC. 

- Retenciones y reanudación de llamadas RTC.

## <a name="configuration"></a>Configuración

Para que la característica SBA funcione, el cliente de Teams necesita saber qué SBA están disponibles en cada sitio de rama y qué SBA se asignan a los usuarios en ese sitio. Los pasos de configuración son los siguientes:

1. Crear las OSN.
2. Cree la directiva de capacidad de ampliación de la rama de Teams.
3. Asigne la directiva a los usuarios.
4. Registrar una aplicación para el SBA con Azure Active Directory.

Toda la configuración se realiza con los cmdlets de PowerShell de Skype Empresarial Online. (El Centro de administración de Teams aún no admite la característica de enrutamiento directo SBA). 

(Para obtener información sobre cómo configurar el SBC, con vínculos a la documentación del proveedor de SBC, consulte la configuración del controlador de borde de sesión al final de este artículo).

### <a name="create-the-sbas"></a>Crear las OSN

Para crear los SBA, usará el cmdlet New-CsTeamsSurvivableBranchAppliance específico. Este cmdlet tiene los siguientes parámetros:

| Parámetro| Descripción |
| :------------|:-------|
| Identity  | La identidad del SBA  |
| Fqdn | El FQDN del SBA |
| Sitio | El sitio tenantNetworksite donde se encuentra el SBA |
| Descripción | Texto con formato gratuito |
|||

Por ejemplo:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Crear la directiva de idoneidad de la rama de Teams 

Para crear una directiva, use el cmdlet New-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Este cmdlet tiene los parámetros siguientes. Tenga en cuenta que la directiva puede contener uno o varios SBA.

| Parámetro| Descripción |
| :------------|:-------|
| Identity | La identidad de la directiva |
| BranchApplianceFqdns  | El FQDN de los SBA en el sitio |
||

Por ejemplo:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Puede agregar o quitar OSBA de una directiva mediante el Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Por ejemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Asignar una directiva a un usuario

Para asignar la directiva a usuarios individuales, usará el cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Este cmdlet tiene los parámetros siguientes:

| Parámetro| Descripción |
| :------------|:-------|
| Identity | La identidad del usuario |
| PolicyName | La identidad de la directiva |
||

Por ejemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Puede quitar una directiva a un usuario concediendo $Null directiva de directiva de usuario como se muestra en el siguiente ejemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrar una aplicación para el SBA con Azure Active Directory

Para permitir que diferentes SBA que se usan en su espacio empresarial puedan leer los datos necesarios de Microsoft 365, debe registrar una aplicación para el SBA en Azure Active Directory. 

Para obtener más información sobre el registro de aplicaciones, vea lo siguiente:

- [Desarrollo de aplicaciones de línea de negocio para Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registra una aplicación en la plataforma de identidad de Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)  

Solo necesita registrar una solicitud para que la usen todos los OBA de su inquilino. 

Para el registro SBA, necesita los siguientes valores creados por el registro: 

- Id. de aplicación (cliente) 
- Secreto de cliente 

Para la aplicación SBA, ten en cuenta lo siguiente: 

- El nombre puede ser el que decida.  
- Tipos de cuenta compatibles = Solo cuenta en este directorio de la organización. 
- El Uri de redirección web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Tokens de concesión implícita = tokens de acceso e identificador. 
- Permisos de API = Acceso para administradores de inquilinos de Skype > -> application_access_custom_sba_appliance.
- Secreto de cliente: puede usar cualquier descripción y expiración. 
- Recuerde copiar el secreto de cliente inmediatamente después de crearlo. 
- El Id. de la aplicación (cliente) se muestra en la pestaña Descripción general.

A continuación, siga estos pasos:

1. Registre la aplicación.
2. Establecer los tokens de concesión implícita.
3. Establezca los permisos de la API.
4. Cree el secreto de cliente.


## <a name="session-border-controller-configuration"></a>Configuración del controlador de borde de sesión 

Para obtener instrucciones paso a paso sobre cómo configurar el controlador de borde de sesión con el dispositivo de rama intercambiable insertado, consulte la documentación proporcionada por su proveedor de SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Cinta de opciones](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Informar de problemas

Informe de cualquier problema a la organización de soporte técnico de su proveedor de SBC. Al informar del problema, indica que tienes configurado un dispositivo de rama manejable.

## <a name="known-issues"></a>Problemas conocidos

- Al agregar nuevos dispositivos de rama intercambiables, es posible que deba tardar algún tiempo antes de poder usarlos en directivas de aplicaciones de sucursal fáciles de usar.

- Al asignar una directiva de aplicación de bifurcación intercambiable a un usuario, puede tardar algún tiempo antes de que se muestra el SBA en la salida de Get-CsOnlineUser. 

- No se realiza la búsqueda inversa de números en los contactos de Azure AD. 

- El SBA no admite la configuración de reenvío de llamadas. 

- No se admite realizar una llamada de emergencia a un número de emergencia configurado para llamadas de emergencia dinámicas (E911).

- El resultado del Get-CsOnlineUser muestra TeamsBranchSur inteligenciabilityPolicy.
