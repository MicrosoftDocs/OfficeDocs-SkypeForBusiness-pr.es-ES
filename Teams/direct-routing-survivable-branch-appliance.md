---
title: Enrutamiento directo SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: Obtenga más información sobre el enrutamiento directo, como la configuración, las decisiones básicas de implementación necesarias y las consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611794"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Dispositivo de rama superviviente (SBA) para enrutamiento directo: vista previa pública


> [!NOTE]
> Esta es una versión preliminar pública.

Ocasionalmente, un sitio del cliente que usa enrutamiento directo para conectarse a Microsoft Phone System puede experimentar una interrupción de Internet.

Supongamos que el sitio del cliente, denominado una rama, no puede conectarse temporalmente a la nube de Microsoft a través del enrutamiento directo. Sin embargo, la intranet dentro de la rama sigue siendo plenamente funcional y los usuarios pueden conectarse al controlador de borde (SBC) de sesión que proporciona conectividad RTC.

En este artículo se describe cómo usar un dispositivo de rama con la supervivencia (SBA) para habilitar el sistema de teléfono de Microsoft para seguir realizando y recibiendo llamadas de red telefónica conmutada (RTC) en caso de interrupción.

## <a name="prerequisites"></a>Requisitos previos

SBA es un código distribuible proporcionado por Microsoft a los proveedores de SBC que, a continuación, Incruste el código en el firmware de su SBCs. 

Para obtener el firmware más reciente del controlador de borde de la sesión con el dispositivo de sucursal insertado, póngase en contacto con el proveedor de SBC. Además, se requiere lo siguiente:

- Es necesario configurar la SBC para la omisión de medios para asegurarse de que el cliente de Microsoft Teams del sitio de la sucursal pueda hacer que el contenido multimedia fluya directamente con el SBC. 

- TLS 1.2 debe estar habilitado en el sistema operativo VM de SBA.

## <a name="supported-teams-clients"></a>Clientes de equipos compatibles

La característica SBA se admite en los siguientes clientes de Microsoft Teams: 

- Microsoft Teams escritorio de Windows 

- Escritorio de Microsoft Teams macOS 

## <a name="how-it-works"></a>Cómo funciona

Durante una interrupción de Internet, el cliente de Teams debe cambiar a SBA automáticamente y las llamadas en curso deben continuar sin interrupciones. El usuario no necesita realizar ninguna acción. En cuanto el cliente del equipo detecte que Internet está en marcha y que se han finalizado las llamadas salientes, el cliente revertirá al modo de funcionamiento normal y se conectará a otros servicios de Teams. SBA cargará los registros de datos de llamadas recopilados en la nube y el historial de llamadas se actualizará para que esta información esté disponible para su revisión por el administrador de inquilinos. 

Cuando el cliente de Microsoft Teams está en modo sin conexión, están disponibles las siguientes funciones relacionadas con la llamada: 

- Hacer llamadas RTC a través de SBA/SBC local con el flujo de medios a través de SBC.

- Recepción de llamadas RTC a través de SBA/SBC local con contenido multimedia que fluye por el SBC. 

- Suspensión y reanudación de llamadas RTC.

## <a name="configuration"></a>Configuración

Para que la característica SBA funcione, el cliente de Teams debe saber qué SBAs están disponibles en cada sitio de la sucursal y qué SBAs están asignados a los usuarios de ese sitio. Los pasos de configuración son los siguientes:

1. Cree el SBAs.
2. Crear la política de superviviente de las sucursales de Teams.
3. Asignar la Directiva a los usuarios.
4. Registre una aplicación para SBA con Azure Active Directory.

Toda la configuración se realiza con los cmdlets de PowerShell de Skype empresarial online. (El centro de administración de equipos aún no admite la característica de enrutamiento directo de SBA). 

Para obtener información sobre la configuración de SBC, con vínculos a la documentación de proveedores de SBC, consulte Configuración del controlador de borde de sesión al final de este artículo.

### <a name="create-the-sbas"></a>Crear la SBAs

Para crear la SBAs, usará el cmdlet New-CsTeamsSurvivableBranchAppliance. Este cmdlet tiene los siguientes parámetros:

| Parámetro| Descripción |
| :------------|:-------|
| Identity  | La identidad de SBA  |
| Fqdn | FQDN de la SBA |
| Sitio | El TenantNetworkSite donde se encuentra la SBA |
| Descripción | Formato de texto libre |
|||

Por ejemplo:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Crear la política de la supervivencia de las sucursales de Teams 

Para crear una directiva, use el cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Este cmdlet tiene los siguientes parámetros. Tenga en cuenta que la Directiva puede contener uno o varios SBAs.

| Parámetro| Descripción |
| :------------|:-------|
| Identity | La identidad de la Directiva |
| BranchApplianceFqdns  | El FQDN de la SBA (s) del sitio |
||

Por ejemplo:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Puede Agregar o quitar SBAs de una Directiva mediante el cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy. Por ejemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Asignar una directiva a un usuario

Para asignar la Directiva a usuarios individuales, usará el cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Este cmdlet tiene los siguientes parámetros:

| Parámetro| Descripción |
| :------------|:-------|
| Identity | La identidad del usuario |
| PolicyName | La identidad de la Directiva |
||

Por ejemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Para quitar una directiva de un usuario, puede conceder la $Null Directiva tal como se muestra en el siguiente ejemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrar una aplicación para SBA con Azure Active Directory

Para permitir que diferentes SBAs usen en su espacio empresarial para leer los datos necesarios de Microsoft 365, debe registrar una aplicación para SBA con Azure Active Directory. 

Para obtener más información sobre el registro de aplicaciones, vea lo siguiente:

- [Desarrollar aplicaciones de línea de negocio para Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrar una aplicación con la plataforma de identidades de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).  

Solo necesita registrar una aplicación para que la usen todos los SBAs de su inquilino. 

Para el registro de SBA, necesita los siguientes valores creados por el registro: 

- IDENTIFICADOR de la aplicación (cliente) 
- Secreto de cliente 

Para la aplicación SBA, tenga en cuenta lo siguiente: 

- El nombre puede ser el que usted decida.  
- Tipos de cuenta admitidos = cuenta solo en este directorio de organización. 
- El URI de redireccionamiento web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Tokens de concesión implícita = tokens de acceso y tokens de identificador. 
- Permisos de API = permisos de administrador de inquilinos de Skype y Teams-> de permisos de aplicaciones-> application_access_custom_sba_appliance.
- Secreto de cliente: puede usar la descripción y la expiración. 
- Recuerde copiar el secreto de cliente inmediatamente después de crearlo. 
- El identificador de la aplicación (cliente) se muestra en la ficha Descripción general.

A continuación, siga estos pasos:

1. Registrar la aplicación.
2. Establezca los tokens de concesión implícitos.
3. Establezca los permisos de la API.
4. Crear el secreto de cliente.


## <a name="session-border-controller-configuration"></a>Configuración del controlador de borde de sesión 

Para obtener instrucciones paso a paso sobre cómo configurar el controlador de borde de sesión con el dispositivo de sucursal incrustado, consulte la documentación proporcionada por el proveedor de SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Lazo](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-sistemas](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Problemas de informes

Informe de cualquier problema a la organización de soporte técnico de su proveedor de SBC. Cuando informe sobre el problema, indique que tiene un equipo de sucursales configurado.

## <a name="known-issues"></a>Problemas conocidos

- Cuando se agregan nuevos equipos de sucursales que se pueden llevar a cabo, es posible que tarden unos minutos en usarlos en directivas de los equipos supervivientes.

- Cuando se asigna a un usuario una directiva de equipo de sucursal con la supervivencia, es posible que tarde un tiempo en mostrarse en el resultado de Get-CsOnlineUser. 

- No se realiza la búsqueda de números invertidas con los contactos de Azure AD. 

- SBA no admite la configuración del desvío de llamadas. 

- No es posible realizar una llamada de emergencia a un número de emergencia configurado para llamadas de emergencia dinámicas (E911).

- El resultado de Get-CsOnlineUser muestra TeamsBranchSurvivabilityPolicy.
