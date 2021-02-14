---
title: Configurar el servicio de correo de voz en la nube para usuarios locales
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
description: Instrucciones para implementar el correo de voz basado en la nube para los usuarios que están en Skype Empresarial Server.
ms.openlocfilehash: 29faba6bf092647f0c55899f013c6b4bf146304f
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552586"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurar el servicio de correo de voz en la nube para usuarios locales

## <a name="overview"></a>Información general 
En este artículo se describe cómo configurar el servicio de correo de voz en la nube de Microsoft para los usuarios locales de Skype Empresarial.  

En este artículo se presupone que Skype Empresarial Server ya está implementado en una topología compatible y que ha cumplido los requisitos previos para configurar la conectividad híbrida.

Para obtener más información sobre las ventajas, consideraciones de planeación y requisitos para implementar el correo de voz en la nube, consulte [Plan Cloud Voicemail service](plan-cloud-voicemail.md).




La configuración del correo de voz en la nube implica las siguientes tareas:

1.  Asegúrese de que ha cumplido los requisitos previos tal como se describe en [Plan Cloud Voicemail service](plan-cloud-voicemail.md).

2.  Asegúrese de que ha configurado la conectividad híbrida como se describe en [Planear la conectividad híbrida](plan-hybrid-connectivity.md) y Configurar la conectividad [híbrida.](configure-hybrid-connectivity.md) 

3.  [Configure el correo de voz en la nube como proveedor de hospedaje en el servidor front-end,](#configure-cloud-voicemail-as-the-hosting-provider) tal como se describe en este artículo.

4.  [Configure una directiva de correo de voz hospedado](#configure-a-hosted-voicemail-policy) como se describe en este artículo.

5.  [Asigne una directiva de correo de voz hospedado](#assign-a-hosted-voicemail-policy) como se describe en este artículo.

6.  [Habilite a un usuario para correo de voz en la nube,](#enable-a-user-for-cloud-voicemail) tal como se describe en este artículo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Configurar el correo de voz en la nube como proveedor de hospedaje 

El correo de voz en la nube se configura como proveedor de hospedaje en un servidor front-end mediante el cmdlet New-CsHostingProvider con los siguientes parámetros:

- **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando; por ejemplo, Correo de voz en la nube. 

- **Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Este parámetro debe establecerse en True.

- **EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido. Este parámetro debe establecerse en True.

- **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Skype Empresarial Server. Este parámetro debe establecerse en False.

- **ProxyFQDN especifica** el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje; por ejemplo, proxyserver.contoso.com. Póngase en contacto con el proveedor de hospedaje para obtener esta información. Este valor no puede modificarse. Si el proveedor de hospedaje cambia su servidor proxy, tendrá que eliminar y, a continuación, volver a crear la entrada para ese proveedor.

- **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Skype Empresarial Server. Este parámetro debe establecerse en False.

Por ejemplo, en el Shell de administración de Skype Empresarial, el siguiente cmdlet configura el correo de voz en la nube como proveedor de hospedaje:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurar una directiva de correo de voz hospedado

Para asegurarse de que el correo de voz de su organización se enruta al servicio de correo de voz en la nube, debe configurar una directiva de correo de voz hospedado para su organización. En muchos casos, solo se necesita una directiva de correo de voz hospedado y puede modificar la directiva global para satisfacer todas sus necesidades. Si su organización requiere varias directivas de correo de voz hospedado, puede agregar directivas con el cmdlet new-cshostedvoicemailpolicy.

Para modificar la directiva global, ejecute el siguiente comando en el Shell de administración de Skype Empresarial Server después de actualizar la organización y tenantID:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **El** destino especifica el nombre de dominio completo (FQDN) del servicio de correo de voz en la nube hospedado. Este valor debe establecerse en **exap.um.outlook.com**.

- **La** organización es el dominio predeterminado asignado a su espacio empresarial. Puede recuperar esta información haciendo que el administrador del espacio empresarial inicie sesión en office.com, haga clic en la aplicación Centro de administración, vaya a **Configuración** a la izquierda y haga clic en **Dominios.** Por ejemplo: mytenant.onmicrosoft.com.

    El nombre de la organización también es el nombre de dominio predeterminado en Microsoft 365 u Office 365.

Para asegurarse de que una directiva de correo de voz hospedado se creó correctamente, ejecute el siguiente comando:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Asignar una directiva de correo de voz hospedado

De forma predeterminada, la directiva global de correo de voz hospedado se asigna a todos los usuarios. Si usa una directiva diferente, antes de habilitar a los usuarios para el correo de voz hospedado, primero debe conceder a los usuarios la directiva de correo de voz hospedada deseada mediante el cmdlet [Grant-CSHostedVoicemailPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)

Por ejemplo, el siguiente comando asigna una directiva de correo de voz hospedado no global a un usuario:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Habilitar un usuario para correo de voz en la nube

Para permitir que las llamadas de correo de voz de un usuario se enrutan al correo de voz en la nube, use el cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con el parámetro HostedVoiceMail. 

Por ejemplo, el siguiente comando habilita una cuenta de usuario para correo de voz en la nube: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

El cmdlet comprueba que una directiva de correo de voz en la nube (a nivel global, de sitio o de usuario) se aplica a este usuario. Si no se aplica ninguna directiva, el cmdlet no se completará correctamente.  

En el siguiente ejemplo se deshabilita una cuenta de usuario para correo de voz en la nube:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

El cmdlet comprueba que ninguna directiva de correo de voz hospedado (a nivel global, de sitio o de usuario) se aplique a este usuario. Si se aplica alguna directiva, el cmdlet no se completará correctamente.

> [!NOTE]
>  Los usuarios deben tener la voz empresarial habilitada para usar el servicio de correo de voz en la nube de Microsoft.
