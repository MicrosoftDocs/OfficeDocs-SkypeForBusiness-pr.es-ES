---
title: Direct Routing SBA
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
description: Obtenga más información sobre enrutamiento directo, como configuración, decisiones básicas de implementación necesarias y consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589244"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Dispositivo de sucursal con funciones de supervivencia (SBA) para enrutamiento directo


En ocasiones, un sitio de cliente que usa Enrutamiento directo para conectarse a Teléfono Microsoft sistema puede experimentar una interrupción de Internet.

Suponga que el sitio del cliente (denominado rama) no puede conectarse temporalmente a la nube de Microsoft a través del enrutamiento directo. Sin embargo, la intranet dentro de la rama sigue siendo totalmente funcional y los usuarios pueden conectarse al controlador de borde de sesión (SBC) que proporciona conectividad RTC.

En este artículo se describe cómo usar un dispositivo de sucursal con funciones de supervivencia (SBA) para permitir que Teléfono Microsoft System siga haciendo y recibiendo llamadas de red telefónica conmutada (RTC) en caso de interrupción.

## <a name="prerequisites"></a>Requisitos previos

El SBA es un código distribuible proporcionado por Microsoft a los proveedores de SBC que, a continuación, insertan código en su firmware o lo distribuyen por separado para que SBA se ejecute en una máquina virtual o hardware independiente. 

Para obtener el firmware más reciente del controlador de borde de sesión con el dispositivo de sucursal con supervivencia incrustado, póngase en contacto con su proveedor de SBC. Además, se requiere lo siguiente:

- El SBC debe configurarse para la omisión de medios para asegurarse de que el cliente Microsoft Teams en el sitio de sucursal puede tener los medios fluyendo directamente con el SBC. 

- TLS1.2 debe estar habilitado en el sistema operativo de máquina virtual de SBA.

## <a name="supported-teams-clients"></a>Clientes Teams compatibles

La característica SBA es compatible con los siguientes Microsoft Teams cliente: 

- Microsoft Teams Windows escritorio 

- Microsoft Teams escritorio de macOS 

## <a name="how-it-works"></a>Cómo funciona

Durante una interrupción de Internet, el Teams debe cambiar al SBA automáticamente y las llamadas en curso deben continuar sin interrupciones. No se requiere ninguna acción del usuario. Tan pronto como el cliente Teams detecta que Internet está listo y las llamadas salientes han finalizado, el cliente volverá al modo de funcionamiento normal y se conectará a otros Teams servicios. El SBA cargará los registros de datos de llamadas recopilados en la nube y el historial de llamadas se actualizará para que esta información esté disponible para su revisión por el administrador de inquilinos. 

Cuando el Microsoft Teams está en modo sin conexión, está disponible la siguiente funcionalidad relacionada con las llamadas: 

- Realizar llamadas RTC a través de SBA/SBC local con los medios que fluyen por el SBC.

- Recibir llamadas RTC a través de SBA/SBC local con los medios que fluyen por el SBC. 

- Retener y reanudar llamadas RTC.

## <a name="configuration"></a>Configuración

Para que la característica SBA funcione, el cliente de Teams debe saber qué SBA están disponibles en cada sitio de sucursal y qué SBA están asignados a los usuarios de ese sitio. Los pasos de configuración son los siguientes:

1. Cree los SBA.
2. Cree la directiva Teams de supervivencia de la rama.
3. Asigne la directiva a los usuarios.
4. Registre una aplicación para el SBA con Azure Active Directory.

Toda la configuración se realiza Skype Empresarial cmdlets de PowerShell en línea. (El Teams de administración de enrutamiento directo aún no es compatible con la característica SBA de enrutamiento directo). 

(Para obtener información sobre cómo configurar el SBC, con vínculos a la documentación del proveedor de SBC, vea Configuración del controlador de borde de sesión al final de este artículo).

### <a name="create-the-sbas"></a>Crear los SBA

Para crear los SBA, usará el cmdlet New-CsTeamsSurvivableBranchAppliance. Este cmdlet tiene los siguientes parámetros:

| Parámetro| Descripción |
| :------------|:-------|
| Identity  | La identidad del SBA  |
| Fqdn | El FQDN del SBA |
| Sitio | El TenantNetworkSite donde se encuentra el SBA |
| Descripción | Texto con formato libre |
|||

Por ejemplo:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Crear la directiva de Teams de supervivencia de la rama 

Para crear una directiva, use el cmdlet New-CsTeamsSurvivableBranchAppliancePolicy datos. Este cmdlet tiene los siguientes parámetros. Tenga en cuenta que la directiva puede contener uno o varios SBA.

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

Puede agregar o quitar SBA de una directiva mediante el cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy directiva. Por ejemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Asignar una directiva a un usuario

Para asignar la directiva a usuarios individuales, usará el cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy usuario. Este cmdlet tiene los siguientes parámetros:

| Parámetro| Descripción |
| :------------|:-------|
| Identity | La identidad del usuario |
| PolicyName | La identidad de la directiva |
||

Por ejemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Puede quitar una directiva de un usuario concediendo la $Null directiva como se muestra en el siguiente ejemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrar una aplicación para el SBA con Azure Active Directory

Para permitir que los distintos SBA usados dentro del espacio empresarial puedan leer los datos necesarios de Microsoft 365, debe registrar una aplicación para el SBA con Azure Active Directory. 

Para obtener más información sobre el registro de aplicaciones, vea lo siguiente:

- [Desarrollar aplicaciones de línea de negocio para Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registre una aplicación con la Plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).  

Solo necesita registrar una aplicación para que la usen todos los SBA en el espacio empresarial. 

Para el registro de SBA, necesita los siguientes valores creados por el registro: 

- Id. de aplicación (cliente) 
- Secreto del cliente 

Para la aplicación SBA, tenga en cuenta lo siguiente: 

- El nombre puede ser lo que decida.  
- Tipos de cuenta admitidos = Solo cuenta en este directorio de la organización. 
- Uri de redirección web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Tokens de concesión implícitos = tokens de Access y tokens de id. 
- Permisos de api = Skype y Teams de acceso de administrador de inquilinos -> de aplicación de inquilinos -> application_access_custom_sba_appliance.
- Secreto del cliente: puede usar cualquier descripción y expiración. 
- Recuerde copiar el secreto del cliente inmediatamente después de crearlo. 
- El id. de aplicación (cliente) se muestra en la pestaña Información general.

A continuación, siga estos pasos:

1. Registre la aplicación.
2. Establezca los tokens de concesión implícitos.
3. Establezca los permisos de la API.
4. Cree el secreto del cliente.


## <a name="session-border-controller-configuration"></a>Configuración del controlador de borde de sesión 

Para obtener instrucciones paso a paso sobre cómo configurar el controlador de borde de sesión con el dispositivo de sucursal con supervivencia incrustado, consulte la documentación proporcionada por el proveedor de SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Cinta de opciones](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Problemas de informes

Informe de cualquier problema a la organización de soporte técnico de su proveedor de SBC. Al informar del problema, indique que tiene un dispositivo de sucursal con funciones de supervivencia configurado.

## <a name="known-issues"></a>Problemas conocidos

- Al agregar nuevos dispositivos de sucursales con funciones de supervivencia, puede tardar algún tiempo antes de poder usarlos en directivas de aplicación de sucursal con funciones de supervivencia.

- Al asignar una directiva de aplicación de sucursal con funciones de supervivencia a un usuario, puede que el SBA se muestra en el resultado de Get-CsOnlineUser. 

- No se realiza la búsqueda inversa de números en contactos de Azure AD. 

- El SBA no admite la configuración de reenvío de llamadas. 

- No se admite realizar una llamada de emergencia a un número de emergencia configurado para llamadas de emergencia dinámicas (E911).
