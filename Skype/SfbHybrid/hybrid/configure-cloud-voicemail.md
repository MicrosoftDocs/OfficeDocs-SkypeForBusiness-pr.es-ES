---
title: Configurar el servicio de correo de voz en la nube para los usuarios locales
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones para implementar el correo de voz basado en la nube para los usuarios alojados en Skype empresarial Server.
ms.openlocfilehash: 8fab0cf237137d87a8b7e49be65232dc0595de6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041249"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurar el servicio de correo de voz en la nube para los usuarios locales

## <a name="overview"></a>Información general 
En este artículo se describe cómo configurar el servicio de correo de voz de Microsoft Cloud para los usuarios locales de Skype empresarial.  

En este artículo se supone que ya ha implementado Skype empresarial Server en una topología compatible y que ha cumplido los requisitos previos para configurar la conectividad híbrida.

Para obtener más información sobre las ventajas, las consideraciones de planeación y los requisitos para implementar el correo de voz de nube, consulte [plan Cloud Cloud Service](plan-cloud-voicemail.md).




La configuración del correo de voz de nube implica las siguientes tareas:

1.  Asegúrese de que cumple con los requisitos previos como se describe en [plan Cloud Cloud Service](plan-cloud-voicemail.md).

2.  Asegúrese de que ha configurado la conectividad híbrida como se describe en [plan Hybrid Connectivity](plan-hybrid-connectivity.md) y [Configure Hybrid Connectivity](configure-hybrid-connectivity.md). 

3.  [Configure el correo de voz en la nube como proveedor de hospedaje en el servidor perimetral](#configure-cloud-voicemail-as-the-hosting-provider) como se describe en este artículo.

4.  [Configure una directiva de correo de voz hospedado](#configure-a-hosted-voicemail-policy) tal como se describe en este artículo.

5.  [Asigne una directiva de correo de voz hospedado](#assign-a-hosted-voicemail-policy) tal y como se describe en este artículo.

6.  [Habilite a un usuario para el correo de voz de la nube](#enable-a-user-for-cloud-voicemail) como se describe en este artículo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Configurar el correo de voz de nube como proveedor de hospedaje 

El correo de voz de nube se configura como el proveedor de hospedaje en un servidor front-end mediante el uso del cmdlet New-CsHostingProvider con los siguientes parámetros:

- **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando; por ejemplo, el correo de voz de la nube. 

- **Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Este parámetro debe establecerse en true.

- **EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido. Este parámetro debe establecerse en true.

- **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Skype empresarial Server. Este parámetro debe establecerse en false.

- **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje; por ejemplo, proxyserver.contoso.com. Póngase en contacto con el proveedor de hospedaje para obtener esta información. Este valor no puede modificarse. Si el proveedor de hospedaje cambia su servidor proxy, tendrá que eliminar y, a continuación, volver a crear la entrada para ese proveedor.

- **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido en su topología de Skype empresarial Server. Este parámetro debe establecerse en false.

Por ejemplo, en el shell de administración de Skype empresarial, el siguiente cmdlet configura el correo de voz de nube como proveedor de hospedaje:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurar una directiva de correo de voz hospedado

Para asegurarse de que el correo de voz de su organización se enruta al servicio de correo de voz en la nube, debe configurar una directiva de correo de voz hospedado para su organización. En muchos casos, solo se requiere una directiva de correo de voz hospedado y puede modificar la directiva global para satisfacer todas sus necesidades. Si su organización requiere varias directivas de correo de voz hospedado, puede Agregar directivas con el cmdlet New-cshostedvoicemailpolicy.

Para modificar la directiva global, ejecute el siguiente comando en el shell de administración de Skype empresarial Server después de actualizar la organización y el TenantID:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- **Destination** especifica el nombre de dominio completo (FQDN) del servicio de correo de voz de la nube hospedada. Este valor debe establecerse en **EXAP.um.Outlook.com**.

- **Organization** es el dominio predeterminado asignado a su inquilino. Puede recuperar esta información haciendo que el administrador del espacio empresarial inicie sesión en office.com, haga clic en la aplicación del centro de administración, desplácese hasta **configuración** en el lado izquierdo y haga clic en **dominios**. Por ejemplo: mytenant.onmicrosoft.com.

    El nombre de la organización también es el nombre de dominio predeterminado en Office 365.

- El **inquilino** se usa para identificar a su inquilino en Office 365. Para obtener más información, vea [Buscar el identificador de inquilino de Office 365](https://support.office.com/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Para asegurarse de que una directiva de correo de voz hospedado se haya creado correctamente, ejecute el siguiente comando:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Asignar una directiva de correo de voz hospedado

De forma predeterminada, la Directiva de correo de voz hospedado global se asigna a todos los usuarios. Si usa una directiva diferente, antes de habilitar a los usuarios para el correo de voz hospedado, primero debe conceder a los usuarios la Directiva de correo de voz hospedado que desee mediante el cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Por ejemplo, el siguiente comando asigna una directiva de correo de voz hospedado no global a un usuario:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Habilitar a un usuario para el correo de voz de la nube

Para permitir que las llamadas de correo de voz de un usuario se enruten al correo de voz de la nube, use el cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con el parámetro HostedVoiceMail. 

Por ejemplo, el siguiente comando habilita una cuenta de usuario para el correo de voz de la nube: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

El cmdlet comprueba que una directiva de correo de voz de nube, en el nivel global, de sitio o de usuario, se aplica a este usuario. Si no se aplica ninguna directiva, el cmdlet no se completará correctamente.  

El siguiente ejemplo deshabilita una cuenta de usuario para el correo de voz de la nube:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

El cmdlet comprueba que ninguna directiva de correo de voz hospedada, en el nivel global, de sitio o de usuario, se aplica a este usuario. Si se aplica alguna directiva, el cmdlet no se completará correctamente.

> [!NOTE]
>  Los usuarios deben tener habilitada la telefonía IP empresarial para usar el servicio de correo de voz de la nube de Microsoft.
